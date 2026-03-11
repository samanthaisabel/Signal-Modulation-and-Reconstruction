<a id="readme-top"></a>

> [!IMPORTANT]
> `Field: RF Engineering` • `Hardware: Emona Telecoms-Trainer 101`

# Communication Systems
> Frequency Modulation • FM Demodulation • Sampling and Reconstruction • PCM Encoding • PCM Decoding • Bandwidth limiting and restoring digital signals
> 
> **Executive Summary:** Experimental evaluation of the communication signal chain, transitioning from analog modulation to digital reconstruction. This repository presents a systematic analysis of:
> * **Frequency Modulation:** Characteristics of generation, deviation limits, and PLL-stabilized recovery.
> * **Digital Communication:** Practical application of Sampling Theory, PCM protocols, and aliasing mitigation.
> * **Signal Integrity:** Analysis of bandwidth-limited channels and Intersymbol Interference (ISI) management.
> 
> *All data validated via real-time oscilloscope measurements on the Emona Trainer 101 platform.*

---

## Technical Skills Demonstrated
*   **Analog Communication:** FM generation, frequency deviation measurement, sideband, and bandwidth analysis.
*   **Signal Recovery:** Slope detector demodulation, Foster-Seeley discriminator analysis, and **Phase-Locked Loop (PLL)** stabilization.
*   **Digital Communication:** Pulse Code Modulation (PCM), quantization, binary encoding, and signal reconstruction.
*   **Signal Integrity:** Nyquist sampling validation, aliasing observation, and **Intersymbol Interference (ISI)** mitigation.

---

## System Analysis
*   **FM Noise Immunity:** Verified that frequency-based modulation is significantly less sensitive to amplitude noise than AM systems.
*   **PLL Signal Recovery:** Confirmed that PLL demodulation provides the most stable and accurate FM signal recovery in interference-heavy environments.
*   **Nyquist Sampling Theorem:** Experimentally validated that the proper sampling rate ($f_s \geq 2f_{max}$) prevents aliasing and ensures accurate reconstruction.
*   **Digital Trade-offs:** Observed how PCM bit resolution directly affects signal fidelity versus bandwidth requirements.

---

## Table of Contents
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
Focuses on the generation of an FM signal using sinusoidal modulating signals and high-frequency carriers. Information is stored in frequency shifts rather than amplitude.

### Equipment
*   **Emona Telecoms-Trainer 101** (plus power-pack)
*   **Dual-channel 20MHz oscilloscope**
*   Emona 101 oscilloscope leads & assorted patch leads

### Experimental Results
*   **Frequency Deviation:** Confirmed that increasing modulating signal amplitude directly increases carrier frequency deviation.
*   **Constant Amplitude:** Verified that carrier amplitude remains constant throughout the modulation process.
*   **Modulation Index ($\beta$):** Observed Narrowband FM characteristics for $\beta < 1$ and Sideband expansion (Wideband FM) for $\beta > 1$.
*   **Bandwidth Validation:** Measured bandwidth via spectrum analyzer closely matched theoretical **Carson’s Rule** calculations.

### Takeaways
FM demonstrates superior noise resistance compared to AM. While theoretical and measured values show minor discrepancies due to equipment tolerances, the core principles of frequency shifting were successfully validated.

### Summary
The experiment confirmed that FM bandwidth is determined by the modulation index, and carrier power remains independent of the modulation depth.

<br>

<details>
<summary><b>Laboratory Documentation</b></summary>

<p align="center">
  <img src="assets/Frequency%20Modulation/2kHz%20squarewave%20message%20(oscilloscope).jpg" height="250">
  <img src="assets/Frequency%20Modulation/2kHz%20squarewave%20message.jpg" height="250">
</p>

<p align="center">
  <img src="assets/Frequency%20Modulation/Frequency%20modulating%20a%20sinewave%20(oscilloscope).jpg" height="250">
  <img src="assets/Frequency%20Modulation/Frequency%20modulating%20a%20sinewave.jpg" height="250">
</p>

</details>
</details>

---

## FM Demodulation
> *Comparative study of signal recovery and noise rejection.*

<details>
<summary><b>View Details</b></summary>

### Introduction
The process of converting frequency variations back into original voltage signals. This study evaluates different demodulator circuit topologies and their performance under noise.

### Equipment
*   **Emona Telecoms-Trainer 101** suite
*   **Dual-channel 20MHz oscilloscope**
*   **Headphones** (for audio signal validation)

### Experimental Results
*   **Slope Detection:** Successfully recovered the signal but exhibited noticeable distortion and noise sensitivity.
*   **Foster-Seeley Discriminator:** Produced higher accuracy and reduced distortion compared to the slope detector.
*   **PLL Stability:** The **Phase-Locked Loop (PLL)** demodulator provided the most stable and clean signal recovery, maintaining lock even under interference.

### Takeaways
The PLL demodulator is superior for modern systems due to its ability to lock onto frequencies and reject amplitude noise. Proper circuit design is essential for minimizing non-ideal component effects.

