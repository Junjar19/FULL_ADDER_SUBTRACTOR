**Implementation-of-Full-Adder-and-Full-subtractor-circuit**

**AIM:**

To design a Full Adder and Full Subtractor circuit and verify its truth table in Quartus using Verilog programming.

**Equipments Required:**

Hardware – PCs, Cyclone II , USB flasher

Software – Quartus prime

**Full Adder and Full Subtractor**

**Full Adder**

Full adder is a digital circuit used to calculate the sum of three binary bits. It consists of three inputs and two outputs. Two of the input variables, denoted by A and B, represent the two significant bits to be added. The third input, Cin, represents the carry from the previous lower significant position. Two outputs are necessary because the arithmetic sum of three binary digits ranges in value from 0 to 3, and binary 2 or 3 needs two digits. The two outputs are sum and carry.

Sum =A’B’Cin + A’BCin’ + ABCin + AB’Cin’ = A ⊕ B ⊕ Cin 
Carry = AB + ACin + BCin

**Figure -1 FULL ADDER**
![Screenshot 2024-11-16 222019](https://github.com/user-attachments/assets/cb3b55ca-1fa8-4001-bea9-00c1542ab5a2)


**Full Subtractor**

A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow.

Diff = A ⊕ B ⊕ Bin 
Borrow out = A'Bin + A'B + BBin

![Screenshot 2024-11-16 223803](https://github.com/user-attachments/assets/d78ad766-cb49-4af0-9134-670028dc96e5)

**Truthtable**

a	b	cin	sum	carry
0	0	0	0	0
0	0	1	1	0
0	1	0	1	0
0	1	1	0	1
1	0	0	1	0
1	0	1	0	1
1	1	0	0	1
1	1	1	1	1
![image](https://github.com/user-attachments/assets/22267702-fbf5-45db-8967-a4b7017b860d)

a	b	bin	difference	borrow
0	0	0	0	0
0	0	1	1	1
0	1	0	1	1
0	1	1	0	1
1	0	0	1	0
1	0	1	0	1
1	1	0	0	0
1	1	1	1	0
![image](https://github.com/user-attachments/assets/97281233-d92d-4431-961b-6b9e6e6cc904)



**Procedure**

Write the detailed procedure here

Procedure for Full Adder 
Inputs and Outputs:
The Full Adder has three inputs: 
𝑎
a, 
𝑏
b, and 
𝑐
𝑖
𝑛
cin (carry-in). It outputs sum and carry (carry-out).

Sum Calculation:
The sum is computed by performing an XOR operation on the three inputs. This determines the result of adding 
𝑎
a, 
𝑏
b, and 
𝑐
𝑖
𝑛
cin.

Carry Calculation:
The carry is calculated based on the combinations of 
𝑎
a, 
𝑏
b, and 
𝑐
𝑖
𝑛
cin. It indicates whether a carry-over is generated.



Procedure for Full Subtractor
Inputs and Outputs:
The Full Subtractor takes three inputs: 
𝑎
a, 
𝑏
b, and 
𝑏
𝑖
𝑛
bin (borrow-in). It produces two outputs: difference and borrow (borrow-out).

Difference Calculation:
The difference is calculated by performing an XOR operation on the inputs. It determines the result of subtracting 
𝑏
b and 
𝑏
𝑖
𝑛
bin from 
𝑎
a.

Borrow Calculation:
The borrow is calculated based on the inputs, determining whether borrowing is needed from the next higher bit.

Logic Gates Used:
The Full Subtractor uses XOR gates for the difference, AND gates for detecting borrow conditions, and OR gates to combine the borrow results.

Application in Arithmetic:
Full Subtractors are used in binary subtraction and multi-bit subtractors.

Logic Gates Used:
The Full Adder uses XOR gates for the sum, AND gates for detecting carry conditions, and OR gates to combine the carry results.

Application in Arithmetic:
Full Adders are used in multi-bit binary addition circuits and ALUs.



**Program:**

i)FULL ADDER
module fulladder(a, b, cin, sum, carry);
input a, b, cin;
output sum, carry;
assign sum = ( (a ^ b) ^ cin );
assign carry = ( (a & b) | ( cin & (a ^ b) ) );
endmodule

ii)FULL SUBTRACTOR
module fullsub(a,b,bin,difference,borrow);
input a,b,bin;
output difference,borrow;
assign difference = (a ^ b)^bin;
assign borrow= ( a & b) | ( bin & ((a ^ b )));
endmodule

/* Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming. Developed by: RegisterNumber:
*/

**RTL Schematic**


![Screenshot 2024-11-16 222405](https://github.com/user-attachments/assets/d7c23745-6a45-4f6d-8f9f-881486e100b8)

![Screenshot 2024-11-16 223933](https://github.com/user-attachments/assets/d1f76a05-1625-4cbc-ac66-4ae16fd885c3)

**Output Timing Waveform**

**Result:**

Thus the Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.



