# **1.6T (8200Gb/s) 2FR4 Silicon Photonic IMDD Transceiver with Monolithically Integrated Ultra-Low Crosstalk and Wideband Multiplexer**

**Haijiang Yu1, 2\* , Gao Xudong1\* , Ming Su<sup>1</sup> , Jun Li<sup>1</sup> , Jian Chen<sup>1</sup> , Ruizhi Zhang<sup>1</sup> , Peng Gao<sup>1</sup> , Mengxue Tao<sup>1</sup> , Yang Wu<sup>1</sup> , Qin Li<sup>1</sup> , Yuan Yao<sup>1</sup> , Qiuhong Hu<sup>1</sup> , Qijian Xu<sup>1</sup> , Madhav Bhatta<sup>2</sup> , Changfei Hu<sup>1</sup>**

*<sup>1</sup>Wuhan HGGenuine Optics Tech Co., Ltd, HUST Science & Technology Park, Wuhan, Hubei, 430223 P.R. China <sup>2</sup>Genuine Optics, 2580 North First Street, Suite 100, San Jose, CA 95131, USA Author e-mail address: yuhaijiang@genuine-opto.com[; gaoxudong@genuine-opto.com;](mailto:gaoxudong@genuine-opto.com) suming@genuine-opto.com*

**Abstract:** We demonstrate a monolithically integrated 1.6T (8×200 Gb/s) 2×FR4 silicon photonic transceiver using a novel Bragg-grating-based Multiplexer (MUX). This design achieves a 15 footprint reduction, 10 dB lower crosstalk, and 5 nm broader bandwidth than conventional MZIbased MUXs. Validated in an OSFP module with 3nm DSP, the 106.25 GBaud PAM4 link shows 2~2.5 dB TDECQ and as low as 110-13 BER, meeting IEEE 802.3dj requirements. © 2026 The Author(s)

### **1. Introduction**

The rapid expansion of AI/ML clusters and hyperscale data centers is driving an urgent transition from 800G to 1.6T optical interconnects. Silicon Photonics (SiPh) has emerged as the premier platform for this scaling, leveraging highdensity monolithic integration and CMOS compatibility. However, migrating to 200 Gb/s per lane in 1.6T 2×FR4 Intensity-Modulation Direct-Detection (IMDD) systems imposes stringent requirements on optical power budgets and signal integrity. Traditional multiplexer (MUX) architectures—including arrayed waveguide gratings (AWGs), Echelle gratings, and cascaded Mach-Zehnder interferometers (CMZIs)—present critical design trade-offs [1]. AWGs and Echelle gratings typically suffer from high insertion loss and restricted flat-top bandwidth, while CMZIs and AWGs require a prohibitive physical footprint. Further more Echelle gratings often exhibit significant interchannel crosstalk, which degrades the bit-error-rate (BER) performance and complicates high-volume manufacturing for 2×FR4 architectures.

In this paper, we propose and demonstrate a novel, monolithically integrated Bragg-grating-based MUX design for 1.6T 2×FR4 SiPh transceivers. This design achieves a 5 nm broader flat-top response and a 10 dB reduction in crosstalk compared to CMZIs fabricated on the same platform. Additionally, it provides significantly wider bandwidth than Echelle gratings adopted in commercial SiPh products [2][3] while maintaining a compact footprint. We experimentally validate the architecture using a fully functional 1.6T 2×FR4 (8×200 Gb/s) OSFP transceiver module. The transmitter demonstrates superior performance, including a TDECQ of 2~2.5dB, an extinction ratio (ER) >4 dB, and BER up to 110-13 , To our knowledge, this is the first demonstration of a Bragg-grating-based MUX implemented in SiPh IMDD pluggable module, providing a scalable and manufacturable pathway for nextgeneration high-capacity optical links.

## **2. Structure, Design and Experiment Setup**

