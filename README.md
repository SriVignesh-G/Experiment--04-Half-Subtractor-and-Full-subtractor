# Name: Sri Vignesh G
# Reference No: 23012556

# Experiment-04: Implementation of Half Subtractor and Full subtractor
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
 Hardware – PCs, Cyclone II , USB flasher
 
 Software – Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Half Subtractor Full Subtractor
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Procedure
1. Create a New Project:
   - Open Quartus and create a new project by selecting "File" > "New Project Wizard."
   - Follow the wizard's instructions to set up your project, including specifying the project name, location, and target device (FPGA).

2. Create a New Design File:
   - Once the project is created, right-click on the project name in the Project Navigator and select "Add New File."
   - Choose "Verilog HDL File" or "VHDL File," depending on your chosen hardware description language.

3. Write the Combinational Logic Code:
   - Open the newly created Verilog or VHDL file and write the code for your combinational logic.
     
4. Compile the Project:
   - To compile the project, click on "Processing" > "Start Compilation" in the menu.
   - Quartus will analyze your code, synthesize it into a netlist, and perform optimizations based on your target FPGA device.

5. Analyze and Fix Errors:
   - If there are any errors or warnings during the compilation process, Quartus will display them in the Messages window.
   - Review and fix any issues in your code if necessary.
   - View the RTL diagram.

6. Verification:
   - Click on "File" > "New" > "Verification/Debugging Files" > "University Program VWF".
   - Once Waveform is created Right Click on the Input/Output Panel > " Insert Node or Bus" > Click on Node Finder > Click On "List" > Select All.
   - Give the Input Combinations according to the Truth Table amd then simulate the Output Waveform.



## Program:
### Half Subtractor:
```
module halfsub(diff,carry,x,y);
input x,y;
output diff,carry;
assign diff = x^y;
assign carry = ~x&y;
endmodule
```
### Full Subtractor:
```
module fullsub(diff,carry,a,b,c);
input a,b,c;
output diff,carry;
assign diff = a^b^c;
assign carry = (~a)&c | (~a)&b | (b&c);
endmodule
```

## Output:
##  RTL realization
### Half Subtractor:
![e4 hsrtl](https://github.com/SriVignesh-G/Experiment--04-Half-Subtractor-and-Full-subtractor/assets/147576510/bdb4820e-95aa-4c8f-958f-d2afd0967fa4)
### Full Subtractor:
![e4 ffrtl](https://github.com/SriVignesh-G/Experiment--04-Half-Subtractor-and-Full-subtractor/assets/147576510/0db79e3a-a576-414d-983f-70c2cf2beb55)

## Truthtable
### Half Subtractor:
![hf e4 tt](https://github.com/SriVignesh-G/Experiment--04-Half-Subtractor-and-Full-subtractor/assets/147576510/d25c6973-2296-45a6-9a2c-f02064d1dd98)
### Full Subtractor:
![e4 tt](https://github.com/SriVignesh-G/Experiment--04-Half-Subtractor-and-Full-subtractor/assets/147576510/beafbe7e-8aba-4d8e-a31e-3e8c28fbe0bc)


## Timing diagram 
### Half Subtractor:
![e4 hf wf](https://github.com/SriVignesh-G/Experiment--04-Half-Subtractor-and-Full-subtractor/assets/147576510/fed810de-5e77-4a46-bd6e-527e91f88f89)


### Full Subtractor:
![e4 ff wf](https://github.com/SriVignesh-G/Experiment--04-Half-Subtractor-and-Full-subtractor/assets/147576510/459ce6e8-b785-4d7e-a9ca-f41538a85181)


## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
