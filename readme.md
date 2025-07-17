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
