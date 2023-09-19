## RISC 为什么与SISC相比对于编译器的发展更有利？

- RISC指令的长度相等，利于解码
- RISC指令功能比较单一（”原子化“），使得指令之间的依赖关系更少，利于流水线并行处理，提高程序执行效率。典型的例子就是只允许内存相关的操作只出现在load/store操作中。
- 更好的兼容性与可移植性

## RISC的几个特点

- 定长
- 严格限制内存操作只能出现在load/stroe指令中
- 指令中寄存器的位置相对固定
- 寻址模式是单一的：base+displacement
- 指令原子化：典型的例子有simple branch condition
- 反对过度设计（overDesign）：如果可以用现有的指令组合成新的指令，则不设计新的指令

## 冯诺依曼机器

- ALU: `$ADD \quad R_3, R_1, R_2$`
- Data transform: `$LD \quad R_5, 100(R_4)$`
- Control: `$JALR \quad 100(R_3)$`

## 从冯诺依曼机器理解slides中的MIPS Datapath