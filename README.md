<a id="readme-top"></a>

# 📡 Communication Systems: Analog & Digital Signal Analysis
> **An experimental evaluation of frequency modulation, PCM encoding, and signal reconstruction, validated via real-time oscilloscope analysis.**

---

> [!IMPORTANT]
> - **Domain:** `RF & Wireless Communications`
> - **Platform:** `Emona Telecoms-Trainer 101` • `net*TIMS`
> - **Methods:** `FM` • `PLL` • `Sampling & Reconstruction` • `PCM` • `Bandwidth Limiting`
> - **Core Objective:** Evaluate analog and digital processing techniques using the Telecommunications Instructional Modeling System (TIMS) to determine performance regarding noise immunity and signal reconstruction accuracy.

---

### 🛠️ Technical Skillset
*   **Analog & Recovery:** FM generation, deviation measurement, and **Phase-Locked Loop (PLL)** stabilization.
*   **Digital & Sampling:** Pulse Code Modulation (PCM), quantization, and **Nyquist Sampling** validation.
*   **Signal Integrity:** Bandwidth-limited channel analysis and **Intersymbol Interference (ISI)** mitigation.

---

### 🔬 System Analysis & Key Findings
*   **FM Noise Immunity:** Verified that frequency-based modulation is significantly more resilient to amplitude noise than AM.
*   **PLL Stability:** Confirmed that PLL demodulation provides the most reliable FM recovery in interference-heavy environments.
*   **Nyquist Criterion:** Experimentally validated that $f_s \geq 2f_{max}$ is critical for alias-free digital reconstruction.
*   **Digital Trade-offs:** Observed the direct correlation between PCM bit-depth, signal fidelity, and bandwidth overhead.

---

