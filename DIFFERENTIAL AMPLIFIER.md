### **"Differential Amplifier"**

A differential amplifier is a fundamental building block in analog circuit design, widely used in applications such as signal amplification, noise reduction, and data acquisition systems. It amplifies the difference between two input signals while rejecting common-mode noise, making it ideal for high-precision circuits, including operational amplifiers and analog front-end systems.

In modern electronics, differential amplifiers play a crucial role in communication systems, biomedical instrumentation, and sensor interfaces, where signal integrity is critical. The ability to suppress external interference and unwanted signals makes them superior to single-ended amplifiers in noisy environments.

### **question:Vdd=2.2v , p<=2.2mv , Vicm=1.2v, Vocm=1.25v , Vp=0.4v**

**Circuit1**<br>

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











 
