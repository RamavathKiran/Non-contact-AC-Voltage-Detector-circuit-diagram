# Non-contact-AC-Voltage-Detector-circuit-diagram
What is a Non-contact AC voltage detector?

It is an AC voltage detector, that can be used to test live wires without any connection, hence the name.

Therefore, it is safer than the neon screwdriver when tested on AC wires and lowers the chance of getting an electric shock while working with high AC voltage.
How does Non-contact AC Voltage Detector circuit work?
Usually, there will be an electric and magnetic field surrounding a live wire created by the flowing of AC current. We can use this phenomenon to detect if a wire still has current inside it, by using an antenna as a detector. Which is the main principle of these circuits.


<img width="490" height="200" alt="image" src="https://github.com/user-attachments/assets/f40784fd-abf4-443c-9100-f0429a8105d0" />

When we put the antenna near AC wires if it detects a magnetic field around that wire, the LED will glow dimly and at the same time, the buzzer emits a high frequency buzzing.

The nearer the antenna from the AC wires, the brighter the LED will get. The buzzing of the buzzer will also be louder.
During the testing process, we should avoid letting the antenna touch the wires directly.
Let’s Create Non-contact AC voltage detector circuits
There are two versions of these circuits in this post. The difference is one of them uses transistors as a core and another uses CD4060 instead. Their function is the same.
Transistors Version
The antenna will converter the magnetic field into a very very small amount of current, and then amplify it with a very high gain amplifier.

This amplified current will then power a LED or buzzer for our visual or sound feedback.

<img width="551" height="317" alt="image" src="https://github.com/user-attachments/assets/29768fe5-5c44-40cc-849a-a2f80bf56b54" />

For the High gain amplifier, we pick the Darlington Transistor pair because it is easy and high efficiency. To make it easier to understand see the illustration below

<img width="589" height="377" alt="image" src="https://github.com/user-attachments/assets/394ac650-8d91-418b-b063-6ce45c8b7ec4" />

Here is a step-by-step process.

#1 The antenna inducts very little electrical energy or AC main signal that frequency of 50Hz (60Hz) into B of Q1.
#2 Makes a higher current flow through R1, C to E of Q1.
#3 Next a higher current flow through R2, C to E of Q2.
#4 Finally, the highest current flow through R3, LED1, C to E of Q3, causing LED1 to glow or flash.
My daughter said it was easy to understand. It works like a tiny water valve, controlling the next big water valve more and more.

The current gain of the Darlington pair is equal to the gain of Each of them (Q1, Q2, Q3) multiplied together. If uses BC547 NPN type with popular to use in many circuits. They have about 8,000 gains. so, they have a very high sensitivity.

Then, see the full circuit diagram. We add a piezo buzzer across LED1 and R3 to emit an alarm to indicate hum tone as the AC main frequency.

This era is very convenient, if you want a buzzer sound, use only one. It has its own buzzer circuit, reducing the circuit to less.
<img width="557" height="440" alt="image" src="https://github.com/user-attachments/assets/8b2de85a-5113-4d3e-83af-93a84ed3c6d8" />

Circuit Overview
1.Antenna/Probe: Detects the AC electromagnetic field.

2.Q1, Q2, Q3 (NPN transistors): Amplify the weak signal.

3.R1, R2, R3: Bias and current-limiting resistors.

4.LED1: Indicates presence of AC voltage.

5.B1 (9V Battery): Powers the circuit.

6.S1: On/off switch.
Current Path and Calculation
Let’s assume the LED turns on fully when detecting AC voltage.

Step 1: Base Current to Q1
The antenna detects an EM field, inducing a small voltage (~mV), providing a small base current to Q1. This current is minimal and difficult to measure, but let’s denote it as:

𝐼
𝐵
1
≈
few 
𝜇
𝐴
I 
B1
​
 ≈few μA

Step 2: Q1 and Q2 as Darlington Pair
Transistors Q1 and Q2 are in a Darlington configuration, giving a high current gain:

Total gain: 
𝛽
𝑡
𝑜
𝑡
𝑎
𝑙
=
𝛽
𝑄
1
×
𝛽
𝑄
2
β 
total
​
 =β 
Q1
​
 ×β 
Q2
​
 

Assume each has 
𝛽
=
100
β=100, so 
𝛽
𝑡
𝑜
𝑡
𝑎
𝑙
=
100
×
100
=
10
,
000
β 
total
​
 =100×100=10,000

So even a small base current into Q1 (say 
1
𝜇
𝐴
1μA) can result in:

𝐼
𝐶
2
=
10
,
000
×
1
𝜇
𝐴
=
10
 
𝑚
𝐴
I 
C2
​
 =10,000×1μA=10mA

Step 3: Current Through LED and Q3
Q3 receives base current from Q2 collector (through R3):

Let’s assume Q3 is fully turned on (saturation).

Now calculate current through LED and Q3 using Ohm’s Law:

Supply voltage 
𝑉
𝐶
𝐶
=
9
𝑉
V 
CC
​
 =9V

LED forward voltage 
𝑉
𝐿
𝐸
𝐷
≈
2
𝑉
V 
LED
​
 ≈2V

V_CE(sat) of Q3 ≈ 0.3V

R3 = 1kΩ

Voltage across R3 = 9V - 2V (LED) - 0.3V (Q3) = 6.7V

So:

𝐼
𝐿
𝐸
𝐷
=
6.7
𝑉
1
𝑘
Ω
=
6.7
 
𝑚
𝐴
I 
LED
​
 = 
1kΩ
6.7V
​
 =6.7mA
This is the current flowing through R3 → LED1 → Q3 → GND when AC is detected.

