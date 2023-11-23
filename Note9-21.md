## Sept. 21

### 如何设计控制器（解析opcode并向几乎所有地方发送指令）

（1）Vertical：靠对指令的一系列逻辑处理来理解。

（2）Horizonal：直接事先存好的表中查找。

（3）Micro-programming：在CPU中放置一段程序，让这段程序自己去处理。 

### Datapath

分为 single-cycle,multi-cycle,pipeline。其中pipeline需要在流程中添加stage以同步指令执行“节奏”，实现流水。

### Harzard（各种阻碍流水线流动的原因和现象）

（1）Structural Harzard：多个指令挤占同一条道（解决方式：拷贝）

（2）Data Harzard：指令由于存在数据依赖不能继续执行，需等待其它指令的数据。

（3）Control Harzard：控制指令导致的任何Harzard（如分支预测就是为了解决条件跳转指令需等待cond数据的Harzard而设计的）

### 耗能问题

早期计算机非常容易发热，因而格外注重程序的耗能情况，其架构的设计使得一些元件可以在不使用时关机以减小散热。“完成程序所需要的能量”是一个很重要的指标。现在，内存和CPU运算仍各占计算机耗能的1/3。
