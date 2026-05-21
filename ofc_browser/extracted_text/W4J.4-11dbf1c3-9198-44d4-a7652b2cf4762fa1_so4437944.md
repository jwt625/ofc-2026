# **A 420 Gb/s/lane O-Band PAM-4 TOSA Based on Thin-Film Lithium Niobate for IM-DD Applications**

**Haijiang Yu1, <sup>2</sup>\*, Ming Su1, \*, Ruizhi Zhang<sup>1</sup> , Hao Zhang<sup>1</sup> , Peng Gao<sup>1</sup> , Yuan Yao<sup>1</sup> , Li huang<sup>1</sup> , Shusheng Peng<sup>1</sup> , Xiaoyu Li<sup>1</sup> , Hongbo Zhan<sup>1</sup> , Wenjia Xu<sup>1</sup> , Xudong Gao<sup>1</sup> , Chuanneng Luo<sup>1</sup> , Madhav Bhatta<sup>2</sup> , Changfei Hu<sup>1</sup>**

*<sup>1</sup>Wuhan HGGenuine Optics Tech Co.,Ltd, HUST Science & Technology Park, Wuhan, Hubei, 430223 P.R. China <sup>2</sup>Genuine Optics, 2580 North First Street, Suite 100, San Jose, CA 95131, USA Author e-mail address[: yuhaijiang@genuine-opto.com;](mailto:yuhaijiang@genuine-opto.com) suming@genuine-opto.com*

**Abstract:** We demonstrate an O-band Transmitter Optical Sub-Assembly (TOSA) based on thinfilm lithium niobate (TFLN) technology for intensity-modulation direct-detection (IM-DD) applications at 400 Gb/s per lane and beyond. Through co-design of the TFLN modulator and a high-speed electronic driver, combined with optimized assembly techniques, the TOSA achieves 210 GBaud / 420 Gb/s PAM-4 operation with clearly open optical eye diagrams. © 2026 The Author(s)

### **1. Introduction**

The explosive bandwidth demand from cloud services, artificial intelligence and hyperscale data centers is rapidly advancing optical link capacities from current 800 Gb/s and 1.6 Tb/s toward 3.2 Tb/s per module within next three to four years [1]. To avoid excessive lane counts, per-wavelength data rates must climb well beyond today's 100– 200 Gb/s levels, driving interest in >400 Gb/s per-lane optical transmitters for short-reach IM-DD links.

Current 400 Gb/s/lane demonstrations rely on ultra-high-baud electrical front-ends paired with advanced modulators such as thin-film lithium niobate (TFLN) and electro-absorption modulated lasers (EMLs) [2]. While EMLs have been the workhorse for 100–200 Gb/s links and were recently extended to 200 GBaud PAM-4 transmission [3], their chirp, limited linearity, and thermal sensitivity pose challenges for scaling beyond 400 Gb/s. In contrast, TFLN modulators offer >100 GHz electro-optic bandwidth, low Vπ (<2 V), and excellent linearity, enabling PAM-4 transmission beyond 200 GBaud. Recent studies have demonstrated single-wavelength IM-DD transmission approaching or exceeding 400 Gb/s using TFLN [1–2], [4–5]. However, due to the lack of commercial 225 GBaud SerDes, many of these demonstrations rely on higher-order modulation (e.g., PAM-6) or dual-polarization schemes (e.g., two 200 Gb/s PAM-4 signals) to reach these data rates [6]. By leveraging TFLN modulators driven by a 3 nm CMOS 225 GBaud SerDes, 448 Gb/s PAM-4 IM-DD transmission over 2 km was recently achieved, paving the way for 3.2 Tb/s modules [7]. Similar results were also demonstrated by several companies at the 2025 Optical Fiber Communication Conference and Exhibition (OFC) [8].

