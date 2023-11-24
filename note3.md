# Notes on W11D2
## Static Pipelining
Q: How to deal with hazards, which include Structural Hazard, Data Hazard (RAW, WAR, WAW) and Control Hazard?

A: (1) Dynamic (Tomasulo)  (2) Static (via compiler)

### 1. Code Movement
Different kinds of instructions have different cost on execution and latency. 
By properly move some codes, we may reduce CPU stalls and harzards. For example, we can introduce **delayed branch**.

### 2. Loop Unrolling
Unrolling the loop, especially "for" loop, is one of the most common ways to optimize the code and can improve **Loop Level Parallelism (LLP)**. It has both pros and cons.

For benefits:
 - reduce the number of operations required to complete the loop
 - reduce number of test-and-branch sequences. 
 - create reuse within the loop body, reducing memory traffic 
 - possibly eliminate cyclic chain of copy operations

For drawbacks：
- increase program size
- increase compile time
- possible data dependency may cause hazard

To deal with so-called **name dependency**, we can use **register renaming**, which can be done during SSA trasformation.

### 3. Software Pipeline
Software Pipeline reorganizes loops so that each iteration is made from instructions chosen from different iterations of the original loop.
If iterations from loops are **independent**, then can get more ILP by taking instructions from different iterations.
It's just like Tomasulo in SW.

According to wiki, Effective compiler generation of such code dates to the invention of **modulo scheduling** by Rau and Glaeser.

Pay attention to **loop-carried dependence**.
It may make loop unrolling and software pipeline unsafe.