Fig. 1(a) illustrates the schematic of the proposed monolithically integrated silicon photonics (SiPh) multiplexer (MUX), which comprises four serially cascaded multimode Bragg gratings (MBGs). To optimize the spectral response, we employed a finite Gaussian apodization profile combined with a positive dispersion design, enabling a Bragg filter with high-extinction single-side sidelobe suppression. By cascading these filters, the sidelobes on the reciprocal side are effectively suppressed, significantly reducing inter-channel crosstalk and ensuring high signal integrity for 200 Gb/s per lane operation.

The physical layout of the MUX is shown in Fig. 1(b). The device occupies a compact footprint of approximately 1400m 40m, representing a 15-fold area reduction compared to a conventional Cascaded Mach-Zehnder Interferometer MUX designed on the same reticle for performance comparison as shown in Fig. 1(c). This footprint efficiency is critical for high-density 1.6T 2FR4 architectures where space for co-packaged electronics and multiple optical channels is at a premium. The Bragg grating MUX is monolithically integrated into a complete SiPh 1.6T 2FR4 transmitter, with the layout (after desensitization) depicted in Fig. 1(d). The chip was fabricated in a commercial 200 mm SiPh foundry to ensure a clear path to volume production. To mitigate the thermal sensitivity inherent in silicon, the material properties and process parameters from the Process Design Kit (PDK) were precisely tuned. This included optimizing MUX material, waveguide geometry and cladding layers to minimize the central wavelength shifts across the operating temperature range, thereby eliminating the needs for active thermal tuning.

![](_page_1_Figure_3.jpeg)

Fig.1. (a) Schematic of Bragg grating based MUX design, (b) Layout of Bragg grating based MUX, (c) Layout of CMZI MUX, (d) Layout of 2FR4 Transmitter with Bragg grating MUX, (e) 1.6T OSPF 2FR4 module, (f) 1.6T OSFP 2FR4 module test setup

For system-level validation, the SiPh transmitter was integrated into a 1.6T (8×200 Gb/s) OSFP module utilizing a state-of-the-art 3nm DSP, as shown in Fig. 1(e). The 2×FR4 architecture employs two sets of four CWDM wavelengths (1271–1331 nm), each modulated at 106.25 GBaud PAM4 (212.5 Gb/s per lane). The fully packaged module was characterized according to the IEEE 802.3dj framework using an evaluation board (EVB) as shown in Fig.1(f). Transmitter performance was evaluated by driving the transceiver with an SSPRQ signal from the DSP on EVB. The optical output was captured by a 120GHz Keysight DCA (N1032A) to measure TDECQ, ER and OMA. For receiver characterization, the signal was routed through a variable optical attenuator (VOA) and a 90/10 splitter for real-time power monitoring. The receiver's electrical output was analyzed by the DSP on EVB board to generate BER waterfall curves, with sensitivity defined at the KP4 FEC threshold (2.4×10<sup>−</sup><sup>4</sup> ).

#### **3**. **Experiments and Results**

The spectral characteristics of the fabricated SiPh CMZI- and Bragg-grating-based MUXs were evaluated using a

![](_page_1_Figure_8.jpeg)

Fig.2. (a) Measured spectrum of CMZI MUX, (b) Measured spectrum of Bragg grating MUX

broadband light source and an optical spectrum analyzer (OSA). As illustrated in Fig. 2(a)-(b) and summarized in Table 1, the Bragg-grating-based MUX achieves a 5 nm wider 1-dB bandwidth than the reference CMZI, which significantly relaxes laser wavelength tuning tolerances and enhances thermal robustness. Furthermore, the Bragg grating MUX improves insertion loss (IL) by 0.1–0.3 dB and reduces inter-channel crosstalk by 10 dB relative to the CMZI, ensuring superior signal isolation for high-baud-rate PAM4 signaling when it's used as DeMUX in the receiver side. While CH2 and CH4 currently exhibit slightly narrower flat-top bandwidths due to minor design deviations, these will be further optimized in the next iteration through the fine tuning of grating period.

