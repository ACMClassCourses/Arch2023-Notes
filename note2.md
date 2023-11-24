# Notes on W7D2
## Reducing Miss Penalty
### 1. Read Priority over Write on Miss (review)
- Key data structure: **Write Buffer**
- Check write buffer contents before read
- When read miss, copy the block to the write buffer, then do the read
- Reduce CPU Stall

### 2. Early Restart and Critical Word First
- About "word" in arch:  
int (in C) = word = max wideh / per instr (i.e. reg. width) ≈ width of M-addr/M-data
- **Early Restart**: As soon as the requested word of the block arrives, send it to the CPU and let the CPU continue execution
- **Critical Word First**: Request the missed word first from memory and send it to the CPU as soon as it arrives; let the CPU continue execution while filling the rest of the words in the block.
- Notice that these only benefit designs with **large cache blocks**.

### 3. Non-blocking Caches to reduce stalls on misses
- Non-blocking cache allow **"hit under miss"**, i.e. allow data cache to continue to supply cache hits during a miss.
- Rambus once designed a CPU in which different parts communicate in a "networking" way without Common Data Bus.

### 4. Add a second-level cache
- About **North Bridge** and **South Bridge**:
![North Bridge & South Bridge](pictures/NB%26SB.jpg)
- **Local** miss rate: miss of **certain unit** / total access to **certain unit**.
- **Global** miss rate: access to main memory (i.e. miss of **memory hierarchy**) / total access by processor.
- L2 design: Inclusive (intel) vs Exclusive (AMD):
$$
\text{Inclusive}: \forall x \in L_1, x \in L_2 \\
\text{Exclusive}: \forall x \in L_1, x \notin L_2 
$$

## Reducing hit time
- Direct mapping instead of multi-way set associative
- Make L1 cache **small** 