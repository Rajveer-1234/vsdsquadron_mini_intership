
# TASK 3
Writing a C code and compile it and see its corresponding RISCV objdump file using RISCV GNU TOOLCHAIN compiler

### GCC
GCC stands for GNU Compiler Collection. It's a suite of compilers for various programming languages including C, C++, Objective-C, Fortran, Ada, and others. Developed by the GNU Project, GCC is free and open-source software and is widely used in both academia and industry. 

### RISCV-GNU-TOOLCHAIN
The RISC-V GNU Toolchain Compiler is a set of tools provided by the GNU Project specifically tailored for compiling code targeting RISC-V architectures.
The RISC-V GNU Toolchain Compiler includes several components:
* GCC (GNU Compiler Collection): The primary compiler for C, C++, and other supported languages.
* Binutils: A collection of binary tools including assemblers, linkers, and object file manipulation utilities.
* GDB (GNU Debugger): A powerful debugger for debugging programs written in C, C++, and other supported languages.
It supports various RISC-V ISA extensions including RV32I, RV32IM, RV64I, RV64IM, and more.

#### 1.First we will write C code for printing sum of numbers from 1 to n
```cpp
#include<stdio.h>

int main()

{
int i,sum=0,n=10;

   for(i=0;i<=n;++i)

   {
      sum+=i;
  }

   printf("The sum of numbers from 1 to %d is %d \n",n,sum);

   return 0;

}
```
#### 2.Compile the code with GCC compiler
```
gcc summ1ton.c
```
#### 3.We can check the output of compiled code by the following command
```
./a.out
```
<img src="https://github.com/Rajveer-1234/vsdsquadron_mini_intership/blob/main/cprogram.png?raw=true" />

<img src="https://github.com/Rajveer-1234/vsdsquadron_mini_intership/blob/main/cprogramoutput.png?raw=true" />

#### 4.Now our C code file will be coverted to object file using RISCV GNU TOOLCHAIN compiler 
```
riscv32-unknown-elf-gcc -O1 -o <summ1ton.o> <summ1ton.c>

```
* riscv32-unknown-elf-gcc -> Command to invoke riscv gcc complier for 32 bit architecture.
* -O1-> Level 1 optimization
* -o-> output
* summ1ton.o-> output file should be object file
* summ1ton.c-> Compiled C code file

#### 5.Now to see the object file
```
riscv32-unknown-elf-objdump -d <summ1ton.o>
```
* riscv32-unknown-elf-objdump->This is the command to invoke the objdump utility specifically for 32 bit RISCV architecture
* -d-> Diassemble the output file
* summ1ton.o-> output file should be object file


#### 6.To see the main function in output file
```
riscv32-unknown-elf-objdump -d <summ1ton.o> | less
/main
```
<img src="https://github.com/Rajveer-1234/vsdsquadron_mini_intership/blob/main/riscvobjdump.png?raw=true">/
<img src="https://github.com/Rajveer-1234/vsdsquadron_mini_intership/blob/main/riscvobjdump1.png?raw=true">/
<img src="https://github.com/Rajveer-1234/vsdsquadron_mini_intership/blob/main/riscvobjdumpmaininstructions.png?raw=true">/




