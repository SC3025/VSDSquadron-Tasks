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


