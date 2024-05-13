# VLSI-LAB-EXP-5
SIMULATION AND IMPLEMENTATION OF FINITE STATE MACHINE

AIM: To simulate and synthesis finite state machine using Xilinx ISE.

**APPARATUS REQUIRED: **

VIVADO 2023.1

**PROCEDURE: **

1. Open Vivado: Launch Xilinx Vivado software on your computer.

2. Create a New Project: Click on "Create Project" from the welcome page or navigate through "File" > "Project" > "New".

3. Project Settings: Follow the prompts to set up your project. Specify the project name, location, and select RTL project type.

4. Add Design Files: Add your Verilog design files to the project. You can do this by right-clicking on "Design Sources" in the Sources window, then selecting "Add Sources". Choose your Verilog files from the file browser.

5. Specify Simulation Settings: Go to "Simulation" > "Simulation Settings". Choose your simulation language (Verilog in this case) and simulation tool (Vivado Simulator).

6. Run Simulation: Go to "Flow" > "Run Simulation" > "Run Behavioral Simulation". This will launch the Vivado Simulator and compile your design for simulation.

7. Set Simulation Time: In the Vivado Simulator window, set the simulation time if it's not set automatically. This determines how long the simulation will run.

8. Run Simulation: Start the simulation by clicking on the "Run" button in the simulation window.

9. View Results: After the simulation completes, you can view waveforms, debug signals, and analyze the behavior of your design.

Logic Diagram :

![image](https://github.com/navaneethans/VLSI-LAB-EXP-5/assets/6987778/34ec5d63-2b3b-4511-81ef-99f4572d5869)


VERILOG CODE:
```
module fsm(clk,rst,x,z); 
input clk,rst,x;
output z;
reg [2:1] ps,ns;
parameter s0=2'b00,s1=2'b01,s2=2'b10,s3=2'b11;
 always@(x,posedge clk)
case(ps) s0:if(x) ns=s1; else ns=s0;
s1:if(x) ns=s1; else ns=s2; s2:if(x) ns=s3;
else ns=s0;
s3:if(x)
ns=s1;
else ns=s0;
 endcase
always@(posedge clk) if(rst)ps<=s0;
else ps=ns;
assign z=(ps==s3);
endmodule
```
OUTPUT:

![image](https://github.com/Siva1309/VLSI-LAB-EXP-5/assets/166374356/d7113fac-446f-49af-a517-c0f8d278d780)


RESULT:
    The simulate and synthesis of finite state machine using VIVADO is successfully verified.




