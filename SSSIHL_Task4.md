**TASK 4:**

OBSERVING WAVEFORMS IN GTKWAVE FOR RISC-V SIMULATION:

After running the Verilog simulation, the results are saved in a VCD (Value Change Dump) file. This file contains all the signal changes that happened during the simulation. To view these signals as waveforms, we use GTKWave, a tool that helps us analyze and debug our design.

![1](https://github.com/user-attachments/assets/321ce93b-c985-44df-aec7-b12fb16f9c76)

![2](https://github.com/user-attachments/assets/d99b9390-84eb-4c7f-bd5c-afb9667d5646)

Steps to View Waveforms in GTKWave

Run the Simulation
First, make sure you have already run the simulation using: ./iiitb_rv32i

This command generates a file called iiitb_rv32i.vcd, which stores the signal changes.

Open GTKWave
To view the waveforms, enter: gtkwave iiitb_rv32i.vcd

This will open GTKWave and load the saved signal data.

Understanding the GTKWave Window
Once GTKWave opens, you will see different sections: Signals Panel (left side): Lists all the signals from your simulation. Waveform Viewer (right side): Shows how signals change over time. Time Scale (top): Represents time steps in the simulation.

Adding Signals to the Waveform Viewer
To observe how different signals change: Find the signals (like pc, instr, or reg_file) in the Signals Panel. Drag and drop them into the Waveform Viewer or right-click and select Insert into Waveform.

Analyzing the Waveforms
Program Counter (pc): Helps track which instruction is being executed. Instruction Register (instr): Shows which instruction is currently running. Registers and Data Paths: Help check if the CPU is working correctly.

Adjusting the View
Zoom In/Out: Use the zoom buttons to focus on specific time intervals. Scroll Along Time: Drag left or right to see how values change at different clock cycles.

Why Use GTKWave? GTKWave helps us visualize what’s happening inside the CPU step by step. It is useful for debugging and ensuring that the instructions are executed correctly.









