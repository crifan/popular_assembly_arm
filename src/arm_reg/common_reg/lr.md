# LR

* `LR`=`Link Register`=`链接寄存器`=`Subroutine Link Register`=`子程序连接寄存器`
  * 作用=用途：用于函数调用function calls
    * 当发生跳转时，记录原先地址（用于后续返回地址）
  * ARM32
    * 英文概述
      * Register r14 is used as the subroutine Link Register (LR).
      * Register r14 receives the return address when a Branch with Link (BL or BLX) instruction is executed.
      * You can treat r14 as a general-purpose register at all other times. The corresponding banked registers r14_svc, r14_irq, r14_fiq, r14_abt, and r14_und are similarly used to hold the return values when interrupts and exceptions arise, or when BL or BLX instructions are executed within interrupt or exception routines.
    * 在ARM汇编语言程序设计时，R14和LR通用
    * ARM的每种模式都有各自专用的R14 寄存器=LR
      * R14
        * User用户模式和System系统模式共用一个LR
      * R14_fiq
      * R14_irq
      * R14_svc
      * R14_abt
      * R14_und
    * 注意
      * 程序设计者要清晰处理器的模式与相应寄存器的对应关系，都是使用 R14，但不同模式下的R14 不是同一个物理资源，其内容很可能不同
  * 对应寄存器
    * ARM32：`R14`
    * ARM64：`X30`

## 跳转逻辑

* 有几种情况会发生跳转，以及对应的逻辑是
  * 子程序的调用（和返回）
    * 作用：保存子程序返回地址
    * 相关指令
      * BL
      * BLX
    * 内部逻辑
      * （ARM处理器）执行（BL或BLX）跳转指令时，（ARM处理器）自动把返回地址放入r14中
        * LR的值 = 当前（BL或BLX）BL指令地址 - 4 = PC - 4
    * 子程序返回时
      * 核心逻辑：把R14=LR赋值到PC
      * 三种方法
        * MOV PC, LR 
        * BX LR
          * 或：BL LR
        * 把R14压栈再出栈
          * 在子程序入口处使用以下指令将R14存入堆栈
            * `STMFD SP!,{<Regs>,LR}`
              * == `stmfd sp!, {lr} ?`
          * 对应的，使用以下指令可以完成子程序的返回
            * `LDMFD SP!, {<Regs>,LR}`
              * == `ldmfd sp!, {pc} ?`
  * 中断和异常（Interrupt and Exception）
    * 常见异常
      * fiq
      * irq
    * 作用：跳转到异常处理=异常响应
    * ARM处理器发生异常时，异常模式的r14用来保存异常返回地址，即 PC值给LR
      * 将r14入栈可以处理嵌套中断
