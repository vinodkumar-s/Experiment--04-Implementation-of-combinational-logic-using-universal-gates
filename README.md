# Experiment--04-Implementation-of-combinational-logic-using-universal-gates
Implementation of combinational logic using universal-gates
 
## AIM:
To implement the given logic function using NAND and NOR gates and to verify its operation in Quartus using Verilog programming.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')' using NAND gate
F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')' using NOR gate
## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime


## Theory
Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output. 

## Using NAND gates
NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

## Logic Diagram

Using NOR gates
NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'

## Logic Diagram
## Procedure:
#### 1.Create a project with required entities.
#### 2.Create a module along with respective file name.
#### 3.Run the respective programs for the given boolean equations.
#### 4.Run the module and get the respective RTL outputs.
#### 5.Create university program(VWF) for getting timing diagram.
#### 6.Give the respective inputs for timing diagram and obtain the results.
## Program:
Program to implement the given logic function using NAND and NOR gates and to verify its operations in quartus using Verilog programming.
#### Developed by: s.vinod kumar
#### RegisterNumber:  22004903
```
Using NAND Operation:

module comb1(A,B,C,D,F);
input A,B,C,D;
output F;
wire P,Q,R;
assign P = C&(~B)&(~A);
assign Q = D&(~C)&(~A);
assign R = (~C)&B&(~A);
assign F = (~P&~Q&~R);
endmodule

Using NOR Operation:

module comb2(A,B,C,D,F);
input A,B,C,D;
output F;
wire P,Q,R,S;
assign P = C&(~B)&A;
assign Q = D&(~C)&A;
assign R = C&(~B)&A;
assign S = ~(P|Q|R);
assign F = ~S;
endmodule
```

## RTL realization
#### for nand operation:
![output](/rtl-1.png)
#### for nor operation:
![output](/rtl-nor.png)
## Output:

## Timing Diagram
#### for nand operation:
![output](/rtl%20ouput-nand.png)
#### for nor operation:
![output](/combo2%20wave.png)

## Truth Table
#### for nand operation:
![output](/truth-table%20nand.png)

##### for nor operation:
![output](/truth%20table-nor.png)
## Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
