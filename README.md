# Experiment--03-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime
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

Write the detailed procedure here 

## Program:

module Halfsubtractor(A,B,Diff,Borrow);
input A,B;
output Diff,Borrow;
wire x;
xor (Diff,Borrow);
not(x,A);
and(Borrow,x,B);
endmodule


module Fullsubtractor(A,B,C,Diff,Borrow);
input A,B,C;
output Diff,Borrow;
wire p;
assign Diff = ((A^B)^C);
not(p,A);
assign Borrow = ((p&B)|(p&C)|(p&C));
endmodule


/*
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by: panimalar.p
RegisterNumber:  22009107
*/

## Output:

## Truthtable
![Screenshot (74)](https://user-images.githubusercontent.com/121490826/214042699-ed2fe77f-e859-41f4-969b-54a9397490e2.png)

![Screenshot (84)](https://user-images.githubusercontent.com/121490826/214042976-05b03fae-c7d3-4b39-97d3-729fa18730d8.png)


##  RTL realization
![Screenshot (85)](https://user-images.githubusercontent.com/121490826/214043564-4e0428f9-e0f3-4126-b484-72011416792f.png)

![Screenshot (86)](https://user-images.githubusercontent.com/121490826/214043910-84c3c476-19fc-4c78-b99a-f14f55cf3e7c.png)

## Timing diagram 
![Screenshot (87)](https://user-images.githubusercontent.com/121490826/214044595-dc3f3ffe-d2c1-499d-8343-36b78e200436.png)

![Screenshot (88)](https://user-images.githubusercontent.com/121490826/214044831-05ee97d7-e433-440c-b360-00fc14b77e04.png)



## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
