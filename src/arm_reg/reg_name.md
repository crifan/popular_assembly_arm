# ARM寄存器命名

ARM中，根据bit位宽，分：32位和64位，分别叫：

* `32位`=`ARM32`
* `64位`=`ARM64`

其中：

* 寄存器
  * 英文：`Register`
    * 缩写：`Reg`
      * ARM中简称：`R`

此处整理ARM中寄存的命名和叫法：

* ARM
  * 寄存器=`Register`=`Reg`
  * 通用叫法：`R`
    * 所以一般叫做：`R1`、`R2`、...、`R15`、`R16`、...、`R31`
    * `ARM32`：`W`
      * 一共有`16`个，所以分别叫：
        * `X1`、`X2`、。。。、`X15`
      * 但是由于历史原因：`ARM32`中也常叫做：`R`
        * 所以`ARM32`中也常用：`R1`、`R2`、...、`R15`
    * `ARM64`：`X`
      * 一共有`32`个，所以分别叫：
        * `X1`、`X2`、`X31`