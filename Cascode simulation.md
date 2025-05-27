### **Cascode Differential Amplifier**

### **Abstract**

The presented circuit is a CMOS differential amplifier using long-tailed pair configuration with current mirror active load and tail current source. The differential pair (M1 and M2)
processes input signals, while M3-M4 act as active loads to increase gain. M5-M6 form a current mirror for output, and M7 supplies constant tail current, enhancing the amplifier's linearity 
and stability. This design enables high gain, low offset, and effective common-mode rejection, making it suitable for precision analog applications.

### **Intoduction**

This circuit represents a CMOS differential amplifier with an active load, used for amplifying the voltage difference between two input signals. It is widely employed in analog front ends, operational amplifiers, and signal processing 
blocks due to its high gain, differential input, and commonmode rejection capabilities.

### **Working Principle**

The input signals Vin1 and Vin2 are applied to the gates of transistors M1 and M2, forming a differential pair. These transistors control the current based on the input voltage difference.
The cascode transistors M3 and M4 improve the gain by increasing the output resistance. The current mirror formed by M5 and M6 reflects the current to the output node, providing high output impedance and thus better 
gain. M7 acts as a tail current source, ensuring a constantbias current for the differential pair, improving linearity and stability.

### **Technical Specifications**


Components: 
- 7 MOSFETs (M1 to M7) 
- Bias voltages: Vb1, Vb 
- Resistor R1 (optional for degeneration) 
Power Supply: 
- VDD = 1.8V 
Design Features: 
- Differential input: Vin1, Vin2 
- Cascode gain boosting (M3, M4) 
- Current mirror load (M5, M6) 
- Tail current source (M7)

### **Circuit Daigram**

![image](https://github.com/user-attachments/assets/3dd2aab1-53b9-4494-bd36-1dcb04eb1221)

![image](https://github.com/user-attachments/assets/b9e0e7a4-1411-4462-a852-74c68a1aa419)


**PARAMETER SELECTION AND CALCULATIONS**

- How to choose Vin1 and Vin2 ?
Vin1 = SINE(0.9 50m 10k)
Vin2 = SINE(0.9 -50m 10k)

This is a differential input where the common-mode voltage is 0.9 V and the differential swing is ±50 mV, resulting in a 
total peak-to-peak swing of 100 mV. This configuration ensures that transistors M1 and M2 remain in saturation and that the circuit operates in the small-signal region, which is 
ideal for gain testing. The value of 0.9 V for the commonmode voltage is chosen to be near mid-supply or slightly below VDD/2 to provide adequate headroom. With VDD set 
to 1.8 V, a common-mode voltage of 0.9 V is appropriate.


-How to Choose Vb for M7

This biases the current source transistor M7.To keep M7 in 
saturation, the condition VGS(7) > VDS(7) + Vth must be 
satisfied. Assuming the NMOS threshold voltage Vth is 
approximately 0.4 V, and using Vb = 0.6V,we have VGS = 
0.6V. Since the drain is at approximately 0.9 V,VDS ≈ 0.9V, 
which satisfies the saturation condition.

- How to Choose Vb1 (for M3, M4)
  
Vb1 = 1.2 V
This sets VGS for cascode transistors M3/M4.
To keep them in saturation:
VGS3=Vb1−VX where VX is the source of M3 (~0.9 V)
VGS=1.2−0.9=0.3 V
Assuming PMOS VTH ≈ 0.4 V
Choosing 1.2 V for Vb1 provides:
Enough voltage to keep M3, M4 in saturation

-Resistor R1
R1 = 10 kΩ

### Results

-Transient Analysis:
A transient analysis was run for 2 ms with 10 kHz sine wave inputs (50 mV amplitude, 0.9 V offset) applied differentially to Vin1 and Vin2. 
The output waveforms at Vout1 and Vout2 showed a stable sinusoidal response, confirming proper differential amplification by the cascode differential amplifier.

![image](https://github.com/user-attachments/assets/c98d0080-3dd6-4954-b203-c3e5941bbd42)

-Frequency Response:
AC analysis was performed from 0.1 Hz to 1 THz to observe the frequency behavior of the amplifier. The gain remained nearly constant at low frequencies and started to roll 
off near the high-frequency region, indicating the bandwidth of the cascode differential amplifier and its high-frequency performance.

![image](https://github.com/user-attachments/assets/d3e8fa95-3805-4f36-9bbf-db8aa33ceff9)

**PERFORMANCE TARGETS**

- Differential Gain 
- Output Swing 
- Common-Mode Rejection Ratio (CMRR) 
- Power Consumption
  
The performance of the cascode differential amplifier was evaluated based on differential gain, output swing, commonmode rejection ratio (CMRR), and power consumption. The 
differential gain was calculated from the transient simulation, where the differential output swing was approximately 240 mV peak-to-peak for a 100 mV peak-topeak input difference, resulting in a gain of 2.4 or 7.6 dB. 
The output swing, observed from Vout1, ranged between 1.35 V and 1.59 V, giving an effective swing of 240 mV. The CMRR was determined by comparing the differential 
gain (~15.85) to an estimated common-mode gain (~0.2), yielding a CMRR of approximately 38 dB. Power consumption was estimated based on the current drawn by 
the tail transistor (M7), which was approximately 100 µA under a supply voltage of 1.8 V, resulting in a total static power dissipation of about 180 µW.

**APPLICATIONS**
- Operational Amplifiers 
- Analog Front-End Circuits 
- Signal Processing Blocks 
- Data Converters 
- Sensor Interfaces
  
**CONCLUSION**
The cascode differential amplifier was designed and simulated successfully. It showed improved gain and bandwidth compared to a basic differential amplifier, making 
it suitable for high-frequency applications.
