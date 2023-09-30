We measure the performance of a computer by its response time.

A program's CPU time is mainly determined by three factors: instruction count, cycles per instruction (CPI), clock rate.

Average CPI equals the sum of the product of each instruction's number of cycles and its frequency.

SISC has a smaller instruction count than RISC, but its CPI is greater.

Harvard architecture vs. von Neumann architecture:

​	Harvard architecture has separate storage and signal pathways for instructions and data, while von Neumann architecture shares storage and signal pathways between instructions and data.

Harvard architecture does not have structural hazards in pipelining, because instructions and data are stored separately.



Memory hierarchy: register, cache, memory, disk, tape

Cache strategies:

1. Direct Mapped Cache: maps one memory address to one cache index.
2. Two-way Set Associative Cache: maps one memory address to two cache indices (see https://zhuanlan.zhihu.com/p/432709015).