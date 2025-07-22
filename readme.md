## Abstraction
high level language program (e.g. C) "compiler"-> assembly language program (e.g. RISCV) "assembler"-> machine language program (e.g. RISCV) "machine interpretation"-> hardward architecture description -> logic circuit description

## Number Representation
### Bits can represent ANYTHING
Decimal(base 10), Binary(base 2), Hexadecimal(base 16)
General Formula: Dn-1Dn-2...D1D0 (n-digit number in base B) = Dn-1 x Bn-1 + Dn-2 x Bn-2 + ... +D0 x B0
- unsigned intergers (only non-negative integers)
- signed integers (first bit gives sign, rest treated as unsigned "magnitude")
- one's complement (complement all the bits)
- two's complement (complement all the bits and then add one)
leftmost bit is most significant bit (MSB)
rightmost bit is least significant bit (LSB)
"Overflow" is when the results of an arithmetic operation can't be represented by the hardware bits

## C, Pointers, Address
C is a compiled language, C compilers map C program into specific machine code (faster than Python)
A pointer is a variable that contains an address

## Memory Management and Usage
"stack(goes downward), heap(goes upward), static data, code"
- stack: local variables
- heap: space requested via malloc() and used with pointers, resizes dynamically
- static data: global and static variables
- code: loaded when program starts

size of an address depends on architecture(32-bit windows, 64-bit mac os)
- for 32-bit, have 2^32 possible addresses

dynamic memory allocation (heap)
- sizeof(): returns size in number of char-sized units of a variable or data type name, eg one char is 1
- malloc(n): allocates a continuous block of n bytes of uninitialized memory (may contains rubbish)
- free(p): release the memory by passing pointer p

memory errors
- segmentation fault: program attempts to access memory not allocated to it
- bus error: failure in the execution of machine language instruction resulting from the processor detecting an anomalous condition on its bus


## Floating Points
floating point encoding: 1bit(sign bit) + 8bits(exponent) + 23bits(significand) = (-1)^2 x (1.significant) x 2^(exponent-127)
eg. 0011111110000000000000000000000 = (-1)^0 x (1.1 base two) x (127-127) = 1.1 base two = 1 x 2^0 + 1 x 2^-1 = 1.5 base ten

## Machine Language RISCV
reducing instruction set computing (RISC)
- simpler instruction set makes it easier to build fast hardware
- let software do the complicated operations by composing simpler ones

register (assembly uses registers to store values, they are small and fast, store most frequently used variables in the registers)

assembly code:
syntax: operation(op) destination(dst), src1, src2
eg. add t0, x0, x0


## Interpreter (slower)
directly executes a program in the source language; directly interpret a high level language when efficiency is not critical
## Translator (faster)
converts a program from the source language to an equivalent program in another language; translate to a lower level language when increased performance is desired!

## More
- compiler (input higher-level language code, output assembly language code)
- assembler (input assembly language code, output object code and information tables)
- linker (input object code files and information tables, output executable code)
- loader (input executable code, output program is run) "it is the operating system"


## Logic Gates and Truth Table
- NOT
- AND
- OR
- NAND
- NOR
- XOR
truth tables are table that relates the inputs to a combinational logic circuit to its output (2^n outputs)

## CPU (central processing unit)
- datapath: contains the hardware necessary to perform operations required by processor
- control: decides what each piece of the datapath should do (what operation am i performing? do i need to get info from memory? ...)

Processor(control, datapath), memory, input, output


## Memory Hierarchy
from smaller/faster/expensive to bigger/slower/cheaper (top to down)
cache: holds a copy of a subset of main memory
eg. L1 cache, L2 cache
then main memory, then secondary memory
- registers <-> memory (assembly level programmer)
- cache <-> main memory (by the cache controller hardware)
- main memory <-> disks (secondary storage)

cache hit: cache holds a valid copy of the block, so return the desired data
cache miss: cache does not have desired block, so fetch from memory and put in empty slot (if cache is full, then discard one and replace it)
Average Memory Access Time (AMAT) = hit time + miss rate x miss penalty (average time to access memory consider hit time and miss time)
