### **CURRENT MIRROR**
**What is Current Mirror?**

A current mirror is an electronic circuit used in analog and mixed-signal applications to replicate or mirror the current flowing through one active device and produce an identical current in another device. The primary purpose of a current mirror is to maintain a consistent current in multiple parts of a circuit, ensuring that different components receive the same current for precise operation.

**Use of Current Mirror**
A current mirror circuit is used in electronic circuits to replicate or mirror a current from one part of the circuit and provide an identical current in another part. The primary purpose of a current mirror is to ensure that different components or branches of a circuit receive the same current, maintaining consistency and precision in the operation of the circuit.

<img width="220" alt="image" src="https://github.com/user-attachments/assets/a7de2ec1-e4ba-435a-a21e-ee1db83a5963" />

Explaination: This simplest form of a current mirror consists of two transistors, where the current is replicated (or mirrored) by ensuring that the transistors are matched in their characteristics. Typically, one transistor is configured to set a reference current, and the other transistor mirrors this current, maintaining an equivalent current in its branch.

**Applications of Current Mirror**
Biasing Circuits
Current Sources
Differential Amplifiers
Cascode Amplifiers

**Advantages**
Simple and easy to design.
Minimal transistor count.

**Disadvantages**
Poor output impedance.
Limited accuracy due to channel-length modulation.

### **AIM:Design and analyis current mirror circuit as active load in amplifier circuit**

### **1st one**
**Case 1: For mirror ratio 1:1**

<img width="403" alt="image" src="https://github.com/user-attachments/assets/49aa33e6-b181-44ba-a149-aa5c12f2fc00" />

<img width="316" alt="image" src="https://github.com/user-attachments/assets/608a48e4-726b-40ab-aa12-1e3152903946" />

RD=820ohm<br>
Iref=100uA<br>
VDD=1.8v<br>

**Current variation because of vx and vout value**
ID=1/2*un*cox*w/L*(VGS-VTH)^2*(1+lambda VDS)


| Iref (µA) | I_appeared (µA) | W/L (MOSFET 2) | W/L (MOSFET 4) | Vx (V)   | Vout (V)  |
|-----------|----------------|----------------|----------------|----------|-----------|
| 100       | 103.506        | 180n/180n      | 180n/180n      | 1.27535  | 1.71512   |
| 100          |    100.715            |  500n/500n              |  500n/500n                |     1.4375     |  1.71741         |
|  100         |       100.648         |    1u/1u            |       1u/1u            |  1.39727        |    1.71747       |
|   200        |  197.637              |       1u/1u            |   2u/1u                |   1.39727       |   1.63794        |
|   50        |   52.1312             |        1u/1u           |      0.5u/1u             |       1.39727     |  1.75725         |

### **2nd one**

Given:
Av > -10 v/v <br>
vdd = 1.8v <br>
p <= 1mv  <br>
Itotal = p / vdd  <br>
Itotal = 1mv / 1.8v = 0.555m <br>
Itotal = Iref + Ix <br>
Iref = 0.2777m <br>
**length = 180nm**
<img width="443" alt="image" src="https://github.com/user-attachments/assets/a33e6821-dc76-4c90-90a7-dbe270e113db" />


| parameters| M1| M2 | M3 |
|----------|----------|----------|----------|
| Model         |   CMOSP       | CMOSP         |   CMOSN       |
|   length(m)       |    180n      |    180n      |    180n      |
|    Width(m)     |  10u         |10u          |      6.527843u    |
|    Current(A)   |    0.2777m      | 0.2777m          |     0.2777m      |

set Vin that the Mosfet should be in saturation region, than changing width of third MOSFET set VX=Vout <br>
for 6.527843u width of 3rd MOSFET i got VX=VOUT (0.966806V = 0.966806V) 

**DC Analysis**

<img width="284" alt="image" src="https://github.com/user-attachments/assets/800a118a-b5f4-41ee-ad96-b104bb29b422" />

**Transient Analysis**
<img width="957" alt="image" src="https://github.com/user-attachments/assets/b937a3fe-6051-4691-94f5-f54ae3a733de" />

to get the gain approx 10V/V change  the amplitude <br>
<img width="959" alt="image" src="https://github.com/user-attachments/assets/2bfa9e9c-a4ee-49c7-b981-855099d9bfde" />

expected gain: 10 V/V <br>
Obtained gain: 10.5 v/v <br>
Av= vout / vin <br>
Av= (1.632-.154)/(770m-630m) 

**AC Analysis**

<img width="956" alt="image" src="https://github.com/user-attachments/assets/8f453c65-aadc-4bfb-8e7a-a2f6aeb8b5bf" />

