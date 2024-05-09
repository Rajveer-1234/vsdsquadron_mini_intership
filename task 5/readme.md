# OVERVIEW OF RISC-V ARCHITECTURE
## Discussing about RV32I
RV32I is a base integer instruction set architecture (ISA) in the RISC-V (pronounced "RISC Five") instruction set architecture.

1. **RV32I**: "RV" stands for RISC-V, "32" refers to the width of the registers (32 bits), and "I" stands for the integer base instruction set.

2. **Instruction Set**: RV32I defines a set of basic instructions for integer operations. It includes instructions for arithmetic (addition, subtraction, multiplication, division), logical operations (AND, OR, XOR), data movement (load, store), control transfer (branches, jumps), and other basic operations.

3. **Registers**: RV32I provides 32 general-purpose registers (X0 to X31), each 32 bits wide. These registers are used for holding data during computation.

4. **Addressing**: RV32I supports a flat memory model where memory addresses are typically 32 bits wide. It can access memory using load and store instructions.

5. **Endianness**: RV32I can be implemented in either little-endian or big-endian mode. Little-endian means the least significant byte is stored at the lowest memory address, while big-endian means the most significant byte is stored at the lowest memory address.

6. **RISC-V Philosophy**: RISC-V is designed with simplicity and extensibility in mind. The base integer instruction set (RV32I) provides a minimal set of instructions necessary for basic computation. Additional instruction set extensions can be added as needed for specific applications or performance optimizations.


#### Commands for cloning RV32I and runnig the files on iverilog and gtkwave
```
$ git clone https://github.com/vinayrayapati/rv32i
$ cd rv32i
$ iverilog -o iiitb_rv32i iiitb_rv32i.v iiitb_rv32i_tb.v
$ ./iiitb_rv32i
$ gtkwave iiitb_rv32i.vcd
 ```
<image src="https://github.com/Rajveer-1234/vsdsquadron_mini_intership/blob/main/commands%20.png?raw=true"/>

## WAVEFORMS

 1:add r6,r2,r1

 <img src="https://github.com/Rajveer-1234/vsdsquadron_mini_intership/blob/main/1.png?raw=true"/>

  2:sub r7,r1,r2

  <img src="https://github.com/Rajveer-1234/vsdsquadron_mini_intership/blob/main/2.png?raw=true"/>

  3:and r8,r1,r3

  <img src="https://github.com/Rajveer-1234/vsdsquadron_mini_intership/blob/main/3.png?raw=true"/>

  4.or r9,r2,r5

  <img src="https://github.com/Rajveer-1234/vsdsquadron_mini_intership/blob/main/4.png?raw=true"/>

  5.xor r10,r1,r4

  <img src="https://github.com/Rajveer-1234/vsdsquadron_mini_intership/blob/main/5.png?raw=true"/>

  6.slt r11,r2,r4
  
  <img src="https://github.com/Rajveer-1234/vsdsquadron_mini_intership/blob/main/6.png?raw=true"/>

  7.addi r12,r4,5

  <img src="https://github.com/Rajveer-1234/vsdsquadron_mini_intership/blob/main/7.png?raw=true"/>
   
   8.sw r3,r1,2

   <img src="https://github.com/Rajveer-1234/vsdsquadron_mini_intership/blob/main/8.png?raw=true"/>

   9.lw r13,r1,2

   <img src="https://github.com/Rajveer-1234/vsdsquadron_mini_intership/blob/main/9.png?raw=true"/>

   10.beq r0,r0,15

   <img src="https://github.com/Rajveer-1234/vsdsquadron_mini_intership/blob/main/10.png?raw=true"/>

   11.bne r0,r1,20

   <img src="https://github.com/Rajveer-1234/vsdsquadron_mini_intership/blob/main/11.png?raw=true"/>

   12.sll r15,r1,r2(2)

   <img src="https://github.com/Rajveer-1234/vsdsquadron_mini_intership/blob/main/12.png?raw=true"/>
   
   13.srl r16,r14,r2(2)

   <img src="https://github.com/Rajveer-1234/vsdsquadron_mini_intership/blob/main/13.png?raw=true"/>

  14.Full 5-stage instruction pipeline and pc-increment description Waveform

  <img src="https://github.com/Rajveer-1234/vsdsquadron_mini_intership/blob/main/14.png?raw=true"/>

  <img src="https://github.com/Rajveer-1234/vsdsquadron_mini_intership/blob/main/14.png?raw=true">/
