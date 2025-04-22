# FULL_ADDER_SUBTRACTOR

Implementation-of-Full-Adder-and-Full-subtractor-circuit

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

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/0f30ba51-5ffb-4198-845f-18e054f675e7)

**Figure -1 FULL ADDER**

**Full Subtractor**

A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow.

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/02b24f51-ab51-4304-9ad6-7b81ffc1ead5)

Diff = A ⊕ B ⊕ Bin 

Borrow out = A'Bin + A'B + BBin

**Truthtable**

![WhatsApp Image 2025-04-22 at 22 36 14_d8c59f94](https://github.com/user-attachments/assets/0e478572-6b94-4186-b5d6-71c66455e404)

![WhatsApp Image 2025-04-22 at 22 36 21_fb190da1](https://github.com/user-attachments/assets/82bc50d4-9866-4224-b71d-15ab03dd86b0)


**Program:**

Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.

Developed by: Lorena Avelyn R

RegisterNumber:212224040174

FULL ADDER
```
module FAS(a, b, c, sum, carry);
    input a;
    input b;
    input c;
    output sum;
    output carry;
	 reg sum,carry;
	 reg t1,t2,t3;
	 always @ (a or b or c) begin
	 sum = (a^b)^c;
	 t1=a & b;
	 t2=b & c;
	 t3=a & c;
	 carry=(t1 | t2) | t3;
	 end
endmodule

```
FULL SUBTRACTOR
```
module FAS1(a, b, cin, diff, borrow);
    input a;
    input b;
    input cin;
    output diff;
    output borrow;
	 reg t1,t2,t3;
	 reg diff,borrow;
	 reg abar;
	 always @ (a or b or cin) begin
	 abar= ~ a;
	 diff = (a^b)^cin;
	 t1=abar & b;
	 t2=b & cin;
	 t3=cin & abar;
	 borrow=(t1 | t2) | t3;
	 end
	endmodule

```

**RTL Schematic**

  ![WhatsApp Image 2025-04-22 at 22 21 57_c17e063b](https://github.com/user-attachments/assets/4d68bc05-6a15-4e1f-af9d-9725222eb765)

  ![WhatsApp Image 2025-04-22 at 22 31 22_8441dbac](https://github.com/user-attachments/assets/f0d9ecb3-9e10-4e4c-82a6-b3f5cfa7b4e6)

**Output Timing Waveform**

![WhatsApp Image 2025-04-22 at 22 21 56_333ac5e4](https://github.com/user-attachments/assets/641d20c8-2697-444d-94d9-1f3dc21d1253)

![WhatsApp Image 2025-04-22 at 22 31 23_42b117d3](https://github.com/user-attachments/assets/97a978fe-44e2-4623-a74b-1b1c7b09c000)


**Result:**

Thus the Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.



