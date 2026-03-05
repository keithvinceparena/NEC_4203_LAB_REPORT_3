# EXPERIMENT 16: FREQUENCY SHIFT KEYING (FSK)

## I. Objectives

The objectives of this experiment are:

1. To understand the principle of **Frequency Shift Keying (FSK)** as a digital modulation technique.
2. To generate an FSK signal using a **Voltage Controlled Oscillator (VCO)** and a digital data source.
3. To observe the behavior of the FSK signal using an **oscilloscope**.
4. To demodulate the FSK signal using a **tunable low-pass filter and envelope detector**.
5. To restore the recovered digital signal using a **comparator circuit**.

---

# II. Materials and Components Used

The following equipment and components were used in the experiment:

- Emona Telecoms-Trainer 101 (plus power pack)
- Dual-channel 20 MHz oscilloscope
- Three Emona Telecoms-Trainer 101 oscilloscope leads
- Assorted Emona Telecoms-Trainer 101 patch leads

These instruments were used to generate, observe, and analyze the FSK signal and its demodulation process. :contentReference[oaicite:1]{index=1}

---

# III. Procedure

## Part A – Generating an FSK Signal
<img width="749" height="512" alt="image" src="https://github.com/user-attachments/assets/5d3add0a-be76-43cf-9a93-d94195615e3f" />

1. Gather all required equipment listed in the materials section.
2. Set up the oscilloscope according to the instructions from the previous experiment.
3. Set the oscilloscope trigger source to **External (EXT)**.
4. Set the oscilloscope trigger source coupling to **HF Reject**.
5. Set the oscilloscope **Channel 1 and Channel 2 input coupling to DC**.
6. Adjust the oscilloscope timebase control to the mid position.
7. Locate the **Voltage Controlled Oscillator (VCO) module** and set the **Gain control to about half of its travel**.
8. Adjust the **Frequency Adjust control to approximately one quarter of its travel**.
9. Set the **VCO module’s Range control to the LO position**.
10. Locate the **Sequence Generator module** and set its **DIP switches to 00**.
11. Connect the modules according to the **FSK generation block diagram**.
12. Turn on the trainer and observe the digital signal and FSK output on the oscilloscope.
13. Compare the digital input signal with the generated FSK waveform.

<img width="728" height="551" alt="image" src="https://github.com/user-attachments/assets/0054b952-1ae6-4969-b61c-3dbe13347d39" />

---

## Part B – Demodulating an FSK Signal Using Filtering and an Envelope Detector
<img width="675" height="297" alt="image" src="https://github.com/user-attachments/assets/847070e6-8308-41e3-8d01-7411cc3afbe2" />

1. Modify the setup to include a **Tunable Low Pass Filter (LPF)** module.
2. Turn the VCO module’s **Frequency Adjust control** to approximately position 2 on the scale.
3. Locate the Tunable LPF module and adjust its **Cut-off Frequency control fully clockwise**.
4. Set the **Gain control of the Tunable LPF fully clockwise**.
5. Connect the circuit as shown in the **FSK demodulation block diagram**.
6. Slowly adjust the LPF cut-off frequency until the higher frequency component of the FSK signal becomes close to zero.
7. Observe the **digital signal and filtered output** on the oscilloscope.
8. Compare the signals displayed on Channel 1 and Channel 2.
<img width="664" height="498" alt="image" src="https://github.com/user-attachments/assets/e789f997-895e-45d0-8221-b2e1e3802bb0" />

<img width="713" height="583" alt="image" src="https://github.com/user-attachments/assets/73696d3a-a4e2-40da-a1fd-06df7da8c45e" />

---

## Part C – Restoring the Recovered Data Using a Comparator
<img width="776" height="319" alt="image" src="https://github.com/user-attachments/assets/efeacbbf-5701-48aa-9aa8-d506a498db5b" />

1. Modify the setup again to include a **Comparator module**.
2. Connect the output of the envelope detector to the **Comparator input**.
3. Adjust the **Variable DC control to the midpoint** to act as a reference voltage.
4. Observe the comparator output on the oscilloscope.
5. Compare the restored digital signal with the original digital signal.
6. Slightly adjust the reference voltage if needed to obtain a clean digital waveform.

<img width="719" height="537" alt="image" src="https://github.com/user-attachments/assets/5ea03c80-49e9-492a-a5f8-231fc441b5ac" />

---

# IV. Results and Discussion

## Part A – Generating an FSK Signal

