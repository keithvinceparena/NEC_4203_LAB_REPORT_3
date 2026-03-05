# Lab Report: Experiment 19 - DSSS Modulation and Demodulation

## I. OBJECTIVES
* To demonstrate the principles of Direct Sequence Spread Spectrum (DSSS) modulation.
* To observe the spreading of a baseband signal's bandwidth using a pseudo-noise (PN) sequence.
* To perform demodulation (de-spreading) and recover the original message signal.
* To investigate the robustness of DSSS against narrowband interference (jamming).

---

## II. MATERIALS AND COMPONENTS USED
* Emona Telecoms-Trainer 101 (plus power pack)
* Dual-channel 20MHz Oscilloscope
* Two Emona Telecoms-Trainer 101 oscilloscope leads
* Assorted Emona Telecoms-Trainer 101 patch leads
* Modules: Master Signals, Sequence Generator, Multiplier, Dual Analog Switch, Baseband LPF.

---

## III. PROCEDURE

### Part A: Generating a DSSS Signal
1. Setup the Message: Connect a 2kHz sine wave from the Master Signals module to the input of the Multiplier.
2. Setup the PN Sequence: Connect the "X-output" of the Sequence Generator (acting as the spreading code) to the second input of the Multiplier.
3. Observe Spreading: Connect Channel 1 of the oscilloscope to the 2kHz message and Channel 2 to the Multiplier output (the DSSS signal). Note the phase reversals in the sine wave.

### Part B: Demodulating the DSSS Signal
1. First Stage De-spreading: Connect the DSSS signal (output of the first Multiplier) to one input of a second Multiplier module.
2. Synchronous Clock: Connect the same "X-output" from the Sequence Generator used in Part A to the other input of the second Multiplier.
3. Recovery: Connect the output of the second Multiplier to the input of the Baseband LPF.
4. Final Observation: Observe the output of the LPF on the oscilloscope and compare it to the original 2kHz message.

### Part C: Jamming Resistance
1. Introduce Interference: Use an Adder module to combine the DSSS signal with a "jamming" signal (e.g., a high-frequency sine wave from a VCO).
2. Analyze Output: Observe if the 2kHz message can still be recovered at the LPF output despite the presence of the interference.

---

## IV. RESULTS AND DISCUSSION

### Data Observations
Based on the oscilloscope outputs provided in the laboratory data:

| Signal Stage | Frequency/Characteristics | Observation |
| :--- | :--- | :--- |
| Original Message | 2.081 kHz | A clean, continuous sine wave. |
| Spreading Sequence | High-rate PN Code | A digital-like sequence of pulses (chips). |
| DSSS Signal | Wideband | The sine wave undergoes phase shifts every time the PN code changes state (Phase Shift Keying effect). |
| Recovered Signal | ~2 kHz | After de-spreading and low-pass filtering, the original sine wave is restored with some minor ripple. |



### Discussion
In this experiment, we utilized Direct Sequence Spread Spectrum. The core mechanism involves multiplying a low-frequency message $m(t)$ with a high-frequency pseudo-noise sequence $c(t)$. 

Mathematically, the transmitted signal is:
$$s(t) = m(t) \cdot c(t)$$

Because $c(t)$ has a much higher bit rate (chip rate) than the frequency of $m(t)$, the bandwidth of the signal is "spread" across a wider spectrum. This makes the signal appear as low-level noise to unauthorized receivers.

During demodulation, we multiply the received signal by the exact same PN sequence:
$$r(t) = [m(t) \cdot c(t)] \cdot c(t) = m(t) \cdot c^2(t)$$
Since $c(t)$ is a sequence of $\pm 1$, $c^2(t)$ equals 1, effectively "collapsing" or de-spreading the signal back to its original baseband form.

### Lab Questions
Q: Why doesn’t the jamming signal interfere with the recovery of the message?
A: When the receiver multiplies the incoming signal by the PN sequence, it de-spreads the desired DSSS signal. However, it spreads the narrowband jamming signal. The jammer's energy is dispersed over a wide bandwidth, and most of it is subsequently filtered out by the Baseband Low Pass Filter (LPF), leaving the recovered message relatively clean.

---

## V. REFLECTION / LEARNING SUMMARY
The experiment successfully demonstrated the "Processing Gain" of spread spectrum technology. I learned that synchronization is critical; if the PN sequence at the receiver is not perfectly aligned with the transmitter, the message cannot be recovered. This experiment highlighted why DSSS is a standard for secure and reliable communications (like GPS and Wi-Fi), as it provides an inherent layer of security and a high tolerance for intentional or accidental interference.
