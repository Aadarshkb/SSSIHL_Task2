Task 5:


Full Adder Circuit Implementation Using RISC-V Assembly

## Overview
A **full adder** is a combinational logic circuit that performs binary addition of three inputs: two operands (**A** and **B**) and a carry-in (**Cin**). This document presents the full adder's implementation using **RISC-V assembly language**.

## Truth Table

| A | B | Cin | Sum | Cout |
|---|---|-----|-----|------|
| 0 | 0 |  0  |  0  |  0   |
| 0 | 0 |  1  |  1  |  0   |
| 0 | 1 |  0  |  1  |  0   |
| 0 | 1 |  1  |  0  |  1   |
| 1 | 0 |  0  |  1  |  0   |
| 1 | 0 |  1  |  0  |  1   |
| 1 | 1 |  0  |  0  |  1   |
| 1 | 1 |  1  |  1  |  1   |

## Logical Expressions

- **Sum** = A ⊕ B ⊕ Cin
- **Cout** = (A & B) | (Cin & (A ⊕ B))

## RISC-V Assembly Code

```assembly
.section .data
A:     .word 1  # First input bit
B:     .word 1  # Second input bit
Cin:   .word 1  # Carry input
Sum:   .word 0  # Sum output
Cout:  .word 0  # Carry output

.section .text
.global _start

_start:
    # Load values of A, B, and Cin
    la a0, A
    lw a1, 0(a0)  # Load A into a1
    la a0, B
    lw a2, 0(a0)  # Load B into a2
    la a0, Cin
    lw a3, 0(a0)  # Load Cin into a3

    # Compute Sum (A XOR B XOR Cin)
    xor a4, a1, a2  # a4 = A XOR B
    xor a5, a4, a3  # a5 = A XOR B XOR Cin
    la a0, Sum
    sw a5, 0(a0)    # Store Sum

    # Compute Cout ((A & B) | (Cin & (A XOR B)))
    and a6, a1, a2  # a6 = A & B
    and a7, a3, a4  # a7 = Cin & (A XOR B)
    or t0, a6, a7   # t0 = Cout
    la a0, Cout
    sw t0, 0(a0)    # Store Cout

    # Exit program
    li a7, 10       # syscall exit
    ecall
```

## Execution Instructions
1. **Assemble the code:**
   ```sh
   riscv64-unknown-elf-as -o full_adder.o full_adder.s
   ```
2. **Link the object file:**
   ```sh
   riscv64-unknown-elf-ld -o full_adder full_adder.o
   ```
3. **Run the program on a RISC-V emulator or board:**
   ```sh
   qemu-riscv64 full_adder
   ```

## Summary
This program demonstrates a **full adder circuit** using **RISC-V assembly**, performing binary addition with carry propagation efficiently.
