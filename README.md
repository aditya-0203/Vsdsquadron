# VSDSquadron-Mini-Internship
---

Details 
## Task 1: Writing a C Code to Compute the Sum of Numbers from 1 to n
---
### Step 1: Creating and Opening a New C File
  : To begin, I opened the terminal and executed commands to create and open a new C file using vim. This set up the environment to start coding.
    ![task1-1](https://github.com/user-attachments/assets/a53c8603-fed5-4c17-b386-4d2b107e9b5a)

### Step 2: Writing the Code
  : Once the file was opened in Vim, I wrote the C code to calculate the sum of numbers from 1 to n. The logic was implemented and saved as shown below.
    ![1](https://github.com/user-attachments/assets/37594d02-1b46-4749-b5f6-881fc159ddf1)

### Step 3: Compiling and Running the Code
  o After completing the code, I compiled it in the terminal to ensure there were no errors. I then ran the program to verify its functionality. The output matched the expected results, confirming the correctness of the code.
    ![2](https://github.com/user-attachments/assets/955b7d81-3de2-4a48-8535-558824d27c1a)

### Step 4: Testing with Different Values of n
  o To further validate the program, I tested it with various values of n, such as 50. Each time, the program produced the correct results, demonstrating its reliability.
    ![3](https://github.com/user-attachments/assets/bcd6655c-09d6-4cf2-b525-7cd05484cec3)
---
# Running the code sum1ToN.c in RiscV simulator 
---

  ## 1] Before simulating the code we have compile it so use the following command

      o riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum1ToN.o sum1ToN.c
    
  ![2](https://github.com/user-attachments/assets/dc5508ad-fb35-44c8-9527-6ac5502009e2)

---
  ## 2] To simulate use below command -->  to obtain the assembly code for the above C program. 
      
     o riscv-unknown-elf-objdump -d sum1ton.o
--- 
  ## 3] now we have to locate to main section 
   o /main

  ![main](https://github.com/user-attachments/assets/a0f16fec-6cfe-4613-ba53-931bb9e7f9e3)

 ## 4] Observations in Assembly Instructions
          o The byte address for main was found to be 10184.
          o There were 15 instructions (in hexadecimal: E) when compiled with the -O1 optimization level.
          o The address of each consecutive instruction increments by 4 bytes, as observed in the disassembled output.

   ![14_E_instruction](https://github.com/user-attachments/assets/60463680-06e0-4d72-9be3-e4179786cf1b)

## 5]The same commands were run with the -Ofast optimization level instead of -O1. This resulted in a reduced number of instructions—12 instructions.

     o This demonstrates that the number and type of assembly instructions generated depend on the compilation optimization level used.
     o The higher optimization (-Ofast) produces a more compact and efficient assembly.

  ![ofast](https://github.com/user-attachments/assets/d66a6fa8-a174-4438-a08f-887a4f75d663)

  ![B_11](https://github.com/user-attachments/assets/a9f9c04c-9150-43e2-afb3-d858c04119d1)

# This is about Task 1.
--- 


# Task 2 
---
## swapping two number

![image](https://github.com/user-attachments/assets/a8f72fea-deb1-4683-bc35-ef895aa05ecd)

--- 
Result using spice simulator
![image](https://github.com/user-attachments/assets/9db18649-2d0a-4099-9c97-1e22567c62a0)

---

Here is a snapshot of the objdump, assembly code for O1, and Ofast profiles respectively:

O1 assembly code:
![image](https://github.com/user-attachments/assets/811cdca3-4cd7-46cb-958b-ffdbf8195036)

---
Ofast assembly code:

![image](https://github.com/user-attachments/assets/794df8f0-f596-405a-b2f2-efa999081ef6)

## Task 2 end
--- 


# Task 3 
---
# what is RISC-V

  It is an open standard instruction set architecture (ISA) based on established reduced instruction set computer (RISC) principles.

  Base Instruction Formats

  ![image](https://github.com/user-attachments/assets/7c7d53f2-c2fc-47f4-aad3-1f2467df30d3)



  R-type Instructions

    Used for register-register operations, such as addition, subtraction, and bitwise logic operations.

    o funct7 (31-25): Used to specify additional operation details or variants.
    o rs2 (24-20): The second source register.
    o rs1 (19-15): The first source register.  
    o funct3 (14-12): Specifies the type of operation (e.g., add, sub, OR).
    o rd (11-7): The Rd register is also called the destination register, and the destination register is the register used to store the result
    o opcode (6-0): Identifies the operation class (e.g., arithmetic, logic).


  I-type Instructions

    Used for immediate data manipulation, load instructions, and other operations involving immediate values.

    o imm[11:0] (31-20): 12-bit immediate value (sign-extended).
    o rs1 (19-15): Source register.
    o funct3 (14-12): Operation type specifier.
    o rd (11-7): Destination register.
    o opcode (6-0): Operation class identifier

S-type Instructions

    Used for store operations to memory.

    o imm[11:5] (31-25): Upper 7 bits of the 12-bit immediate value.
    o rs2 (24-20): Source register for the data to be stored.
    o rs1 (19-15): Source register specifying the base address.
    o funct3 (14-12): Operation type specifier.
    o imm[4:0] (11-7): Lower 5 bits of the 12-bit immediate value.
    o opcode (6-0): Operation class identifier.

B-type Instructions

    Used for conditional branch operations.

    o imm[12] (31): Most significant bit of the immediate value (sign bit).
    o imm[10:5] (30-25): Upper 6 bits of the immediate value.
    o rs2 (24-20): Second source register.
    o rs1 (19-15): First source register.
    o funct3 (14-12): Specifies the branch condition (e.g., equal, not equal).
    o imm[4:1] (11-8): Bits [4:1] of the immediate value.
    o imm[11] (7): Bit 11 of the immediate value.
    o opcode (6-0): Operation class identifier.

U-type Instructions

    Used for upper immediate instructions, such as loading upper 20 bits into a register.

    o imm[31:12] (31-12): 20-bit immediate value (upper bits).
    o rd (11-7): Destination register.
    o opcode (6-0): Operation class identifier.

    This image illustrates the instruction format for a RISC-V Instruction Set Architecture (ISA). RISC-V supports six primary instruction formats: R-type, I-type, S-type, B-type, U-type, and J-type. Each format specifies the arrangement of fields in a 32-bit instruction word. Here's a detailed explanation of each format:
R-type Instructions

Used for register-register operations, such as addition, subtraction, and bitwise logic operations.

    funct7 (31-25): Used to specify additional operation details or variants.
    rs2 (24-20): The second source register.
    rs1 (19-15): The first source register.
    funct3 (14-12): Specifies the type of operation (e.g., add, sub, OR).
    rd (11-7): Destination register where the result is stored.
    opcode (6-0): Identifies the operation class (e.g., arithmetic, logic).

I-type Instructions

Used for immediate data manipulation, load instructions, and other operations involving immediate values.

    imm[11:0] (31-20): 12-bit immediate value (sign-extended).
    rs1 (19-15): Source register.
    funct3 (14-12): Operation type specifier.
    rd (11-7): Destination register.
    opcode (6-0): Operation class identifier.

S-type Instructions

Used for store operations to memory.

    imm[11:5] (31-25): Upper 7 bits of the 12-bit immediate value.
    rs2 (24-20): Source register for the data to be stored.
    rs1 (19-15): Source register specifying the base address.
    funct3 (14-12): Operation type specifier.
    imm[4:0] (11-7): Lower 5 bits of the 12-bit immediate value.
    opcode (6-0): Operation class identifier.

B-type Instructions

Used for conditional branch operations.

    imm[12] (31): Most significant bit of the immediate value (sign bit).
    imm[10:5] (30-25): Upper 6 bits of the immediate value.
    rs2 (24-20): Second source register.
    rs1 (19-15): First source register.
    funct3 (14-12): Specifies the branch condition (e.g., equal, not equal).
    imm[4:1] (11-8): Bits [4:1] of the immediate value.
    imm[11] (7): Bit 11 of the immediate value.
    opcode (6-0): Operation class identifier.

U-type Instructions

    Used for upper immediate instructions, such as loading upper 20 bits into a register.

    o imm[31:12] (31-12): 20-bit immediate value (upper bits).
    o rd (11-7): Destination register.
    o opcode (6-0): Operation class identifier.

J-type Instructions

    Used for jump instructions.

    o imm[20] (31): Most significant bit of the 21-bit immediate value (sign bit).
    o imm[10:1] (30-21): Bits [10:1] of the immediate value.
    o imm[11] (20): Bit 11 of the immediate value.
    o imm[19:12] (19-12): Bits [19:12] of the immediate value.
    o rd (11-7): Destination register.
    o opcode (6-0): Operation class identifier.


---

 ## The unique RISC-V instructions between the addresses 10184 to 10204

![image](https://github.com/user-attachments/assets/811cdca3-4cd7-46cb-958b-ffdbf8195036)

addi - Add immediate.

    Example: addi sp, sp, -32 (adjusts the stack pointer).

sd - Store double word.

    Example: sd ra, 24(sp) (stores the return address on the stack).

lui - Load upper immediate.

    Example: lui a0, 0x2b (loads the upper 20 bits of a value into a0).

jal - Jump and link.

    Example: jal ra, 10460 <printf> (calls the printf function and stores the return address in ra).

ld - Load double word.

    Example: ld ra, 24(sp) (loads the return address from the stack).

li - Load immediate (pseudo-instruction).

    Example: li a0, 0 (loads the value 0 into a0).

lw - Load word.

    Example: lw a1, 12(sp) (loads a word from the stack into a1).

sw - Store word.

    Example: sw a1, 12(sp) (stores a word from a1 onto the stack).

ret - Return from subroutine (pseudo-instruction).

    Example: ret (returns control to the caller).

---

### Task 4

---

cloned the repository and downloaded the netlist files for simulation.

![image](https://github.com/user-attachments/assets/8bd0eaa1-08e2-40ca-923a-63acef4ef149)

 following commands in your terminal.
  
     iverilog -o iiitb_rv32i iiitb_rv32i.v iiitb_rv32i_tb.v
    ./iiitb_rv32i

To see the output waveform in gtkwave, enter the following commands in your terminal.

    gtkwave iiitb_rv32i.vcd

![image](https://github.com/user-attachments/assets/74490d22-6c2e-4103-a68e-8ae22b02753a)

![image](https://github.com/user-attachments/assets/991b5e53-00b5-4e7b-b23c-df6b05f5298b)


![image](https://github.com/user-attachments/assets/e3bd1284-68a1-4f8e-87af-30b17e673e14)

![image](https://github.com/user-attachments/assets/8c98a3b0-ad4f-4cb8-a771-ab930d151fee)

End Task 4 
---
