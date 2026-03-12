# SSB

EXP NO: 3	SSB-SC-AM MODULATION using SCILAB

AIM:

To write a program to perform SSBSC modulation and demodulation using SCI LAB and study its spectral characteristics

EQUIPMENTS REQUIRED

•	Computer with i3 Processor

•	SCI LAB

Note: Keep all the switch faults in off position


Algorithm
1.	Define Parameters:
•	Fs: Sampling frequency.
•	T: Duration of the signal.
•	Fc: Carrier frequency.
•	Fm: Frequency of the message signal.
•	Amplitude: Maximum amplitude of the message signal.
2.	Generate Signals:
•	Message Signal: The baseband signal that will be modulated.
•	Carrier Signal: A high-frequency signal used for modulation.
•	Analytic Signal: Constructed using the Hilbert transform to get the in-phase and quadrature components.
3.	SSBSC Modulation:
•	Modulated Signal: Create the SSBSC signal using the in-phase and quadrature components, modulated by the carrier.
4.	SSBSC Demodulation:
•	Mixing: Multiply the SSBSC signal with the carrier to retrieve the message signal.
•	Low-pass Filtering: Apply a low-pass filter to remove high-frequency components and recover the original message signal.
5.	Visualization:
•	Plot the message signal, carrier signal, SSBSC modulated signal, and the recovered signal after demodulation.


PROCEDURE

•	Refer Algorithms and write code for the experiment.
•	Open SCILAB in System
•	Type your code in New Editor
•	Save the file
 
•	Execute the code
•	If any Error, correct it in code and execute again
•	Verify the generated waveform using Tabulation and Model Waveform

Model Waveform

<img width="704" height="178" alt="image" src="https://github.com/user-attachments/assets/32ee29b3-0d95-4192-9762-972d50c05c90" />
<img width="706" height="167" alt="image" src="https://github.com/user-attachments/assets/bff0d8fd-d679-444e-af37-0b34585853c1" />

Program
```
Am=6.1;
Fm=225;
Ac=12.2;
Fc=2250;
Fs=22500;
t=0:1/Fs:2/Fm;
Em1=Am*cos(2*3.14*Fm*t);
subplot(4,1,1);
plot(t,Em1);
Ec1=Ac*cos(2*3.14*Fc*t);
subplot(4,1,2);
plot(t,Ec1);
Eam1=Ac*(1+(Em1/Ac)).*cos(2*3.14*Fc*t);
Eam2=Ac*(-1+(Em1/Ac)).*cos(2*3.14*Fc*t);
Edsbsc1=Eam1+Eam2;
Em2=Am*sin(2*3.14*Fm*t);
Ec2=Ac*sin(2*3.14*Fc*t);
Eam3=Ac*(1+(Em2/Ac)).*sin(2*3.14*Fc*t);
Eam4=Ac*(-1+(Em2/Ac)).*sin(2*3.14*Fc*t);
Edsbsc2=Eam3+Eam4;
Essbsc1=Edsbsc1-Edsbsc2;
subplot(4,1,3);
plot(t,Essbsc1);
Essbsc2=Edsbsc1+Edsbsc2;
subplot(4,1,4);
plot(t,Essbsc2);
```
OUTPUT WAVEFORM
<img width="1918" height="1009" alt="image" src="https://github.com/user-attachments/assets/6edc1147-365c-47ae-8f46-99a42e4cc495" />

TABULATION

![WhatsApp Image 2026-03-12 at 10 16 26](https://github.com/user-attachments/assets/bab5398a-8d31-4c26-a4c0-6000698b4e92)



RESULT:

Thus, the SSB-SC-AM Modulation and Demodulation is experimentally done and the output is verified.





