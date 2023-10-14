# Arch W3D2 Note

**Arthor: [DarkSharpness](https://github.com/DarkSharpness)**

## Performance

### Definition

Performance is tasks over time (tasks per day, hour, minute, second......).

Simple metric: $\text{performance}(x) = \dfrac{1}{\text{execution} \_ \text{time} (x)}$

### Aspects of CPU performance

$$
\text{CPU time} = \dfrac{\text{Seconds}}{\text{Program}} = \dfrac{\text{Instructions}}{\text{Program}} \times \dfrac{\text{Cycles}}{\text{Instructions}} \times \dfrac{\text{Seconds}}{\text{Cycles}}
$$

Three key factors:

- Inst count
- CPI (Clock per inst)
- Clock rate.

|              | Inst Count |     CPI     | Clock Rate  |
| :----------: | :---------: | :---------: | :-------: |
|   Program   | $\sqrt{}$ |            |             |
|   Compiler   | $\sqrt{}$ | $\sqrt{}$ |             |
|   Inst.Set   | $\sqrt{}$ | $\sqrt{}$ |             |
| Organization |            | $\sqrt{}$ | $\sqrt{}$ |
|  Technology  |            |            | $\sqrt{}$ |

- Program : Reduce inst count (not code length!)
- Compiler: Optimize to reduce inst count, reduce stall by code movement.
- Inst.Set.: CISC has a larger inst.set. Consequently, its inst count will surely be smaller thanm RISC. However, RISC commands may be better tailored for pipeline.
- Organization: Increase operation speed and use simple design to allow a higher clock rate.
- Technology: Improve the clock rate (Moore's law)

Harvard architecture vs. von Neumann architecture:

- Harvard architecture has separate storage and signal pathways for instructions and data, while von Neumann architecture shares storage and signal pathways between instructions and data.
- Harvard architecture does not have structural hazards in pipelining, because instructions and data are stored separately.

## Memory Hierarchy

Register, cache, memory, disk, tape.

The Principle of Locality:
- temporal locality
- spatial locality 

### Cache

Accessing register is much faster than memory, so we need cache to bridge that gap.

- Direct mapped cache : mapping one memory address to one cache index. 
- Two-way Set Associative Cache: $N$ direct mapped caches operates in parallel ($N$ typically $2 \sim 4$ . In this case $N = 2$ )

