# EXPERIMENT 18: QUADRATURE PHASE SHIFT KEYING (QPSK)

---

# I. OBJECTIVES

The objectives of this experiment are:

1. To understand the principle of **Quadrature Phase Shift Keying (QPSK)** as a digital modulation technique.
2. To observe how a digital data stream can be split into **two parallel bit streams** for transmission.
3. To generate **two BPSK signals (PSK₁ and PSK₂)** and combine them to produce a QPSK signal.
4. To analyze the QPSK signal using an oscilloscope.
5. To understand how **phase discrimination** can be used to recover one of the component BPSK signals.
6. To study the phase relationships between the **local carrier and the transmitted carriers** in QPSK systems.

Quadrature Phase Shift Keying is a digital modulation scheme that transmits **two bits per symbol by shifting the carrier phase into four possible states (0°, 90°, 180°, and 270°)**. :contentReference[oaicite:1]{index=1}

---

# II. MATERIALS AND COMPONENTS USED

The following equipment and components were used:

- Emona Telecoms-Trainer 101 (plus power pack)
- Dual-channel 20 MHz oscilloscope
- Three Emona Telecoms-Trainer 101 oscilloscope leads
- Assorted Emona Telecoms-Trainer 101 patch leads

These instruments were used to generate, observe, and analyze the QPSK signal and its component signals.

---

# III. PROCEDURE

## Part A – Generating a QPSK Signal

1. Gather the equipment listed in the materials section.
2. Set up the oscilloscope according to the standard configuration used in previous experiments.
3. Use the **Sequence Generator module** to produce a digital data stream.
4. Connect the Sequence Generator output to the **Serial-to-Parallel (S/P) converter module**.
5. The S/P converter splits the digital data into two streams:
   - **Odd bits**
   - **Even bits**
6. Connect the outputs of the S/P converter to two **Multiplier modules**.
7. Use the **Master Signals module** to generate a **100 kHz sine carrier**.
8. Apply the carrier signal to both multiplier modules.
9. The multipliers produce two BPSK signals:
   - **PSK₁**
   - **PSK₂**
10. Observe the signals using the oscilloscope.

---

## Part B – Creating the QPSK Signal

1. Connect the outputs of the two multiplier modules to the **Adder module**.
2. Adjust the Adder module’s gain control to obtain approximately a **4 Vp-p output**.
3. Observe the Adder module output on the oscilloscope.
4. Compare the waveform with the individual BPSK signals.

The Adder combines the two BPSK signals to create the **QPSK signal**.

---

## Part C – Using Phase Discrimination to Recover One QPSK Component

1. Modify the setup to include a **Phase Shifter module**.
2. Connect the phase shifter to the **local carrier signal**.
3. Adjust the **Phase Adjust control** while observing the output.
4. Use the **Tunable Low Pass Filter (LPF)** to filter the product detector output.
5. Observe the signal on the oscilloscope while adjusting the phase control.

This process allows the demodulator to recover one of the two BPSK signals that make up the QPSK signal.

---

# IV. RESULTS AND DISCUSSION

## Part A – Modeling the Digital Data

The Sequence Generator module produced a digital bit stream which was divided into two parallel data streams using the Serial-to-Parallel converter. One output contained the **odd bits** while the other contained the **even bits**.

### Question 1  
**What is the relationship between the bit rate of these two digital signals and the bit rate of the Sequence Generator module’s output?**

Each of the two digital signals has **half the bit rate** of the Sequence Generator output.  

This occurs because the serial bit stream is split into two parallel streams. Each stream carries alternating bits, so each channel processes only half the total bit rate.

---

## Part B – Observing the Multiplier Outputs

Each multiplier module multiplies its digital data input with the carrier signal. This produces a **Binary Phase Shift Keying (BPSK)** signal.

### Question 2  
**What feature of the Multiplier’s output suggests that it’s a BPSK signal?**

The multiplier output shows a **constant-amplitude sinusoidal waveform whose phase reverses by 180° whenever the digital data changes state**.  

This phase reversal is the defining characteristic of BPSK modulation.

---

## Part C – Signal Type at the Multiplier Output

### Question 3  
**What type of signal is present on the Multiplier’s output?**

The signal present at the multiplier output is a **BPSK (Binary Phase Shift Keying) modulated carrier signal**.

It is equivalent to a **Double Sideband Suppressed Carrier (DSBSC)** signal whose phase changes depending on the digital data.

---

## Part D – Generating the QPSK Signal

The outputs of the two BPSK modulators are combined using an Adder module. The two signals are phase-shifted versions of the same carrier, allowing them to be transmitted simultaneously.

### Question 4  

**According to theory, what type of digital signal transmission is present on the Adder’s output?**

The signal on the Adder’s output is a **Quadrature Phase Shift Keying (QPSK) signal**.

QPSK combines two BPSK signals that are **90° out of phase** with each other.

---

### Question 5  

**Why is there only one sinewave when the QPSK signal is made up of two BPSK signals?**

Although two BPSK signals are combined, they share the same carrier frequency. Because the two carriers are **orthogonal (90° apart in phase)**, their combination still produces a single sinusoidal waveform whose phase changes to represent the digital data.

Thus the waveform appears as one sinewave whose phase changes among four possible states.

---

## Part E – Phase Discrimination

### Question 6  

**What is the cause of the 3-level and 4-level signals observed at the Tunable LPF output during phase adjustments?**

These multi-level signals occur because the demodulator is receiving **both BPSK components simultaneously**.  

If the phase alignment is not correct, the demodulator partially detects both signals, producing intermediate amplitude levels.

---

### Question 7  

**How many different Phase Adjust control positions give a bipolar signal?**

Two phase positions produce a bipolar signal. These correspond to the phase alignments where the demodulator correctly detects one of the two BPSK components.

---

### Question 8  

**What is the phase relationship between the local carrier and the carrier signals used to generate the PSK₁ and PSK₂ signals?**

The local carrier must be **phase-synchronized with one of the transmitted carrier signals** to correctly demodulate the corresponding BPSK component.

PSK₁ and PSK₂ carriers differ by **90° in phase**.

---

### Question 9  

**Why is the demodulator considered to be only one half of a full QPSK receiver?**

The demodulator extracts only **one of the two BPSK signals** (either PSK₁ or PSK₂).  

A complete QPSK receiver requires **two demodulators**, one for the in-phase (I) component and one for the quadrature (Q) component.

---

# V. REFLECTION / LEARNING SUMMARY

This experiment demonstrated the operation of **Quadrature Phase Shift Keying (QPSK)**, a digital modulation technique that allows two bits to be transmitted per symbol by using four different carrier phase states.

Through this experiment, the following concepts were learned:

- A serial digital data stream can be split into **two parallel bit streams**.
- Each stream can modulate a carrier using **BPSK modulation**.
- Two BPSK signals that are **90° out of phase** can be combined to form a **QPSK signal**.
- QPSK improves spectral efficiency by transmitting **two bits per symbol** instead of one.
- Phase discrimination can be used to extract one component of the QPSK signal.
- A full QPSK receiver requires **two demodulation paths** to recover both data streams.

Overall, the experiment improved understanding of how advanced digital modulation techniques such as QPSK are implemented and analyzed in communication systems.
