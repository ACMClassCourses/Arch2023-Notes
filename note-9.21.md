### 如何设计控制器

Vertical：通过一定的逻辑来处理指令并输出控制信号

Horizonal：对于所有可能的opcode输入保存对应的输出控制信号

Micro-programming：一个用微码编写的代码库，处理指令时直接调用

Hybrid：以上三种方式的混合

### 对于Datapath的处理

可以分为Single-cycle，Multi-cycle和Pipeline等方式

对于后两者，Instruction cycle被细分为更多machine cycle

其中Multi-cycle方法在一个machine cycle中只运行一个部件，而Pipeline方法则允许不同的指令同时运行多个部件

### 关于流水线中的Hazard

Structural Hazard：多个指令占用同一条道路

Data Hazard：不同指令之间存在数据依赖导致后续指令无法执行

Control Hazard：由于等待控制指令导致后续指令无法执行