# EXPERIMENT 13: PCM DECODING

---

# I. OBJECTIVES

The objectives of this experiment are:

1. To understand the operation of a **Pulse Code Modulation (PCM) decoder**.
2. To observe how a **digital PCM signal is converted back into an analog signal**.
3. To investigate the relationship between **PCM data input and reconstructed analog output**.
4. To analyze how the PCM decoder reconstructs quantized voltage levels.
5. To observe the reconstruction of both **static and continuously varying signals** using PCM decoding.

---

# II. MATERIALS AND COMPONENTS USED

The following equipment and modules were used in this experiment.

### Equipment
- Emona Telecoms-Trainer 101 (plus power pack)
- Dual Channel 20 MHz Oscilloscope
- Two Emona Telecoms-Trainer oscilloscope leads
- Assorted Emona Telecoms-Trainer patch leads

### Modules
- PCM Encoder module
- PCM Decoder module
- Master Signals module
- Variable DC Voltage module
- Low-Pass Filter module
- VCO module

---

# III. PROCEDURE

## Part A – Introduction to PCM Decoding
<img width="723" height="544" alt="image" src="https://github.com/user-attachments/assets/b336dd06-896d-4a35-9329-506fc59dcaad" />
<img width="517" height="409" alt="image" src="https://github.com/user-attachments/assets/4134026e-03cc-4f70-92a5-3738e1d9470c" />

1. Gather the equipment listed in the materials section.

2. Connect the **PCM Encoder and PCM Decoder modules** using patch leads according to the circuit diagram provided in the experiment manual.

3. Ensure the PCM Encoder produces a **PCM data output** using the Master Signals module clock.

4. Connect the PCM Encoder **PCM DATA output** to the **PCM Decoder input**.

5. Connect the oscilloscope:
   - Channel 1 → PCM DATA signal
   - Channel 2 → PCM Decoder analog output

6. Set the oscilloscope controls:
   - Trigger Source → CH1 or EXT
   - Mode → DUAL
   - Timebase → Adjust to clearly observe the digital pulses.

7. Observe the PCM data waveform on Channel 1 and the reconstructed output on Channel 2.

8. Sketch or record the waveforms.

<img width="676" height="516" alt="image" src="https://github.com/user-attachments/assets/fa890f57-0158-42b7-9465-8c867cd85f73" />

<img width="778" height="643" alt="image" src="https://github.com/user-attachments/assets/1e112832-77b5-41c6-a8f6-cfdf714ce683" />

---

## Part B – Decoding a Static Voltage Signal
<img width="662" height="404" alt="image" src="https://github.com/user-attachments/assets/96528b2c-7544-442e-b9b6-0a91cc4c4f6a" />

1. Connect the **Variable DC Voltage module** to the PCM Encoder input.

2. Adjust the Variable DC voltage to produce different PCM output codes.

3. Observe how the PCM Decoder converts these digital codes into corresponding analog voltage levels.

4. Measure the reconstructed output voltage using the oscilloscope.

5. Record the relationship between:
   - Input DC voltage
   - PCM binary code
   - Decoded output voltage.
<img width="627" height="491" alt="image" src="https://github.com/user-attachments/assets/64f3cd79-44a0-46f8-83e0-68ad54669b68" />

---

## Part C – Decoding Continuously Varying Signals

1. Modify the circuit to allow a **continuously varying signal** to be encoded.

2. Use the **VCO module** to generate the clock signal for the PCM encoder.

3. Ensure the PCM encoder produces a continuous stream of digital data.

4. Feed the PCM DATA output into the PCM Decoder module.

5. Observe the reconstructed analog signal on the oscilloscope.

6. Compare the decoded waveform with the original analog input signal.

7. Note any differences caused by **quantization error**.

---

## Part D – Signal Reconstruction
<img width="778" height="386" alt="image" src="https://github.com/user-attachments/assets/133acba1-1e8c-480a-b0ec-bfe695c4ac22" />

1. Pass the PCM Decoder output through a **low-pass filter module**.

2. Observe how the filter smooths the stepped waveform.

3. Compare the filtered output signal with the original input signal.

4. Adjust the filter cutoff frequency and observe its effect on signal reconstruction.
<img width="654" height="501" alt="image" src="https://github.com/user-attachments/assets/42198469-1be4-4a9f-8e34-2d1f5336f9f5" />

---

# IV. RESULTS AND DISCUSSION

The experiment demonstrated how a PCM decoder converts digital PCM signals back into analog voltages. The PCM encoder first converts the analog signal into binary codes representing discrete quantization levels. These binary codes are then transmitted to the PCM decoder.

The PCM decoder interprets each binary code and reconstructs the corresponding voltage level. When a static DC voltage was applied to the encoder, the decoder output produced a constant voltage level corresponding to the encoded binary value.

When the input voltage was varied gradually, the decoder output changed in discrete steps, reflecting the quantized levels produced during encoding. This behavior confirmed the presence of **quantization**, where continuous signals are represented by a finite set of discrete values.

When a continuously varying input signal was applied, the PCM decoder produced a staircase-like waveform corresponding to the sampled and quantized input signal. Passing this waveform through a low-pass filter smoothed the output, resulting in a signal that closely resembled the original analog waveform.

This experiment highlighted the importance of the PCM decoding process in digital communication systems, where digital signals must be accurately converted back into analog form for practical use.

<img width="723" height="544" alt="image" src="https://github.com/user-attachments/assets/382bfa5c-0bdb-4d2d-9135-f18818fdc083" />

<img width="676" height="516" alt="image" src="https://github.com/user-attachments/assets/53fac087-92ae-4217-9849-d222cd933618" />

<img width="627" height="491" alt="image" src="https://github.com/user-attachments/assets/df53f7cf-edd7-49bb-a2d6-db00d1d9fc8d" />

<img width="654" height="501" alt="image" src="https://github.com/user-attachments/assets/a70a846c-0b34-439c-a468-609e8dd2eb15" />

---

# V. REFLECTION / LEARNING SUMMARY

This experiment provided practical insight into how PCM decoding works in digital communication systems. By observing the decoded output signals on the oscilloscope, it became clear how digital PCM data can be converted back into analog voltages corresponding to the original signal.

The experiment also illustrated the effect of quantization on signal reconstruction. Since PCM encoding represents signals using discrete voltage levels, the decoded signal initially appears as a staircase waveform. However, applying a low-pass filter helps smooth the signal and approximate the original analog waveform.

Understanding PCM decoding is essential in many modern technologies such as digital telephony, audio processing, and multimedia communication systems. Through this experiment, the principles of digital-to-analog conversion and signal reconstruction became clearer.

Overall, the experiment reinforced the importance of PCM systems in digital communication and demonstrated how encoded signals can be successfully decoded and reconstructed.
