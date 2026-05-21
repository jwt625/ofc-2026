# **400G/lane for Linear-drive Optics Applications**

**Jianying Zhou(1) , Lei Xin(2), Xuelei Zhang(2), Fangyuan Meng(2), Yang Liu(2) , Qisheng Zhao (2) and Jin Hong(1)**

> *(1) Ligent Technologies, Inc., 2580 N. First Street, San Jose, CA, USA (2) Ligent Technologies, Inc., 17 Donghai Xi Road, Qingdao, China Author email address[: jzhou@ligent.com](mailto:jzhou@ligent.com)*

**Abstract:** We demonstrate performances of 400G/lane with a high bandwidth efficient thin-film lithium niobate Mach-Zehnder modulator and practical equalizations. Our studies indicate the feasibility of 400G/lane for linear-drive optics applications in NPO/CPO with an enhanced CTLE. © 2024 The Author(s)

### **1. Introduction**

The demand for high bandwidth has rapidly increased to support AI/ML applications in hyperscale data centers and AI clusters. 1.6T modules utilizing 200G/lane are currently under development with accelerated deployment timelines. This progression has driven significant research interest in 3.2T or higher systems requiring 400G/lane implementations, where novel technologies must simultaneously address performance, power efficiency, cost constraints, and scalability challenges [1-4]. High symbol rate modulation employing various material platforms and technologies, e.g., thin-film lithium niobate (TFLN) based Mach-Zehnder modulator (MZM), Indium phosphide (InP) based electro-absorption modulated lasers (EML), and heterogeneously integrated InP electro-absorption modulator (EAM) on silicon waveguides, has been reported for 400G/lane implementations [1-3]. However, existing demonstrations face critical limitations for short reach connections: failure either to achieve 400G/lane with forward error correction (FEC) overhead (OH), or to rely on offline digital signal processing (DSP) with computationally intensive equalization, or to require of high FEC BER thresholds (e.g. 2.4E-2 with 20% OH) [1-3]. IEEE standards for 200G/lane systems adopt KP4 FEC and a concatenated KP4 and Hamming (128,120) code for short reach connections for power efficiency and low latency [4,5], scalable to 400G/lane with BER thresholds of 2.4E-4 (KP4) and 4.85E-3 (KP4 + Hamming), corresponding to gross bitrates of 425Gb/s and 453.75Gb/s per lane, respectively.

Linear-drive optics (LDO) eliminates digital signal processing (DSP) in the module, aligns well with the requirements of AI/ML applications such as low power, low latency and low cost [4]. There are two types of LDO form factors: one is Linear-drive Pluggable Optics (LPO), and the other is linear Co-Package Optics (CPO) or Near-Package Optics (NPO). LPO modules show promise in adapting to links with existing DSP-based pluggable modules; however, achieving 400G/lane in LPO is impossible in conventional models due to high RF connection loss in the switch [4]. To support 400G/lane, new high-density RF connectors are proposed under OIF standards, which show that 3dB bandwidth (BW) can be over 120GHz [6], to enable 400G/lane with the improved RF loss of interconnect.

In this paper, we demonstrate 400G/lane solutions, compliant with KP4 FEC and KP4 + Hamming code FEC specifications, utilizing a high bandwidth efficient TFLN MZM with practical equalizations for short reach connection applications. We experimentally demonstrated performances of 160Gbd PAM4 with KP4 FEC and 180Gbd PAM4 with KP4 + Hamming FEC using 15 feed-forward equalizer (FFE) taps. The symbol rate scalability is currently constrained by arbitrary waveform generator (AWG) with 25dB RF loss at 100GHz. Furthermore, we validated design implementations using the TFLN MZM and state-of-the-art integrated circuits (IC) and RF connector to support bumpto-bump RF loss up to 12dB with practical equalizations and an enhanced continuous-time linear equalizer (CTLE), indicating feasibility of 400G/lane for LDO in CPO/NPO applications.

# **2. Modulator and Demonstration**