### Summary
FM demodulation effectively translates frequency changes back to original messages. The choice of demodulator directly impacts the stability and clarity of the recovered signal.

<br>

<details>
<summary><b>Laboratory Documentation</b></summary>

<p align="center">
  <img src="assets/FM%20Demodulation/Transmitting%20and%20recovering%20a%20sinewave%20using%20FM.jpg" height="250">
  <img src="assets/FM%20Demodulation/Transmitting%20and%20recovering%20speech%20using%20FM%20(oscilloscope).jpg" height="250">
</p>

<p align="center">
  <img src="assets/FM%20Demodulation/Transmitting%20and%20recovering%20speech%20using%20FM.jpg" height="250">
</p>

<p align="center">
  <a href="assets/FM%20Demodulation/Speech%20Output.mp4"><strong>Watch: Speech Output Recovery Demo</strong></a>
</p>

</details>
</details>

---

## Sampling & Reconstruction
> *Validation of the Nyquist-Shannon Theorem and signal recovery.*

<details>
<summary><b>View Details</b></summary>

### Introduction
Focuses on the conversion of analog signals into discrete-time signals. This process is fundamental for digital processing and transmission.

### Equipment
*   **Emona Telecoms-Trainer 101**
*   **Dual-channel 20MHz oscilloscope**
*   Assorted Emona patch leads

### Experimental Results
*   **Nyquist Verification:** Confirmed perfect reconstruction when sampling at $f_s \ge 2f_{max}$.
*   **Aliasing Observation:** Observed irreversible distortion and overlapping frequency components when undersampled.
*   **Signal Smoothing:** Successfully utilized a low-pass filter to restore the original waveform.

### Takeaways
Proper sampling frequency is the primary factor in preserving signal integrity, while the reconstruction filter is essential for removing high-frequency artifacts.

### Summary
The experiment validated the Nyquist Sampling Theorem, proving that accurate reconstruction depends on an adequate sampling rate and precise filtering.

<br>

<details>
<summary><b>Laboratory Documentation</b></summary>

<p align="center">
  <img src="assets/Sampling%20and%20Reconstruction/Sampling%20a%20simple%20message%20(oscilloscope).jpg" height="250">
  <img src="assets/Sampling%20and%20Reconstruction/Sampling%20a%20simple%20message.jpg" height="250">
</p>

<p align="center">
  <img src="assets/Sampling%20and%20Reconstruction/Reconstructing%20a%20sampled%20message%20(oscilloscope).jpg" height="250">
  <img src="assets/Sampling%20and%20Reconstruction/Reconstructing%20a%20sampled%20message.jpg" height="250">
</p>

<p align="center">
  <img src="assets/Sampling%20and%20Reconstruction/New%20sampled%20message%20(oscilloscope).jpg" height="250">
  <img src="assets/Sampling%20and%20Reconstruction/New%20sampled%20message.jpg" height="250">
</p>

<p align="center">
  <img src="assets/Sampling%20and%20Reconstruction/Aliasing.jpg" height="250">
  <img src="assets/Sampling%20and%20Reconstruction/Output.jpg" height="250">
  <img src="assets/Sampling%20and%20Reconstruction/Waveform.jpg" height="250">
</p>

<p align="center">
  <a href="assets/Sampling%20and%20Reconstruction/ALIASING%20OUTPUT.mp4"><strong>Watch: Aliasing Output Video</strong></a>
</p>

</details>
</details>

---

## PCM Encoding
> *Digitizing signals via sampling, quantization, and binary mapping.*

<details>
<summary><b>View Details</b></summary>

### Introduction
Pulse Code Modulation (PCM) encoding is a method used to digitally represent analog signals through sampling, quantization, and binary encoding.

### Equipment
*   **Emona Telecoms-Trainer 101** (plus power-pack)
*   **Dual-channel 20MHz oscilloscope**
*   Emona 101 oscilloscope leads & assorted patch leads

### Experimental Results
*   **Quantization:** Successfully quantized the sampled signal into discrete levels.
*   **Binary Mapping:** Binary outputs correctly corresponded to quantized amplitudes.
*   **Resolution Error:** Increasing the number of bits significantly reduced quantization error.

### Takeaways
Learned the critical trade-off between signal quality (more bits) and transmission bandwidth requirements.

### Summary
PCM encoding successfully digitizes analog signals, forming the hardware foundation of modern digital telecommunication.

<br>

<details>
<summary><b>Laboratory Documentation</b></summary>

<p align="center">
  <img src="./assets/PCM%20Encoding/Introduction%20to%20PCM%20encoding%20using%20a%20static%20DC%20Voltage.jpg?raw=true" height="250">
  <img src="./assets/PCM%20Encoding/Introduction%20to%20PCM%20encoding%20using%20a%20static%20DC%20Voltage%20(different%20time%20div).jpg?raw=true" height="250">
</p>

<p align="center">
  <img src="./assets/PCM%20Encoding/PCM%20encoder%20module%27s%20output%20(5.8mV).jpg?raw=true" height="250">
  <img src="./assets/PCM%20Encoding/PCM%20encoder%20module%27s%20output%20(200mV).jpg?raw=true" height="250">
