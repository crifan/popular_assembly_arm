# 特殊用途寄存器

AArch64=ARM64中，有一系列的：

* `特殊用途寄存器`=`Special-purpose registers`
  * 包括

| 特殊用途寄存器 | 对应PSTATE中的字段/域 |
| ------------ | ------------------ |
| `NZCV` | `N, Z, C, V` |
| `DAIF` | `D, A, I, F` |
| `CurrentEL` | `EL` |
| `SPSel` | `SP` |
| `PAN` | `PAN` |
| `UAO` | `UAO` |
| `DIT` | `DIT` |
| `SSBS` | `SSBS` |
| `TCO` | `TCO` |

  * 用法
    * 读取和写入，用特殊的指令
      * `MSR`
        * 举例
          * NZCV
            * `MSR NZCV, <Xt>`
      * `MRS`
        * 举例
          * NZCV
            * `MRS <Xt>, NZCV`