This work presents a TOSA architecture that integrates a high-speed driver with a TFLN modulator, enabling PAM-4 IM-DD transmission beyond 400 Gb/s per lane. This development is a critical step toward 3.2 Tb/s optical modules with 225 Gbaud SerDes. The design features a co-optimized TFLN modulator with driver and packaging, achieving up to 100 GHz bandwidth to support high-speed PAM-4 signaling. Through both simulation and experimental characterization, we evaluate the impact of key parameters—including driver performance, modulator efficiency, and assembly techniques—on PAM-4 transmission. Based on these insights, we present an optimized TOSA design that achieves PAM-4 data rates up to 420 Gb/s per lane. To the best of our knowledge, this represents the highest reported per-lane PAM-4 rate without relying on a 225 GBaud SerDes, paving the way for PAM-4 448Gb/s per-lane 3.2Tb/s modules with 225 GBaud Serdes.

### **2. Experiments setup**

The test setup for the 400 Gb/s measurement is schematically illustrated in Fig.1 (a). It comprises a Keysight 8199B arbitrary waveform generator (AWG), a Keysight N1000A digital communication analyzer (DCA) equipped with a N1032A optical module, and an evaluation board (EVB) designed for testing the TOSA. The TOSA primarily comprises a TFLN-based Mach-Zehnder modulator (MZM) chip, a single-channel differential driver optimized for 400G PAM-4 operation, a 1310 nm distributed feedback (DFB) laser with 70 mW output power, and a single-mode fiber assembly. The differential TFLN MZMs exhibit an electro-optic 3dB bandwidth of approximately 110 GHz and are designed with low Vπ values (< 2V) to match the output swing of various drivers evaluated in this work. The electrical interface between the driver and the TFLN MZM chip is realized using optimized bonding techniques to minimize parasitic effects. As shown in Fig.1 (a) and 1 (b), a 400 Gb/s PAM-4 signal with a 2 14 -1 pseudo-random binary sequence (PRBS) pattern and a 0.4 Vppd amplitude is generated by the AWG and fed into the EVB through RF connectors. This signal is then amplified by a commercial high-speed driver—designed for 400 Gb/s applications—to an output swing exceeding 2 Vppd, which drives the TFLN MZM. The modulated optical signal is coupled into a single-mode fiber and analyzed using the Keysight DCA (N1032A) for optical eye diagram characterization. The driver gain and peaking are configured based on RF simulation results, and all optical eye measurements are performed with a 23-tap equalizer and a symbol error rate (SER) setting of 9.7 × 10-3 .

![](_page_1_Picture_3.jpeg)

![](_page_1_Picture_4.jpeg)

Fig.1. (a) Illustration of 400 Gb/s per-lane TOSA test setup, (b) Picture of a 400Gb/s per-lane TOSA on EVB

### **3. Experiments and Results**

We first simulated the impact of three different assembly processes on reducing RF loss between the driver and the TFLN modulator. As shown by the simulated S21 responses in Fig.2, the optimal process-C reduces RF loss by approximately 2 dB at the Nyquist frequency of 112 GHz compared to the other processes. We then evaluated the overall S21 response of the complete TOSA link—from the RF input to the TFLN modulator output—for two different driver designs. As shown in Fig.3, driver-A extends the electro-optic (EO) 3 dB bandwidth of the TOSA link to about 95 GHz by leveraging strong peaking around 80 GHz. However, its S21 magnitude drops sharply beyond 90 GHz, leading to roughly 15 dB higher RF loss at 112 GHz compared with driver-B, which achieves a comparable EO bandwidth but maintains a flatter S21 response due to optimized peaking and gain configurations. Based on these simulation results, the TOSA design that offers the best overall RF performance combines process-C, a 110 GHz-bandwidth TFLN modulator with low Vπ (< 2V), and driver-B.

![](_page_1_Figure_8.jpeg)

![](_page_1_Figure_9.jpeg)

Fig.2. Simulated RF loss between the driver and the TFLN modulator for different assembly processes

Fig.3. Simulated S21 response of the complete TOSA link for two different drivers -A and -B

Optical eye measurements were performed on four TOSA samples, each incorporating different assembly processes and driver designs. The clean optical eye diagrams after equalization, shown in Fig.4, correspond to the highest achievable baud rates for each sample. All measurements were conducted using optimized driver settings with a DCA configuration of a 23-tap equalizer and a target SER of 9.7 × 10-3 . As predicted by the simulation in Fig. 2, the maximum supported baud rate increases with improved assembly processes that reduce parasitic effects—from 185 GBaud (370 Gb/s) in Fig. 4 (a), to 200 GBaud (400 Gb/s) in Fig. 4 (b), and up to 210 GBaud (420 Gb/s) in Fig. 4 (c). To the best of our knowledge, this 420 Gb/s per-lane PAM-4 performance represents highest demonstrated data rate

