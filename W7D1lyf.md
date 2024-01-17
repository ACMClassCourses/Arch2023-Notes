# Reduce the Miss Rate

## 访问顺序与空间顺序一致降低 miss rate

### 例子

1. `val` 和 `key` 放在一个结构体里而不是开两个数组。

2. 改变循环顺序遍历二维数组。

3. 矩阵乘法优化。

# Reduce the Miss Penalty

## 二级 Cache

不能直接扩大一级 Cache（影响效率）。

## Read Priority over Write on Miss

利用 Write Buffer 放要写到内存的数据。

## Early Restart and Critical Word First