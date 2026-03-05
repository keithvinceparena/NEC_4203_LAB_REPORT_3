# EXPERIMENT 12: PCM ENCODING

## I. OBJECTIVES

The objectives of this experiment are:

1. To understand the operation of a **Pulse Code Modulation (PCM) encoder**.
2. To observe how **analog voltage signals are converted into digital binary codes**.
3. To examine the relationship between **input voltage and PCM output code**.
4. To investigate **quantization and its effects on the encoded signal**.
5. To observe PCM encoding for both **static and continuously varying signals**.

---

# II. MATERIALS AND COMPONENTS USED

The following equipment and modules were used in the experiment:

### Equipment
- Emona Telecoms-Trainer 101 (plus power pack)
- Dual Channel 20 MHz Oscilloscope
- Two Emona Telecoms-Trainer 101 oscilloscope leads
- Assorted Emona Telecoms-Trainer 101 patch leads

### Modules
- PCM Encoder module
- Master Signals module
- Variable DC Voltage module
- VCO module
- Buffer/Adder module (used in quantization investigation)

---

# III. PROCEDURE

## Part A – Introduction to PCM Encoding Using a Static DC Voltage

1. Gather the equipment listed in the materials section.

2. Configure the oscilloscope according to the settings used in **Experiment 1**. Ensure that:
   - The **Trigger Source control** is set to the **CH1 or EXT position**.
   - The **Mode control** is set to **CH1**.

3. Locate the **PCM Encoder module** and set the **Mode switch to the PCM position**.

4. Connect the circuit as shown in **Figure 2** of the manual.

5. Adjust the oscilloscope **Timebase control** so that **three pulses of the PCM Encoder module’s FS output** are visible.

6. Set the oscilloscope **Slope control to the negative (-) position**.

7. Adjust the **Horizontal Position control** so that the beginning of the trace aligns with the left-most vertical grid line.

8. Set the oscilloscope **Timebase control to 0.1 ms/div**.

9. Adjust the **Variable Sweep control** until the FS signal appears stable on the display.

10. Set the oscilloscope **Mode control to DUAL** to observe both:
   - The **PCM Encoder clock signal**
   - The **Frame Synchronization (FS) signal**

11. Draw the two waveforms to scale:
   - The **third clock signal** in the upper part of the graph.
   - The **FS signal** in the middle section.

12. Connect **Channel 2 of the oscilloscope** to the **PCM Encoder module’s PCM DATA output**.

13. Draw the PCM DATA waveform to scale.

---

## Part B – PCM Encoding of a Variable DC Voltage

14. Connect the **Variable DC Voltage (Variable DCV) module** to the PCM Encoder input.

15. Set the oscilloscope **Mode control to CH1**.

16. Set the **Trigger Source control to EXT**.

17. Modify the circuit setup according to **Figure 7** in the manual.

18. Set **Channel 1 Vertical Attenuation to 1V/div**.

19. Set **Channel 1 Input Coupling to GND**.

20. Adjust the **Vertical Position control** to align the trace with one of the horizontal grid lines.

21. Set both Channel 1 and Channel 2 **Input Coupling controls to DC**.

22. Set the oscilloscope **Mode control to DUAL**.

23. Adjust the **Variable DC Voltage control** until the PCM Encoder outputs the binary code observed earlier.

24. Use the oscilloscope to measure the **Variable DCV module output voltage**.

---

## Part C – Quantisation Investigation

25. Turn the **Variable DCV control clockwise** while observing the oscilloscope display.

26. Continue increasing the voltage until the PCM Encoder output reaches **11111111**.

27. Measure the PCM Encoder module's **input voltage** and record it.

28. Adjust the circuit setup if necessary to ensure that the encoder input voltage range is appropriate.

29. Adjust the system so that the input voltage corresponds to the required measurement conditions.

30. Increase the PCM encoder input voltage until it reaches its maximum value.

31. Measure the Variable DC voltage output and record it in the table.

---

## Part D – PCM Encoding of Continuously Changing Voltages

32. Return the oscilloscope **Trigger Source control to CH1 or EXT**.

33. Remove the buffer module to return the setup to the configuration shown in **Figure 7**.

34. Adjust the **Variable DC control** and observe the PCM encoder output.

35. Observe how the **PCM DATA output changes continuously** as the input signal varies.

36. Return the oscilloscope **Trigger Source control to AC**.

37. Set **Channel 1 and Channel 2 Vertical Attenuation controls to 2V/div**.

38. Locate the **VCO module** and set its **Range control to HI**.

39. Turn the **VCO Frequency Adjust control fully counter-clockwise**.

40. Disassemble the current setup.

41. Reconnect the circuit according to **Figure 9**.

42. Set the oscilloscope **Timebase control to 500 µs/div**.

43. Observe the **PCM DATA output waveform** on the oscilloscope display.

---

# IV. RESULTS AND DISCUSSION

In this experiment, the PCM encoder module was used to convert analog voltage signals into digital binary codes. The encoder divides the analog input voltage range into discrete voltage intervals called **quantization levels**.

Each quantization level corresponds to a unique binary number. When a DC voltage was applied to the encoder input, the module produced a digital output code representing the quantized level closest to the input voltage.

As the **Variable DC voltage** was increased gradually, the output binary code changed in discrete steps. This confirmed that the PCM encoder performs **quantization**, where continuous analog signals are approximated by discrete digital values.

During the quantization investigation, it was observed that the output code eventually reached **11111111**, indicating the highest quantization level supported by the encoder.

When a **continuously varying input signal** was applied, the PCM encoder produced a digital output that changed continuously in response to the signal variations. This demonstrated how PCM encoding is used in digital communication systems to convert analog signals into digital bit streams.

The **Frame Synchronization (FS)** signal and **clock signal** played an important role in controlling the encoding process by defining the timing of each encoded sample.

---

# V. REFLECTION / LEARNING SUMMARY

This experiment helped demonstrate the practical implementation of Pulse Code Modulation (PCM) in digital communication systems. By observing the relationship between input voltage and output binary codes, the experiment showed how analog signals are quantized and encoded into digital form.

The use of the Variable DC voltage module allowed the gradual adjustment of the encoder input, making it possible to observe how binary output codes change with voltage levels. This helped illustrate the concept of quantization and its effect on digital representation of analog signals.

The experiment also highlighted the importance of synchronization signals such as the clock and frame synchronization signals in ensuring accurate sampling and encoding.

Overall, the experiment reinforced the theoretical concepts of **PCM encoding, quantization, and digital signal representation**, which are fundamental in modern communication systems such as digital telephony, audio processing, and data transmission technologies.
