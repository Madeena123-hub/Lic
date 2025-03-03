### **"Differential Amplifier"**

A differential amplifier is a fundamental building block in analog circuit design, widely used in applications such as signal amplification, noise reduction, and data acquisition systems. It amplifies the difference between two input signals while rejecting common-mode noise, making it ideal for high-precision circuits, including operational amplifiers and analog front-end systems.

In modern electronics, differential amplifiers play a crucial role in communication systems, biomedical instrumentation, and sensor interfaces, where signal integrity is critical. The ability to suppress external interference and unwanted signals makes them superior to single-ended amplifiers in noisy environments.

### **question:Vdd=2.2v , p<=2.2mv , Vicm=1.2v, Vocm=1.25v , Vp=0.4v**

**Circuit 1** <br>

![Screenshot 2025-03-02 161240](https://github.com/user-attachments/assets/338eb269-48a4-4138-a1c0-25b625fd9123)

**Step 1:Dc analysis design Rd and Rss**
![WhatsApp Image 2025-03-02 at 16 24 34_a544ce2f](https://github.com/user-attachments/assets/dcbb4266-b814-49d4-894a-854e76ae5f80)

from the calculation we have finded Iss value as 1mA <br>
Id1 and Id2 as 0.5mA <br>
Rd as 1.9kohm <br>
Rss as 400ohm <br>
Vgs=vg - vp = 1.2v - 0.4v = 0.8v <br>
Vov = vgs - vth = 0.8v - 0.366v = 0.434v <br>

### **DC Analysis**

To set the operating point go to Configure Analysis and select Dc operating Point <br>

to set correct operating point vary width and length values 
width = 6.45u <br>
length = 180n <br>

![Screenshot 2025-03-02 164823](https://github.com/user-attachments/assets/2fe5efbe-f348-4bdd-b18f-ee9ddc551ac3)

![Screenshot 2025-03-02 164908](https://github.com/user-attachments/assets/316231bf-4a42-4e40-a95e-72c4710cc051)

### **Analysis**

**Increase Vicm from 1.2v to 1.3v and observe Vocm and Vp** <br>
| **Common-Mode Input Voltage (V_ICM)** | **Output Voltage (V_out)** | **Voltage at Point P (V_P)** |
|--------------------------------------|--------------------------|--------------------------|
| **1.2V**                            | **1.24836V**             | **0.4V**                |
| **1.3V**                            | **1.1V**                 | **0.46V**               |

### Effect of VICM on Vout and VP

As the common-mode input voltage \( VICM \) increases, the source voltage \( VP \) also increases, causing a shift in the operating point. This leads to a higher drain current, resulting in a greater voltage drop across \( RD \), which reduces \( Vout \).

![Screenshot 2025-03-02 165923](https://github.com/user-attachments/assets/9935d54d-cf30-47ea-80d7-b6691c1cbb31)

### **Calculate maximum input and output Swing**

![WhatsApp Image 2025-03-02 at 20 58 55_50bf8a35](https://github.com/user-attachments/assets/528ca83b-b081-42c5-a450-f31491dd1fcd)

![WhatsApp Image 2025-03-02 at 20 58 55_6f38755a](https://github.com/user-attachments/assets/cfb49074-5091-4a3b-8e2e-0772f622ec15)

### **GAIN**

![WhatsApp Image 2025-03-02 at 21 16 06_1f174e67](https://github.com/user-attachments/assets/5ab85112-8fa7-4060-ba94-98c5b5cdaa32)

### **TRANSIENT ANALYSIS**
go to configure Analysis and select transient analysis then <br>
stop time as 5m <br>
time to start saving data as 0 <br>

• Waveform Type: Sine Wave
• Amplitude: 20 mV
• DC Offset: 1.2 V
• Frequency: 1 kHz

And in V2 phi(deg) as 180

![Screenshot 2025-03-02 212112](https://github.com/user-attachments/assets/74b10d4b-3cdb-4b45-b7ad-b8be02706d6c)

![Screenshot 2025-03-02 212304](https://github.com/user-attachments/assets/92739734-338d-42f2-8d4f-f6904b5718fb)

![Screenshot 2025-03-02 212546](https://github.com/user-attachments/assets/470d1956-3964-4aa2-a722-cb605d867b1b)

### **AC Analysis**

go to configure analysis and select AC Analysis
• Type of sweep: Decade
• Number of points per decade: 5
• Start frequency: 0.1 Hz
• Stop frequency: 1 THz

Set <br>
AC Amplitude as 1 and AC Phase as 0 in V1 <br>
AC Amplitude as 1 and AC Phase as 180 in V2 <br>

![Screenshot 2025-03-02 235653](https://github.com/user-attachments/assets/db083118-03a3-4021-8a05-7e8285b9bea3)

![Screenshot 2025-03-02 215847](https://github.com/user-attachments/assets/832d0f56-d7ed-4f4a-b0cb-d0fc4634f410)

![Screenshot 2025-03-02 220006](https://github.com/user-attachments/assets/ecfef7ef-22da-4aa5-93b4-74fba38dd18f)


### **Circuit 2** <br>

Replacing Resistor with Current Source

![Screenshot 2025-03-02 222734](https://github.com/user-attachments/assets/dc70cd6c-eed5-4693-bb86-b6c9e4096b61)

### **DC Analysis**

![Screenshot 2025-03-02 222935](https://github.com/user-attachments/assets/d922b434-5aa1-4bb5-8855-bf281f8d0f53)

![Screenshot 2025-03-02 223027](https://github.com/user-attachments/assets/7ed89486-72bf-409c-a950-a7bc6410a323)

### **AC Analysis**

![Screenshot 2025-03-02 235653](https://github.com/user-attachments/assets/698fa1bf-381b-4deb-a83d-4cf1f8227d05)

![Screenshot 2025-03-02 223315](https://github.com/user-attachments/assets/d0db6eb8-ab1e-4649-bf22-f65bace10bb8)

### **TRANSIENT ANALYSIS**

![Screenshot 2025-03-02 224140](https://github.com/user-attachments/assets/e68ff7b8-09b1-4afa-9d31-49f6f7a2c907)

![Screenshot 2025-03-02 224947](https://github.com/user-attachments/assets/f1914323-d85a-4be8-a213-21e988cb0678)

![Screenshot 2025-03-02 225541](https://github.com/user-attachments/assets/e4d83695-4ca3-460d-972c-5aeafdbbca74)

### **Circuit 3** <br>

Replacing current Source with MOSFET 

![Screenshot 2025-03-03 000910](https://github.com/user-attachments/assets/3b155209-c3eb-4a34-b1ed-1a664c0c2067)

How to find Vb?🤔🤔
Vb = vth + Vp <br>
Vb = 0.366v + 0.4v <br>
Vb = 0.766v <br>

### **DC Analysis**

To set the operating point vary 3rd MOSFET width and keep length as same before 
For approx operating Point i got width as 17.75u

![Screenshot 2025-03-03 001117](https://github.com/user-attachments/assets/b8eab2f6-7e14-4b52-b01e-cfe42d79ec75)

### **AC Analysis**

### **TRANSIENT ANALYSIS**

### ""Result and Inference""

### **Circuit 4**
Replace two resistor with PMOS Transistor

![Screenshot 2025-03-03 054151](https://github.com/user-attachments/assets/3bddfece-f2be-4f60-9caf-61d53a124653)

### **DC Analysis**

### **AC Analysis**

### **TRANSIENT ANALYSIS**

### ""Result and Inference""














































 
