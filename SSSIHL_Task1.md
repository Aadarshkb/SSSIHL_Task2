# SSSIHL_Task1

**WEEK-1**


We write a C program that adds numbers from 1 to 'n'.

We first installed the leafpad editor if it was not previously installed.

![1](https://github.com/user-attachments/assets/c366efbe-7c03-48e2-9b2a-25c0b196d9fe)

Then we write down our C code in the editor and save it as {filename.c} file.

![2](https://github.com/user-attachments/assets/a9642425-282f-427f-b005-12009d38a1ce)

Code
# include <stdio.h.>

int main() {
    int i, sum= 0, n= 5;
    for (i=o; i<=n; ++i) {
    sum +=i;
    }
    printf("Sum of the numbers from 1 to %d is %d\n", n,sum);
    return 0;
}
After saving the file we write down the command gcc {filename.c}  ./a.out

![3](https://github.com/user-attachments/assets/4a32f4da-dc42-4026-b28e-2d50bbaa0ccb)

![4](https://github.com/user-attachments/assets/ed6b9569-2c2d-4841-b642-282ca365304d)

Then we can play with the numbers to get different outputs.

We write another command and run it.  riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o {filename}.o {filename}.c

![5](https://github.com/user-attachments/assets/1f0fedae-185c-4ccc-80ac-c5399446b481)

We go to another tab and see the assembly code of the program
riscv64-unknown-elf-objdump -d {filename}.o

![6](https://github.com/user-attachments/assets/897e1819-1124-403b-8b95-60aa7cb653e3)

Then we type another command

riscv64-unknown-elf-objdump -d {filename}.o | less

This will give us the section of the code but we require only the main section.

Then we locate the byte address of the main section.

![7](https://github.com/user-attachments/assets/d9dde8c2-3a6f-4abd-914f-155a6327fc22)

Finding the number of instructions:-

We add the last instruction with 4 to get the next address. As it is byte instructions it always increments by 4.

![8](https://github.com/user-attachments/assets/83adb0b8-7a95-473a-a7dc-b49a3ab3c66f)

To count the number of instructions:-

The first instruction is subtracted from the first instruction of the previous address and then divided by 4.

![9](https://github.com/user-attachments/assets/4d4ae507-0374-4124-bec5-7e7e0322d25f)

Then we get the number of instructions in the DEC section.

We run the same command but instead of O1 we use Ofast  riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o {filename}.o {filename}.c

We run the same command and search for the main again

Then we again calculate the number of instructions.

![10](https://github.com/user-attachments/assets/192630c5-d904-4b98-b1f2-d8044653de49)

![11](https://github.com/user-attachments/assets/99beaeac-942d-4119-a949-0ad89815ed2e)

