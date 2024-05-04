# TASK 4
SPIKE Simulation and observation with -O1 and -Ofast

## SPIKE
It exhibits following features

* RISC-V ISA Support: Spike accurately models the RISC-V Instruction Set Architecture (ISA), covering all user-level and privileged instructions defined in the RISC-V specification.
* Privileged Architecture: It fully supports the RISC-V privileged architecture, enabling simulation of supervisor and machine-level code execution. This allows for running operating systems and low-level software.
* Modes of Operation: Spike supports multiple modes of operation, including user mode for application execution and kernel mode for system-level software. It accurately simulates context switching and privilege level transitions.
* Debugging Features: Spike provides a range of debugging capabilities such as breakpoints, single-stepping, register inspection, and memory examination. These tools are essential for debugging RISC-V programs and understanding their behavior.
* Performance Analysis: It includes performance monitoring counters to analyze the execution behavior of RISC-V code. This feature helps developers optimize their programs for better performance.
* Configurability: Spike is highly configurable, allowing users to customize parameters like the number of processor cores, memory size, and boot options. This flexibility makes it adaptable to various use cases and experimental setups.
* Open Source: Spike is an open-source project released under the BSD license. Its source code is freely available, encouraging collaboration and contributions from the community.


### SPIKE SIMULATION WITH O1

Here we will use spike RISCV ISA Simulator to rum the object file of RISCV

##### Our C program output should be equal to output generated from spike simulator

Here is the below code to do that

```
   gcc sum1ton.c
   ./a.out
   riscv64-unknown-elf-gcc O1 -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
   spike pk sum1ton.o
   spike -d pk sum1ton.o
   ```
##### O1->Optimization Level 1

<img src="https://github.com/Rajveer-1234/vsdsquadron_mini_intership/blob/main/riscv64spike01.png?raw=true">/

<img src="https://github.com/Rajveer-1234/vsdsquadron_mini_intership/blob/main/riscv64%20O1%20main.png?raw=true">/

### SPIKE SIMULATION WITH Ofast

Here is below code to do that

  ```
   gcc sum1ton.c
   ./a.out
   riscv64-unknown-elf-gcc Ofast -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
   spike pk sum1ton.o
   spike -d pk sum1ton.o
   ```

##### Ofast -> Highest Optimization Level

<img src="https://github.com/Rajveer-1234/vsdsquadron_mini_intership/blob/main/riscv64spikeOfast.png?raw=true">/

<img src="https://github.com/Rajveer-1234/vsdsquadron_mini_intership/blob/main/Ofastmain.png?raw=true">/

#### Major Difference between both the optimization levels are

* In the RISC-V GNU toolchain, `-Ofast` and `-O1` are optimization flags. 

* `-Ofast` aggressively optimizes code by enabling all optimization flags.

* `-O1` enables basic optimizations to improve code execution speed.

`-Ofast` aims for maximum performance, potentially at the expense of precision, while `-O1` focuses on moderate optimization without compromising code integrity.
