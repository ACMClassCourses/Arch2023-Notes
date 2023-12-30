## 如何降低miss penalty

### 1:Read priority over write on miss

添加一个write buffer

将数据先写入到write buffer中，后续读时优先在write buffer中查找

用于应对写操作时的cache miss

### 2:Early restart and critical word first

提前重启动：只要块中被请求的字到达缓存就立刻发给CPU

关键字优先：从内存中请求并立刻向CPU传缺失的字（关键字），在CPU执行时再补充块中的其他字

### 3:Non-blocking caches to reduce stalls on misses

非阻塞式缓存可以做到：

hit under miss——允许在发生cache miss时继续提供cache hit

miss under miss——允许多个cache miss互相重叠从而降低整体的miss penalty

### 4:Add a second-level cache

$AMAT = HitTime_1 + Miss Rate_1 * (Hit Time_2 + Miss Rate_2 * Miss Penalty_2)$

Local miss rate: 本地cache miss的次数/对本地的访问请求数

Global miss rate: 内存访问数/处理器的访问请求数