AV(db) = 26.602db <br>
3db Bandwidth = 294.45011MHz. 

**DC Sweep**
<img width="949" alt="image" src="https://github.com/user-attachments/assets/c7b5e124-6d68-4b39-8cca-3aa46ccc87b7" />

**Now for length= 500nm**

| parameters| M1| M2 | M3 |
|----------|----------|----------|----------|
| Model         |   CMOSP       | CMOSP         |   CMOSN       |
|   length(m)      |    500n      |    500n      |    500n      |
|    Width(m)   |  10u         |10u          |     16.89664u   |
|    Current(A)   |    0.2777m      | 0.2777m          |     0.2777m      |

changing width of third MOSFET set VX=Vout <br>
for 16.89664u  width of 3rd MOSFET i got VX=VOUT (0.64368v = 0.64368v) 

**DC operating Point**

<img width="277" alt="image" src="https://github.com/user-attachments/assets/e3e8b151-45bf-4304-a7ae-0fbceeed26ff" />

**AC Analysis**
<img width="956" alt="image" src="https://github.com/user-attachments/assets/83f9386f-cc2e-4c1e-8768-0bb89651d3e4" />

AV(db) = 34.11db <br>
3db Bandwidth = 75.752503MHz.

**Transient Analysis**
<img width="958" alt="image" src="https://github.com/user-attachments/assets/2399f916-ccbb-47fd-a329-9889c77be8b2" />

obtained gain is 28.475v/v

**Now for length= 1um**

| parameters| M1| M2 | M3 |
|----------|----------|----------|----------|
| Model         |   CMOSP       | CMOSP         |   CMOSN       |
|   length(m)      |  1u     |    1u     |   1u |
|    Width(m)   |  10u         |10u          |     31.18954u   |
|    Current(A)   |    0.278m      | 0.278m          |     0.278m      |

**DC operating Point**
<img width="280" alt="image" src="https://github.com/user-attachments/assets/cb5948f0-4c59-45a7-a15a-4324a33771cd" />

**AC analysis**
<img width="956" alt="image" src="https://github.com/user-attachments/assets/6994d7bc-d111-4d74-a90b-7cdd4c6737b4" />

**Transient Analysis**
<img width="947" alt="image" src="https://github.com/user-attachments/assets/e80e15e4-6fd9-4856-b360-b7d6fa627327" />

**Case 2: For mirror ratio 1:2**
**length=180nm**

<img width="562" alt="image" src="https://github.com/user-attachments/assets/96d3877d-343a-4e78-938b-1ce51c8acad4" />

**DC operating Point**
<img width="284" alt="image" src="https://github.com/user-attachments/assets/6d04b53d-1b73-4238-8ffc-4b086c984bb3" />

**AC analysis**
<img width="957" alt="image" src="https://github.com/user-attachments/assets/7478425d-9cf4-4374-9f53-7caaca79866b" />

**Transient Analysis**

<img width="959" alt="image" src="https://github.com/user-attachments/assets/ae386b37-37c6-437d-8020-4304cf38f149" />

### **for length=500nm**
| parameters| M1| M2 | M3 |
|----------|----------|----------|----------|
| Model         |   CMOSP       | CMOSP         |   CMOSN       |
|   length(m)      |  190n    |    180n   |   180n |
|    Width(m)   |  20u         |20u          |     11.0123u  |
|    Current(A)   |    0.18m      | 0.18m          |     0.18m      |

**DC operating Point**
<img width="284" alt="image" src="https://github.com/user-attachments/assets/c1220a36-76ab-47f5-a83d-c3bc8983de8b" />

**AC analysis**
<img width="959" alt="image" src="https://github.com/user-attachments/assets/eb8b1d98-1c2d-485b-87a7-78c1156d5561" />

**Transient Analysis**
<img width="959" alt="image" src="https://github.com/user-attachments/assets/4c7a98be-7b00-4a44-b390-27da1ab6b8f5" />

### **circuit-3**
Circuit daigram:
<img width="491" alt="image" src="https://github.com/user-attachments/assets/6baeb64f-68b3-4e68-800f-85b23538b196" />

**DC operating Point**
<img width="290" alt="image" src="https://github.com/user-attachments/assets/821dc309-227b-4be9-9e6d-eaf18ee240bf" />

**AC analysis**
<img width="957" alt="image" src="https://github.com/user-attachments/assets/5167d4ed-ee54-4e5c-8aa7-810a8b57e0cf" />

**Transient Analysis**
<img width="957" alt="image" src="https://github.com/user-attachments/assets/9f95466c-0ffd-43bc-ab44-3ed39933d982" />

















