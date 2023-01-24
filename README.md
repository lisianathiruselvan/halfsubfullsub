# halfsubfullsub

Experiment--03-Half-Subtractor-and-Full-subtractor

Implementation-of-Half-subtractor-and-Full-subtractor-circuit

AIM:

To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

Equipments Required:

Hardware – PCs, Cyclone II , USB flasher
Software – Quartus prime

Theory

Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

Half Subtractor Full Subtractor

Half Subtractor

The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed. 

![166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a](https://user-images.githubusercontent.com/119389971/214307294-38d4655b-6675-42a1-8a5c-d27930de83c3.png)


Sum = X'Y+XY' = X ⊕ Y Carry=X'Y

Full Subtractor

A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 


![166112541-24c68359-3de8-4674-ae22-8272ffc385ed](https://user-images.githubusercontent.com/119389971/214307405-762b98ae-0ab6-48d4-9b6a-05eece8e9cb7.png)

Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

Procedure

Write the detailed procedure here

Program:

Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.

Developed by: lisiana t

RegisterNumber: 22006964

Half Subtractor:
```
module half_sub(x, y, x1, d, b);
input x, y;
output x1, d, b;
xor(d, x, y);
not(x1, x);
and(b, x1, y);
endmodule
```
Full Subtractor:
```
module full_sub(x, y ,z, x1, x2, x3, x4, x5, d, b);
input x, y, z;
output x1, x2, x3, x4, x5, d, b;
xor(x1, x, y);
xor(d, x1, z);
not(x2, x);
and(x3, x2, y);
and(x4, x2, z);
and(x5, y, z);
or(b, x3, x4, x5);
endmodule
```
Output:

Truthtable

Half Subtractor:

![half_sub_truthtable](https://user-images.githubusercontent.com/119389971/214307451-a40bad3f-5d1f-4428-b516-9885b67afd45.png)



Full Subtractor:

![full_sub_truthtable](https://user-images.githubusercontent.com/119389971/214307474-920c6f96-3da3-4841-9df4-4cdb8b011270.jpg)


RTL realization

Half Subtractor:

![half_sub_rtl](https://user-images.githubusercontent.com/119389971/214307662-be775d4b-f96c-4390-a76e-19560050a195.png)


Full Subtractor:

![full_sub_rtl](https://user-images.githubusercontent.com/119389971/214307682-9c6ec73c-2722-43e7-8859-04f0a07104a9.png)

Timing diagram


Half Subtractor:

![half_sub_timingdiag](https://user-images.githubusercontent.com/119389971/214307620-6464bf82-21da-493c-af94-53cce90b6a21.png)


Full Subtractor:

![full_sub_timingdiag](https://user-images.githubusercontent.com/119389971/214307809-3c998aec-f7b8-4f40-99fe-86011c00f019.png)


Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.

