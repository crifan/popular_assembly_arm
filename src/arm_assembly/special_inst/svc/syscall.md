# syscall

* syscall
  * 硬件中
    * perform a syscall
      * 指令=opcode
        * x86的`INT`（=interrupt）
          * INT 0x80
        * x86-64：`syscall`
        * ARM
          * 新：`SVC`=`SuperVisor Call`
            * 旧：`SWI`=`SoftWare Interrupt`
  * 软件中
    * `syscall`=`system call`=`系统调用`=`软中断`=`软件中断`
      * 具体实现方式
        * C函数：`syscall()`
          * 举例
            * openResult = syscall(SYS_stat64, filePathStr, &stat_info);
          * 说明
            * C函数syscall()，是底层的汇编级别svc 0x80的封装
        * inline汇编：`svc xxx`
          * 举例：
            * `svc #0x80`
      * 内部逻辑
        * CPU跳转到特定的代码段（section），即 中断处理函数（interrupt handler）继续在 内核上下文（context of the kernel）中运行
          * -》使得：
            * 用户空间（userspace）可以以受控的方式触发特权代码的执行，而不能随意执行特权代码
        * 在计算机中，尤其是 IBM 大型机中，主管调用 (SVC) 指令是指令处理器将计算机的控制权传递给操作系统的主管程序的处理器指令
        * 多数 SVC 是来自应用程序或操作系统的其他部分对特定操作系统服务的请求
  * 其他详解
    * 越狱 hook 反越狱 相关
      * 背景知识
        * 上层（C语言等）调用fopen函数 fopen(xxx)，底层最终都是转换为 SVC 0x80 去实现对应的调用的
      * 反hook
        * 所以要防止自己的上层函数调用被hook
        * 可以直接用底层的syscall
        * 尤其是asm内联汇编代码实现svc 0x80的调用（传入对应的操作码，即syscall的number参数）
      * 但是直接调用svc的syscall有缺点
        * 维护起来很麻烦
          * 自己写syscall的函数调用，要自己注意参数和格式
          * 如果有新的架构升级后
            * 代码也要更新
          * 且本身syscall的接口，可能会升级和变化
            * 代码也要及时更新和支持
        * 后续的返回值等流程中，也存在被hook的风险
          * 虽然用户难以绕过hook你的svc 0x80的调用
          * 但是调用后的返回值，也存在被hook的风险
            * 比如
              * patch修改代码，绕过检查
                * 注：但是此处需要修改原先app的代码，或者（用Friada等工具去）运行时去检测，才能实现
                  * 不符合我此处的：
                    * 希望一次性写好代码，绕开svc 0x80的调用
              * 直接修改内核kernel
                * 注：此处iOS的kernel，很难轻易被修改
                  * 此路也很难行得通
    * ARM的svc 0x80的汇编代码
      * ARM的SVC指令
        * =`Supervisor Call instruction`
          * `SVC`=`SuperVisor Call`
            * 旧称：`SWI` = `SoftWare Interrupt`
          * 详见
            * [SVC系统调用](../svc/README.md)
        * 结果：
          * 会产生Supervisor Call exception
          * 请求supervisor功能
          * 使得处理器进入Supervisor模式
          * -》与在所有 ARM 中（即也在 Android 上）一样，内核入口是由 SVC 命令完成的
        * 作用：软件可以留用此（SVC指令）作为一个系统调用，去提供某些服务
        * 注意事项
          * 在 SVC 处理程序的第一条指令执行之前发生的迟到异常可能会破坏仍保存在 R0 到 R3 中的参数副本。 这意味着参数的堆栈副本必须由 SVC 处理程序使用。 任何返回值也必须通过修改堆叠的寄存器值传递回调用者。 
          * 为此，必须在 SVC 处理程序的开头实现一小段汇编代码。 这标识了寄存器的保存位置，从指令中提取 SVC 编号，并将编号和指向参数的指针传递给用 C 编写的处理程序的主体
      * 编译链接等底层基础知识
        * Args参数是保存在寄存器中的
          * 就像 R0/X0 中的 arg1
        * 此处的系统调用system call的number编号(#开头的数值)是作为参数，保存到 IP（这是程序内的intra-procedura，而不是指令指针instruction pointer）
          * IP 又称 R12/X16
    * iOS中的ARM的SVC指令
      * 在内核端，低级 CPU 异常处理程序 (fleh_swi) 作为 ExceptionVectorsBase 的一部分安装，并且 - 在发出 SWI/SVC 时 - 控制转移到该地址
      * 此处理程序可以检查系统调用号以区分
        * POSIX call=POSIX 调用（非负）
        * Mach trap=Mach 陷阱（负）

## ARM中如何写SVC指令

典型写法：

```asm
MOV IP, #x // number from following list into Intraprocedural, a.k.a. r12 on arm32 and x16 on arm64
SVC 0x80   // Formerly, SWI (software interrupt)
```

-》

arm32就是：

```asm
MOV r12, #x 
SVC 0x80
```

arm64就是：

```asm
MOV x16, #x 
SVC 0x80
```

举例：

arm32中的chown的汇编实现：

```bash
(gdb) disass chown
0x30d2ad54 <chown>:       mov     r12, #16               ; 0x10, being # of chown
0x30d2ad58 <chown+4>:     svc     0x00000080
```

rm64中的chown的汇编实现：

```bash
libsystem_kernel.dylib`chown:
    0x1866c6084 <+0>:  mov    x16, #0x10
    0x1866c6088 <+4>:  svc    #0x80
```

-》

XNU开源代码中，可以找到类似写法

* XNU
  * syscall=Supervisor Call

## system call table

`XNU`中的`system call table`叫做：`sysent`

为了防止被hook（hooking），所以不开源

但是其实很容易被找出内部具体的定义

相关定义：

`bsd/sys/sysent.h`

```c
struct sysent {         /* system call table */
    int16_t         sy_narg;        /* number of args */
    int8_t          sy_resv;        /* reserved  */
    int8_t          sy_flags;       /* flags */
    sy_call_t       *sy_call;       /* implementing function */
    sy_munge_t      *sy_arg_munge32; /* system call arguments munger for 32-bit process */
    sy_munge_t      *sy_arg_munge64; /* system call arguments munger for 64-bit process */
    int32_t         sy_return_type; /* system call return types */
    uint16_t        sy_arg_bytes;   /* Total size of arguments in bytes for
                                        * 32-bit system calls
                                        */
};
```

别人写工具，去找出iOS中的syscall的number定义是：

```c
$ joker -u ~/Documents/projects/iOS.6.0.iPod4.kernel 
This is an ARM binary. Applying iOS kernel signatures
Entry point is 0x80085084....This appears to be XNU 2107.2.33
Syscall names are @2a70f0
Sysent offset in file/memory (for patching purposes): 0x2ef0c0/0x802f00c0


Suppressing enosys (0x800b3429)  T = Thumb
1. exit                  801d4a74 T
2. fork                  801d7980 T
3. read                  801eb584 T
4. write                 801eb958 T
5. open                  800b13a4 T
6. close                 801ccab4 T
。。。
442. guarded_close_np     801cebdc T
```

注：

相关完整定义，包括源码中的定义，已整理到：

【整理】iOS中syscall的系统调用编号number的定义

其中就有对应的开源代码：

https://opensource.apple.com/source/xnu/xnu-4570.1.46/bsd/kern/syscalls.master

与syscall = POSIX call 相关的：

还有个：`Mach trap` = `Mach system call`

* syscall
  * number参数：都是正的，大于0的
* Mach system call = Mach trap = trap
  * number参数：都是负的，小于0的

Mac trap举例：

（1）-30

```asm
_mach_msg_trap:
0001a8b4        e1a0c00d        mov     ip, sp
0001a8b8        e92d0170        push    {r4, r5, r6, r8}
0001a8bc        e89c0070        ldm     ip, {r4, r5, r6}
0001a8c0        e3e0c01e        mvn     ip, #30 @ 0x1e    ; Move NEGATIVE -30 into IP (R12)
0001a8c4        ef000080        svc     0x00000080        ; issue a supervisor call
0001a8c8        e8bd0170        pop     {r4, r5, r6, r8}
0001a8cc        e12fff1e        bx      lr
```

（1）-33

```asm
_semaphore_signal_all_trap:
0001a8f8        e3e0c021        mvn     ip, #33 @ 0x21   ; NEGATIVE -33 into IP (R12)
0001a8fc        ef000080        svc     0x00000080
0001a900        e12fff1e        bx      lr
```

对应的完整的table编号定义叫做：Mach Trap table

对应着iOS中的fleh_swi 函数 = fleh_swi handler

别人分析出的：mach_trap_table

```asm
$ ./joker -ls mach kernel.iPod4.iOS6.0b1
This is an ARM binary. Applying iOS kernel signatures
mach_trap_table offset in file (for patching purposes): 3064992 (0x2ec4a0)
Kern invalid should be 0x80027ec1. Ignoring those
..This appears to be XNU 2107.1.78
 10 _kernelrpc_mach_vm_allocate_trap         80014460 T
 12 _kernelrpc_mach_vm_deallocate_trap       800144cc T
 14 _kernelrpc_mach_vm_protect_trap          80014510 T
 16 _kernelrpc_mach_port_allocate_trap       80014564 T
 17 _kernelrpc_mach_port_destroy_trap        800145b4 T
 18 _kernelrpc_mach_port_deallocate_trap     800145f0 T
 19 _kernelrpc_mach_port_mod_refs_trap       8001462c T
 20 _kernelrpc_mach_port_move_member_trap    8001466c T
 21 _kernelrpc_mach_port_insert_right_trap   800146b0 T
 22 _kernelrpc_mach_port_insert_member_trap  80014710 T
 23 _kernelrpc_mach_port_extract_member_trap 80014754 T
 26 mach_reply_port                          8001b5b4 T
 27 thread_self_trap                         8001b598 T
 28 task_self_trap                           8001b578 T
 29 host_self_trap                           80019910 T
 31 mach_msg_trap                            80014ec0 T
 32 mach_msg_overwrite_trap                  80014d20 T
 33 semaphore_signal_trap                    80027188 T
 34 semaphore_signal_all_trap                8002720c T
 35 semaphore_signal_thread_trap             80027114 T
 36 semaphore_wait_trap                      800274b0 T
 37 semaphore_wait_signal_trap               80027658 T
 38 semaphore_timedwait_trap                 80027598 T
 39 semaphore_timedwait_signal_trap          8002773c T
 44 task_name_for_pid                        8021a838 T
 45 task_for_pid                             8021a688 T
 46 pid_for_task                             8021a63c T
 48 macx_swapon                              8021b414 T
 49 macx_swapoff                             8021b668 T
 51 macx_triggers                            8021b3f4 T
 52 macx_backing_store_suspend               8021b370 T
 53 macx_backing_store_recovery              8021b318 T
 58 pfz_exit                                 80027818 T
 59 swtch_pri                                800278e4 T
 60 swtch                                    8002781c T
 61 thread_switch                            80027ad4 T
 62 clock_sleep_trap                         80017520 T
 89 mach_timebase_info_trap                  80016658 T
 90 mach_wait_until_trap                     80016d20 T
 91 mk_timer_create_trap                     8001f2f4 T
 92 mk_timer_destroy_trap                    8001f500 T
 93 mk_timer_arm_trap                        8001f544 T
 94 mk_timer_cancel_trap                     8001f5c8 T
100 iokit_user_client_trap                   8026c11c T
```

供参考。