## 📋 Table of Contents
&nbsp;&nbsp;&nbsp;&nbsp; [🔊 Frequency Modulation](#fm) <br>
&nbsp;&nbsp;&nbsp;&nbsp; [🔄 FM Demodulation](#fm-demod) <br>
&nbsp;&nbsp;&nbsp;&nbsp; [📉 Sampling & Reconstruction](#sampling) <br>
&nbsp;&nbsp;&nbsp;&nbsp; [🔢 PCM Encoding](#pcm-enc) <br>
&nbsp;&nbsp;&nbsp;&nbsp; [🔡 PCM Decoding](#pcm-dec) <br>
&nbsp;&nbsp;&nbsp;&nbsp; [🚫 Bandwidth Limiting & Restoration](#bw-limit)

**Analysis & Footnotes** <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [💡 Key Findings](#findings) <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [📈 Final Conclusion](#conclusion) <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [🛠️ Summary](#summary)

---

<a name="fm"></a>
## 🔊 Frequency Modulation
> *Analysis of frequency deviation and carrier stability.*

<details>
<summary><b>View Details</b></summary>

### Introduction
Focuses on the generation of an FM signal using sinusoidal modulating signals and high-frequency carriers. Information is stored in frequency shifts rather than amplitude.

### Block Diagram
<details>
<summary><b>View FM System Configuration</b></summary>
<p align="center">
  <img src="assets/Frequency%20Modulation/Block%20Diagram%20(FM).png" height="220">
</p>
</details>

### Equipment
*   **Emona Telecoms-Trainer 101** (plus power-pack)
*   **Dual-channel 20MHz oscilloscope**
*   Emona 101 oscilloscope leads & assorted patch leads

### Experimental Results
*   **Frequency Deviation:** Confirmed that increasing the modulating signal amplitude directly increases carrier frequency deviation.
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

<a name="fm-demod"></a>
## 🔄 FM Demodulation
> *Comparative study of signal recovery and noise rejection.*

<details>
<summary><b>View Details</b></summary>

### Introduction
The process of converting frequency variations back into original voltage signals. This study evaluates different demodulator circuit topologies and their performance under noise.

### Block Diagram
<details>
<summary><b>View FM Demodulator Configuration</b></summary>
<p align="center">
  <img src="assets/FM%20Demodulation/Block%20Diagram%20(FM%20Demodulator).png" height="220">
</p>
</details>

### Equipment
*   **Emona Telecoms-Trainer 101**
*   **Dual-channel 20MHz oscilloscope**
*   **Headphones** (for audio signal validation)

### Experimental Results
*   **Slope Detection:** Successfully recovered the signal but exhibited noticeable distortion and noise sensitivity.
*   **Foster-Seeley Discriminator:** Produced higher accuracy and reduced distortion compared to the slope detector.
*   **PLL Stability:** The **Phase-Locked Loop (PLL)** demodulator provided the most stable and clean signal recovery, maintaining lock even under interference.

### Takeaways
The PLL demodulator is superior for modern systems due to its ability to lock onto frequencies and reject amplitude noise. Proper circuit design is essential for minimizing the effects of nonideal components.

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

<a name="sampling"></a>
## 📉 Sampling & Reconstruction
> *Validation of the Nyquist-Shannon Theorem and signal recovery.*

<details>
<summary><b>View Details</b></summary>

### Introduction
Focuses on the conversion of analog signals into discrete-time signals. This process is fundamental for digital processing and transmission.

### Block Diagram
<details>
<summary><b>View Sampling and Reconstruction Configuration</b></summary>
<p align="center">
  <img src="assets/Sampling%20and%20Reconstruction/Block%20Diagram%201.png" height="220">
  <img src="assets/Sampling%20and%20Reconstruction/Block%20Diagram%202.png" height="220">
</p>
</details>


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

<a name="pcm-enc"></a>
## 🔢 PCM Encoding
> *Digitizing signals via sampling, quantization, and binary mapping.*

<details>
<summary><b>View Details</b></summary>

### Introduction
Pulse Code Modulation (PCM) encoding is a method used to digitally represent analog signals through sampling, quantization, and binary encoding.

### Block Diagram
<details>
<summary><b>View PCM Encoding Configuration</b></summary>
<p align="center">
  <img src="assets/PCM%20Encoding/Block%20Diagram%20(PCM%20Encoding).png" height="220">
</p>
</details>

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

<a name="pcm-dec"></a>
## 🔡 PCM Decoding
> *Recovering analog signals from digital binary data.*

<details>
<summary><b>View Details</b></summary>

### Introduction
The process of converting digital binary data back into an analog signal is essential for recovering the original transmitted information in digital receivers.

### Block Diagram
<details>
<summary><b>View PCM Decoding Configuration</b></summary>
<p align="center">
  <img src="assets/PCM%20Decoding/Block%20Diagram%20(PCM%20Decoding).png" height="220">
</p>
</details>

### Platform
*   **net*TIMS**

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
  <img src="assets/PCM%20Decoding/Exp13_A.png" height="250">
  <img src="assets/PCM%20Decoding/Exp13_B.png" height="250">
</p>

<p align="center">
  <img src="assets/PCM%20Decoding/Exp13_D.png" height="250">
</p>

</details>
</details>

---

<a name="bw-limit"></a>
## 🚫 Bandwidth Limiting & Restoration
> *Managing Intersymbol Interference (ISI) in restricted channels.*

<details>
<summary><b>View Details</b></summary>

### Introduction
Analysis of bandwidth limitation effects on digital signals, where restricted channels cause pulse distortion and rounding.

### Block Diagram
<details>
<summary><b>View Bandwidth Limiting & Restoration Configuration</b></summary>
<p align="center">
  <img src="assets/Bandwidth%20limiting%20and%20restoring%20digital%20signals/Block%20Diagram%201.png" height="220">
  <img src="assets/Bandwidth%20limiting%20and%20restoring%20digital%20signals/Block%20Diagram%202.png" height="220">
  <img src="assets/Bandwidth%20limiting%20and%20restoring%20digital%20signals/Block%20Diagram%203.png" height="220">
</p>
</details>


### Platform
*   **net*TIMS**

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
  <img src="assets/Bandwidth%20limiting%20and%20restoring%20digital%20signals/Exp14_A_1.png" height="250">
  <img src="assets/Bandwidth%20limiting%20and%20restoring%20digital%20signals/Exp14_A_step13.png" height="250">
</p>

<p align="center">
  <img src="assets/Bandwidth%20limiting%20and%20restoring%20digital%20signals/Exp14_B_1.png" height="250">
  <img src="assets/Bandwidth%20limiting%20and%20restoring%20digital%20signals/Exp14_B_step25.png" height="250">
</p>

<p align="center">
  <img src="assets/Bandwidth%20limiting%20and%20restoring%20digital%20signals/Exp14_B_step29.png" height="250">
  <img src="assets/Bandwidth%20limiting%20and%20restoring%20digital%20signals/Exp14_B_step31.png" height="250">
</p>

<p align="center">
  <img src="assets/Bandwidth%20limiting%20and%20restoring%20digital%20signals/Exp14_C_step36.png" height="250">
  <img src="assets/Bandwidth%20limiting%20and%20restoring%20digital%20signals/Exp14_C_step40.png" height="250">
</p>

</details>
</details>

---

<a name="findings"></a>
### 💡 Key Findings
*   **System-Level Integration:** Successfully modeled the comprehensive transition between analog and digital communication domains, specifically the progression from Frequency Modulation (FM) to Pulse Code Modulation (PCM) signal reconstruction.
*   **Empirical Validation of Theory:** Provided experimental verification for core electromagnetic and signal processing theorems, including Carson’s Rule for bandwidth estimation, the Nyquist-Shannon sampling criterion, and the closed-loop frequency tracking characteristics of Phase-Locked Loops (PLL).
*   **Operational Optimization:** Analyzed the critical engineering trade-offs inherent in modern telecommunications, particularly the balance between signal-to-noise ratio (SNR), spectral efficiency, and quantization resolution.

---

<a name="conclusion"></a>
### 📈 Final Conclusion
This series of laboratories successfully validated the foundational principles of modern communication theory through the practical application of the **Emona Telecoms-Trainer 101** platform. By achieving high-fidelity signal recovery in both analog frequency modulation and digital pulse code modulation, the data reinforced the necessity of adhering to sampling limits and filtering requirements. Ultimately, these results provide a concrete bridge between theoretical mathematical models and the physical constraints of contemporary hardware systems.

---

<a name="summary"></a>
### 🛠️ Summary
*   **Platform:** Emona Telecoms-Trainer 101 & Net-TIMS
*   **Measurement:** Dual-Channel 20MHz Oscilloscope & Signal Analyzer
*   **Verification:** Captured data validated against hardware-accurate noise and bandwidth constraints.

<p align="right"><a href="#readme-top">Back to top ↑</a></p>
