#### Memory banks

Memory banks partition the whole memory into independent banks to support parallel access.

Bank conflict: accessing the same bank(s) (leading to sequential access).

To avoid bank conflict: use $p$ banks ( $p$ is prime), each having $m$ entries.

Problem: to find out which bank to access, division by $m$ is slow.

Optimization: let bank number $u=\lfloor \frac d {m+1} \rfloor$, where $m=2^l-1$. This strategy leaves holes (memory not used fully).

Optimization 2: $u=d \mod 2^k$, $v=d \mod m$, where $m=2^l-1$. This only involves bit operations.

To avoid conflicting addressing, the number of banks should be no more than the number of clock cycles of accessing a word in a bank.

#### Error correction

The most common way: introduce redundancy through parity bits, e.g. Hamming code.