### **INSTRUMENTATION AMPLIFIER**

- Instrumentation Amplifiers are basically used to amplify small differential signals. Instrumentation Amplifier provides the most important function of Common-Mode Rejection (CMR). It cancels out any signals that have the same potential on both the inputs. The signals that have a potential difference between the inputs get amplified.

- An Instrumentation Amplifier (In-Amp) is used for low-frequency signals (≪1 MHz) to provide a large amount of Gain. It amplifies the input signal rejecting Common-Mode Noise that is present in the input signal.

![image](https://github.com/user-attachments/assets/81176071-d497-4995-9fa1-10fe4a0b5ec3)

### **Applications**

- They are used extensively in Bio-medical applications like ECG’s and EEG’s.<br>
- Instrumentation Amplifiers are used where long-term stability is essential like Industrial applications that includes automation.<br>
- Instrumentation amplifiers are incorporated with pressure transducers in Weighing Systems to monitor various physical quantities such as weight, force, pressure, displacement and torque.<br>
- They are used in Gaming industry.<br>
- Instrumentation Amplifiers are also used in hand held batteries.<br>

### **Advantages**

- Offset voltage is minimized.<br>
- Voltage Gain is high as the configuration uses high precision resistors.<br>
- The Gain of the circuit can be varied by using specific value of resistor.<br>
- Non-linearity is very low.<br>
- Input impedance is very high to avoid loading down the input signal source and Output impedance is very low.<br>
- Common-mode rejection is very high.<br>

### **Disadvantage**

- The biggest disadvantage of Instrumentation Amplifier is the occurrence of noise when used for long range transmission purpose.<br>

### **KEY FEATURES**

- Differential gain<br>
- High common-mode rejection<br>
- High input impedance<br>
- Low output impedance<br>
- Low offset and low noise (in newer devices).<br>

---
### **Design an instrumentation amplifier using 3-OPamp Configuration with the following Constraints**

a) R1=R2=R3=R4=R5=R6= 100Kohm<br>
b) Differnce gain ADM = 20 V/V<br>
Find ACM (common mode gain) and Calculate CMRR for ADM = 20 V/V   and 50 V/V . Use Ltspice Simulator <br>

### **circuit diagram**

<img width="642" alt="image" src="https://github.com/user-attachments/assets/13c3448b-c699-4d00-8734-a58ee208f7af" />

### **Formula to find RG**

