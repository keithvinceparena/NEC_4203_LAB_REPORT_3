# EXPERIMENT 14: BANDWIDTH LIMITING AND RESTORING DIGITAL SIGNALS

---

# I. OBJECTIVES

The objectives of this experiment are:

1. To investigate the effect of **bandwidth limiting on digital communication signals**.
2. To observe how a limited bandwidth channel can **distort digital signals**.
3. To analyze how bandwidth limitations affect **PCM decoding performance**.
4. To study how the **shape of a digital signal changes when bandwidth is restricted**.
5. To demonstrate how a **comparator can restore distorted digital signals**.

---

# II. MATERIALS AND COMPONENTS USED

The following equipment and modules were used in this experiment:

### Equipment
- Emona Telecoms-Trainer 101 (plus power pack)
- Dual-channel 20 MHz oscilloscope
- Three Emona Telecoms-Trainer 101 oscilloscope leads
- Assorted Emona Telecoms-Trainer 101 patch leads
- One set of stereo headphones

These components are required to construct the PCM communication system and observe the effects of bandwidth limitations in the transmission channel. :contentReference[oaicite:1]{index=1}

---

# III. PROCEDURE

## Part A – The Effects of Bandwidth Limiting on PCM Decoding
<img width="784" height="403" alt="image" src="https://github.com/user-attachments/assets/d4f48704-770a-48ea-bdc7-a9afaa28020e" />

<img width="780" height="323" alt="image" src="https://github.com/user-attachments/assets/04f353d8-6dc7-4e87-a0db-1f6f322b3805" />

1. Gather all equipment listed in the materials section.

2. Set up the oscilloscope according to the instructions used in previous experiments.

3. Locate the **PCM Encoder module** and set its **Mode switch to PCM**.

4. Set up the circuit as shown in the **Bandwidth Limiting on the PCM Decoding block diagram**.

5. Connect the **Variable DC Voltage module** to the PCM Encoder input to provide the message signal.

6. Use the **Master Signals module** to generate a **2 kHz clock signal** for the PCM Encoder.

7. Connect the PCM Encoder output through a **channel that models the communication path**.

8. Connect the output of the channel to the **PCM Decoder module**.

9. Observe the decoded signal using the oscilloscope.

10. Introduce bandwidth limitation in the channel by inserting the **Tunable Low-Pass Filter module**.

11. Adjust the **cut-off frequency control** of the Tunable Low-Pass Filter.

12. Observe how reducing the bandwidth affects the PCM Decoder output.

13. Record the waveform and note the errors produced in the decoded signal.
<img width="708" height="531" alt="image" src="https://github.com/user-attachments/assets/5d60f87c-1269-44ec-9225-2de906fd069e" />

---

## Part B – The Effects of Bandwidth Limiting on a Digital Signal’s Shape
<img width="763" height="376" alt="image" src="https://github.com/user-attachments/assets/f450ab16-9245-4147-9106-eb5941327e61" />

1. Disconnect the previous setup and configure the system according to the **Digital Signal Modelling block diagram**.

2. Use the **Sequence Generator module** to generate a digital signal.

3. Connect the output of the Sequence Generator to the **Tunable Low-Pass Filter module**.

4. Observe the digital signal before the filter using **Channel 1 of the oscilloscope**.

5. Observe the bandwidth-limited signal after the filter using **Channel 2 of the oscilloscope**.

6. Adjust the filter’s **cut-off frequency** gradually.

7. Observe how the square digital signal begins to lose its sharp edges and becomes distorted.

8. Note that the signal transitions become slower and the waveform begins to resemble a sinusoidal shape.

9. Compare the original digital signal with the bandwidth-limited signal.

<img width="579" height="449" alt="image" src="https://github.com/user-attachments/assets/c0c3ba11-4f43-41e6-b49a-f77d971e93d4" />
<img width="751" height="367" alt="image" src="https://github.com/user-attachments/assets/947c5c47-e1cc-4839-a132-7f0a2802384b" />

---

## Part C – Restoring Digital Signals

1. Reconfigure the system according to the **Bandwidth Restoration block diagram**.

2. Connect the bandwidth-limited digital signal to a **Comparator module**.

3. Adjust the **DC reference voltage** on the comparator.

4. Observe the comparator output on the oscilloscope.

5. The comparator converts the distorted analog-like waveform back into a digital signal.

6. Compare the restored digital signal with the original digital signal.

7. Gradually vary the DC reference voltage and observe its effect on the restored signal.

8. Increase or decrease the comparator threshold and observe when incorrect outputs begin to occur.

9. Record the restored waveform and compare it with the original signal.

<img width="688" height="516" alt="image" src="https://github.com/user-attachments/assets/117da98b-983b-4bc0-8529-b13d19618c56" />
<img width="775" height="381" alt="image" src="https://github.com/user-attachments/assets/76704981-e88a-4fb4-ae42-875a8d9b5b84" />

---

# IV. RESULTS AND DISCUSSION

The experiment demonstrated how bandwidth limitations affect the performance of digital communication systems. When a signal passes through a channel with limited bandwidth, some of the higher frequency components of the digital signal are removed. Since digital signals rely on sharp transitions between logic levels, removing these high-frequency components causes the signal edges to become slower and distorted.

In Part A of the experiment, bandwidth limiting caused errors in the PCM decoding process. The PCM Decoder module produced incorrect voltages because the digital data arriving from the channel was no longer a clean digital signal. This distortion can cause misinterpretation of logic levels and result in incorrect decoding.

In Part B, the shape of the digital signal changed significantly when passed through a low-pass filter. The originally square waveform gradually became rounded and less defined as the bandwidth decreased. This demonstrated that digital signals require sufficient bandwidth to maintain their shape.

In Part C, the distorted digital signal was restored using a comparator. The comparator acted as a threshold detector, converting the distorted waveform back into a digital square wave. Although the restored signal closely resembled the original signal, slight differences remained due to delays and signal distortion.

Overall, the experiment showed that bandwidth limitations can significantly degrade digital signals, but restoration techniques such as threshold detection can recover the signal for proper decoding.

<img width="708" height="531" alt="image" src="https://github.com/user-attachments/assets/39168404-26b0-4dae-bda6-c87e69e647a3" />

<img width="688" height="516" alt="image" src="https://github.com/user-attachments/assets/229b6411-841e-4742-bf8b-2f10c67c79e2" />

---

# V. REFLECTION / LEARNING SUMMARY

This experiment helped demonstrate the importance of bandwidth in digital communication systems. By observing how bandwidth limitations distort digital signals, it became clear that adequate bandwidth is necessary to maintain signal integrity during transmission.

The experiment also showed that when digital signals are distorted, the receiver may interpret incorrect logic values, which can lead to errors in the decoded message. However, using signal restoration techniques such as comparators can help recover the digital signal by converting distorted waveforms back into clean digital levels.

Through this experiment, the relationship between signal bandwidth, waveform shape, and digital signal recovery became clearer. Understanding these concepts is important in designing reliable communication systems where signals must travel through channels with limited bandwidth.

Overall, this experiment reinforced the importance of bandwidth management and signal restoration techniques in maintaining accurate digital communication.
