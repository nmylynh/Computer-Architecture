****# CPU Functional Components

## The Basics

### Transistors 

- They're like basic little switches
- The basis for all the computations that we do.
- They can be used to build logic gates.

### Gates

- Are logic gates made out of transistors. 
- They perform boolean logic, 
  - like OR, AND, NOT (conditionals in code)
  - XOR, NOR, NAND
- Can be put together into far more complex structures
  - ALU (arithmetic logic units used to do math)
  - CPUs

### CPU structure

![cpu structure](https://i.imgur.com/zEiv1ln.png)
![ALU](http://www.mathcs.emory.edu/~jallen/Courses/355/Syllabus/1-circuits/alu-func.gif)

- **CPU:** Executes instructions that are in RAM, and it can do math from the ALU, and can talk to the keyboard
- **RAM:** Random access memory; This is where we store data and instructions that the CPU runs. The data in RAM can be accessed at any point at any time randomly (we can jump around).
  - It's super fast compared to hard drives and SSDs. 
  - Think of it likes a big array of bytes that you can access by index, just like an array in your favourite programming language.
  - Each element in RAM can store one byte, an 8-bit number between 0-255, larger than that would be stored in...
  - Larger, multi-byte values are store in sequential addresses in RAM.
  - The CPU communicates with RAM via the _memory bus_.
- **ALU**: Arithmetic logic unit; An arithmetic logic unit (ALU) is a digital circuit used to perform arithmetic and logic operations. It represents the fundamental building block of the central processing unit (CPU) of a computer. Modern CPUs contain very powerful and complex ALUs. In addition to ALUs, modern CPUs contain a control unit (CU).
- **Memory Bus**: cpu accesses a memory address, for instance, 12, through the memory bus which is a collection of cables connecting to RAM, and RAM says yeah memory address 12 value is 47, and cpu takes 47 and does things with it

### RAM

![RAM](https://i.imgur.com/vs8XaG0.png)

- Here the address is just like the index of an array.
- Inside each of these is a 1 byte value.
- These values are written in hexidemical because hexidemical bytes are 2 digits long in hex
- Even though RAM stores values in bytes, the CPU operates on words

### CPU words

- Bytes of data are stored in RAM (memory)
- Larger 64-bit (8-byte) numbers, stored sequentially in RAM, that the CPU can operate on are called _words_.
  - Words are typically the size of your CPU as it was advertised.
- The exact number of bytes per word depends on the architecture, it represents how much the CPU can operate upon at once. For example, if you have an add operation on a CPU, it can add 2 64-bit numbers together at once.
  - 8 bytes for a 64-bit CPU
  - 4 bytes for a 32-bit CPU
  - 1 byte for an 8-bit CPU
    - If the CPU wants to add more than it's capacity, it has to do so 1 byte at a time.

### CPU Registers

- **_Registers_ store words that can be accessed at an ultra-high speed**
- Think of them like variables that the CPU has at its disposal
  - They're little variables that are built inside the CPU
  - In the example, we have eight of them (R0 - R7) and it cannot be changed
  - Different CPUs from different manufacturers have different number of registers and different names for their registers-- it depends on the CPU
- Similar to RAM, except store directly on the CPU so they are much faster
- There are a limited number of them at your disposal, usually 8, 16, or 32, depending on the CPU
- They have fixed names, e.g. R0, R1, or EAX, EBX, etc. depending on the CPU
- Many CPUs can _only_ perform math operations on registers which must be loaded from RAM first. (The x86 family can often perform math on registers quickly, or RAM slowly.)

### CPU Instructions

- Are also stored in RAM with other data
- Are actually just numbers
- Humans often use mneumonics to refer to the instruction in a human-readable way
- The CPU keeps track of the address of the currently-executing instruction in RAM and performs different actions based on the instruction found there
- The address of the currently-executing instruction is head in a special register called the _program counter_ (PC)
- CPUs usually have a significant number of instructions, around 50-200