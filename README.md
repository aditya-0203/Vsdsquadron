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



  
