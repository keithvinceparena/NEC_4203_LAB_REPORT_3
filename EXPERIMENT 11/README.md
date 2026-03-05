# EXPERIMENT 11: SAMPLING AND RECONSTRUCTION
## I. OBJECTIVES

1. Understand the concept of **sampling** in digital communication systems.
2. Observe how an **analog signal** is converted into a **sampled signal**.
3. Differentiate between **natural sampling** and **sample-and-hold sampling**.
4. Reconstruct a sampled signal using a **low-pass filter**.
5. Investigate the effects of **aliasing** when the sampling frequency is reduced.

---

## II. MATERIALS AND COMPONENTS USED

### Main Equipment
- Emona Telecoms-Trainer 101 (plus power pack)
- Dual-channel 20 MHz oscilloscope
- Two Emona Telecoms-Trainer 101 oscilloscope leads
- Assorted Emona Telecoms-Trainer 101 patch leads

### Modules / Components
- Master Signals module (2 kHz sinewave + digital sampling signal)
- Dual Analog Switch module
- Sample-and-Hold (S/H) module
- Tunable Low-Pass Filter module
- VCO module (for variable sampling frequency)

---

## III. PROCEDURE

> **Note:** This is organized as a guide-style procedure (step-by-step), based on the experiment module and your setup photos.

### Part A – Sampling a Simple Message (Natural Sampling)
<img width="765" height="504" alt="image" src="https://github.com/user-attachments/assets/6bbe19ba-b5e3-445c-a670-5602fdcc6465" />

1. Gather all required equipment and modules.
2. Construct the **natural sampling setup** using the Dual Analog Switch:
   - Use **2 kHz sinewave** as the message (input).
   - Use **8 kHz digital pulse** as the sampling/control signal.
3. Connect oscilloscope:
   - **CH1:** message signal (2 kHz sinewave)
   - **CH2:** sampled message output
4. Adjust oscilloscope settings to clearly view both waveforms.
5. Observe and record the waveform behavior of the sampled signal.
<img width="765" height="583" alt="image" src="https://github.com/user-attachments/assets/557b0c20-5dac-455c-adce-28d6e5e77851" />

---

### Part B – Sampling Speech

1. Disconnect the **2 kHz sinewave** message signal connection.
2. Connect the **Speech module output** as the message source.
3. Observe the sampled speech waveform on the oscilloscope while speaking.
4. Record observations (shape changes, amplitude variation, pulse sampling behavior).

---

### Part C – Reconstructing a Sampled Message

1. Prepare the reconstruction setup:
   - Feed the sampled message into the **Tunable Low-Pass Filter**.
2. Set filter controls:
   - **Gain:** around midpoint
   - **Cut-off frequency:** fully counter-clockwise (minimum)
3. Observe filter output (initially should be nearly nothing / highly attenuated).
4. Slowly increase the cut-off frequency clockwise until the **message is reconstructed**.
5. Record the reconstructed waveform and compare with the original message.

---

### Part D – Aliasing

1. Replace the fixed sampling signal with the **VCO module** (variable frequency).
2. Start from a frequency where reconstruction works normally.
3. Slowly reduce the sampling frequency while observing the reconstructed signal.
4. Note the point where distortion appears and identify it as **aliasing**.
5. Measure the VCO output period and compute frequency for the table if required.

---

## IV. RESULTS AND DISCUSSION

### A. Natural Sampling Result
**Observed behavior:** The sampled waveform appears as pulses whose amplitudes follow the original sinewave envelope.

**Why this confirms natural sampling:**
- The pulse heights change according to the message amplitude.
- The output resembles a “gated” version of the sinewave.

✅ **Conclusion:** The setup models **natural sampling**.

---

### B. Sample-and-Hold Result
**Observed behavior:** The sampled waveform resembles a **staircase / stepped** signal.

**Why this confirms sample-and-hold:**
- Each sampled level remains constant (held) until the next sample.
- Flat “steps” appear instead of continuously varying pulses.

✅ **Conclusion:** The setup models **sample-and-hold sampling**.

---

### C. Reconstruction Result
**Observed behavior:** Passing the sampled signal through a low-pass filter produces a smooth waveform resembling the original message.

**Explanation:**  
Sampling introduces high-frequency components (images). A **low-pass filter** removes the higher components and keeps the baseband message.

✅ **Conclusion:** The original message is recovered by low-pass filtering.

---

### D. Aliasing Result
**Observed behavior:** As sampling frequency decreases, the reconstructed signal becomes distorted.

**Distortion name:** **Aliasing**

**Nyquist condition:**
\[
f_s \ge 2f_m
\]

For a **2 kHz** message:
\[
f_s(min) = 2(2kHz) = 4kHz
\]

**Why actual minimum is higher than theoretical:**
- Real filters are not “ideal”; cutoff is gradual (not a sharp wall).
- Some alias components may still leak through if \(f_s\) is too close to Nyquist.

✅ **Conclusion:** Sampling frequency must be **higher than the Nyquist minimum** in real systems.

---

## V. REFLECTION / LEARNING SUMMARY

This experiment made sampling concepts more concrete by directly showing waveforms on the oscilloscope. I learned that **natural sampling** produces pulse amplitudes that follow the signal envelope, while **sample-and-hold** produces a stepped waveform because values are held between sampling instants. I also learned how a **low-pass filter** can reconstruct the original analog message by removing higher-frequency components introduced during sampling. Finally, I understood why **aliasing** occurs and why real systems must sample above the theoretical Nyquist minimum due to practical filter limitations.


