# Notes on Sep. 21st

1.  Q: How to design control unit?

    A: Hardwired or Micro-programming in the style of *Vertical*, *Horizonal*, or *Hybrid*.
    
    | Horizonal | Vertical |
    | :---: | :---: |
    | $n$ control signals require $n$ bit encoding. | $n$ control signals require $\log_2n$ bit encoding.|
    | longer control words | shorter control words |
    | allows a higher degree of parallelism | allows a low degree of parallelism |
    | faster | lower |
    | uses horizontal micro-instruction, where every bit in the control field attaches to a control line. | uses vertical micro-instruction, where a code is used for each action and the decoder translates this code into individual control signals. |

2. Most programmers view the computer architeture 'top-down', but system engineers do so 'bottom-up'.

3. Datapath can work in single-cycle, multi-cycle or pipeline. Note the difference between *instruction cycle* and *machine cycle*. Pipeline needs data stationary control for each stage.
    
4. Great algorithms in CS often come from daily life, such as hash table and shortest path.

5. Limits to pipeline: 3 kinds of **harzards**:
    - Structural hazards: hardware cannot support this combination of instructions
    - Data hazards: Instruction depends on result of prior instruction still in the pipeline
    - Control hazards: Caused by delay between the fetching of instructions and decisions about changes in control flow. Delayed branch is designed to deal with it.

6. Signed-extend is used to prevent errors caused by direct extending negative number.

7. Multiple read-write to register file can be achieved by ping-pong buffers.
