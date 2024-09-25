# 按字母排序的ARM汇编指令列表

参考：

[Arm A-profile A64 Instruction Set Architecture - 2024-06](https://developer.arm.com/documentation/ddi0602/2024-06/)

的指令列表：

## A64 -- Base Instructions (alphabetic order)

```asm
ABS: Absolute value.
ADC: Add with carry.
ADCS: Add with carry, setting flags.
ADD (extended register): Add (extended register).
ADD (immediate): Add (immediate).
ADD (shifted register): Add (shifted register).
ADDG: Add with tag.
ADDPT: Add checked pointer.
ADDS (extended register): Add (extended register), setting flags.
ADDS (immediate): Add (immediate), setting flags.
ADDS (shifted register): Add (shifted register), setting flags.
ADR: Form PC-relative address.
ADRP: Form PC-relative address to 4KB page.
AND (immediate): Bitwise AND (immediate).
AND (shifted register): Bitwise AND (shifted register).
ANDS (immediate): Bitwise AND (immediate), setting flags.
ANDS (shifted register): Bitwise AND (shifted register), setting flags.
ASR (immediate): Arithmetic shift right (immediate): an alias of SBFM.
ASR (register): Arithmetic shift right (register): an alias of ASRV.
ASRV: Arithmetic shift right variable.
AT: Address translate: an alias of SYS.
AUTDA, AUTDZA: Authenticate data address, using key A.
AUTDB, AUTDZB: Authenticate data address, using key B.
AUTIA, AUTIA1716, AUTIASP, AUTIAZ, AUTIZA: Authenticate instruction address, using key A.
AUTIA171615: Authenticate instruction address, using key A.
AUTIASPPC: Authenticate return address using key A, using an immediate offset.
AUTIASPPCR: Authenticate return address using key A, using a register.
AUTIB, AUTIB1716, AUTIBSP, AUTIBZ, AUTIZB: Authenticate instruction address, using key B.
AUTIB171615: Authenticate instruction address, using key B.
AUTIBSPPC: Authenticate return address using key B, using an immediate offset.
AUTIBSPPCR: Authenticate return address using key B, using a register.
AXFLAG: Convert floating-point condition flags from Arm to external format.
B: Branch.
B.cond: Branch conditionally.
BC.cond: Branch consistent conditionally.
BFC: Bitfield clear: an alias of BFM.
BFI: Bitfield insert: an alias of BFM.
BFM: Bitfield move.
BFXIL: Bitfield extract and insert at low end: an alias of BFM.
BIC (shifted register): Bitwise bit clear (shifted register).
BICS (shifted register): Bitwise bit clear (shifted register), setting flags.
BL: Branch with link.
BLR: Branch with link to register.
BLRAA, BLRAAZ, BLRAB, BLRABZ: Branch with link to register, with pointer authentication.
BR: Branch to register.
BRAA, BRAAZ, BRAB, BRABZ: Branch to register, with pointer authentication.
BRB: Branch record buffer: an alias of SYS.
BRK: Breakpoint instruction.
BTI: Branch target identification.
CAS, CASA, CASAL, CASL: Compare and swap word or doubleword in memory.
CASB, CASAB, CASALB, CASLB: Compare and swap byte in memory.
CASH, CASAH, CASALH, CASLH: Compare and swap halfword in memory.
CASP, CASPA, CASPAL, CASPL: Compare and swap pair of words or doublewords in memory.
CBNZ: Compare and branch on nonzero.
CBZ: Compare and branch on zero.
CCMN (immediate): Conditional compare negative (immediate).
CCMN (register): Conditional compare negative (register).
CCMP (immediate): Conditional compare (immediate).
CCMP (register): Conditional compare (register).
CFINV: Invert carry flag.
CFP: Control flow prediction restriction by context: an alias of SYS.
CHKFEAT: Check feature status.
CINC: Conditional increment: an alias of CSINC.
CINV: Conditional invert: an alias of CSINV.
CLRBHB: Clear branch history.
CLREX: Clear exclusive.
CLS: Count leading sign bits.
CLZ: Count leading zeros.
CMN (extended register): Compare negative (extended register): an alias of ADDS (extended register).
CMN (immediate): Compare negative (immediate): an alias of ADDS (immediate).
CMN (shifted register): Compare negative (shifted register): an alias of ADDS (shifted register).
CMP (extended register): Compare (extended register): an alias of SUBS (extended register).
CMP (immediate): Compare (immediate): an alias of SUBS (immediate).
CMP (shifted register): Compare (shifted register): an alias of SUBS (shifted register).
CMPP: Compare with tag: an alias of SUBPS.
CNEG: Conditional negate: an alias of CSNEG.
CNT: Count bits.
COSP: Clear other speculative prediction restriction by context: an alias of SYS.
CPP: Cache prefetch prediction restriction by context: an alias of SYS.
CPYFP, CPYFM, CPYFE: Memory copy forward-only.
CPYFPN, CPYFMN, CPYFEN: Memory copy forward-only, reads and writes non-temporal.
CPYFPRN, CPYFMRN, CPYFERN: Memory copy forward-only, reads non-temporal.
CPYFPRT, CPYFMRT, CPYFERT: Memory copy forward-only, reads unprivileged.
CPYFPRTN, CPYFMRTN, CPYFERTN: Memory copy forward-only, reads unprivileged, reads and writes non-temporal.
CPYFPRTRN, CPYFMRTRN, CPYFERTRN: Memory copy forward-only, reads unprivileged and non-temporal.
CPYFPRTWN, CPYFMRTWN, CPYFERTWN: Memory copy forward-only, reads unprivileged, writes non-temporal.
CPYFPT, CPYFMT, CPYFET: Memory copy forward-only, reads and writes unprivileged.
CPYFPTN, CPYFMTN, CPYFETN: Memory copy forward-only, reads and writes unprivileged and non-temporal.
CPYFPTRN, CPYFMTRN, CPYFETRN: Memory copy forward-only, reads and writes unprivileged, reads non-temporal.
CPYFPTWN, CPYFMTWN, CPYFETWN: Memory copy forward-only, reads and writes unprivileged, writes non-temporal.
CPYFPWN, CPYFMWN, CPYFEWN: Memory copy forward-only, writes non-temporal.
CPYFPWT, CPYFMWT, CPYFEWT: Memory copy forward-only, writes unprivileged.
CPYFPWTN, CPYFMWTN, CPYFEWTN: Memory copy forward-only, writes unprivileged, reads and writes non-temporal.
CPYFPWTRN, CPYFMWTRN, CPYFEWTRN: Memory copy forward-only, writes unprivileged, reads non-temporal.
CPYFPWTWN, CPYFMWTWN, CPYFEWTWN: Memory copy forward-only, writes unprivileged and non-temporal.
CPYP, CPYM, CPYE: Memory copy.
CPYPN, CPYMN, CPYEN: Memory copy, reads and writes non-temporal.
CPYPRN, CPYMRN, CPYERN: Memory copy, reads non-temporal.
CPYPRT, CPYMRT, CPYERT: Memory copy, reads unprivileged.
CPYPRTN, CPYMRTN, CPYERTN: Memory copy, reads unprivileged, reads and writes non-temporal.
CPYPRTRN, CPYMRTRN, CPYERTRN: Memory copy, reads unprivileged and non-temporal.
CPYPRTWN, CPYMRTWN, CPYERTWN: Memory copy, reads unprivileged, writes non-temporal.
CPYPT, CPYMT, CPYET: Memory copy, reads and writes unprivileged.
CPYPTN, CPYMTN, CPYETN: Memory copy, reads and writes unprivileged and non-temporal.
CPYPTRN, CPYMTRN, CPYETRN: Memory copy, reads and writes unprivileged, reads non-temporal.
CPYPTWN, CPYMTWN, CPYETWN: Memory copy, reads and writes unprivileged, writes non-temporal.
CPYPWN, CPYMWN, CPYEWN: Memory copy, writes non-temporal.
CPYPWT, CPYMWT, CPYEWT: Memory copy, writes unprivileged.
CPYPWTN, CPYMWTN, CPYEWTN: Memory copy, writes unprivileged, reads and writes non-temporal.
CPYPWTRN, CPYMWTRN, CPYEWTRN: Memory copy, writes unprivileged, reads non-temporal.
CPYPWTWN, CPYMWTWN, CPYEWTWN: Memory copy, writes unprivileged and non-temporal.
CRC32B, CRC32H, CRC32W, CRC32X: CRC32 checksum.
CRC32CB, CRC32CH, CRC32CW, CRC32CX: CRC32C checksum.
CSDB: Consumption of speculative data barrier.
CSEL: Conditional select.
CSET: Conditional set: an alias of CSINC.
CSETM: Conditional set mask: an alias of CSINV.
CSINC: Conditional select increment.
CSINV: Conditional select invert.
CSNEG: Conditional select negation.
CTZ: Count trailing zeros.
DC: Data cache operation: an alias of SYS.
DCPS1: Debug change PE state to EL1.
DCPS2: Debug change PE state to EL2.
DCPS3: Debug change PE state to EL3.
DGH: Data gathering hint.
DMB: Data memory barrier.
DRPS: Debug restore PE state.
DSB: Data synchronization barrier.
DVP: Data value prediction restriction by context: an alias of SYS.
EON (shifted register): Bitwise exclusive-OR NOT (shifted register).
EOR (immediate): Bitwise exclusive-OR (immediate).
EOR (shifted register): Bitwise exclusive-OR (shifted register).
ERET: Exception return.
ERETAA, ERETAB: Exception return, with pointer authentication.
ESB: Error synchronization barrier.
EXTR: Extract register.
GCSB: Guarded Control Stack barrier.
GCSPOPCX: Guarded Control Stack pop and compare exception return record: an alias of SYS.
GCSPOPM: Guarded Control Stack pop: an alias of SYSL.
GCSPOPX: Guarded Control Stack pop exception return record: an alias of SYS.
GCSPUSHM: Guarded Control Stack push: an alias of SYS.
GCSPUSHX: Guarded Control Stack push exception return record: an alias of SYS.
GCSSS1: Guarded Control Stack switch stack 1: an alias of SYS.
GCSSS2: Guarded Control Stack switch stack 2: an alias of SYSL.
GCSSTR: Guarded Control Stack store.
GCSSTTR: Guarded Control Stack unprivileged store.
GMI: Tag mask insert.
HINT: Hint instruction.
HLT: Halt instruction.
HVC: Hypervisor call.
IC: Instruction cache operation: an alias of SYS.
IRG: Insert random tag.
ISB: Instruction synchronization barrier.
LD64B: Single-copy atomic 64-byte Load.
LDADD, LDADDA, LDADDAL, LDADDL: Atomic add on word or doubleword in memory.
LDADDB, LDADDAB, LDADDALB, LDADDLB: Atomic add on byte in memory.
LDADDH, LDADDAH, LDADDALH, LDADDLH: Atomic add on halfword in memory.
LDAPR: Load-acquire RCpc register.
LDAPRB: Load-acquire RCpc register byte.
LDAPRH: Load-acquire RCpc register halfword.
LDAPUR: Load-acquire RCpc register (unscaled).
LDAPURB: Load-acquire RCpc register byte (unscaled).
LDAPURH: Load-acquire RCpc register halfword (unscaled).
LDAPURSB: Load-acquire RCpc register signed byte (unscaled).
LDAPURSH: Load-acquire RCpc register signed halfword (unscaled).
LDAPURSW: Load-acquire RCpc register signed word (unscaled).
LDAR: Load-acquire register.
LDARB: Load-acquire register byte.
LDARH: Load-acquire register halfword.
LDAXP: Load-acquire exclusive pair of registers.
LDAXR: Load-acquire exclusive register.
LDAXRB: Load-acquire exclusive register byte.
LDAXRH: Load-acquire exclusive register halfword.
LDCLR, LDCLRA, LDCLRAL, LDCLRL: Atomic bit clear on word or doubleword in memory.
LDCLRB, LDCLRAB, LDCLRALB, LDCLRLB: Atomic bit clear on byte in memory.
LDCLRH, LDCLRAH, LDCLRALH, LDCLRLH: Atomic bit clear on halfword in memory.
LDCLRP, LDCLRPA, LDCLRPAL, LDCLRPL: Atomic bit clear on quadword in memory.
LDEOR, LDEORA, LDEORAL, LDEORL: Atomic exclusive-OR on word or doubleword in memory.
LDEORB, LDEORAB, LDEORALB, LDEORLB: Atomic exclusive-OR on byte in memory.
LDEORH, LDEORAH, LDEORALH, LDEORLH: Atomic exclusive-OR on halfword in memory.
LDG: Load Allocation Tag.
LDGM: Load tag multiple.
LDIAPP: Load-Acquire RCpc ordered pair of registers.
LDLAR: Load LOAcquire register.
LDLARB: Load LOAcquire register byte.
LDLARH: Load LOAcquire register halfword.
LDNP: Load pair of registers, with non-temporal hint.
LDP: Load pair of registers.
LDPSW: Load pair of registers signed word.
LDR (immediate): Load register (immediate).
LDR (literal): Load register (literal).
LDR (register): Load register (register).
LDRAA, LDRAB: Load register, with pointer authentication.
LDRB (immediate): Load register byte (immediate).
LDRB (register): Load register byte (register).
LDRH (immediate): Load register halfword (immediate).
LDRH (register): Load register halfword (register).
LDRSB (immediate): Load register signed byte (immediate).
LDRSB (register): Load register signed byte (register).
LDRSH (immediate): Load register signed halfword (immediate).
LDRSH (register): Load register signed halfword (register).
LDRSW (immediate): Load register signed word (immediate).
LDRSW (literal): Load register signed word (literal).
LDRSW (register): Load register signed word (register).
LDSET, LDSETA, LDSETAL, LDSETL: Atomic bit set on word or doubleword in memory.
LDSETB, LDSETAB, LDSETALB, LDSETLB: Atomic bit set on byte in memory.
LDSETH, LDSETAH, LDSETALH, LDSETLH: Atomic bit set on halfword in memory.
LDSETP, LDSETPA, LDSETPAL, LDSETPL: Atomic bit set on quadword in memory.
LDSMAX, LDSMAXA, LDSMAXAL, LDSMAXL: Atomic signed maximum on word or doubleword in memory.
LDSMAXB, LDSMAXAB, LDSMAXALB, LDSMAXLB: Atomic signed maximum on byte in memory.
LDSMAXH, LDSMAXAH, LDSMAXALH, LDSMAXLH: Atomic signed maximum on halfword in memory.
LDSMIN, LDSMINA, LDSMINAL, LDSMINL: Atomic signed minimum on word or doubleword in memory.
LDSMINB, LDSMINAB, LDSMINALB, LDSMINLB: Atomic signed minimum on byte in memory.
LDSMINH, LDSMINAH, LDSMINALH, LDSMINLH: Atomic signed minimum on halfword in memory.
LDTR: Load register (unprivileged).
LDTRB: Load register byte (unprivileged).
LDTRH: Load register halfword (unprivileged).
LDTRSB: Load register signed byte (unprivileged).
LDTRSH: Load register signed halfword (unprivileged).
LDTRSW: Load register signed word (unprivileged).
LDUMAX, LDUMAXA, LDUMAXAL, LDUMAXL: Atomic unsigned maximum on word or doubleword in memory.
LDUMAXB, LDUMAXAB, LDUMAXALB, LDUMAXLB: Atomic unsigned maximum on byte in memory.
LDUMAXH, LDUMAXAH, LDUMAXALH, LDUMAXLH: Atomic unsigned maximum on halfword in memory.
LDUMIN, LDUMINA, LDUMINAL, LDUMINL: Atomic unsigned minimum on word or doubleword in memory.
LDUMINB, LDUMINAB, LDUMINALB, LDUMINLB: Atomic unsigned minimum on byte in memory.
LDUMINH, LDUMINAH, LDUMINALH, LDUMINLH: Atomic unsigned minimum on halfword in memory.
LDUR: Load register (unscaled).
LDURB: Load register byte (unscaled).
LDURH: Load register halfword (unscaled).
LDURSB: Load register signed byte (unscaled).
LDURSH: Load register signed halfword (unscaled).
LDURSW: Load register signed word (unscaled).
LDXP: Load exclusive pair of registers.
LDXR: Load exclusive register.
LDXRB: Load exclusive register byte.
LDXRH: Load exclusive register halfword.
LSL (immediate): Logical shift left (immediate): an alias of UBFM.
LSL (register): Logical shift left (register): an alias of LSLV.
LSLV: Logical shift left variable.
LSR (immediate): Logical shift right (immediate): an alias of UBFM.
LSR (register): Logical shift right (register): an alias of LSRV.
LSRV: Logical shift right variable.
MADD: Multiply-add.
MADDPT: Multiply-add checked pointer.
MNEG: Multiply-negate: an alias of MSUB.
MOV (bitmask immediate): Move (bitmask immediate): an alias of ORR (immediate).
MOV (inverted wide immediate): Move (inverted wide immediate): an alias of MOVN.
MOV (register): Move (register): an alias of ORR (shifted register).
MOV (to/from SP): Move (to/from SP): an alias of ADD (immediate).
MOV (wide immediate): Move (wide immediate): an alias of MOVZ.
MOVK: Move wide with keep.
MOVN: Move wide with NOT.
MOVZ: Move wide with zero.
MRRS: Move System register to two adjacent general-purpose registers.
MRS: Move System register to general-purpose register.
MSR (immediate): Move immediate value to special register.
MSR (register): Move general-purpose register to System register.
MSRR: Move two adjacent general-purpose registers to System register.
MSUB: Multiply-subtract.
MSUBPT: Multiply-subtract checked pointer.
MUL: Multiply: an alias of MADD.
MVN: Bitwise NOT: an alias of ORN (shifted register).
NEG (shifted register): Negate (shifted register): an alias of SUB (shifted register).
NEGS: Negate, setting flags: an alias of SUBS (shifted register).
NGC: Negate with carry: an alias of SBC.
NGCS: Negate with carry, setting flags: an alias of SBCS.
NOP: No operation.
ORN (shifted register): Bitwise OR NOT (shifted register).
ORR (immediate): Bitwise OR (immediate).
ORR (shifted register): Bitwise OR (shifted register).
PACDA, PACDZA: Pointer Authentication Code for data address, using key A.
PACDB, PACDZB: Pointer Authentication Code for data address, using key B.
PACGA: Pointer Authentication Code, using generic key.
PACIA, PACIA1716, PACIASP, PACIAZ, PACIZA: Pointer Authentication Code for instruction address, using key A.
PACIA171615: Pointer Authentication Code for instruction address, using key A.
PACIASPPC: Pointer Authentication Code for return address, using key A.
PACIB, PACIB1716, PACIBSP, PACIBZ, PACIZB: Pointer Authentication Code for instruction address, using key B.
PACIB171615: Pointer Authentication Code for instruction address, using key B.
PACIBSPPC: Pointer Authentication Code for return address, using key B.
PACM: Pointer authentication modifier.
PACNBIASPPC: Pointer Authentication Code for return address, using key A, not a branch target.
PACNBIBSPPC: Pointer Authentication Code for return address, using key B, not a branch target.
PRFM (immediate): Prefetch memory (immediate).
PRFM (literal): Prefetch memory (literal).
PRFM (register): Prefetch memory (register).
PRFUM: Prefetch memory (unscaled offset).
PSB: Profiling synchronization barrier.
PSSBB: Physical speculative store bypass barrier: an alias of DSB.
RBIT: Reverse bits.
RCWCAS, RCWCASA, RCWCASL, RCWCASAL: Read check write compare and swap doubleword in memory.
RCWCASP, RCWCASPA, RCWCASPL, RCWCASPAL: Read check write compare and swap quadword in memory.
RCWCLR, RCWCLRA, RCWCLRL, RCWCLRAL: Read check write atomic bit clear on doubleword in memory.
RCWCLRP, RCWCLRPA, RCWCLRPL, RCWCLRPAL: Read check write atomic bit clear on quadword in memory.
RCWSCAS, RCWSCASA, RCWSCASL, RCWSCASAL: Read check write software compare and swap doubleword in memory.
RCWSCASP, RCWSCASPA, RCWSCASPL, RCWSCASPAL: Read check write software compare and swap quadword in memory.
RCWSCLR, RCWSCLRA, RCWSCLRL, RCWSCLRAL: Read check write software atomic bit clear on doubleword in memory.
RCWSCLRP, RCWSCLRPA, RCWSCLRPL, RCWSCLRPAL: Read check write software atomic bit clear on quadword in memory.
RCWSET, RCWSETA, RCWSETL, RCWSETAL: Read check write atomic bit set on doubleword in memory.
RCWSETP, RCWSETPA, RCWSETPL, RCWSETPAL: Read check write atomic bit set on quadword in memory.
RCWSSET, RCWSSETA, RCWSSETL, RCWSSETAL: Read check write software atomic bit set on doubleword in memory.
RCWSSETP, RCWSSETPA, RCWSSETPL, RCWSSETPAL: Read check write software atomic bit set on quadword in memory.
RCWSSWP, RCWSSWPA, RCWSSWPL, RCWSSWPAL: Read check write software swap doubleword in memory.
RCWSSWPP, RCWSSWPPA, RCWSSWPPL, RCWSSWPPAL: Read check write software swap quadword in memory.
RCWSWP, RCWSWPA, RCWSWPL, RCWSWPAL: Read check write swap doubleword in memory.
RCWSWPP, RCWSWPPA, RCWSWPPL, RCWSWPPAL: Read check write swap quadword in memory.
RET: Return from subroutine.
RETAA, RETAB: Return from subroutine, with pointer authentication.
RETAASPPC, RETABSPPC: Return from subroutine, with enhanced pointer authentication return using an immediate offset.
RETAASPPCR, RETABSPPCR: Return from subroutine, with enhanced pointer authentication return using a register.
REV: Reverse bytes.
REV16: Reverse bytes in 16-bit halfwords.
REV32: Reverse bytes in 32-bit words.
REV64: Reverse bytes: an alias of REV.
RMIF: Rotate, mask insert flags.
ROR (immediate): Rotate right (immediate): an alias of EXTR.
ROR (register): Rotate right (register): an alias of RORV.
RORV: Rotate right variable.
RPRFM: Range prefetch memory.
SB: Speculation barrier.
SBC: Subtract with carry.
SBCS: Subtract with carry, setting flags.
SBFIZ: Signed bitfield insert in zeros: an alias of SBFM.
SBFM: Signed bitfield move.
SBFX: Signed bitfield extract: an alias of SBFM.
SDIV: Signed divide.
SETF8, SETF16: Evaluation of 8-bit or 16-bit flag values.
SETGP, SETGM, SETGE: Memory set with tag setting.
SETGPN, SETGMN, SETGEN: Memory set with tag setting, non-temporal.
SETGPT, SETGMT, SETGET: Memory set with tag setting, unprivileged.
SETGPTN, SETGMTN, SETGETN: Memory set with tag setting, unprivileged and non-temporal.
SETP, SETM, SETE: Memory set.
SETPN, SETMN, SETEN: Memory set, non-temporal.
SETPT, SETMT, SETET: Memory set, unprivileged.
SETPTN, SETMTN, SETETN: Memory set, unprivileged and non-temporal.
SEV: Send event.
SEVL: Send event local.
SMADDL: Signed multiply-add long.
SMAX (immediate): Signed maximum (immediate).
SMAX (register): Signed maximum (register).
SMC: Secure monitor call.
SMIN (immediate): Signed minimum (immediate).
SMIN (register): Signed minimum (register).
SMNEGL: Signed multiply-negate long: an alias of SMSUBL.
SMSTART: Enables access to Streaming SVE mode and SME architectural state: an alias of MSR (immediate).
SMSTOP: Disables access to Streaming SVE mode and SME architectural state: an alias of MSR (immediate).
SMSUBL: Signed multiply-subtract long.
SMULH: Signed multiply high.
SMULL: Signed multiply long: an alias of SMADDL.
SSBB: Speculative store bypass barrier: an alias of DSB.
ST2G: Store Allocation Tags.
ST64B: Single-copy atomic 64-byte store without status result.
ST64BV: Single-copy atomic 64-byte store with status result.
ST64BV0: Single-copy atomic 64-byte EL0 store with status result.
STADD, STADDL: Atomic add on word or doubleword in memory, without return: an alias of LDADD, LDADDA, LDADDAL, LDADDL.
STADDB, STADDLB: Atomic add on byte in memory, without return: an alias of LDADDB, LDADDAB, LDADDALB, LDADDLB.
STADDH, STADDLH: Atomic add on halfword in memory, without return: an alias of LDADDH, LDADDAH, LDADDALH, LDADDLH.
STCLR, STCLRL: Atomic bit clear on word or doubleword in memory, without return: an alias of LDCLR, LDCLRA, LDCLRAL, LDCLRL.
STCLRB, STCLRLB: Atomic bit clear on byte in memory, without return: an alias of LDCLRB, LDCLRAB, LDCLRALB, LDCLRLB.
STCLRH, STCLRLH: Atomic bit clear on halfword in memory, without return: an alias of LDCLRH, LDCLRAH, LDCLRALH, LDCLRLH.
STEOR, STEORL: Atomic exclusive-OR on word or doubleword in memory, without return: an alias of LDEOR, LDEORA, LDEORAL, LDEORL.
STEORB, STEORLB: Atomic exclusive-OR on byte in memory, without return: an alias of LDEORB, LDEORAB, LDEORALB, LDEORLB.
STEORH, STEORLH: Atomic exclusive-OR on halfword in memory, without return: an alias of LDEORH, LDEORAH, LDEORALH, LDEORLH.
STG: Store Allocation Tag.
STGM: Store Allocation Tag multiple.
STGP: Store Allocation Tag and pair of registers.
STILP: Store-release ordered pair of registers.
STLLR: Store LORelease register.
STLLRB: Store LORelease register byte.
STLLRH: Store LORelease register halfword.
STLR: Store-release register.
STLRB: Store-release register byte.
STLRH: Store-release register halfword.
STLUR: Store-release register (unscaled).
STLURB: Store-release register byte (unscaled).
STLURH: Store-release register halfword (unscaled).
STLXP: Store-release exclusive pair of registers.
STLXR: Store-release exclusive register.
STLXRB: Store-release exclusive register byte.
STLXRH: Store-release exclusive register halfword.
STNP: Store pair of registers, with non-temporal hint.
STP: Store pair of registers.
STR (immediate): Store register (immediate).
STR (register): Store register (register).
STRB (immediate): Store register byte (immediate).
STRB (register): Store register byte (register).
STRH (immediate): Store register halfword (immediate).
STRH (register): Store register halfword (register).
STSET, STSETL: Atomic bit set on word or doubleword in memory, without return: an alias of LDSET, LDSETA, LDSETAL, LDSETL.
STSETB, STSETLB: Atomic bit set on byte in memory, without return: an alias of LDSETB, LDSETAB, LDSETALB, LDSETLB.
STSETH, STSETLH: Atomic bit set on halfword in memory, without return: an alias of LDSETH, LDSETAH, LDSETALH, LDSETLH.
STSMAX, STSMAXL: Atomic signed maximum on word or doubleword in memory, without return: an alias of LDSMAX, LDSMAXA, LDSMAXAL, LDSMAXL.
STSMAXB, STSMAXLB: Atomic signed maximum on byte in memory, without return: an alias of LDSMAXB, LDSMAXAB, LDSMAXALB, LDSMAXLB.
STSMAXH, STSMAXLH: Atomic signed maximum on halfword in memory, without return: an alias of LDSMAXH, LDSMAXAH, LDSMAXALH, LDSMAXLH.
STSMIN, STSMINL: Atomic signed minimum on word or doubleword in memory, without return: an alias of LDSMIN, LDSMINA, LDSMINAL, LDSMINL.
STSMINB, STSMINLB: Atomic signed minimum on byte in memory, without return: an alias of LDSMINB, LDSMINAB, LDSMINALB, LDSMINLB.
STSMINH, STSMINLH: Atomic signed minimum on halfword in memory, without return: an alias of LDSMINH, LDSMINAH, LDSMINALH, LDSMINLH.
STTR: Store register (unprivileged).
STTRB: Store register byte (unprivileged).
STTRH: Store register halfword (unprivileged).
STUMAX, STUMAXL: Atomic unsigned maximum on word or doubleword in memory, without return: an alias of LDUMAX, LDUMAXA, LDUMAXAL, LDUMAXL.
STUMAXB, STUMAXLB: Atomic unsigned maximum on byte in memory, without return: an alias of LDUMAXB, LDUMAXAB, LDUMAXALB, LDUMAXLB.
STUMAXH, STUMAXLH: Atomic unsigned maximum on halfword in memory, without return: an alias of LDUMAXH, LDUMAXAH, LDUMAXALH, LDUMAXLH.
STUMIN, STUMINL: Atomic unsigned minimum on word or doubleword in memory, without return: an alias of LDUMIN, LDUMINA, LDUMINAL, LDUMINL.
STUMINB, STUMINLB: Atomic unsigned minimum on byte in memory, without return: an alias of LDUMINB, LDUMINAB, LDUMINALB, LDUMINLB.
STUMINH, STUMINLH: Atomic unsigned minimum on halfword in memory, without return: an alias of LDUMINH, LDUMINAH, LDUMINALH, LDUMINLH.
STUR: Store register (unscaled).
STURB: Store register byte (unscaled).
STURH: Store register halfword (unscaled).
STXP: Store exclusive pair of registers.
STXR: Store exclusive register.
STXRB: Store exclusive register byte.
STXRH: Store exclusive register halfword.
STZ2G: Store Allocation Tags, zeroing.
STZG: Store Allocation Tag, zeroing.
STZGM: Store Allocation Tag and zero multiple.
SUB (extended register): Subtract (extended register).
SUB (immediate): Subtract (immediate).
SUB (shifted register): Subtract (shifted register).
SUBG: Subtract with tag.
SUBP: Subtract pointer.
SUBPS: Subtract pointer, setting flags.
SUBPT: Subtract checked pointer.
SUBS (extended register): Subtract (extended register), setting flags.
SUBS (immediate): Subtract (immediate), setting flags.
SUBS (shifted register): Subtract (shifted register), setting flags.
SVC: Supervisor call.
SWP, SWPA, SWPAL, SWPL: Swap word or doubleword in memory.
SWPB, SWPAB, SWPALB, SWPLB: Swap byte in memory.
SWPH, SWPAH, SWPALH, SWPLH: Swap halfword in memory.
SWPP, SWPPA, SWPPAL, SWPPL: Swap quadword in memory.
SXTB: Signed extend byte: an alias of SBFM.
SXTH: Sign extend halfword: an alias of SBFM.
SXTW: Sign extend word: an alias of SBFM.
SYS: System instruction.
SYSL: System instruction with result.
SYSP: 128-bit system instruction.
TBNZ: Test bit and branch if nonzero.
TBZ: Test bit and branch if zero.
TCANCEL: Cancel current transaction.
TCOMMIT: Commit current transaction.
TLBI: TLB invalidate operation: an alias of SYS.
TLBIP: TLB invalidate pair operation: an alias of SYSP.
TRCIT: Trace instrumentation: an alias of SYS.
TSB: Trace synchronization barrier.
TST (immediate): Test bits (immediate): an alias of ANDS (immediate).
TST (shifted register): Test (shifted register): an alias of ANDS (shifted register).
TSTART: Start transaction.
TTEST: Test transaction state.
UBFIZ: Unsigned bitfield insert in zeros: an alias of UBFM.
UBFM: Unsigned bitfield move.
UBFX: Unsigned bitfield extract: an alias of UBFM.
UDF: Permanently undefined.
UDIV: Unsigned divide.
UMADDL: Unsigned multiply-add long.
UMAX (immediate): Unsigned maximum (immediate).
UMAX (register): Unsigned maximum (register).
UMIN (immediate): Unsigned minimum (immediate).
UMIN (register): Unsigned minimum (register).
UMNEGL: Unsigned multiply-negate long: an alias of UMSUBL.
UMSUBL: Unsigned multiply-subtract long.
UMULH: Unsigned multiply high.
UMULL: Unsigned multiply long: an alias of UMADDL.
UXTB: Unsigned extend byte: an alias of UBFM.
UXTH: Unsigned extend halfword: an alias of UBFM.
WFE: Wait for event.
WFET: Wait for event with timeout.
WFI: Wait for interrupt.
WFIT: Wait for interrupt with timeout.
XAFLAG: Convert floating-point condition flags from external format to Arm format.
XPACD, XPACI, XPACLRI: Strip Pointer Authentication Code.
YIELD: Yield.
```

## A64 -- SIMD and Floating-point Instructions (alphabetic order)

```asm
ABS: Absolute value (vector).
ADD (vector): Add (vector).
ADDHN, ADDHN2: Add returning high narrow.
ADDP (scalar): Add pair of elements (scalar).
ADDP (vector): Add pairwise (vector).
ADDV: Add across vector.
AESD: AES single round decryption.
AESE: AES single round encryption.
AESIMC: AES inverse mix columns.
AESMC: AES mix columns.
AND (vector): Bitwise AND (vector).
BCAX: Bit clear and exclusive-OR.
BF1CVTL, BF1CVTL2, BF2CVTL, BF2CVTL2: 8-bit floating-point convert to BFloat16 (vector).
BFCVT: Floating-point convert from single-precision to BFloat16 format (scalar).
BFCVTN, BFCVTN2: Floating-point convert from single-precision to BFloat16 format (vector).
BFDOT (by element): BFloat16 floating-point dot product (vector, by element).
BFDOT (vector): BFloat16 floating-point dot product (vector).
BFMLALB, BFMLALT (by element): BFloat16 floating-point widening multiply-add long (by element).
BFMLALB, BFMLALT (vector): BFloat16 floating-point widening multiply-add long (vector).
BFMMLA: BFloat16 floating-point matrix multiply-accumulate into 2x2 matrix.
BIC (vector, immediate): Bitwise bit clear (vector, immediate).
BIC (vector, register): Bitwise bit clear (vector, register).
BIF: Bitwise insert if false.
BIT: Bitwise insert if true.
BSL: Bitwise select.
CLS (vector): Count leading sign bits (vector).
CLZ (vector): Count leading zero bits (vector).
CMEQ (register): Compare bitwise equal (vector).
CMEQ (zero): Compare bitwise equal to zero (vector).
CMGE (register): Compare signed greater than or equal (vector).
CMGE (zero): Compare signed greater than or equal to zero (vector).
CMGT (register): Compare signed greater than (vector).
CMGT (zero): Compare signed greater than zero (vector).
CMHI (register): Compare unsigned higher (vector).
CMHS (register): Compare unsigned higher or same (vector).
CMLE (zero): Compare signed less than or equal to zero (vector).
CMLT (zero): Compare signed less than zero (vector).
CMTST: Compare bitwise test bits nonzero (vector).
CNT: Population count per byte.
DUP (element): Duplicate vector element to vector or scalar.
DUP (general): Duplicate general-purpose register to vector.
EOR (vector): Bitwise exclusive-OR (vector).
EOR3: Three-way exclusive-OR.
EXT: Extract vector from pair of vectors.
F1CVTL, F1CVTL2, F2CVTL, F2CVTL2: 8-bit floating-point convert to half-precision (vector).
FABD: Floating-point absolute difference (vector).
FABS (scalar): Floating-point absolute value (scalar).
FABS (vector): Floating-point absolute value (vector).
FACGE: Floating-point absolute compare greater than or equal (vector).
FACGT: Floating-point absolute compare greater than (vector).
FADD (scalar): Floating-point add (scalar).
FADD (vector): Floating-point add (vector).
FADDP (scalar): Floating-point add pair of elements (scalar).
FADDP (vector): Floating-point add pairwise (vector).
FAMAX: Floating-point absolute maximum.
FAMIN: Floating-point absolute minimum.
FCADD: Floating-point complex add.
FCCMP: Floating-point conditional quiet compare (scalar).
FCCMPE: Floating-point conditional signaling compare (scalar).
FCMEQ (register): Floating-point compare equal (vector).
FCMEQ (zero): Floating-point compare equal to zero (vector).
FCMGE (register): Floating-point compare greater than or equal (vector).
FCMGE (zero): Floating-point compare greater than or equal to zero (vector).
FCMGT (register): Floating-point compare greater than (vector).
FCMGT (zero): Floating-point compare greater than zero (vector).
FCMLA: Floating-point complex multiply accumulate.
FCMLA (by element): Floating-point complex multiply accumulate (by element).
FCMLE (zero): Floating-point compare less than or equal to zero (vector).
FCMLT (zero): Floating-point compare less than zero (vector).
FCMP: Floating-point quiet compare (scalar).
FCMPE: Floating-point signaling compare (scalar).
FCSEL: Floating-point conditional select (scalar).
FCVT: Floating-point convert precision (scalar).
FCVTAS (scalar): Floating-point convert to signed integer, rounding to nearest with ties to away (scalar).
FCVTAS (vector): Floating-point convert to signed integer, rounding to nearest with ties to away (vector).
FCVTAU (scalar): Floating-point convert to unsigned integer, rounding to nearest with ties to away (scalar).
FCVTAU (vector): Floating-point convert to unsigned integer, rounding to nearest with ties to away (vector).
FCVTL, FCVTL2: Floating-point convert to higher precision long (vector).
FCVTMS (scalar): Floating-point convert to signed integer, rounding toward minus infinity (scalar).
FCVTMS (vector): Floating-point convert to signed integer, rounding toward minus infinity (vector).
FCVTMU (scalar): Floating-point convert to unsigned integer, rounding toward minus infinity (scalar).
FCVTMU (vector): Floating-point convert to unsigned integer, rounding toward minus infinity (vector).
FCVTN (half-precision to 8-bit floating-point): Half-precision to 8-bit floating-point convert and narrow (vector).
FCVTN, FCVTN2 (double to single-precision, single to half-precision): Floating-point convert to lower precision narrow (vector).
FCVTN, FCVTN2 (single-precision to 8-bit floating-point): Single-precision to 8-bit floating-point convert and narrow (vector).
FCVTNS (scalar): Floating-point convert to signed integer, rounding to nearest with ties to even (scalar).
FCVTNS (vector): Floating-point convert to signed integer, rounding to nearest with ties to even (vector).
FCVTNU (scalar): Floating-point convert to unsigned integer, rounding to nearest with ties to even (scalar).
FCVTNU (vector): Floating-point convert to unsigned integer, rounding to nearest with ties to even (vector).
FCVTPS (scalar): Floating-point convert to signed integer, rounding toward plus infinity (scalar).
FCVTPS (vector): Floating-point convert to signed integer, rounding toward plus infinity (vector).
FCVTPU (scalar): Floating-point convert to unsigned integer, rounding toward plus infinity (scalar).
FCVTPU (vector): Floating-point convert to unsigned integer, rounding toward plus infinity (vector).
FCVTXN, FCVTXN2: Floating-point convert to lower precision narrow, rounding to odd (vector).
FCVTZS (scalar, fixed-point): Floating-point convert to signed fixed-point, rounding toward zero (scalar).
FCVTZS (scalar, integer): Floating-point convert to signed integer, rounding toward zero (scalar).
FCVTZS (vector, fixed-point): Floating-point convert to signed fixed-point, rounding toward zero (vector).
FCVTZS (vector, integer): Floating-point convert to signed integer, rounding toward zero (vector).
FCVTZU (scalar, fixed-point): Floating-point convert to unsigned fixed-point, rounding toward zero (scalar).
FCVTZU (scalar, integer): Floating-point convert to unsigned integer, rounding toward zero (scalar).
FCVTZU (vector, fixed-point): Floating-point convert to unsigned fixed-point, rounding toward zero (vector).
FCVTZU (vector, integer): Floating-point convert to unsigned integer, rounding toward zero (vector).
FDIV (scalar): Floating-point divide (scalar).
FDIV (vector): Floating-point divide (vector).
FDOT (8-bit floating-point to half-precision, by element): 8-bit floating-point dot product to half-precision (vector, by element).
FDOT (8-bit floating-point to half-precision, vector): 8-bit floating-point dot product to half-precision (vector).
FDOT (8-bit floating-point to single-precision, by element): 8-bit floating-point dot product to single-precision (vector, by element).
FDOT (8-bit floating-point to single-precision, vector): 8-bit floating-point dot product to single-precision (vector).
FJCVTZS: Floating-point Javascript convert to signed fixed-point, rounding toward zero.
FMADD: Floating-point fused multiply-add (scalar).
FMAX (scalar): Floating-point maximum (scalar).
FMAX (vector): Floating-point maximum (vector).
FMAXNM (scalar): Floating-point maximum number (scalar).
FMAXNM (vector): Floating-point maximum number (vector).
FMAXNMP (scalar): Floating-point maximum number of pair of elements (scalar).
FMAXNMP (vector): Floating-point maximum number pairwise (vector).
FMAXNMV: Floating-point maximum number across vector.
FMAXP (scalar): Floating-point maximum of pair of elements (scalar).
FMAXP (vector): Floating-point maximum pairwise (vector).
FMAXV: Floating-point maximum across vector.
FMIN (scalar): Floating-point minimum (scalar).
FMIN (vector): Floating-point minimum (vector).
FMINNM (scalar): Floating-point minimum number (scalar).
FMINNM (vector): Floating-point minimum number (vector).
FMINNMP (scalar): Floating-point minimum number of pair of elements (scalar).
FMINNMP (vector): Floating-point minimum number pairwise (vector).
FMINNMV: Floating-point minimum number across vector.
FMINP (scalar): Floating-point minimum of pair of elements (scalar).
FMINP (vector): Floating-point minimum pairwise (vector).
FMINV: Floating-point minimum across vector.
FMLA (by element): Floating-point fused multiply-add to accumulator (by element).
FMLA (vector): Floating-point fused multiply-add to accumulator (vector).
FMLAL, FMLAL2 (by element): Floating-point fused multiply-add long to accumulator (by element).
FMLAL, FMLAL2 (vector): Floating-point fused multiply-add long to accumulator (vector).
FMLALB, FMLALT (by element): 8-bit floating-point multiply-add long to half-precision (vector, by element).
FMLALB, FMLALT (vector): 8-bit floating-point multiply-add long to half-precision (vector).
FMLALLBB, FMLALLBT, FMLALLTB, FMLALLTT (by element): 8-bit floating-point multiply-add long-long to single-precision (vector, by element).
FMLALLBB, FMLALLBT, FMLALLTB, FMLALLTT (vector): 8-bit floating-point multiply-add long-long to single-precision (vector).
FMLS (by element): Floating-point fused multiply-subtract from accumulator (by element).
FMLS (vector): Floating-point fused multiply-subtract from accumulator (vector).
FMLSL, FMLSL2 (by element): Floating-point fused multiply-subtract long from accumulator (by element).
FMLSL, FMLSL2 (vector): Floating-point fused multiply-subtract long from accumulator (vector).
FMOV (general): Floating-point move to or from general-purpose register without conversion.
FMOV (register): Floating-point move register without conversion.
FMOV (scalar, immediate): Floating-point move immediate (scalar).
FMOV (vector, immediate): Floating-point move immediate (vector).
FMSUB: Floating-point fused multiply-subtract (scalar).
FMUL (by element): Floating-point multiply (by element).
FMUL (scalar): Floating-point multiply (scalar).
FMUL (vector): Floating-point multiply (vector).
FMULX: Floating-point multiply extended.
FMULX (by element): Floating-point multiply extended (by element).
FNEG (scalar): Floating-point negate (scalar).
FNEG (vector): Floating-point negate (vector).
FNMADD: Floating-point negated fused multiply-add (scalar).
FNMSUB: Floating-point negated fused multiply-subtract (scalar).
FNMUL (scalar): Floating-point multiply-negate (scalar).
FRECPE: Floating-point reciprocal estimate.
FRECPS: Floating-point reciprocal step.
FRECPX: Floating-point reciprocal exponent (scalar).
FRINT32X (scalar): Floating-point round to 32-bit integer, using current rounding mode (scalar).
FRINT32X (vector): Floating-point round to 32-bit integer, using current rounding mode (vector).
FRINT32Z (scalar): Floating-point round to 32-bit integer toward zero (scalar).
FRINT32Z (vector): Floating-point round to 32-bit integer toward zero (vector).
FRINT64X (scalar): Floating-point round to 64-bit integer, using current rounding mode (scalar).
FRINT64X (vector): Floating-point round to 64-bit integer, using current rounding mode (vector).
FRINT64Z (scalar): Floating-point round to 64-bit integer toward zero (scalar).
FRINT64Z (vector): Floating-point round to 64-bit integer toward zero (vector).
FRINTA (scalar): Floating-point round to integral, to nearest with ties to away (scalar).
FRINTA (vector): Floating-point round to integral, to nearest with ties to away (vector).
FRINTI (scalar): Floating-point round to integral, using current rounding mode (scalar).
FRINTI (vector): Floating-point round to integral, using current rounding mode (vector).
FRINTM (scalar): Floating-point round to integral, toward minus infinity (scalar).
FRINTM (vector): Floating-point round to integral, toward minus infinity (vector).
FRINTN (scalar): Floating-point round to integral, to nearest with ties to even (scalar).
FRINTN (vector): Floating-point round to integral, to nearest with ties to even (vector).
FRINTP (scalar): Floating-point round to integral, toward plus infinity (scalar).
FRINTP (vector): Floating-point round to integral, toward plus infinity (vector).
FRINTX (scalar): Floating-point round to integral exact, using current rounding mode (scalar).
FRINTX (vector): Floating-point round to integral exact, using current rounding mode (vector).
FRINTZ (scalar): Floating-point round to integral, toward zero (scalar).
FRINTZ (vector): Floating-point round to integral, toward zero (vector).
FRSQRTE: Floating-point reciprocal square root estimate.
FRSQRTS: Floating-point reciprocal square root step.
FSCALE: Floating-point adjust exponent by vector.
FSQRT (scalar): Floating-point square root (scalar).
FSQRT (vector): Floating-point square root (vector).
FSUB (scalar): Floating-point subtract (scalar).
FSUB (vector): Floating-point subtract (vector).
INS (element): Insert vector element from another vector element.
INS (general): Insert vector element from general-purpose register.
LD1 (multiple structures): Load multiple single-element structures to one, two, three, or four registers.
LD1 (single structure): Load one single-element structure to one lane of one register.
LD1R: Load one single-element structure and replicate to all lanes (of one register).
LD2 (multiple structures): Load multiple 2-element structures to two registers.
LD2 (single structure): Load single 2-element structure to one lane of two registers.
LD2R: Load single 2-element structure and replicate to all lanes of two registers.
LD3 (multiple structures): Load multiple 3-element structures to three registers.
LD3 (single structure): Load single 3-element structure to one lane of three registers.
LD3R: Load single 3-element structure and replicate to all lanes of three registers.
LD4 (multiple structures): Load multiple 4-element structures to four registers.
LD4 (single structure): Load single 4-element structure to one lane of four registers.
LD4R: Load single 4-element structure and replicate to all lanes of four registers.
LDAP1 (SIMD&FP): Load-acquire RCpc one single-element structure to one lane of one register.
LDAPUR (SIMD&FP): Load-acquire RCpc SIMD&FP register (unscaled offset).
LDNP (SIMD&FP): Load pair of SIMD&FP registers, with non-temporal hint.
LDP (SIMD&FP): Load pair of SIMD&FP registers.
LDR (immediate, SIMD&FP): Load SIMD&FP register (immediate offset).
LDR (literal, SIMD&FP): Load SIMD&FP register (PC-relative literal).
LDR (register, SIMD&FP): Load SIMD&FP register (register offset).
LDUR (SIMD&FP): Load SIMD&FP register (unscaled offset).
LUTI2: Lookup table read with 2-bit indices.
LUTI4: Lookup table read with 4-bit indices.
MLA (by element): Multiply-add to accumulator (vector, by element).
MLA (vector): Multiply-add to accumulator (vector).
MLS (by element): Multiply-subtract from accumulator (vector, by element).
MLS (vector): Multiply-subtract from accumulator (vector).
MOV (element): Move vector element to another vector element: an alias of INS (element).
MOV (from general): Move general-purpose register to a vector element: an alias of INS (general).
MOV (scalar): Move vector element to scalar: an alias of DUP (element).
MOV (to general): Move vector element to general-purpose register: an alias of UMOV.
MOV (vector): Move vector: an alias of ORR (vector, register).
MOVI: Move immediate (vector).
MUL (by element): Multiply (vector, by element).
MUL (vector): Multiply (vector).
MVN: Bitwise NOT (vector): an alias of NOT.
MVNI: Move inverted immediate (vector).
NEG (vector): Negate (vector).
NOT: Bitwise NOT (vector).
ORN (vector): Bitwise inclusive OR NOT (vector).
ORR (vector, immediate): Bitwise inclusive OR (vector, immediate).
ORR (vector, register): Bitwise inclusive OR (vector, register).
PMUL: Polynomial multiply.
PMULL, PMULL2: Polynomial multiply long.
RADDHN, RADDHN2: Rounding add returning high narrow.
RAX1: Rotate and exclusive-OR.
RBIT (vector): Reverse bit order (vector).
REV16 (vector): Reverse elements in 16-bit halfwords (vector).
REV32 (vector): Reverse elements in 32-bit words (vector).
REV64: Reverse elements in 64-bit doublewords (vector).
RSHRN, RSHRN2: Rounding shift right narrow (immediate).
RSUBHN, RSUBHN2: Rounding subtract returning high narrow.
SABA: Signed absolute difference and accumulate.
SABAL, SABAL2: Signed absolute difference and accumulate long.
SABD: Signed absolute difference.
SABDL, SABDL2: Signed absolute difference long.
SADALP: Signed add and accumulate long pairwise.
SADDL, SADDL2: Signed add long (vector).
SADDLP: Signed add long pairwise.
SADDLV: Signed add long across vector.
SADDW, SADDW2: Signed add wide.
SCVTF (scalar, fixed-point): Signed fixed-point convert to floating-point (scalar).
SCVTF (scalar, integer): Signed integer convert to floating-point (scalar).
SCVTF (vector, fixed-point): Signed fixed-point convert to floating-point (vector).
SCVTF (vector, integer): Signed integer convert to floating-point (vector).
SDOT (by element): Dot product signed arithmetic (vector, by element).
SDOT (vector): Dot product signed arithmetic (vector).
SHA1C: SHA1 hash update (choose).
SHA1H: SHA1 fixed rotate.
SHA1M: SHA1 hash update (majority).
SHA1P: SHA1 hash update (parity).
SHA1SU0: SHA1 schedule update 0.
SHA1SU1: SHA1 schedule update 1.
SHA256H: SHA256 hash update (part 1).
SHA256H2: SHA256 hash update (part 2).
SHA256SU0: SHA256 schedule update 0.
SHA256SU1: SHA256 schedule update 1.
SHA512H: SHA512 hash update part 1.
SHA512H2: SHA512 hash update part 2.
SHA512SU0: SHA512 schedule update 0.
SHA512SU1: SHA512 schedule update 1.
SHADD: Signed halving add.
SHL: Shift left (immediate).
SHLL, SHLL2: Shift left long (by element size).
SHRN, SHRN2: Shift right narrow (immediate).
SHSUB: Signed halving subtract.
SLI: Shift left and insert (immediate).
SM3PARTW1: SM3PARTW1.
SM3PARTW2: SM3PARTW2.
SM3SS1: SM3SS1.
SM3TT1A: SM3TT1A.
SM3TT1B: SM3TT1B.
SM3TT2A: SM3TT2A.
SM3TT2B: SM3TT2B.
SM4E: SM4 encode.
SM4EKEY: SM4 key.
SMAX: Signed maximum (vector).
SMAXP: Signed maximum pairwise.
SMAXV: Signed maximum across vector.
SMIN: Signed minimum (vector).
SMINP: Signed minimum pairwise.
SMINV: Signed minimum across vector.
SMLAL, SMLAL2 (by element): Signed multiply-add long (vector, by element).
SMLAL, SMLAL2 (vector): Signed multiply-add long (vector).
SMLSL, SMLSL2 (by element): Signed multiply-subtract long (vector, by element).
SMLSL, SMLSL2 (vector): Signed multiply-subtract long (vector).
SMMLA (vector): Signed 8-bit integer matrix multiply-accumulate (vector).
SMOV: Signed move vector element to general-purpose register.
SMULL, SMULL2 (by element): Signed multiply long (vector, by element).
SMULL, SMULL2 (vector): Signed multiply long (vector).
SQABS: Signed saturating absolute value.
SQADD: Signed saturating add.
SQDMLAL, SQDMLAL2 (by element): Signed saturating doubling multiply-add long (by element).
SQDMLAL, SQDMLAL2 (vector): Signed saturating doubling multiply-add long.
SQDMLSL, SQDMLSL2 (by element): Signed saturating doubling multiply-subtract long (by element).
SQDMLSL, SQDMLSL2 (vector): Signed saturating doubling multiply-subtract long.
SQDMULH (by element): Signed saturating doubling multiply returning high half (by element).
SQDMULH (vector): Signed saturating doubling multiply returning high half.
SQDMULL, SQDMULL2 (by element): Signed saturating doubling multiply long (by element).
SQDMULL, SQDMULL2 (vector): Signed saturating doubling multiply long.
SQNEG: Signed saturating negate.
SQRDMLAH (by element): Signed saturating rounding doubling multiply accumulate returning high half (by element).
SQRDMLAH (vector): Signed saturating rounding doubling multiply accumulate returning high half (vector).
SQRDMLSH (by element): Signed saturating rounding doubling multiply subtract returning high half (by element).
SQRDMLSH (vector): Signed saturating rounding doubling multiply subtract returning high half (vector).
SQRDMULH (by element): Signed saturating rounding doubling multiply returning high half (by element).
SQRDMULH (vector): Signed saturating rounding doubling multiply returning high half.
SQRSHL: Signed saturating rounding shift left (register).
SQRSHRN, SQRSHRN2: Signed saturating rounded shift right narrow (immediate).
SQRSHRUN, SQRSHRUN2: Signed saturating rounded shift right unsigned narrow (immediate).
SQSHL (immediate): Signed saturating shift left (immediate).
SQSHL (register): Signed saturating shift left (register).
SQSHLU: Signed saturating shift left unsigned (immediate).
SQSHRN, SQSHRN2: Signed saturating shift right narrow (immediate).
SQSHRUN, SQSHRUN2: Signed saturating shift right unsigned narrow (immediate).
SQSUB: Signed saturating subtract.
SQXTN, SQXTN2: Signed saturating extract narrow.
SQXTUN, SQXTUN2: Signed saturating extract unsigned narrow.
SRHADD: Signed rounding halving add.
SRI: Shift right and insert (immediate).
SRSHL: Signed rounding shift left (register).
SRSHR: Signed rounding shift right (immediate).
SRSRA: Signed rounding shift right and accumulate (immediate).
SSHL: Signed shift left (register).
SSHLL, SSHLL2: Signed shift left long (immediate).
SSHR: Signed shift right (immediate).
SSRA: Signed shift right and accumulate (immediate).
SSUBL, SSUBL2: Signed subtract long.
SSUBW, SSUBW2: Signed subtract wide.
ST1 (multiple structures): Store multiple single-element structures from one, two, three, or four registers.
ST1 (single structure): Store a single-element structure from one lane of one register.
ST2 (multiple structures): Store multiple 2-element structures from two registers.
ST2 (single structure): Store single 2-element structure from one lane of two registers.
ST3 (multiple structures): Store multiple 3-element structures from three registers.
ST3 (single structure): Store single 3-element structure from one lane of three registers.
ST4 (multiple structures): Store multiple 4-element structures from four registers.
ST4 (single structure): Store single 4-element structure from one lane of four registers.
STL1 (SIMD&FP): Store-release a single-element structure from one lane of one register.
STLUR (SIMD&FP): Store-release SIMD&FP register (unscaled offset).
STNP (SIMD&FP): Store pair of SIMD&FP registers, with non-temporal hint.
STP (SIMD&FP): Store pair of SIMD&FP registers.
STR (immediate, SIMD&FP): Store SIMD&FP register (immediate offset).
STR (register, SIMD&FP): Store SIMD&FP register (register offset).
STUR (SIMD&FP): Store SIMD&FP register (unscaled offset).
SUB (vector): Subtract (vector).
SUBHN, SUBHN2: Subtract returning high narrow.
SUDOT (by element): Dot product with signed and unsigned integers (vector, by element).
SUQADD: Signed saturating accumulate of unsigned value.
SXTL, SXTL2: Signed extend long: an alias of SSHLL, SSHLL2.
TBL: Table vector lookup.
TBX: Table vector lookup extension.
TRN1: Transpose vectors (primary).
TRN2: Transpose vectors (secondary).
UABA: Unsigned absolute difference and accumulate.
UABAL, UABAL2: Unsigned absolute difference and accumulate long.
UABD: Unsigned absolute difference (vector).
UABDL, UABDL2: Unsigned absolute difference long.
UADALP: Unsigned add and accumulate long pairwise.
UADDL, UADDL2: Unsigned add long (vector).
UADDLP: Unsigned add long pairwise.
UADDLV: Unsigned sum long across vector.
UADDW, UADDW2: Unsigned add wide.
UCVTF (scalar, fixed-point): Unsigned fixed-point convert to floating-point (scalar).
UCVTF (scalar, integer): Unsigned integer convert to floating-point (scalar).
UCVTF (vector, fixed-point): Unsigned fixed-point convert to floating-point (vector).
UCVTF (vector, integer): Unsigned integer convert to floating-point (vector).
UDOT (by element): Dot product unsigned arithmetic (vector, by element).
UDOT (vector): Dot product unsigned arithmetic (vector).
UHADD: Unsigned halving add.
UHSUB: Unsigned halving subtract.
UMAX: Unsigned maximum (vector).
UMAXP: Unsigned maximum pairwise.
UMAXV: Unsigned maximum across vector.
UMIN: Unsigned minimum (vector).
UMINP: Unsigned minimum pairwise.
UMINV: Unsigned minimum across vector.
UMLAL, UMLAL2 (by element): Unsigned multiply-add long (vector, by element).
UMLAL, UMLAL2 (vector): Unsigned multiply-add long (vector).
UMLSL, UMLSL2 (by element): Unsigned multiply-subtract long (vector, by element).
UMLSL, UMLSL2 (vector): Unsigned multiply-subtract long (vector).
UMMLA (vector): Unsigned 8-bit integer matrix multiply-accumulate (vector).
UMOV: Unsigned move vector element to general-purpose register.
UMULL, UMULL2 (by element): Unsigned multiply long (vector, by element).
UMULL, UMULL2 (vector): Unsigned multiply long (vector).
UQADD: Unsigned saturating add.
UQRSHL: Unsigned saturating rounding shift left (register).
UQRSHRN, UQRSHRN2: Unsigned saturating rounded shift right narrow (immediate).
UQSHL (immediate): Unsigned saturating shift left (immediate).
UQSHL (register): Unsigned saturating shift left (register).
UQSHRN, UQSHRN2: Unsigned saturating shift right narrow (immediate).
UQSUB: Unsigned saturating subtract.
UQXTN, UQXTN2: Unsigned saturating extract narrow.
URECPE: Unsigned reciprocal estimate.
URHADD: Unsigned rounding halving add.
URSHL: Unsigned rounding shift left (register).
URSHR: Unsigned rounding shift right (immediate).
URSQRTE: Unsigned reciprocal square root estimate.
URSRA: Unsigned rounding shift right and accumulate (immediate).
USDOT (by element): Dot product with unsigned and signed integers (vector, by element).
USDOT (vector): Dot product with unsigned and signed integers (vector).
USHL: Unsigned shift left (register).
USHLL, USHLL2: Unsigned shift left long (immediate).
USHR: Unsigned shift right (immediate).
USMMLA (vector): Unsigned and signed 8-bit integer matrix multiply-accumulate (vector).
USQADD: Unsigned saturating accumulate of signed value.
USRA: Unsigned shift right and accumulate (immediate).
USUBL, USUBL2: Unsigned subtract long.
USUBW, USUBW2: Unsigned subtract wide.
UXTL, UXTL2: Unsigned extend long: an alias of USHLL, USHLL2.
UZP1: Unzip vectors (primary).
UZP2: Unzip vectors (secondary).
XAR: Exclusive-OR and rotate.
XTN, XTN2: Extract narrow.
ZIP1: Zip vectors (primary).
ZIP2: Zip vectors (secondary).
```
