**DC,AC and Transient Analysis of Common Source Amplifier using LTSpice**

**1.**

A Common Source (CS) Amplifier is a basic MOSFET-based amplifier where the source terminal is common to both the input and output. It is widely used for voltage amplification in analog circuits.

**In this configuration:** 
The input signal is applied at the gate.
The output is taken from the drain.
The source is typically grounded or connected through a resistor.
![image alt](https://raw.githubusercontent.com/Madeena123-hub/Lic/f4652ef83b55e58b655bd7b14e00a048523df175/Screenshot%202025-02-15%20023611.png) 
### **Component Details & Their Roles**

| **Component**       | **Value/Specification** | **Role in the Circuit** |
|---------------------|------------------------|-------------------------|
| **MOSFET Model**    | `CMOSN (TSMC 180nm)`   | Acts as the **main amplifying device** in the common-source configuration. |
| **Channel Length (L)** | **180 nm (0.18 µm)**  | Controls MOSFET **short-channel effects** and impacts transconductance (\( g_m \)). |
| **Channel Width (W)**  | **0.21 µm**          | Determines **current driving capability** and affects gain. |
| **Threshold Voltage (\( V_{th} \))** | **0.366V** | The minimum gate voltage required to turn **ON** the MOSFET. |
| **Drain Resistor (\( R_D \))** | **2.9 kΩ**   | Converts **drain current (\( I_D \))** into **output voltage**; higher \( R_D \) increases gain but limits bandwidth. |
| **Supply Voltage (\( V_{DD} \))** | **1.8V** | Provides the necessary **power** for MOSFET operation. |
| **DC Bias Voltage (\( V_{in} \))** | **0.9V** | Ensures MOSFET is **in saturation region**, allowing proper amplification. |
| **AC Input Signal** | `SINE(0.9V 50mV 1kHz)` | Small **sinusoidal signal** applied at the **gate** for amplification. |
| **Amplitude of AC Input** | **50mV** | Determines the **input signal strength** to be amplified. |
| **Frequency of AC Input** | **1 kHz** | The frequency of the input **test signal** for amplification. |
| **Output Voltage (\( V_{out} \))** | **Measured at Drain** | The **amplified** and **inverted** version of the input signal. |
