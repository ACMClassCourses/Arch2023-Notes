## RISC 与 CISC 的比较
### CISC：复杂指令集(Complex InstrucTIon Set Computer)
类似文言文。单条指令复杂，表达同样语义用复杂指令集使程序简短

### RISC：精简指令集(Reduced InstrucTIon Set Computer)
类似白话文。单条指令简单，但程序冗长

## RISC 的特点

- 32位固定格式指令
- 内存访问只通过 load/store 指令
- 32个32位通用寄存器
- 寄存器或立即数间进行算数运算指令
- load/store 简单的寻址模式：base + displacement
- 简单分支条件
- 分支延迟

## 冯·诺伊曼机器三类指令

1.Arith/Logic(ALU)：进行数据计算
2.Data Transform：内存，寄存器等间数据的转移
3.Control：JMP，CALL，RET等，改变指令执行的顺序