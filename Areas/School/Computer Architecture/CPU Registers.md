## Introduction
---
In Computer Architecture the CPU Register hold the key role which is fast and small data holding memory and is an integral part of the processor.

The register can perform the following operations:
1. FETCH: Fetches instruction provided by user.
2. DECODE: Decodes instruction to be performed.
3. EXECUTE: Executes operation on CPU

<u>Types of Memory Registers</u>
- Accumulator (AC)
- Flag Register
- Address Register (AR)
- Data Register (DR)
- Programm Counter (PC)
- Instruction Register (IR)

---
<u>ARM | RISC | CISC</u>
**ARM**: Advanced RISC Machine.
**RISC**: Reduced Instruction Set Computer.
**CISC**: Complex Instuction Set Computer.

ARM processors are used in a lot of commercial applications.
(Old) Examples:
- Video Games (This is outdated and possibly incorrect usage of the use here, other than older video game consoles)
- Modem
- Mobile Phones
- Handy Cameras
ARM will have a high performance, low code size, low power consumption, and low silicon area.

ARM Architectures:
- 32-bit arch
- bytes = 8 bit
- word = 32 bits
- half word = 16 bits

Two Types of Instuction sets for the ARM processor:
1. 32 bit ARM Inst. set
2. 16 bit Thumb Inst. set

<u>ARM Registers</u>
- 13 general pupose registers (R<sub>0</sub>, ..., R<sub>12</sub>)
- 3 special purpose registers (R<sub>13</sub>, R<sub>14</sub>, R<sub>15</sub>)
R<sub>13</sub>: Stack Register (PUSH, POP)
R<sub>14</sub>: Link Register
R<sub>15</sub>: PC

---

<u>CPSR</u>
Current Program Status Register

![[CSPR Figure.excalidraw]]
N: Negative Flag
Z: Zero Flag
C: Carry Flag
V: Overflow Flag

IF: Interupt Flag
T:
- Thumb State
- ARM State
- Set 1 = T
- Set 0 = T
Mode: 
- There are 7 types: 
	- User
	- System
	- FIQ
	- IRQ
	- Abort
	- Supervised
	- Undefined