During the first part of the experiment, the Sequence Generator produced a digital data stream consisting of logic-1s and logic-0s. This digital signal controlled the Voltage Controlled Oscillator (VCO), which generated a sinusoidal output whose frequency changed depending on the logic level of the input signal.

When the digital signal was **logic-1**, the VCO produced a sinewave with a certain frequency called the **Mark Frequency**. When the digital signal changed to **logic-0**, the VCO output switched to a different sinewave frequency called the **Space Frequency**.

This switching between two different frequencies represents the **Frequency Shift Keying (FSK)** modulation process. Instead of varying amplitude, the system transmits digital information by switching the **frequency of the carrier signal**.
<img width="728" height="551" alt="image" src="https://github.com/user-attachments/assets/ae99c460-3923-490b-98e1-dc64b93219f1" />

### Answers

**What is the name for the VCO output frequency that corresponds with logic-1s in the digital data?**

The frequency corresponding to logic-1 is called the **Mark Frequency**.

**What is the name for the VCO output frequency that corresponds with logic-0s in the digital data?**

The frequency corresponding to logic-0 is called the **Space Frequency**.

**Which of the two is the higher frequency? Explain.**

The **Mark frequency is usually higher than the Space frequency**. This is because the VCO increases its output frequency when the control voltage corresponds to the logic-1 state.

---

## Part B – Demodulating an FSK Signal

In this stage, the FSK signal was passed through a **tunable low-pass filter**. The purpose of the filter was to isolate one of the two frequencies present in the FSK waveform.

Since an FSK signal consists of two alternating sinusoidal frequencies, the filter can be tuned to allow only one of these frequencies to pass while attenuating the other. In the experiment, the filter was adjusted so that it selected the **higher frequency component** of the FSK signal.

When this filtering process occurred, the output waveform showed bursts of sinewaves corresponding to when the selected frequency was present. When the other frequency appeared, the filter greatly reduced its amplitude.

This filtered signal resembled an amplitude-modulated waveform where the presence of the selected frequency indicated a digital logic state.

<img width="664" height="498" alt="image" src="https://github.com/user-attachments/assets/e789f997-895e-45d0-8221-b2e1e3802bb0" />

<img width="713" height="583" alt="image" src="https://github.com/user-attachments/assets/4cec980f-5f1c-40af-8102-7cd71f237ee3" />

### Answers

**Which of the FSK signal’s two sinewaves is the filter picking out?**

The filter is selecting the **higher frequency sinewave (Mark frequency)** from the FSK signal.

**What does the filtered FSK signal look like?**

The filtered signal appears as **bursts of sinewaves** whenever the selected frequency is present. When the other frequency occurs, the output amplitude becomes very small.

**What can be used to “clean up” the recovered digital signal?**

A **Comparator circuit** can be used to clean up the recovered digital signal.

---

## Part C – Restoring the Recovered Digital Signal

After filtering and envelope detection, the recovered signal still contained slow rising and falling edges. This occurred because the envelope detector and filter smooth out the waveform, preventing sharp transitions.

To restore the signal into a clean digital waveform, a **Comparator module** was used. The comparator compares the recovered analog signal with a reference voltage.

When the input signal rises above the reference voltage, the comparator outputs a **logic high**. When the input signal falls below the reference voltage, the comparator outputs a **logic low**.

This process converts the distorted analog signal into a clean square-wave digital signal.
<img width="719" height="537" alt="image" src="https://github.com/user-attachments/assets/0ad600a7-3660-44cc-a7d5-81903295b833" />

### Answer

**How does the comparator turn the slow-rising voltages of the recovered digital signal into sharp transitions?**

The comparator compares the signal with a reference threshold voltage. When the signal crosses this threshold, the comparator switches rapidly between high and low states, producing sharp transitions that resemble the original digital signal.

---

# V. Reflection / Learning Summary

This experiment demonstrated the operation of **Frequency Shift Keying (FSK)** as a digital modulation technique. Unlike amplitude modulation, FSK transmits digital information by switching between two different carrier frequencies.

Through this experiment, the following key concepts were learned:

- Digital data can be transmitted by changing the **frequency of a carrier signal**.
- The two frequencies used in FSK are called the **Mark frequency** and **Space frequency**.
- Tunable filters can be used to separate specific frequency components of a signal.
- Envelope detection helps recover the information embedded in the signal.
- Comparator circuits are essential for restoring distorted analog signals into clean digital signals.

Overall, the experiment improved understanding of **digital communication systems**, particularly how digital information can be modulated, transmitted, demodulated, and reconstructed using electronic circuits.
