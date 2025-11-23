# -Amplitude-Modulation-and-Demodulation-using-NumPy-and-Matplotlib

__Aim__: 

To implement and analyze amplitude modulation (AM) using Python's NumPy and Matplotlib libraries. 

__Apparatus Required__: 

Software: Python with NumPy and Matplotlib libraries 
Hardware: Personal Computer 

__Theory__: 

Amplitude Modulation (AM) is a technique used in electronic communication, primarily for transmitting 
information via a radio carrier wave. In AM, the amplitude of the carrier wave is varied in proportion to that of 
the message signal. The general form of an AM signal is: 


__Algorithm__:
1. Initialize Parameters: Set the values for carrier frequency, message frequency, and sampling frequency. 
2. Generate Time Axis: Create a time vector for the signal duration. 
3. Generate Message Signal: Define the message signal as a cosine wave. 
4. Generate Carrier Signal: Define the carrier signal as a cosine wave. 
5. Modulate Signal: Apply the AM formula to obtain the modulated signal. 
6. Plot the Signals: Use Matplotlib to plot the message signal, carrier signal, and modulated signal.

__Program__:
```
import numpy as np
import matplotlib.pyplot as plt

# Parameters
Am =   14.5   # Message amplitude
Ac = 29     # Carrier amplitude
fm = 570       # Message frequency
fc = 5700       # Carrier frequency
fs = 57000      # Sampling frequency (must be high for smooth signal)

t = np.arange(0, 0.01, 1/fs)   # Time vector

# Message Signal
message = Am * np.cos(2 * np.pi * fm * t)

# Carrier Signal
carrier = Ac * np.cos(2 * np.pi * fc * t)

# Modulation Index
m = Am / Ac

# AM Modulated Signal
am_signal = Ac * (1 + m * np.cos(2 * np.pi * fm * t)) * np.cos(2 * np.pi * fc * t)

# Demodulation (Envelope Detector)
demodulated = np.abs(am_signal)

# Plotting
plt.figure(figsize=(12,10))

plt.subplot(4,1,1)
plt.plot(t, message)
plt.title("Message Signal")
plt.xlabel("Time")
plt.ylabel("Amplitude")

plt.subplot(4,1,2)
plt.plot(t, carrier)
plt.title("Carrier Signal")
plt.xlabel("Time")
plt.ylabel("Amplitude")

plt.subplot(4,1,3)
plt.plot(t, am_signal)
plt.title("AM Modulated Signal")
plt.xlabel("Time")
plt.ylabel("Amplitude")

plt.subplot(4,1,4)
plt.plot(t, demodulated)
plt.title("Demodulated Signal (Envelope)")
plt.xlabel("Time")
plt.ylabel("Amplitude")

plt.tight_layout()
plt.show()
```
__Calculations__:

![WhatsApp Image 2025-11-23 at 5 31 04 PM](https://github.com/user-attachments/assets/97b1a6ad-2fd6-4ca7-a36d-c422d296a774)


 __Output__:

 <img width="1189" height="990" alt="image" src="https://github.com/user-attachments/assets/a69d8da4-5d92-464d-bce4-4972f8a97cac" />

 


 __Result__:
 ![WhatsApp Image 2025-11-23 at 5 31 46 PM](https://github.com/user-attachments/assets/74ec58be-9744-4522-875e-4f9814e486dd)



