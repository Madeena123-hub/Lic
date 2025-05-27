### ** Monostable multivibrator using 555 timer IC **

![image](https://github.com/user-attachments/assets/f2662e75-d999-4a0f-82fb-f574dcfc4052)


**1. Aim**

Generate pulse of width 0.5 ms using input triggers.

**2. Theory**

A monostable multivibrator is a circuit that has one stable state and one temporary state. Using a 555 timer IC in monostable mode, the circuit generates a single output pulse when triggered. The pulse duration is set by an external resistor and capacitor using the formula 
T=1.1×R×C. This setup is useful for delay timers, pulse generation, and switch debouncing.

Where:

R = Resistance in ohms
C = Capacitance in farads

In monostable mode:

-The 555 Timer has one stable state (LOW) and one quasi-stable state (HIGH).
-Upon receiving a negative trigger pulse (when pin 2 drops below 1/3 Vcc), the timer output switches from LOW to HIGH.
-It remains HIGH for a time duration determined by an external resistor (R) and capacitor (C) connected to the circuit.
-Once the capacitor charges to 2/3 Vcc, the output returns to LOW automatically.
-The circuit has one stable state (LOW) and one quasi-stable state (HIGH).
-Upon receiving a LOW-going trigger pulse at pin 2, the timer output (pin 3) transitions from LOW to HIGH.
-The HIGH state persists for a time period determined by the RC time constant, after which the timer automatically returns to LOW.
-This behavior is internally managed by voltage comparators, a flip-flop, and a discharge transistor within the IC.

### **3.working**

A monostable multivibrator works by staying in a stable state under normal conditions.When an external trigger pulse is applied,  the circuit temporarily shifts to an unstable state (for a pre-defined time) and then returns automatically to the stable state.

**4.Calculation**

Given: T = 0.5 ms = 0.5 × 10⁻³ seconds C = 1 µF = 1 × 10⁻⁶ farads

Formula: T = 1.1 × R × C

R = (0.5 × 10⁻³) / (1.1 × 1 × 10⁻⁶) R = 0.0005 / 0.0000011 R ≈ 454.54 Ω

** 555 Timer Monostable Configuration : **
Pin 1 → GND
Pin 2 → Trigger (LOW to activate)
Pin 3 → Output
Pin 4 → Reset → tied to Vcc
Pin 5 → Control → 0.01 µF to GND
Pin 6 → Threshold
Pin 7 → Discharge
Pin 8 → Vcc (+5V)
Connect resistor (R) between Vcc and pin 7
Connect capacitor (C) between pin 6 and GND
Join pins 6 & 7 together
Apply trigger pulse to pin 2 (e.g., push-button)
Observe output at pin 3 (LED or oscilloscope)


**5.Procedure**

1.Connect the 555 timer in monostable mode as per the circuit diagram.
2.Choose R = 470 Ω and C = 1 µF for a pulse width of approximately 0.5 ms.
3.Connect a signal generator or push-button to provide a trigger at pin 2.
4.Observe the voltage at:
5.Output pin 3
6.Capacitor charging at pin 6
7.Measure the width of the output pulse using an oscilloscope or simulation software.
8.Verify the output pulse width matches the theoretical value.

**frequency and time period**

![image](https://github.com/user-attachments/assets/343a70c1-51d1-4fc0-bb21-90ab9cb45987)

**6.circuit daigram**

<img width="389" alt="image" src="https://github.com/user-attachments/assets/220c023c-455e-4016-afa5-a7fded1e5ab4" />


**7.simulation results**

<img width="311" alt="image" src="https://github.com/user-attachments/assets/f5eac499-0cd6-41f3-ba00-fd4178ebdf95" />


**8.Result**

The 555 timer in monostable mode successfully generates a single output pulse when the trigger voltage drops below 1/3 Vcc.

### 9.Applications

- Pulse generation  
- Switch debouncing  
- Delay timer circuits  
- Frequency divider  
- Missing pulse detection  
- Timing control in digital circuits  

### 10.Key Features

- Generates a single, stable output pulse  
- Time duration set by external R and C  
- Easy to design and implement  
- Uses widely available 555 timer IC  
- Works with low power supply (typically 5V–15V)  
- Reliable and low-cost timing solution  


**11.Inference**
When the trigger voltage < 1/3 Vcc, the 555 timer recognizes it as a valid trigger.
This causes the output (pin 3) to go HIGH for a specific time period.
The capacitor charges during this time, determining the pulse width.
After the time elapses, the output returns to LOW, completing the monostable operation.

**12.CONCLUSION**

The NE555 timer configured in monostable mode provides accurate, predictable timing pulses when triggered by clean falling edges. In this simulation, a 0.5 ms output pulse was reliably generated using selected resistor-capacitor values, and its response under different trigger scenarios was analysed. The circuit performs well in digital timimg applications and can be extended using external logic for automated triggering.


### **Astable multivibrator using 555 timer IC**

**1.Aim**

 Generate pulse of width 0.5ms using 555 timer IC.

 ![image](https://github.com/user-attachments/assets/f665c854-a99b-458b-9db1-04b2a14a491b)

 **2.Theory**

 In Astable mode, the 555 timer continuously switches between HIGH and LOW states, generating a square wave without the need for any external trigger. This configuration is used for applications like blinking LEDs, pulse generation, clock signals, etc.

Two resistors (R1 and R2) and a capacitor (C) are connected externally to set the frequency and duty cycle of the output waveform.

Key Formulas:

-Time HIGH:
T_HIGH = 0.693 × (R1 + R2) × C

-Time LOW:
T_LOW = 0.693 × R2 × C

-Total Time Period:
T = T_HIGH + T_LOW

-Frequency:
f = 1.44 / ((R1 + 2R2) × C)

The output is a continuous square wave, making the circuit useful in timer applications and pulse-width modulation (PWM) setups.

**Calculations**
Time Delay Formula

ton = 0.69 (R1 + R2)C2

toff = 0.69 x R1 x C2

Where:

T = Time period in seconds (s)
R = Resistance in ohms (Ω)
C = Capacitance in farads (F)


**Working**

-The 555 timer in astable mode has no stable state.

-When powered ON, the capacitor charges through R1 and R2.

-Once the capacitor voltage reaches 2/3 of Vcc, the output at pin 3 goes LOW.

-The capacitor then discharges through R2.

-When the capacitor voltage drops below 1/3 of Vcc, the output goes HIGH again.

-This charging and discharging cycle repeats, generating a continuous square wave.

-The frequency and duty cycle depend on R1, R2, and C.

**Procedure**

-Place the 555 timer IC on a breadboard or PCB.

-Connect pin 1 to GND and pin 8 to Vcc (typically 5V–15V).

-Connect a resistor R1 between pin 7 and pin 8.

-Connect a resistor R2 between pin 7 and pin 6.

-Connect a capacitor C between pin 6 and GND.

-Short pin 2 and pin 6 together.

-Connect a 0.01µF capacitor (optional for stability) between pin 5 and GND.

-Connect pin 4 (Reset) to Vcc to disable the reset function.

-Connect an LED (with a series resistor) or oscilloscope to pin 3 (output) to observe the waveform.

-Power the circuit and observe the blinking LED or square wave output.

**Output Waveform**

![image](https://github.com/user-attachments/assets/cf86c1b3-e6cb-41f0-9218-5c69d5eb611e)

**Circuit Daigram**

![image](https://github.com/user-attachments/assets/6a8ab5d0-8069-463b-a8cc-fd5938c3b417)



**Output Waveforms**

**Case 1:**

Consider ton = 0.3 ms, toff = 0.2 ms and C2 = 0.01 µF

R2 = 0.2 x 10^-3/0.69 x 0.01µ = 28.985k Ω

R1 = (0.3 x 10^-3/0.69 x 0.01µ) - 28.985k = 14.493k Ω

![image](https://github.com/user-attachments/assets/2dcc7d68-2257-4bfb-a3f3-6664964d1f7a)

**Case 2:**

Consider ton = 0.7 ms, toff = 0.3 ms and C2 = 0.01 µF

R2 = 0.3 x 10^-3/0.69 x 0.01µ = 43.478k Ω

R1 = (0.7 x 10^-3/0.69 x 0.01µ) - 43.478k = 57.971k Ω

![image](https://github.com/user-attachments/assets/261b4a7e-9a69-45f5-a95f-7b3401ee61b6)

**Case 3:**
For ton = 0.4 ms and toff = 0.1 ms, Period = 0.5 ms. Then by using a transistor inverter, the final waveform that triggers the monostable will have

ton = 0.1 ms
toff = 0.4 ms This allows:
Clear separation between trigger pulses.
Enough time for the monostable to reset before the next pulse.

![image](https://github.com/user-attachments/assets/7f2f07fd-a194-4d4f-bea3-782502c020f6)

![image](https://github.com/user-attachments/assets/ac3bdb48-90ff-489c-aeda-626928625446)

###  Applications

- LED and lamp flashers  
- Clock pulse generation for digital circuits  
- Tone generation in audio systems  
- Pulse Width Modulation (PWM)  
- Frequency generation  
- Light chasers and sequence controllers  
- Square wave generation for testing purposes  

---

### Key Features

- Simple and low-cost circuit  
- Continuous square wave output  
- Frequency and duty cycle adjustable using R1, R2, and C  
- No external triggering required  
- Works with a wide range of supply voltages (5V–15V)  
- Easily implemented on breadboard or PCB  

---

### Inference

The astable multivibrator using the 555 timer successfully generates a continuous and stable square wave output. The frequency and ON/OFF timing can be precisely controlled by adjusting resistor and capacitor values, making it suitable for various timing and signal generation applications.

---

### Conclusion

The 555 timer IC in astable mode provides a reliable and efficient way to generate continuous pulses without external triggers. Its ease of use, low cost, and versatility make it a popular choice in both educational and practical electronic projects.




### **Virtual Lab Simulation of Monostable Multivibrator**

**AIM**

-To perform a Monostable Multivibrator using 555 Timer
-To observe and plot the Trigger Input Voltage.
-To observe and plot the Output Voltage.
-To observe and plot the Capacitance Voltage.

**PROCEDURE**
   
-Connect the components as mentioned below: L1-L12, L14-L12, L16-L12, L4-L9, L8-L9, L9-L10, L3-L17, L11-L13, L7-L11, L6-L13, L5-L15.(For eg. click on 1 and then drag to 12 and so on.)
-Click on 'Check Connection' button to check the connections. If connected wrong, click on the wrong connection. Else click on 'Delete all connection' button to erase all the connections.
-Intially set R a=10 kΩ, C=1 µf, Vcc=5 V, Tin = 20 msec.
-Click on "Calculate" button.
-Now note the output voltage.
-Click on "Plot" button to plot, Trigger Input Voltage, Output Voltage, Capacitance Voltage
-Click on "Clear" button to clear the data.
-Repeat the experiment for another set of resistance value and capacitance value.
-Set the Resistance (R a) value (1 kΩ - 10 kΩ).
-Set the Capacitance (C) value .
-Set supply voltage (Vcc).


**CIRCUIT**


![image](https://github.com/user-attachments/assets/c72e1c6d-7ab6-4644-b977-b4c621ae3a00)

### **Output Waveforms**

Trigger Input Voltage

![image](https://github.com/user-attachments/assets/a44e26e6-24d7-49f6-8001-3b00e5f90c09)

Output Voltage

![image](https://github.com/user-attachments/assets/dfaf6715-630b-4432-9fdc-94d5879fd5d1)

Capacitor Voltage

![image](https://github.com/user-attachments/assets/4b423654-ff38-437d-89c4-3ff5b24c5873)

### **Virtual Lab Simulation of Astable Multivibrator**

**AIM**

-To perform an Astable Multivibrator using 555 Timer
-To observe and plot the Output Voltage.
-To observe and plot the Capacitance Voltage.

**PROCEDURE**

-Connect the components as mentioned below: L1-L12, L14-L12, L16-L12, L4-L9, L8-L9, L10-L19, L3-L17, L11-L13, L7-L19, L6-L13, L2-L13, L5-L15, L18-L9.(For eg. click on 1 and then drag to 12 and so on.)
-Click on 'Check Connection' button to check the connections. If connected wrong, click on the wrong connection. Else click on 'Delete all connection' button to erase all the connections.
-Intially set R a=3.3 kΩ, R b=6.8kΩ, C=0.1µf, Vcc=5 V.
-Click on "Calculate" button.
-Now note the output voltage.
-Click on "Plot" button to plot Output Voltage, Capacitance Voltage
-Click on "Clear" button to clear the data.
-Repeat the experiment for another set of resistance value.
-Set the Resistance (R a) value (1 kΩ - 10 kΩ).
-Set the Resistance (R b) value (1 kΩ - 10 kΩ).
-Set the Capacitance (C) value (0.1 µf - 10 µf) .
-Set supply voltage (Vcc).

**CIRCUIT DIAGRAM**

![image](https://github.com/user-attachments/assets/7016b0e0-afc3-4171-b048-c0140b9629aa)

Output Waveforms

Output Voltage

![image](https://github.com/user-attachments/assets/af9e209b-97d9-470d-b921-23fa084a7521)

Capacitor Voltage

![image](https://github.com/user-attachments/assets/a0ee52c5-380a-4422-b154-105f3fa7b1e2)