</p>

<p align="center">
  <img src="./assets/PCM%20Encoding/PCM%20encoder%20module%27s%20output.jpg?raw=true" height="250">
  <img src="./assets/PCM%20Encoding/End%20Output.jpg?raw=true" height="250">
</p>

<p align="center">
  <a href="./assets/PCM%20Encoding/PCM%20output.mp4"><strong>Watch: PCM Output Video</strong></a>
</p>

</details>
</details>

---

## PCM Decoding
> *Recovering analog signals from digital binary data.*

<details>
<summary><b>View Details</b></summary>

### Introduction
The process of converting digital binary data back into an analog signal, essential for recovering original transmitted info in digital receivers.

### Equipment
*   **Emona Telecoms-Trainer 101** suite
*   **Dual-channel 20MHz oscilloscope**

### Experimental Results
*   **Binary Recovery:** Successfully converted binary data back into quantized amplitude levels.
*   **Reconstruction:** Successfully reconstructed the "staircase" waveform from quantized samples.
*   **Smoothing:** Passing the signal through a low-pass filter removed high-frequency components to restore the analog signal.

### Takeaways
Confirmed that proper filtering is as essential as bit resolution for achieving accurate signal recovery.

### Summary
PCM decoding successfully restores analog information, completing the digital-to-analog loop.

<br>

<details>
<summary><b>Laboratory Documentation</b></summary>

<p align="center">
  <img src="assets/PCM%20Decoding/Setting%20up%20the%20PCM%20encoder.jpg" height="250">
  <img src="assets/PCM%20Decoding/Part%20A.png" height="250">
</p>

<p align="center">
  <img src="assets/PCM%20Decoding/Part%20B%20no%2016.png" height="250">
  <img src="assets/PCM%20Decoding/Part%20B%20no%2025.png" height="250">
</p>

<p align="center">
  <img src="assets/PCM%20Decoding/Part%20C%20(no%20speech).png" height="250">
  <img src="assets/PCM%20Decoding/Part%20D.png" height="250">
</p>

</details>
</details>

---

## Bandwidth Limiting & Restoration
> *Managing Intersymbol Interference (ISI) in restricted channels.*

<details>
<summary><b>View Details</b></summary>

### Introduction
Analysis of bandwidth limitation effects on digital signals, where restricted channels cause pulse distortion and rounding.

### Equipment
*   **Emona Telecoms-Trainer 101** suite
*   **Dual-channel 20MHz oscilloscope**

### Experimental Results
*   **Distortion:** Observed digital pulses becoming rounded after passing through a bandwidth-limited channel.
*   **ISI Observation:** Identified overlapping adjacent pulses (Intersymbol Interference).
*   **Restoration:** Successfully used restoration filters to sharpen signal edges and improve clarity.

### Takeaways
Proved that bandwidth is a finite resource; restoration techniques are essential for high-speed data integrity.

### Summary
Proper filtering and restoration are necessary to maintain reliable communication in bandwidth-limited environments.

<br>

<details>
<summary><b>Laboratory Documentation</b></summary>

<p align="center">
  <img src="assets/Bandwidth%20limiting%20and%20restoring%20digital%20signals/Part%20A.png" height="250">
  <img src="assets/Bandwidth%20limiting%20and%20restoring%20digital%20signals/Part%20B.png" height="250">
</p>

<p align="center">
  <img src="assets/Bandwidth%20limiting%20and%20restoring%20digital%20signals/Part%20C%20(2).png" height="250">
  <img src="assets/Bandwidth%20limiting%20and%20restoring%20digital%20signals/Part%20C.png" height="250">
</p>

</details>
</details>

---

---

## Analysis
*   **System-Level Integration:** Successfully modeled the comprehensive transition between analog and digital communication domains, specifically the progression from Frequency Modulation (FM) to Pulse Code Modulation (PCM) signal reconstruction.
*   **Empirical Validation of Theory:** Provided experimental verification for core electromagnetic and signal processing theorems, including Carson’s Rule for bandwidth estimation, the Nyquist-Shannon sampling criterion, and the closed-loop frequency tracking characteristics of Phase-Locked Loops (PLL).
*   **Operational Optimization:** Analyzed the critical engineering trade-offs inherent in modern telecommunications, particularly the balance between signal-to-noise ratio (SNR), spectral efficiency, and quantization resolution.

---

## Conclusion
This series of laboratories successfully validated the foundational principles of modern communication theory through the practical application of the **Emona Telecoms-Trainer 101** platform. By achieving high-fidelity signal recovery in both analog frequency modulation and digital pulse code modulation, the data reinforced the necessity of adhering to sampling limits and filtering requirements. Ultimately, these results provide a concrete bridge between theoretical mathematical models and the physical constraints of contemporary hardware systems.

---

<p align="right"><a href="#readme-top">Back to top ↑</a></p>

---

<p align="right"><a href="#readme-top">Back to top ↑</a></p>
