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
## Procedure
## Program:

Program to implement the given logic function using NAND and NOR gates and to verify its operations in quartus using Verilog programming.
```
Developed by: Goparapu Lutheesh
RegisterNumber:  212221230029
```


## QUESTION 01
```
USING NAND
module comblogic(A,B,C,D,F);
input A,B,C,D;
output F;
wire P,Q,R;
assign P = (~C&~B&~A);
assign Q = (~D&~C&~A);
assign R = (C&~(~B)&~A);
assign F= P&~Q&~R;
endmodule
```
## QUESTION 02
```
USING NOR
module comblogic(a,b,c,d,f);
input a,b,c,d;
output F;
wire f1,f2,f3,f4;
assign f1 = c&(~b)&a;
assign f2 = d&(~c)&a;
assign f3 = c&(~b)&a;
assign f4 = ~(f1|f2|f3);
not(F,f4);
endmodule
```
## RTL realization

# Output:
### Question 01
## RTL
![Screenshot 2022-09-27 172921](https://user-images.githubusercontent.com/94154531/192554343-a1b03213-2d28-4450-af8d-e9164302a518.jpg)
## Timing Diagram

![192535468-14cf07df-60f1-4b71-95d3-49535ba9f8f4](https://user-images.githubusercontent.com/94154531/192554616-b78d70a9-1935-4cd7-ab70-74db16bd9119.jpg)
## Truth Table
![192535507-5e25c1ef-6654-4cb3-af31-6e25f0c794ce](https://user-images.githubusercontent.com/94154531/192554763-1ea93e07-8759-4510-b470-f91da6b2024a.jpg)
# Question 02
## RTL
![192535367-31b82494-58f7-47df-aa80-0e72ebac4292](https://user-images.githubusercontent.com/94154531/192555341-d59784d9-f063-4cad-b783-059590b9d61f.jpg)
## Timing diagram
![192535468-14cf07df-60f1-4b71-95d3-49535ba9f8f4](https://user-images.githubusercontent.com/94154531/192555479-7ce3ea8a-e56f-4f35-ae19-8c6474e42811.jpg)
## Truth Table
![192535507-5e25c1ef-6654-4cb3-af31-6e25f0c794ce](https://user-images.githubusercontent.com/94154531/192555595-3479b8d9-295c-4f04-a109-b17ae45355ac.jpg)


## Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
