# TASK1 

Installation of tools

## UBUNTU INSTALLATION
1.Installing Oracle Virtual Box for Windows

2.Installing Ubuntu iso file on windows

3.Launching UBUNTU in Virtual Box

<img src = "https://github.com/Rajveer-1234/vsdsquadron_mini_intership/blob/main/UBUNTU.png?raw=true" />

## RISCV-GNU-TOOLCHAIN

#### COMMAND TO INSTALL
```
$ git clone https://github.com/riscv/riscv-gnu-toolchain
$ sudo apt-get install autoconf automake autotools-dev curl python3 python3-pip libmpc-dev libmpfr-dev libgmp-dev gawk build-essential bison flex texinfo gperf libtool patchutils bc zlib1g-dev libexpat-dev ninja-build git cmake libglib2.0-dev libslirp-dev
./configure --prefix=/opt/riscv
make linux
./configure --prefix=/opt/riscv --with-arch=rv32gc --with-abi=ilp32d
make linux
```

![image](https://github.com/Rajveer-1234/vsdsquadron_mini_intership/assets/110220051/ab7ad3d1-1118-4ef2-9b4b-23ce5cf044ab)

<img src= "https://github.com/Rajveer-1234/vsdsquadron_mini_intership/blob/main/RISC%20GNU%20TOOL%20CHAIN.png?raw=true" />


## YOSYS

#### COMMAND TO INSTALL
```
$ git clone https://github.com/YosysHQ/yosys.git
$ cd yosys
$ sudo apt install make (If make is not installed please install it) 
$ sudo apt-get install build-essential clang bison flex \
    libreadline-dev gawk tcl-dev libffi-dev git \
    graphviz xdot pkg-config python3 libboost-system-dev \
    libboost-python-dev libboost-filesystem-dev zlib1g-dev
$ make config-gcc
$ make 
$ sudo make install
```

<img src= "https://github.com/Rajveer-1234/vsdsquadron_mini_intership/blob/main/Yosys.png?raw=true" />

<img src="https://github.com/Rajveer-1234/vsdsquadron_mini_intership/blob/main/yosys%20.png?raw=true" />

## iVerilog

#### COMMAND TO INSTALL
```
$sudo apt-get install iverilog
```

<img src="https://github.com/Rajveer-1234/vsdsquadron_mini_intership/blob/main/iverilog.png?raw=true" />

## Gtkwave

#### COMMAND TO INSTALL
```
$sudo apt update
$sudo apt install gtkwave
```

<img src ="https://github.com/Rajveer-1234/vsdsquadron_mini_intership/blob/main/gtkwave.png?raw=true" />
