# PC

* `PC`=`Program Counter`=`程序计数器`
  * 对应寄存器
    * `AArch32`=`ARM32` == `R15`
    * `AArch64`=`ARM64` != `X31`
      * AArch64中有PC，但不是通用寄存器X31
        * 无法直接访问到PC的值
        * 只有其他一些操作才能访问PC的值
          * 读取PC
            * 计算相对地址
          * 写入PC
            * 特殊的跳转类的指令
  * 用途：记录当前CPU的地址，总是指向正在“取指”的指令
    * 流水线（一般）使用三个阶段，因此指令分为三个阶段执行
      * 1、取指：从存储器装载一条指令
      * 2、译码：识别将要被执行的指令
      * 3、执行：处理 指令并将结果写回寄存器
    * -》
      * PC总是指向正在“取指”的指令
        * 而不是指向正在“执行”的指令 或 正在“译码”的指令
      * 一般来说，人们习惯性约定 将“正在执行的指令作为参考点”，称之为当前第一条指令，因此PC总是指向第三条指令
      * 当ARM状态时，每条指令为4字节长，所以PC始终指向该指令地址加8字节的地址，即：PC值=当前程序执行位置+8
    * -> ARM指令是三级流水线，取指，译指，执行时同时执行的
      * 现在PC指向的是正在取指的地址
        * 假设在ARM状态 下，一个指令占4个字节
          * 那么
            * cpu正在译指的指令地址是PC-4
            * cpu正在执行的指令地址是PC-8
            * 下一个指令的值就是：PC+4
      * -》也就是说PC所指向的地址和现在所执行的指令地址相差8
        * 当突然发生中断的时候，保存的是PC的地址
        * 如果返回的时候返回PC，那么中间就有一个指令没有执行，所以用 
          * SUB pc lr-irq #4