![image](https://github.com/user-attachments/assets/49e1f480-fc2e-47cc-a1f2-d4f58c13223a)

![WhatsApp Image 2025-04-18 at 19 22 15_c1615374](https://github.com/user-attachments/assets/7df39dc5-041b-4998-99f5-b438dd626caf)


![WhatsApp Image 2025-04-18 at 21 00 50_629d090e](https://github.com/user-attachments/assets/97cf0cfb-31b3-4e38-8865-fe048f1161a6)

| Desired Gain (A<sub>dm</sub>) | R<sub>G</sub> (Ohms) |
|------------------------------|----------------------|
| 10 V/V                       | 22.23 kΩ             |
| 20 V/V                       | 10.52 kΩ             |
| 50 V/V                       | 4.08 kΩ              |
| 100 V/V                      | 2.02 kΩ              |
| 200 V/V                      | 1.005 kΩ             |
| 1000 V/V                     | 200.2 Ω              |

### **1) For Adm= 20 v/v **
- **Transient Analysis**

<img width="853" alt="image" src="https://github.com/user-attachments/assets/c05b7830-94f7-41b8-bc35-4e5ef1f1ce93" />

- Analysis of Adm
- 11.06735109 / 2-1.44 = 19.8 ≈ 20 v/v

### **Transient Analysis for Acm**

<img width="959" alt="image" src="https://github.com/user-attachments/assets/a785c41c-98bd-4d76-afe8-7cd32ec2545d" />

 **Analysis of Acm**
 
- (195.22394 n)-(-195.16567 n) / 0.5 + 0.5 = 3.903 * 10^-7
- Acm = 3.903 * 10^-7
- CMRR = Adm / Acm
- 20 v/v / 3.903 * 10^-7 =  51.242 * 10^6
- 20log( 51.242 * 10^6) = 154.19 dB
  
### **2) For Adm= 50 v/v **
- **Transient Analysis**

<img width="958" alt="image" src="https://github.com/user-attachments/assets/a6aab529-99a1-4b59-aea0-cdaa64334cbf" />

- Analysis of Adm
- 11.06762148 / 1-0.76 = 49.5 ≈ 50 v/v

### **Transient Analysis for Acm**

<img width="959" alt="image" src="https://github.com/user-attachments/assets/ac81d207-10e0-4ebd-9e68-b5a6e1c2b7ca" />

- (195.22394 n)-(-195.16567 n) / 0.5 + 0.5 = 3.903 * 10^-7
- Acm = 3.903 * 10^-7
- CMRR = Adm / Acm
- 50 v/v / 3.903 * 10^-7 =  128.106 * 10^6
- 20log( 128.106 * 10^6 ) = 162.151 dB

  
### **3) For Adm= 10 v/v **

- **Transient Analysis**
<img width="956" alt="image" src="https://github.com/user-attachments/assets/11d62c59-4c81-4050-8ff4-3605584568e0" />

- Analysis of Adm
- 11.067460323 / 1.4-0.2 ≈ 10 v/v

### **Transient Analysis for Acm**

<img width="956" alt="image" src="https://github.com/user-attachments/assets/9546d2a5-c7bd-4573-87fd-7d526759e3d2" />

- (195.22394 n)-(-195.16567 n) / 0.5 + 0.5 = 3.903 * 10^-7
- Acm = 3.903 * 10^-7
- CMRR = Adm / Acm
- 10 v/v / 3.903 * 10^-7 =  25.621 * 10^6
- 20log( 25.621 * 10^6 ) = 148.171 dB

### **4) For Adm= 100 v/v **

- **Transient Analysis**  
<img width="953" alt="image" src="https://github.com/user-attachments/assets/233606b1-4d48-4799-834a-abc632aa5268" />

- Analysis of Adm
- 11.067469834 / 1.4-1.28 ≈ 100 v/v

### **Transient Analysis for Acm**

<img width="958" alt="image" src="https://github.com/user-attachments/assets/1da98992-216b-4d6a-83c3-f4efb6e4ea84" />

- (195.22394 n)-(-195.16567 n) / 0.5 + 0.5 = 3.903 * 10^-7
- Acm = 3.903 * 10^-7
- CMRR = Adm / Acm
- 100 v/v / 3.903 * 10^-7 =  256.21 * 10^6
- 20log( 256.21 * 10^6 ) = 168.171 dB

### **5) For Adm= 200 v/v **

- **Transient Analysis**  
<img width="956" alt="image" src="https://github.com/user-attachments/assets/92a8c9e9-c105-48ae-b33c-465202a70ef1" />


- Analysis of Adm
- 11.067 / 0.08-0.02 ≈ 200 v/v

### **Transient Analysis for Acm**

<img width="958" alt="image" src="https://github.com/user-attachments/assets/572af4eb-4310-4ac0-ad38-809ec4763639" />

- (195.22394 n)-(-195.16567 n) / 0.5 + 0.5 = 3.903 * 10^-7
- Acm = 3.903 * 10^-7
- CMRR = Adm / Acm
- 200 v/v / 3.903 * 10^-7 =  512.426 * 10^6
- 20log(  512.426 * 10^6 ) = 174.192 dB

 ### **6) For Adm= 1000 v/v **

- **Transient Analysis**

<img width="959" alt="image" src="https://github.com/user-attachments/assets/b0eafc80-87c3-4bec-bd6a-c13a128e1671" />

- Analysis of Adm
- 11.067 / 0.014-0.002 ≈ 1000 v/v

### **Transient Analysis for Acm**

<img width="956" alt="image" src="https://github.com/user-attachments/assets/4a248e09-6bc7-4b50-aad1-134f2ade6903" />

- (195.22394 n)-(-195.16567 n) / 0.5 + 0.5 = 3.903 * 10^-7
- Acm = 3.903 * 10^-7
- CMRR = Adm / Acm
- 1000 v/v / 3.903 * 10^-7 =  2.5621 * 10^9
- 20log(  2.5621 * 10^9 ) = 188.171 dB

### **Comparasion table**

| Desired Gain `A_dm` (V/V) | `R_G` (Ω)     | `A_cm` (V/V)            | CMRR (dB)    |
|---------------------------|---------------|--------------------------|--------------|
| 10                        | 22.23 k       | 3.903 × 10⁻⁷             | 148.171    |
| 20                        | 10.52 k     | 3.903 × 10⁻⁷             | 154.190    |
| 50                        | 4.08 k        | 3.903 × 10⁻⁷             | 162.151    |
| 100                       | 2.02 k        | 3.903 × 10⁻⁷             | 168.171    |
| 200                       | 1.005 k       | 3.903 × 10⁻⁷             | 174.192   |
| 1000                      | 200.2       | 3.903 × 10⁻⁷             | 188.171    |

