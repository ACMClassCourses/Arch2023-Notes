# Computer Architecture Note W7D1

## Reduce the Miss Rate

### How can we reduce misses?

1. change Block Size

2. change Associativity

3. **change Compiler**

### Reducing misses by compiler optimizations 

1. merging arrays

   e.g. 把key和value放在结构体里再一起开数组，而不是开两个数组

2. loop interchange

   e.g. 改变遍历二维数组的循环顺序

3. blocking

   e.g. 分块计算矩阵乘法

## Reduce the Miss Penalty

### L2 Cache

Q: Why not increase L1 Cache directly?

A: Larger capacity would lead to lower hit speed. 

### Write Policy

- Write-through

  update cache and underlying memory/cache

- Write-back

  simply update cache, another *dirty* control bit

### Read Priority over Write on Miss

Using **Write Buffer** for both write-through and write-back.

Special case: *Read miss replacing dirty block (write-back)*

- Copy the dirty block to a write buffer, then do the read and write parallel

### Early Restart and Critical Word First

Generally useful only in large blocks.