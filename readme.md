## Abstraction
high level language program (e.g. C) "compiler"-> assembly language program (e.g. RISCV) "assembler"-> machine language program (e.g. RISCV) "machine interpretation"-> hardward architecture description -> logic circuit description

## Number Representation
# Bits can represent ANYTHING
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
