# Experiment--03-Half-Subtractor-and-Full-subtractor
# Implementation-of-Half-subtractor-and-Full-subtractor-circuit

# AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

# Equipments Required:

# Hardware – PCs, Cyclone II , USB flasher

# Software – Quartus prime

# Theory

Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

# Half Subtractor and Full Subtractor

# Half Subtractor

The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed. half-subtractor9

![Screenshot (80)](https://user-images.githubusercontent.com/119476322/215166321-488a5189-a724-44ce-b994-f161772cc6f1.png)

Sum = X'Y+XY' = X ⊕ Y Carry=X'Y

# Full Subtractor

A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. full-subtractor6

![Screenshot (81)](https://user-images.githubusercontent.com/119476322/215166392-64a0c0a5-b661-4499-bbf9-001958ca4e54.png)

Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

# Procedure
 
 Using xor ,and,not gates and wires,construct Half Subtractor.
 
 Repeat same steps to construct Full Subtractor
 
 Find RTL logic and timing diagram for both Subtractors
 
 End the program

# Program:
```
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.

Developed by: SivaramaKrishnan B 

RegisterNumber: 22006798

```

# Half Subtractor

```
module HalfSubtractor(A,B,Diff,Borrow);

input A,B;

output Diff,Borrow;

wire x;

xor (Diff, A,B);

not(x,A);

and(Borrow,x,B);

endmodule
```

# Full Subtractor

```
module FullSubtractor(A,B,C,Diff,Borrow);

input A,B,C;

output Diff,Borrow;

wire p;

assign Diff = ((A^B)^C);

not(p,A);

assign Borrow = ((p&B)|(p&C)|(B&C));

endmodule
```

# Output:

# HALF SUBRACTOR

# Truth Table
![Screenshot (82)](https://user-images.githubusercontent.com/119476322/215167353-15b8e628-0a88-4f24-9c6a-952f9df5f60a.png)

# RTL Realisation 
![Screenshot (83)](https://user-images.githubusercontent.com/119476322/215167388-663aba86-5023-4ecf-8879-2dcdbca986c6.png)

# Timing Diagram 
![Screenshot (84)](https://user-images.githubusercontent.com/119476322/215167437-a829d1ce-9384-4929-b541-d1e3d649c0e3.png)

#FULL SUBRCTOR 

# Truthtable
![Screenshot (85)](https://user-images.githubusercontent.com/119476322/215167507-73f39a9f-bf17-406a-9d70-77f1469795cb.png)

# RTL realization
![Screenshot (86)](https://user-images.githubusercontent.com/119476322/215167550-7b88e24d-43eb-4ba0-aeb6-9b9c27e93ad4.png)

# Timing diagram
![Screenshot (87)](https://user-images.githubusercontent.com/119476322/215167572-1b8f5877-83d6-4b38-9706-392de403d57d.png)

# Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
