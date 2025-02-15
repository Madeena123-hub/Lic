### **DC,AC and Transient Analysis of Common Source Amplifier using LTSpice**

**1.**

A Common Source (CS) Amplifier is a basic MOSFET-based amplifier where the source terminal is common to both the input and output. It is widely used for voltage amplification in analog circuits.

**In this configuration:** 
The input signal is applied at the gate.
The output is taken from the drain.
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

- Final RD = 2.75kΩ
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
![image alt](https://raw.githubusercontent.com/Madeena123-hub/Lic/e2884ffe5e6483ac27b8d6b585380654c2d9b409/Screenshot%202025-02-15%20055950.png)  ![image alt](https://raw.githubusercontent.com/Madeena123-hub/Lic/391b45042d78792c58b533adc1f2b86f6dfec6ad/Screenshot%202025-02-15%20060040.png) 