for 400G/lane TOSAs without employing 225 GBaud SerDes. The experimentally observed influence of driver characteristics on link performance (Fig. 4 (c) and 4 (d)) is consistent with the simulated trends shown in Fig.3. Driver-A, with an EO 3 dB bandwidth of 95 GHz and a steep S21 roll-off beyond 90 GHz, supports a maximum PAM-4 data rate of 180 GBaud (360 Gb/s). In contrast, Driver-B enables 210 GBaud (420 Gb/s) operation, benefiting from optimized peaking and gain configuration. TDECQ values were calculated with a target SER of 9.7 × 10<sup>-3</sup>. The measured TDECQ for TOSA samples a, b, and d are 2.97 dB, 3.83 dB, and 2.76 dB, respectively. A TDECQ value could not be extracted for sample c, which demonstrated the highest baud rate performance.

![](_page_2_Figure_3.jpeg)

Fig.4. Optical eyes measured by DCA after equalization from four TOSA samples, a: Process-A + Driver-B, b: Process-B + Driver-B, c: Process-C + Driver-B, d: Process-C + Driver-A,

#### 4. Conclusions

Through the co-design of a TFLN modulator and its high speed electronic driver, combined with an optimized assembly process, we have successfully demonstrated a TFLN modulator-based O-band TOSA for IM-DD applications at 400 Gb/s per-lane and beyond. The TOSA achieves 210 GBaud PAM-4 (420 Gb/s) operation with well-defined optical eye diagrams after equalization, and a TDECQ below 4 dB at 200 GBaud PAM-4 (400 Gb/s). To the best of our knowledge, this represents the highest per-lane data rate demonstrated for TOSAs without relying on 225 GBaud SerDes. These results pave the way for 448 Gb/s per-lane PAM-4 implementations in 3.2 Tb/s modules and highlight the strong potential of TFLN technology for future co-packaged optics (CPO) with 400 Gb/s per-lane linear interfaces.

## 5. References

- [1] Essam Berikaa et al., "Net 400-Gbps/ $\lambda$  IMDD transmission using a single-DAC DSP-free transmitter and a thin-film lithium niobate MZM," Optics Letters, 47(23) 6273-6276 (2022)
- [2] Berikaa, E. et al. TFLN MZMs and next-gen DACs: enabling beyond 400 Gbps IMDD O-band and C-band transmission. IEEE Photonics Technology Letters 35, 850-853 (2023)
- [3] Xin Chen et al., "540Gbps IMDD Transmission over 30km SMF using 110GHz Bandwidth InP EML," in OFC 2025, paper Th4B.2
- [4] AFR, "400 Gb/s per-lane TFLN modulator chip for PAM-4 transmission," OFC 2025, OFC 2025 Forecast: AFR Demonstrates 400 Gbps/lane TFLN Modulator Chip For PAM-4 Transmission-www.fiber-resources.com
- [5] OneTouch Technology, "Single-wavelength 400 Gb/s per-lane heterogeneous TFLN-on-Si modulator," OFC 2025, OneTouch Technology presents its Single-Wavelength 400G per lane Heterogeneous Integrated Thin-Film Lithium Niobate on Silicon Photonic Modulator at OFC | OFC
- [6] Ying Zhao et al., "425-Gbps/λ Dual-polarization IMDD Transceiver," in OFC 2025, paper Th4B.5
- [7] C. St-Arnault, et al., "Net 3.2 Tbps 225 Gbaud PAM4 O-Band IM/DD 2 km Transmission Using FR8 and DR8 with a CMOS 3 nm SerDes and TFLN Modulators", Proceedings of the Optical Fiber Communications Conference and Exhibition (OFC) 2025. San Francisco, CA, USA: Optica Publishing Group, 2025, Th4B.1
- [8] Marvell Technology, "400 G/lane PAM-4 electrical-to-optical link at 224 Gbaud," OFC 2025, Marvell to Demonstrate Industry's First 400G/lane PAM4 Electrical-to-Optical Link Technology at OFC 2025