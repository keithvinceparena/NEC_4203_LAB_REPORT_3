# EXPERIMENT 20: UNDERSAMPLING IN SDR (SOFTWARE DEFINED RADIO)

## I. OBJECTIVES
* To set up and observe a bandwidth-limited DSBSC signal.
* To demonstrate direct down-conversion of a high-frequency signal using the principle of undersampling.
* To analyze the relationship between sampling frequency, carrier frequency, and the resulting baseband signal.

---

## II. MATERIALS AND COMPONENTS USED
* Emona Telecoms-Trainer 101 (plus power pack)
* Dual-channel 20MHz oscilloscope
* Two Emona Telecoms-Trainer 101 oscilloscope leads
* Assorted Emona Telecoms-Trainer 101 patch leads
* Modules: Master Signals, Multiplier, Dual Analog Switch, Tuneable LPF, Baseband LPF.

---

## III. PROCEDURE

### PART A – Setting up a Bandwidth-limited Signal
1.  Connect the equipment according to the "Setting up a Bandwidth-limited Signal" block diagram.
2.  Input a 2kHz Sine wave and a 100kHz Sine wave into the Multiplier module to generate a Double Sideband Suppressed Carrier (DSBSC) signal.
3.  Connect the output of the Multiplier to the Oscilloscope (Channel 1) to observe the modulated waveform.
4.  Measure the frequency and bandwidth of the resulting signal.

### PART B – Direct Down-conversion using Undersampling
1.  Use the Dual Analog Switch to sample the DSBSC signal generated in Part A.
2.  Provide a sampling clock ($f_s$) from the VCO module or Master Signals.
3.  Pass the sampled signal through the Baseband LPF to recover the message.
4.  Observe the output on Channel 2 of the oscilloscope and compare it with the original 2kHz message signal.
5.  Vary the sampling frequency to observe the effects of undersampling on signal recovery.

---

## IV. RESULTS AND DISCUSSION

### Data Observations
Based on the oscilloscope captures (Images 74, 75, and 76):
* Message Signal ($f_m$): 2kHz Sine wave.
* Carrier Signal ($f_c$): 100kHz Sine wave.
* DSBSC Output: A complex envelope where the carrier is suppressed, showing the phase reversals characteristic of DSBSC.
* Recovered Signal: After undersampling and low-pass filtering, the original 2kHz message was successfully reconstructed, despite the sampling rate being significantly lower than the carrier frequency.

### Questions & Answers

1. For the given inputs to the Multiplier module, what are the frequencies of the two sinewaves that make up the DSBSC signal?
The DSBSC signal is composed of the sum and difference frequencies:
* Upper Sideband (USB): $f_c + f_m = 100\text{kHz} + 2\text{kHz} = 102\text{kHz}$
* Lower Sideband (LSB): $f_c - f_m = 100\text{kHz} - 2\text{kHz} = 98\text{kHz}$

2. What’s the bandwidth of the DSBSC signal?
The bandwidth ($BW$) is the difference between the highest and lowest frequency components:
$$BW = (f_c + f_m) - (f_c - f_m) = 2f_m$$
$$BW = 102\text{kHz} - 98\text{kHz} = 4\text{kHz}$$

3. What’s the significance of the signal on the Baseband LPF’s output?
The signal at the output of the Baseband LPF represents the reconstructed message signal. In an SDR context, this proves that undersampling (sampling at a rate much lower than the carrier frequency, but at least twice the *bandwidth* of the signal) can successfully down-convert a high-frequency signal directly to baseband without needing multiple analog mixing stages.

4. Given the sampling frequency ($f_s$) is $X$, why is the signal recovered?
The signal is recovered because of the Nyquist Criterion for Bandpass Signals. Even though $f_s < f_c$, as long as $f_s > 2 \times BW$, the information is preserved in the aliases. The filter then selects the correct alias at the baseband frequency.

---

## V. REFLECTION / LEARNING SUMMARY
This experiment successfully demonstrated the power of Undersampling in modern radio architecture. I learned that the traditional Nyquist rate ($f_s > 2f_{max}$) is a specific case for baseband signals. For bandpass signals, like those in SDR, we can use a lower sampling rate to effectively "alias" the high-frequency signal down to a lower frequency. This technique is crucial in Software Defined Radio because it reduces the requirements on the Analog-to-Digital Converter (ADC) speed and eliminates the need for expensive local oscillators and mixers for down-conversion. The clarity of the recovered 2kHz signal on the oscilloscope confirmed that the message remains intact as long as the bandwidth-based sampling criteria are met.
