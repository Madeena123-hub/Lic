### **AIM: DC,AC and Transient Analysis of Common Source Amplifier using LTSpice**

**1.**<br>
**THEORY**<br>
A Common Source (CS) Amplifier is a basic MOSFET-based amplifier where the source terminal is common to both the input and output. It is widely used for voltage amplification in analog circuits.

**In this configuration:** <br>
The input signal is applied at the gate.<br>
The output is taken from the drain.<br>
The source is typically grounded or connected through a resistor.

![image alt](https://github.com/Madeena123-hub/Lic/blob/main/Screenshot%202025-02-15%20053848.png?raw=true) 
### **Component Details & Their Roles**

| **Component**       | **Value/Specification** | **Role in the Circuit** |
|---------------------|------------------------|-------------------------|
| **MOSFET Model**    | `CMOSN (TSMC 180nm)`   | Acts as the **main amplifying device** in the common-source configuration. |
| **Channel Length (L)** | **180 nm (0.18 µm)**  | Controls MOSFET **short-channel effects** and impacts transconductance (\( g_m \)). |
| **Channel Width (W)**  | **0.2091 µm**          | Determines **current driving capability** and affects gain. |
| **Threshold Voltage (\( V_{th} \))** | **0.366V** | The minimum gate voltage required to turn **ON** the MOSFET. |
| **Drain Resistor (\( R_D \))** | **2.749414941 kΩ**   | Converts **drain current (\( I_D \))** into **output voltage**; higher \( R_D \) increases gain but limits bandwidth. |
| **Supply Voltage (\( V_{DD} \))** | **1.8V** | Provides the necessary **power** for MOSFET operation. |
| **DC Bias Voltage (\( V_{in} \))** | **0.9V** | Ensures MOSFET is **in saturation region**, allowing proper amplification. |
| **AC Input Signal** | `SINE(0.9V 50mV 1kHz)` | Small **sinusoidal signal** applied at the **gate** for amplification. |
| **Amplitude of AC Input** | **50mV** | Determines the **input signal strength** to be amplified. |
| **Frequency of AC Input** | **1 kHz** | The frequency of the input **test signal** for amplification. |
| **Output Voltage (\( V_{out} \))** | **Measured at Drain** | The **amplified** and **inverted** version of the input signal. |

### DC,AC and Transient analysis
| **Analysis Type**  | **Purpose**                        | **Key Result**                     |
|-------------------|--------------------------------|--------------------------------|
| **DC Analysis**   | Determines **biasing point**   | Confirms MOSFET in **saturation** |
| **AC Analysis**   | Measures **gain & frequency response** | Calculates **Voltage Gain (\( A_v \))** |
| **Transient Analysis** | Observes **real-time behavior** | Shows **amplified and inverted output** |

### **DC ANALYSIS**

To determine the proper biasing for the MOSFET so that it operates in the saturation region with a desired drain current (ID = 55.55 µA).  
The analysis is performed using **.OP (Operating Point) analysis**, and power is given as **100 µW**.

1. **Assume Initial Drain Resistor (RD)**
   - Start with RD = 1kΩ.

2. **Run DC Simulation using .OP Analysis**
   - Obtain Vout (Drain Voltage) from the simulation.
   - Results:
     - Vout = 1.64727V
     - VDD = 1.8V
     - Power = 100 µW

3. **Calculate Drain Current (ID) using Power Formula:**
   - Formula: P = V × I
   - Given P = 100 µW and VDD = 1.8V:
     - ID = P / VDD = (100 µW) / (1.8V) = 55.55 µA

4. **Calculate New RD Value:**
   - Using the output voltage equation: Vout = VDD - ID * RD
   - Rearranging for RD:
     - RD = (VDD - Vout) / ID
   - Substituting values:
     - RD = (1.8V - 1.64727V) / (55.55 µA) = 2.749414941kΩ

5. **Replace RD with New Value**
   - Update RD in the circuit to 2.749414941kΩ and rerun the simulation.

6. **Iterative Width Calculation (W)**
   - Keep adjusting MOSFET Width (W) while maintaining Length (L = 180nm).
   - Repeat until ID = 55.55 µA is achieved.
   - **Final width found: W = 0.2091 µm (or 2091 nm).**

- Final RD = 2.749414941kΩ
- Final MOSFET Width (W) = **0.2091 µm**
- Biasing confirmed for correct MOSFET operation.
- .OP analysis verifies the correct operating point.

# MOSFET Width vs. Drain Current (ID)

| Width (W) in µm | Drain Current (ID) in µA |
|-----------------|-------------------------|
| 0.100          | 47.62                   |
| 0.150          | 50.00                   |
| 0.190          | 53.632                  |
| 0.200          | 54.624                  |
| 0.2091          | 55.55                   |

As the width (W) increases, the drain current (ID) also increases. The desired ID = **55.55 µA** was achieved at **W = 0.2091µm**.

![image alt](https://raw.githubusercontent.com/Madeena123-hub/Lic/e2884ffe5e6483ac27b8d6b585380654c2d9b409/Screenshot%202025-02-15%20055950.png)
![image alt](https://raw.githubusercontent.com/Madeena123-hub/Lic/391b45042d78792c58b533adc1f2b86f6dfec6ad/Screenshot%202025-02-15%20060040.png) 
**To check if the MOSFET is in the saturation region:**<br>

VDS > VOV<br>
VDS = vout = 1.64727V<br>
VOV = VGS-VTH = 0.9v-0.366v = 0.534v<br>
1.64727V > 0.534v<br>

### **AC ANALYSIS**
AC analysis is a frequency-domain simulation used to determine the gain, phase shift, and bandwidth of a circuit over a specified frequency range. It helps in analyzing the circuit’s behavior for different frequencies, which is essential for amplifier and filter design.

**Simulation Parameters:**
• Type of sweep: Decade  
• Number of points per decade: 5  
• Start frequency: 0.1 Hz  
• Stop frequency: 1 THz  

**Input Signal Parameters:**
• Waveform Type: Sine Wave  
• Amplitude: 50 mV  
• DC Offset: 0.9 V  
• Frequency: 1 kHz 

![image alt](https://raw.githubusercontent.com/Madeena123-hub/Lic/4f42b8073d32a4c5dc16c2596b857d1f35a5d6a4/Screenshot%202025-02-16%20041856.png) 
![image alt](https://raw.githubusercontent.com/Madeena123-hub/Lic/2d10d1e7464795842fdf58d109ee5d23dcd20b84/Screenshot%202025-02-16%20040310.png) 

Gain=-8.1606db
### **Transient analysis**

Transient Analysis is used to simulate the time-domain response of a circuit when a time-varying input (such as a sine wave or pulse) is applied. It helps in analyzing circuit behavior over time, including signal amplification, switching characteristics, and transient response.

**Transient Analysis Parameters:**
• Stop time: 5 ms  
• Step time: 1 µs  
• Time to start saving data: 0 s  

![image alt](https://raw.githubusercontent.com/Madeena123-hub/Lic/6a647b74104c4a1c6465cd706ee6fc54c51f54b2/Screenshot%202025-02-16%20044344.png) 
![image alt](https://raw.githubusercontent.com/Madeena123-hub/Lic/1aaa704b1243b06915342aed977369e1d3933232/Screenshot%202025-02-16%20043228.png) 


vout=1.64727v<br>
vin=0.9v<br>
Av=vout/vin=1.64727v/0.9v=1.8303v

### **Inference**
The MOSFET amplifier properly amplifies the signal with a gain of 1.8303v<br>
DC biasing is correct, ensuring good operation in the active region.<br>
AC analysis confirms the gain and frequency response, and transient analysis shows proper output waveforms.<br>
The circuit is suitable for low-frequency applications like audio and analog signal processing.<br>
There is 180 degree phase differnce between input and output



### **2nd**
**"In the second circuit, the resistor is replaced with a PMOS transistor to observe the differences in performance."**

![image alt](https://raw.githubusercontent.com/Madeena123-hub/Lic/7ffe4f824e63e51cdecf8da8d6dbb11d2e064707/Screenshot%202025-02-16%20095920.png) 

### **DC ANALYSIS**
**"In the second circuit, the resistor is replaced with a PMOS transistor. For Id=55.55uA, the required width (W) of the NMOS and PMOS transistor is found to be 0.31599 µm." **


![image alt](https://raw.githubusercontent.com/Madeena123-hub/Lic/a479d90884108446e40a1fc5f1a704cf919f96c6/Screenshot%202025-02-16%20101239.png) 


### **AC ANALYSIS**
With same Simulation and Input Signal Parameters

![image alt](https://raw.githubusercontent.com/Madeena123-hub/Lic/45e58f09e3fb84169d824bc2a3c1aa01dda783af/Screenshot%202025-02-16%20103519.png)
Gain=2.638db

### **Transient analysis**
with same Transient analysis Parameters
![image alt](https://raw.githubusercontent.com/Madeena123-hub/Lic/a479d90884108446e40a1fc5f1a704cf919f96c6/Screenshot%202025-02-16%20101239.png) 




