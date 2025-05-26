### ** Monostable multivibrator using 555 timer IC **

![image](https://github.com/user-attachments/assets/f2662e75-d999-4a0f-82fb-f574dcfc4052)


**1. Aim**

Generate the waveform with pulse width of 0.5ms using 555 IC

**2. Theory**

A monostable multivibrator is a circuit that has one stable state and one temporary state. Using a 555 timer IC in monostable mode, the circuit generates a single output pulse when triggered. The pulse duration is set by an external resistor and capacitor using the formula 
T=1.1×R×C. This setup is useful for delay timers, pulse generation, and switch debouncing.

Where:

R = Resistance in ohms
C = Capacitance in farads

**3.working**

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


** 11.Inference**
When the trigger voltage < 1/3 Vcc, the 555 timer recognizes it as a valid trigger.
This causes the output (pin 3) to go HIGH for a specific time period.
The capacitor charges during this time, determining the pulse width.
After the time elapses, the output returns to LOW, completing the monostable operation.

** 12.CONCLUSION**

The NE555 timer configured in monostable mode provides accurate, predictable timing pulses when triggered by clean falling edges. In this simulation, a 0.5 ms output pulse was reliably generated using selected resistor-capacitor values, and its response under different trigger scenarios was analysed. The circuit performs well in digital timimg applications and can be extended using external logic for automated triggering.