Table 1. Key performance metrics comparison of the two kinds of MUX

| MUX/DEMUX type | Insertion loss | Flattop BW | Cross-talk | Size                 |
|----------------|----------------|------------|------------|----------------------|
| Bragg Grating  | 0.6-0.9dB      | 16-20nm    | -25dB      | 1.6mm<br><br>0.04mm |
| Cascaded MZI   | 0.9-1dB        | 11-14nm    | -15dB      | 2.2mm<br><br>0.4mm  |

The 1.6T 2xFR4 OSFP module was validated under 106.25 GBaud PAM4 modulation using the test setup shown in Fig.1(f). Fig.3(a) and (b) display representative optical eye diagrams for the four CWDM channels measured at 15℃ and 70℃, respectively. All eight channels exhibit clear eye openings with an extinction ratio (ER) >4 dB, a linearity (RLM)0.96, an OMA1.5dBm, and TDECQ values less than 2.5dB, falling well within the IEEE 802.3dj specifications for FR4 links. The system-level performance was evaluated using the 3nm DSP on EVB board. As shown in the BER waterfall curves in Fig. 3(c), the module achieves a pre-FEC BER as low as 110-13 and a receiver sensitivity better than -4dBm at a BER of 110-6 . These results demonstrate a significant margin against the KP4 FEC threshold (2.410-4 ). These findings confirm that the monolithically integrated Bragg grating MUX effectively mitigates the insertion loss, bandwidth and crosstalk trade-offs typical of traditional MUX designs, enabling a high-performance and manufacturable solutions for 1.6T 2FR4 transceiver modules and next-generation high-capacity CWDM optical links.

![](_page_2_Figure_6.jpeg)

Fig.3 Representative optical eye diagrams for the four CWDM channels under 106.25 GBaud PAM4 modulation: (a) measured at 15 ℃, (b) measured at 70 ℃, (c) BER curves from 8 channels of 2FR4 module measured at 70 ℃

## **4. Conclusions**

In this paper, we have proposed and demonstrated a novel, monolithically integrated Bragg-grating-based MUX for 1.6T (8200Gb/s) 2×FR4 silicon photonics transceivers. Our architecture achieves a 15-fold footprint reduction compared to conventional CMZI structures while simultaneously providing a 5 nm broader flat-top bandwidth and a 10 dB reduction in inter-channel crosstalk suppression. The MUX was successfully integrated into a fully functional 1.6T 2×FR4 OSFP module driven by a state-of-the-art 3nm CMOS DSP. System-level validation under 106.25 GBaud PAM4 modulation yielded robust performance, with an TDECQ less than 2.5 dB, a pre-FEC BER as low as 110-13 and a receiver sensitivity of -4dBm at a BER of 110-6 , comfortably meeting IEEE 802.3dj requirements. These results establish the Bragg-grating-based SiPh platform as a highly scalable, high-performance, and manufacturable high-capacity optical connectivity solution for 1.6T and beyond hyperscale data centers.

#### **5. References**

- [1] Wim Bogaerts, et al., "Silicon photonics non-resonant wavelength filters: comparison between AWGs, echelle gratings, and cascaded Mach-Zehnder filters", Proc. SPIE 9365, Integrated Optics: Devices, Materials, and Technologies XIX, 93650H (2 April 2015).
- [2] H. Yu et al., "100Gbps CWDM4 Silicon Photonics Transmitter for 5G applications", W3E.4, OFC *2020*.
- [3] Sunil Priyadarshi, "Charting the Path Toward 1.6T and 3.2T Optical Module Solutions*,*" [https://www.photonics.com/Articles/Charting-the-](https://www.photonics.com/Articles/Charting-the-Path-Toward-16T-and-32T-Optical/a70490)[Path-Toward-16T-and-32T-Optical/a70490](https://www.photonics.com/Articles/Charting-the-Path-Toward-16T-and-32T-Optical/a70490)