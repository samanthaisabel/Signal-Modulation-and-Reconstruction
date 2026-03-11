<a id="readme-top"></a>

# 📡 Communication Systems: FM Mod • FM Demod • Sampling • PCM • Bandwidth Restoration
> 🟦 **Field:** Telecommunications Engineering  
> 🟧 **Hardware:** Emona Telecoms-Trainer 101 Suite  

---

## 📝 Executive Summary
This repository provides a technical validation of the end-to-end signal chain. It covers the transition from **Analog Frequency Modulation (FM)** to **Digital Pulse Code Modulation (PCM)**, along with critical analysis of **Nyquist Sampling** and **Bandwidth Restoration** techniques using industry-standard trainer modules.

---

## 🛠️ Technical Skills
*   **Modulation:** FM Generation, Frequency Deviation, and Sideband Analysis.
*   **Demodulation:** Slope Detection, Foster-Seeley, and PLL Stabilization.
*   **Digital Processing:** PCM Encoding/Decoding, Quantization, and Binary Mapping.
*   **Signal Integrity:** Nyquist Rate Validation, Aliasing Mitigation, and ISI Recovery.

---

## 📋 Table of Contents
* [Frequency Modulation](#frequency-modulation)
* [FM Demodulation](#fm-demodulation)
* [Sampling & Reconstruction](#sampling--reconstruction)
* [PCM Encoding](#pcm-encoding)
* [PCM Decoding](#pcm-decoding)
* [Bandwidth Limiting & Restoration](#bandwidth-limiting--restoration)

---

## Frequency Modulation
> *Analysis of frequency deviation and carrier stability.*

<details>
<summary><b>View Details</b></summary>

### Introduction
Exploration of FM signal generation where carrier frequency shifts in proportion to modulating signal amplitude while maintaining constant power.

### Equipment
*   **Emona Telecoms-Trainer 101** (plus power-pack)
*   **Dual-channel 20MHz oscilloscope**
*   Emona 101 oscilloscope leads & assorted patch leads

### Experimental Results
*   **Constant Amplitude:** Confirmed carrier amplitude remains static during modulation.
*   **Deviation:** Proved that increasing modulating amplitude directly increases frequency deviation.
*   **Carson’s Rule:** Measured bandwidth aligned with theoretical predictions.

### Laboratory Observations
<p align="center">
  <img src="assets/Frequency%20Modulation/2kHz_squarewave_message_osc.jpg" width="45%">
  <img src="assets/Frequency%20Modulation/2kHz_squarewave_message.jpg" width="45%">
</p>

<p align="center">
  <img src="assets/Frequency%20Modulation/FM_sinewave_osc.jpg" width="45%">
  <img src="assets/Frequency%20Modulation/FM_sinewave_setup.jpg" width="45%">
</p>

### Takeaways
Successfully validated that information in FM is stored in frequency shifts, providing high resistance to amplitude noise.

### Summary
FM systems effectively trade bandwidth for improved signal-to-noise ratios.
</details>

---

## FM Demodulation
> *Comparative study of signal recovery and noise rejection.*

<details>
<summary><b>View Details</b></summary>

### Introduction
The process of converting frequency variations back into original voltage signals using different circuit topologies.

### Equipment
*   **Emona Telecoms-Trainer 101** suite
*   **Dual-channel 20MHz oscilloscope**
*   **Headphones** (for audio signal validation)

### Experimental Results
*   **Slope Detector:** Recovered signal but showed high sensitivity to noise.
*   **Foster-Seeley:** Improved accuracy via phase-relationship detection.
*   **PLL Demodulator:** Provided the most stable and clean recovered signal.

### Laboratory Observations
<p align="center">
  <img src="assets/FM%20Demodulation/Transmitting_Recovering_Sinewave.jpg" width="45%">
  <img src="assets/FM%20Demodulation/Recovering_Speech_Osc.jpg" width="45%">
</p>

<p align="center">
  <img src="assets/FM%20Demodulation/Transmitting_Recovering_Speech_Setup.jpg" width="45%">
</p>

<p align="center">
  <a href="assets/FM%20Demodulation/Speech_Output.mp4"><strong>🎥 Watch: Speech Output Recovery Demo</strong></a>
</p>

### Takeaways
Identified the **Phase-Locked Loop (PLL)** as the superior method for stable, low-distortion signal recovery.

### Summary
Proper demodulator selection is critical for maintaining signal fidelity in practical communication.
</details>

---

## Sampling & Reconstruction
> *Validation of the Nyquist-Shannon Theorem and signal recovery.*

<details>
<summary><b>View Details</b></summary>

### Introduction
Converting continuous analog signals into discrete-time samples for digital processing.

### Equipment
*   **Emona Telecoms-Trainer 101**
*   **Dual-channel 20MHz oscilloscope**
*   Assorted Emona patch leads

### Experimental Results
*   **Nyquist Rate:** Confirmed perfect reconstruction when $f_s \ge 2f_{max}$.
*   **Aliasing:** Observed overlapping frequencies and distortion when undersampled.
*   **Reconstruction:** Successfully used an LPF to smooth samples back to analog.

### Laboratory Observations
<p align="center">
  <img src="assets/Sampling%20and%20Reconstruction/Sampling_Simple_Osc.jpg" width="45%">
  <img src="assets/Sampling%20and%20Reconstruction/Sampling_Simple_Setup.jpg" width="45%">
</p>

<p align="center">
  <img src="assets/Sampling%20and%20Reconstruction/Reconstructing_Message_Osc.jpg" width="45%">
  <img src="assets/Sampling%20and%20Reconstruction/Reconstructing_Message_Setup.jpg" width="45%">
</p>

<p align="center">
  <img src="assets/Sampling%20and%20Reconstruction/New_Sampled_Osc.jpg" width="45%">
  <img src="assets/Sampling%20and%20Reconstruction/New_Sampled_Setup.jpg" width="45%">
</p>

<p align="center">
  <img src="assets/Sampling%20and%20Reconstruction/Aliasing_Osc.jpg" width="45%">
  <img src="assets/Sampling%20and%20Reconstruction/Output_Final.jpg" width="45%">
</p>

<p align="center">
  <a href="assets/Sampling%20and%20Reconstruction/Aliasing_Output.mp4"><strong>🎥 Watch: Aliasing Waveform Output</strong></a>
</p>

### Takeaways
Verified that the sampling rate and output filtering are the two most critical factors in digital signal integrity.

### Summary
Accurate reconstruction depends on adhering to the Nyquist limit to prevent aliasing.
</details>

---

## PCM Encoding
> *Digitizing signals via sampling, quantization, and binary mapping.*

<details>
<summary><b>View Details</b></summary>

### Introduction
Pulse Code Modulation (PCM) converts analog waveforms into a serial binary bitstream.

### Equipment
*   **Emona Telecoms-Trainer 101**
*   **Dual-channel 20MHz oscilloscope**

### Experimental Results
*   **Quantization:** Observed the "staircase" approximation of the input signal.
*   **Resolution:** Verified that more bits per sample reduce quantization error.
*   **Encoding:** Successfully mapped analog samples to binary code.

### Laboratory Observations
<p align="center">
  <img src="assets/PCM%20Encoding/PCM_Static_DC_Diff.jpg" width="45%">
  <img src="assets/PCM%20Encoding/PCM_Static_DC_Setup.jpg" width="45%">
</p>

<p align="center">
  <img src="assets/PCM%20Encoding/PCM_Output_5.8mV.jpg" width="30%">
  <img src="assets/PCM%20Encoding/PCM_Output_200mV.jpg" width="30%">
  <img src="assets/PCM%20Encoding/PCM_Output_Module.jpg" width="30%">
</p>

<p align="center">
  <img src="assets/PCM%20Encoding/PCM_End_Output.jpg" width="45%">
</p>

<p align="center">
  <a href="assets/PCM%20Encoding/PCM_Output_Video.mp4"><strong>🎥 Watch: PCM Output Signal Demo</strong></a>
</p>

### Takeaways
Learned the trade-off between signal quality (bits) and transmission bandwidth.

### Summary
PCM encoding creates a robust digital representation of analog data for telecommunications.
</details>

---

## PCM Decoding
> *Recovering analog signals from digital binary data.*

<details>
<summary><b>View Details</b></summary>

### Introduction
The inverse of encoding: converting binary logic back into quantized voltages and smooth waveforms.

### Equipment
*   **Emona Telecoms-Trainer 101**
*   **Dual-channel 20MHz oscilloscope**

### Experimental Results
*   **Reconstruction:** Binary inputs were converted back to a staircase waveform.
*   **Recovery:** Low-pass filtering successfully removed sampling noise.
*   **Fidelity:** Recovered waveform closely matched the original analog input.

### Laboratory Observations
<p align="center">
  <img src="assets/PCM%20Decoding/Setup_PCM_Encoder.jpg" width="45%">
  <img src="assets/PCM%20Decoding/Part_A.jpg" width="45%">
</p>

<p align="center">
  <img src="assets/PCM%20Decoding/Part_B_16.jpg" width="30%">
  <img src="assets/PCM%20Decoding/Part_B_25.jpg" width="30%">
  <img src="assets/PCM%20Decoding/Part_C_NoSpeech.jpg" width="30%">
</p>

<p align="center">
  <img src="assets/PCM%20Decoding/Part_D.jpg" width="45%">
</p>

### Takeaways
Confirmed that digital-to-analog conversion requires precise filtering to restore signal smoothness.

### Summary
PCM decoding successfully restores analog information, completing the digital-to-analog loop.
</details>

---

## Bandwidth Limiting & Restoration
> *Managing Intersymbol Interference (ISI) in restricted channels.*

<details>
<summary><b>View Details</b></summary>

### Introduction
Analysis of how bandwidth-limited channels distort digital pulses and techniques to restore them.

### Equipment
*   **Emona Telecoms-Trainer 101**
*   **Dual-channel 20MHz oscilloscope**

### Experimental Results
*   **Distortion:** Observed "rounding" of digital pulses and signal overlapping (ISI).
*   **ISI Effects:** Overlapping between adjacent bits was identified as a source of bit errors.
*   **Restoration:** Successfully used restoration filters to improve signal clarity.

### Laboratory Observations
<p align="center">
  <img src="assets/Bandwidth%20limiting%20and%20restoring%20digital%20signals/Part_A.jpg" width="30%">
  <img src="assets/Bandwidth%20limiting%20and%20restoring%20digital%20signals/Part_B.jpg" width="30%">
  <img src="assets/Bandwidth%20limiting%20and%20restoring%20digital%20signals/Part_C_2.jpg" width="30%">
</p>

<p align="center">
  <img src="assets/Bandwidth%20limiting%20and%20restoring%20digital%20signals/Part_C_Final.jpg" width="45%">
</p>

<p align="center">
  <a href="assets/Bandwidth%20limiting%20and%20restoring%20digital%20signals/Bandwidth_Output_Video.mp4"><strong>🎥 Watch: Bandwidth Restoration Demo</strong></a>
</p>

### Takeaways
Proved that bandwidth is a finite resource and restoration is necessary for high-speed data integrity.

### Summary
Proper filtering and restoration techniques are essential for reliable communication in bandwidth-limited channels.
</details>

---

## Conclusion
This technical validation bridged the gap between theoretical signal mathematics and physical hardware deployment using the **Emona Telecoms-Trainer 101** system. By navigating the complexities of **FM noise immunity**, **Nyquist sampling limits**, and **PCM resolution trade-offs**, this work demonstrates a professional understanding of modern telecommunication protocols.

---

<p align="right"><a href="#readme-top">Back to top ↑</a></p>