The TFLN MZM is designed and fabricated by Liobate Technology. This TFLN MZM employs a GSSG differential electrode configuration. This TFLN MZM demonstrates exceptional high-frequency performance with merely 1dB roll-off at 67GHz (S21 parameter) and an extrapolated 3dB bandwidth exceeding 140GHz, while maintaining a low half-wave voltage (Vπ) of 2.7V. Fig.1 shows the measured EO S21 response and Vπ of TFLN MZM, 400G/lane test setup, and measured frequency responses of AWG and calibration. 400G/lane testing was conducted using a Keysight M8199B AWG and a 1032 digital communication analyzer (DCA) with 120GHz analog bandwidth. A continuouswave (CW) laser source was coupled into PIC, modulated by TFLN MZM and subsequently fiber-coupled to the DCA for performance test. The MZM differential driving signal was delivered from the AWG through RF cables, optional RF amplifier and RF probe. As the AWG response has 25dB RF loss at 100GHz, the maximum tone frequency of 90GHz was used for AWG calibration as shown in Fig. 1.

![](_page_1_Figure_2.jpeg)

Fig.1 Measured EO S21 response and Vπ of TFLN MZM (left), 400G/lane test setup (middle) and measured frequency responses of AWG and calibration (right).

Transmitter characteristics are quantified via transmitter dispersion eye closure quaternary (TDECQ) and extinction ratio (ER) measurements by the DCA. PRBSQ pattern is employed in the testing. The differential signals (Vppd) are generated by AWG in the range of 1.3-2V. MZM bias is controlled to maintain linearity and ER. KP4 FEC with BER threshold of 2.4E-4 and KP4 + Hamming code FEC with BER threshold of 4.85E-3, compliant with IEEE 802.3dj standards [5]. Fig.2 shows measured eyes and TDECQ and ER vs symbol rate under different FECs and equalizations with PAM4 modulation. The measured TDECQ and ER exhibit progressive degradation with increasing symbol rates across 140-182.5Gbd. For 160Gbd PAM4 with KP4 FEC, the measured TDECQ is 3.7dB using 15 FFE taps. For 180Gbd PAM4 with KP4 + Hamming code FEC, the measured TDECQ is 2.5dB using 15 FFE taps, 2.3dB using 23 FFE taps, and 1.9dB using 1-tap DFE in addition to 23 FFE taps. The measured TDECQ at 182.5Gbd increases to 2.6dB from 2.3dB at 180Gbd using 23 FFE taps. The performance undergoes rapid degradation beyond 180Gbd, due to high RF loss at 100GHz from AWG as shown in Fig. 1.

![](_page_1_Figure_5.jpeg)

Fig.2 Eyes for PAM4 at 140Gbd, 160Gbd, 180Gbd, and 182.5Gbd using 23 FFE taps (left), and TDECQ and ER vs symbol rate with KP4 FEC and KP4 + Hamming code FEC using 23 FFE taps, 15 FFE taps, and 1-tap DFE in addition to 23 FFE taps (right).

# **3. Design Implementation and Validation**

We studied performance of 400G/lane implementations in LDO with the TFLN MZM and a linear driver. Fig. 3 shows small signal EO response of Tx, frequency response of CTLE at Tx, and frequency response of bump-to-bump loss. Tx response is from the linear driver input to optical output. The bump-to-bump losses in a range from 3dB to 15dB at 106GHz, Nyquist frequency for 212.5Gbd, with same frequency response scaled from ones for 200G/lane in reference [4]. To compensate RF loss, an enhanced CTLE is used with a gain of 4.4dB and 9dB at 106GHz. In an actual implementation, we can design an active CTLE which can be integrated into the linear driver.

![](_page_1_Figure_9.jpeg)

Fig.3 Small signal response of Tx (left), frequency response of CTLE at Tx (middle), and frequency response of bump-to-bump loss(right).

