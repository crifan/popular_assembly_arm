# 指令和二进制opcode互转

* ARM 指令 在线 生成 转换
  * [Online ARM to HEX Converter (armconverter.com)](https://armconverter.com)
    * `00 42 1B D5` -> ARM64的: `msr nzcv, x0`
      * ![arm_opcode_to_ins_msr](../assets/img/arm_opcode_to_ins_msr.png)
    * `01 42 3B D5` -> ARM64的: `mrs x1, nzcv`
      * ![arm_opcode_to_ins_mrs](../assets/img/arm_opcode_to_ins_mrs.png)
