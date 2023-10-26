# W6D1笔记 ——Caches

## 为何要引入缓存cache?

* CPU的性能增长速度大于Memory，CPU($\mu Proc$)的处理速度远大于Memory($DRAM$)；
* 引入cache可以让memory访问数据的速度适应CPU的处理速度，提高整体性能；
* 数据访问具有很强的空间本地性与时间本地性(locality)，使用cache可以降低对内存的重复访问，提升性能。

## 什么是cache?

* 用于降低平均内存访问时间的结构，通常用SRAM技术实现，相对较小且处理快速；
* cache的有效性是基于数据访问的空间本地性与时间本地性(locality)的；
* 更广义来看，在体系结构的多层结构中，上一级都可以看作下一级的cache。如可以视寄存器是变量的cache，内存是外存的cache，等。

## 插入——关于Harvard结构
Harvard结构: 指令存储和数据存储分离
Von Neumann结构： 指令存储和数据存储共用
![](https://notes.sjtu.edu.cn/uploads/upload_7a69c94b0e84d738bb58c24f60acd3e3.png)


由于每条指令所需的平均时间
$$CPU_{time}=InstrCycle\times(\frac{ALU_{ops}}{Instr}\cdot CPI+\frac{Mem_{ops}}{Instr}\cdot ASMT)\times CycleTime$$

而若用Von Neumann结构设置cache，那么由于每条指令都需要访问cache，故若指令还需要访问数据，就会造成structure hazard；但是若用Harvard结构设置cache，那么虽然cache容量减少（分成instr-cache和data-cache），miss率增大，但是不会有structure hazard，所以很多时候用Harvard结构设置cache，综合效果比Von Neumann结构好。


## 如何提升cache的性能？

由于平均内存访问时间
$$AMAT_$=T_{hit}+\eta_{miss-rate}\times T_{penalty}$$
故提升cache性能，主要有三个方向：
* 降低命中时间$T_{hit}$
* 降低未命中率$\eta_{miss-rate}$
* 降低未命中处理时间$T_{penalty}$

本节课主要讨论如何降低未命中率$\eta_{miss-rate}$。

## cache未命中的原因

cache未命中的原因主要有：
* **强制性失效（compulsory）**:首次访问时，cache中没有对应的内容，亦称冷启动失效/首次访问失效；
* **容量失效（capacity）**：cache的容量有限，如果程序执行时所需的内容不能全部存入 Cache 中，则当某些块被替换后，若又重新被访问，就会发生失效；
* **冲突失效（conflict miss）**：若太多的块映像到cache的同一位置中，则会出现该位置上内容被别的块替换、然后又被重新访问的情况；
* **相干性失效（coherence）**：多核CPU中，如果一个核改变了内存的内容，为保证数据正确性，其他核的cache的相应内容会失效，防止不一致数据的出现。

一些解决方案：
* 预热，减少compulsory miss
* **一定程度上**，增大cache容量，减少capacity miss
* **一定程度上**，增加cache的关联路数，减少conflict miss

![](https://notes.sjtu.edu.cn/uploads/upload_f5810f4f49e580777ae452206223e332.png)

从图中可以看出，不论是增大容量还是增大关联路数，其对cache的miss率减少作用都是有限的，并不是无限增加便是最好的。
