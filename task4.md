GTKWave is a waveform visualization tool that presents simulation outcomes in a user-friendly graphical format, assisting users in examining signal variations over time, focusing on particular events, and troubleshooting their designs. Combined, these tools create a comprehensive simulation and verification framework, with Iverilog carrying out the simulation and GTKWave facilitating the interpretation of the results.

for simulation, we use a verilog netlist and testbench. a .vcd file is generated, and the output waveforms are simulated using gtkwave.


![image](https://github.com/user-attachments/assets/0613b508-1962-47d5-80e1-96f2018c788b)


INSTALLATION STEPS
-----------------------

(1) Installing:
sudo apt-get update
sudo apt-get install iverilog gtkwave
-------------------------------


(2) Generating files:
MAKE TWO FILES IN .v FORMAT AS SAID EARLIER FOR VERILOG NETLIST AND FOR THE TESTBENCH

(my files were sv.v and stb.v)

-----------------------------------

(3) Compiling the iverilog:
iverilog -o my_simulation.vvp sv.v sbt.v
--------------------------------



(4) To run the simulation:
vvp my_simulation.vvp
------------------------------------
Waveform Using GTKWave:
gtkwave iiitb_rv32i.vcd
[it will give the simulation]
[ if the vcd file is not found to be in directory then give commant : "ls -1" and see the .vcd file in the directory and run the command for GTKwave]









![image](https://github.com/user-attachments/assets/51ed6a2c-f11d-4d2d-afb0-b7d75c446537)

![image](https://github.com/user-attachments/assets/472870db-fc98-4531-87a9-cd52dbc91fb4)





---------------------------------------------------------
---------------------------------------------------------


5-Stage RISC Pipeline:
---------------------




1. Instruction Fetch (IF) Stage:
   ---------------------------
   
Signals:
IF_ID_IR: Instruction Register that holds the instruction fetched from memory.
IF_ID_NPC: Next Program Counter, which holds the address of the next instruction to be fetched.
Process:

In the Instruction Fetch stage, the instruction is fetched from memory based on the Program Counter (PC).
The PC is updated to the next instruction address (PC + 4 in a typical RISC-V architecture, as instructions are usually 4 bytes).
The Instruction Register (IR) is loaded with the fetched instruction, and the Next Program Counter (NPC) is calculated, which will point to the next instruction for the following cycle.




2. Instruction Decode (ID) Stage:
   --------------------------------
Signals:
ID_EX_A: The first register operand read from the register file.
ID_EX_B: The second register operand read from the register file.
ID_EX_IMMEDIATE: Immediate value (if applicable), depending on the type of instruction (e.g., I-type, S-type, etc.).
ID_EX_IR: Instruction Register, which contains the instruction that was fetched in the IF stage.
Process:

During Instruction Decode, the instruction fetched in the IF stage is decoded to determine the type of operation to perform.
The registers specified in the instruction are read from the register file.
For some types of instructions (like I-type or S-type), an immediate value might be extracted from the instruction and passed to the next stages.
The decoded instruction and the corresponding values (operands and immediate) are passed along to the Execution (EX) stage for further processing.








3. Execution (EX) Stage:
   -------------------
   
Purpose:

The Execution stage performs the actual computation or operation required by the instruction. It is the core of the processor where arithmetic, logic, and address calculations happen.
Operations:

Arithmetic Operations: For R-type instructions (like ADD, SUB, etc.), the ALU (Arithmetic Logic Unit) performs the specified operation (e.g., addition or subtraction) on the operands obtained from the decode stage.
Address Calculation: For load and store instructions (I-type or S-type instructions), the EX stage calculates the address where data will be loaded from or stored into memory. This is done by adding the base register value and the immediate value (for load/store) or by using the values in the registers for addressing.






4. Memory (MEM) Stage:
   ------------------
Purpose:

The Memory stage is where memory operations are performed. If the instruction involves accessing data from memory, this is where the memory is read or written.
Operations:

Load: For instructions like LW (Load Word), data is fetched from memory. The address to read from is passed from the EX stage. The memory is accessed, and the data is fetched from the calculated address.
Store: For instructions like SW (Store Word), data is written to memory. The value to store comes from the register file, and the address where the data is to be stored is calculated in the EX stage. The memory operation writes the data to the computed address.




5. Write-back (WB) Stage:
   --------------------
Purpose:

The Write-back stage is the final stage in the pipeline where the result of the instruction (either an arithmetic result or data from memory) is written back to the register file, completing the instruction execution cycle.
Operations:

If the instruction is a load instruction (like LW), the value fetched from memory in the MEM stage is written back into the register file.
If the instruction is an arithmetic operation (like ADD or SUB), the result computed in the EX stage is written back to the register file.
The WB stage ensures that the result is stored in the correct register for later use in subsequent instructions.