We built the model with VPI photonics [4]. The simulation is carried out with 212.5Gbaud PAM4 and KP4 FEC which has FEC BER threshold of 2.4 × 10-4 [4,5]. TDECQ and ER are measured to characterize Tx performance and BER vs Rx OMA is measured to study system performance. An enhanced CTLE is introduced to improve TDECQ and Rx BER performance. Fig. 4 shows design parameters, TDECQ and ER vs bump-to-bump loss with an inserted eye, and BER vs Rx OMA. The data shows that 9dB CTLE gain is required to support a bum-to-bump RF loss up to 12dB to meet TDECQ < 3.5dB and BER floor <1E-6 as performance requirements for short reach applications [4,5]. The penalty of Rx sensitivity is less than 1dB for a bump-to-bump RF loss of 12dB, compared one with the RF loss of 9dB. However, TDECQ degrades to 6.5dB with BER floor >1E-5 when the bump-to-bump RF loss is 15dB.

![](_page_2_Figure_3.jpeg)

Fig.4 Design parameters (left), TDECQ and ER vs Bump-to-bump RF loss (middle), and BER vs Rx OMA (right).

The results with 400G/lane in LDO show that the design implantation can support the bump-to-bump loss of 12dB at 106GHz with an enhanced CTLE at Tx to meet the performance requirements. The RF loss of 12dB may not support 400G/lane LPO [4]. In case study of CPO, the RF loss of 12dB can support RF trace length of 4.5inch with 2dB/inch loss after subtracting 3dB RF loss for other connections. In case study of NPO with fly-over cables, we use the stateof-the-art high density RF connector for on-board and on-package connections with RF loss of 2.5dB for each RF connector [6]; after subtracting 5dB RF loss from on-board and on-package connectors, and 2.5dB RF loss for other connections such as between ASIC bump and connector, the RF loss of 12dB can support fly-over cables of 10inch with 0.45dB/inch loss. These indicate that 12dB bump-to-bump RF loss can support LDO applications in NPO/CPO.

### **4. Conclusion**

We demonstrate the high performance of 400G/lane using a wide bandwidth efficient TFLN MZM and practical equalizations. The measured TDECQ using 15 FFE taps is 2.5dB for 180Gbd PAM4 with KP4 + Hamming code FEC and is 3.7dB for 160Gbd PAM4 with KP4 FEC, respectively. The symbol rate scalability is currently constrained by AWG with 25dB RF loss at 100GHz. The simulation results valid practical implementations for 400G/lane using the TFLN MZM and state-of-the-art IC and connector with TDECQ and BER meeting product requirements for bumpto-bump RF loss up to 12dB, confirming the feasibility of 400G/lane for LDO applications in NPO/CPO.

### **Acknowledgement**

We thank Liobate Technology for providing TFLN modulators.

## **5. References**

- [1] C. St-Arnault, et al., "Net 3.2 Tbps 225 Gbaud PAM4 O-Band IM/DD 2 km Transmission Using FR8 and DR8 with a CMOS 3 nm SerDes and TFLN Modulators," OFC 2025, paper Th4B.1, 2025
- [2] P. Bhaskeret, al., "413 Gbits/s PAM-6 O-band CWDM Electroabsorption Modulated Lasers for 400G per lane IM-DD Applications," OFC 2025, paper Tu2J2.
- [3] A. Ostrovskis, et al., "Heterogeneously Integrated InP Electro-Absorption Modulator for Beyond 300 Gb/s Optical Links," in Journal of Lightwave Technology, vol. 43, no. 4, pp. 1826-1836, February 15, 2025.
- [4] J. Zhou, et al., "Performance Limitations and Optimizations of Linear Driver Optics for 200G/Lane and beyond", OFC 2025. Paper M2H.1.
- [5] IEEE Draft P802.3dj/D2.1, IEEE P802.3dj 200 Gb/s, 400 Gb/s, 800 Gb/s, and 1.6 Tb/s Ethernet Task Force, 14 August 2025.
- [6] T. Ito, "Touchstone of 2D connector for 448G," OIF PLL working group, OIF2025.138.01, 2025.