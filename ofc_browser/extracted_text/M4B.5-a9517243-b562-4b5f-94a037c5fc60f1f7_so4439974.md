# **Highly-Integrated 16-channel Silicon-Photonics Optical Engine Enabling PAM6 Transmission with BER < 1E-9**

Son Thai Le(1) , Sara Kacmoli(1) , Amitkumar Mahadevan(1) , Guilhem de Valicourt(1) and Peter Winzer(1)

*<sup>1</sup>Ciena, NJ, USA, [thle@ciena.com](mailto:thle@ciena.com)*

**Abstract:** We demonstrate 53-GBaud PAM6 transmission with an aggregate data rate exceeding 2 Tb/s using a highly-integrated, high-density, low-power 16-channel SiPh optical engine, achieving a raw BER < 1E-9 for the first time, showing the feasibility of reliable optical PAM6 transmission.

**OCIS codes:** (060.2330) Fiber optics communications;

## **1. Introduction**

The exponential growth in data center traffic, driven by AI workloads has accelerated the need for ultra-high speed Ethernet standards. In response, 200G, 400G, 800G and 1.6T Ethernet standards with 200G per lane over copper and single-mode optical fiber (SMF) are currently being finalized [1]. Following a well-established technical approach adopted in previous standards, 200G per lane Ethernet also specifies a common signalling, which is PAM4 and KP4 forward error correction (FEC), over both copper channels and SMF. This common standard between copper and optics enables low-power linear-drive interfaces, such as linear pluggable optics (LPO), halfretimed pluggable optics (LRO, RTLR) as well as co-packaged and near-packaged optics (CPO, NPO) to meet the demands in capacity and power of future AI clusters.

The next logical step in the evolution of Ethernet standards is 400G signalling per lane. At 400G, it has been shown that adopting PAM4 (at 212 to 224 Gbaud) for the copper channel is not feasible using existing connector technologies, e. g. OSFP, OSFP-XD [2], due to notches in the transfer function between 90 and 100GHz. As a result, 170-GBaud PAM6 with a Nyquist frequency of 85 GHz is being actively investigated [3]. In parallel, PAM6 has also been actively investigated for SMF channel interfaces with data rates from 100 Gb/s to 400 Gb/s per lane [4-6] due to its reduced bandwidth requirement compared to PAM4. However, the practical feasibility of optical PAM6 has not been demonstrated so far, as previous demonstrations showed BER floors exceeding 1E-5 due to the stringent noise and linearity requirements of PAM6 signals. This is counter to practical Ethernet applications where several orders of magnitude of BER margin relative to the standard KP4 FEC (i.e., a BER floor < 1E-8) is considered mandatory for practically reliable link performance. If electrical interfaces are standardized using PAM6 but optical PAM6 is not practically viable, a retimer gearbox from PAM6 electrical to PAM4 optical would be needed. This would put an end to all recent efforts of LPO, LRO, CPO, and NPO, which are the only path forward to reduce power consumption of optical I/O in AI clusters.

In this paper, we demonstrate the practical viability of optical PAM6 using a 16-channel highly-integrated Silicon Photonics (SiPh) optical engine (OE) designed for up to 56 Gbaud systems. We achieve the first optical PAM6 transmission with BER < 1E-9 over 1 km of SMF at an aggregate module data rate exceeding 2 Tb/s (16 × 132.8 Gb/s). The OE provides effective peaking to compensate for up to 16 dB of electrical loss before the driver without compromising the performance of the PAM6 signals.

## **2. 16-channel SiPh Stacked-Die Chiplet Assembly**

The 16-channel OE comprises the stacked-die chiplet assembly (SDA) shown in Fig. 1(a) [7]. The SDA has a footprint of 6.9 mm x 8.5 mm, resulting in a chiplet edge I/O density exceeding 580 Gbps/mm (TX+RX) and can be tiled to multiply this density. Fully packaged as a nearpackage module, the 0.6-mm pitch land-grid array (LGA) socket-mountable engine has a footprint of 15 x 15 mm and a height of < 10 mm, Fig. 1(b). The SDA, Fig. 1(a), comprises a SiPh die that monolithically integrates 16 Mach-Zehnder (MZ) based TXs and 16 optical RXs,

![](_page_0_Picture_13.jpeg)

![](_page_0_Picture_14.jpeg)

Fig. 1. (a) Stacked-die chiplet assembly of the OE. (b) Fully packaged electrically LGA-socketable module.

operated here at 53.125 Gbaud. The SiPh die is fabricated in 220-nm overlayer SOI on a high-volume commercial foundry platform. Two 8-lane drivers and two 8-lane trans-impedance amplifiers (TIAs) are flip-chip mounted with an 80-um bump spacing onto the SiPh die. These high-speed electronics chips are implemented in a highvolume commercial BiCMOS foundry process. They have a size of 0.8 mm x 2.3 mm each, are closely codesigned with the SiPh die for minimal parasitics and improved noise and linearity performance.

The OE can be driven by standard digital SerDes macros embedded within a host ASIC and used to drive linear copper channels. Advanced analog equalization built into the drivers and TIAs allow for up to 16 dB of loss at Nyquist for 53-GBaud PAM6 between the SerDes TX and the OE as well as between the OE and the SerDes RX

Fig. 2(a) Experimental setup, (b) – A picture of OE in its socket; VOA – Variable optical attenuator; DAC – Digital to analog converter; RTO – Realtime oscilloscope; DUT – Device under test; ELSFP – External laser source.

to flexibly accommodate the placement of the OE for CPO/NPO/LPO/LRO applications. Being able to linearly drive substantial electrical trace losses between SerDes and OE without the need for retimers or optics-specific digital signal processors is essential to minimize latency, complexity, real estate, and power consumption while maximizing architectural flexibility. Fiber interfacing is done through a 2D array of grating couplers using a 3x12 fiber array unit with  $16\ TX\ SMFs$ ,  $16\ RX\ SMFs$ , and  $4\ PMFs$  to couple external laser light at  $1311\pm6.5$  nm into the chip.

#### 3. Experimental PAM6 setup, results and discussions

The experimental setup is depicted in Fig. 2(a). First, we generated a 53.125-Gbaud signal with a random sequence of 2<sup>17</sup> PAM6 symbols offline following a QAM32 mapping approach [8]. Digital pre-emphasis with a 7-tap FFE typical of today's SerDes macros (5 dB maximum pre-emphasis) was performed to partially compensate for the electrical channel loss. The generated signal was then uploaded to the memory of a DAC running at 106.25 GS/s. No pulse shaping was used, as would be typical for symbol-rate sampled high-speed SerDes. To emulate a channel loss up to 16 dB, an RF loss-board was added between the DAC and the OE evaluation board (EVB). We used an ELSFP with 4 industry-standard 21-dBm DFB lasers at 1310 nm to provide optical power to 16 channels of OE simultaneously using a 1:4 split on each ELS fiber. The optical channel under test (CUT) is also connected to an adjustable reflection emulator (ARE), including a VOA, polarization controller, couplers, 5 m of SMF (for decorrelation) and an optical isolator, to emulate the impact of multipath interference (MPI). The signal with MPI is launched into 1 km of SMF. The received optical signal is fed to a RX under test. The RX output is differentially detected by a 2-channel 256 GS/s RTO for offline processing. Offline processing emulates functions implemented on a state-of-the-art symbol-rate sampling SerDes: *i*) signal conditioning and filtering (emulating the analog SerDes front-end); *ii*) timing recovery; *iii*) symbol-spaced equalization (EQ); *iv*) direct BER counting (for BER > 2e-7) or BER estimation based on the received signal histogram (for BER < 2e-7).

We consider three practical equalization approaches for PAM6: *i*) 65-tap symbol-spaced FFE (FFE-65); *ii*) FFE-65 and 1-tap DFE (DFE-1) and *iii*) FFE-65 followed by a 3-tap MLSE. The 65-tap FFE emulates a commonly implemented shorter FFE with floating taps to compensate for electrical reflections due to electrical connectors. The inset to Fig. 3(a) shows a typical FFE impulse response, showing that most of the EQ action takes place within about 10 symbols around the main tap as well as by 2 banks of floating taps.

The sensitivity measurement for a typical channel (Ch15) at 132.8 Gb/s and ER of 3.4 dB and no additional peaking from the OE (PKC = 0) with the three considered EQ techniques is depicted in Fig. 3(a). A simple FFE-65 EQ already offers very good performance, with a BER < 1E-9. Adding a 1-tap DFE enhances the performance significantly (BER  $\sim$  2E-10 at OMA  $\sim$  0 dBm). Additional performance benefits are achieved by a 3-tap MLSE (after the FFE-65), noting that BER < 2E-7 cannot be measured with the MLSE due to the limited length of the

![](_page_1_Figure_9.jpeg)

Fig. 3(a) – Sensitivity measurements for Ch15 at 132.8 Gb/s with three different EQ techniques, inset shows the constellations with FFE-65 at OMA = 0 dBm, (b) – BER at 0 dBm of OMA versus ER with FFE-65 and DFE-1; (c) – BER of 16 channels with FFE-65 + DFE-1 after 1 km of SFM transmission; The electrical channel loss (DAC to driver) is ~ 7 dB.

![](_page_2_Figure_2.jpeg)

Fig. 4(a) – Received signal spectra with 7-dB channel loss (w/o peaking from the driver) and 16-dB channel loss with and without driver peaking; (b) – Sensitivity measurement for Ch15 with 16-dB electrical loss and no driver peaking and (b) – Sensitivity measurement for Ch15 with 16-dB electrical loss and driver peaking; PKC – OE driver peaking setting

processed trace. At a BER of 1E-6, the MLSE enhances the sensitivity by ~ 1.4 dB. There is no indication of an error floor.

The dependency of BER (at OMA of 0 dBm) on optical ER is depicted in Fig. 3(b); the inset shows an eye diagram at 3.4 dB ER. Driver nonlinearity only shows a significant impact on the BER at ER >4 dB. Fig. 3(c) depicts the BER measurements for all 16 channels after 1 km of SMF (- 53 dB MPI), showing that a record low BER below 1E-9 for >100 Gb/s PAM6 was achieved for all 16 channels with FFE-65 and DFE-1, and even better BERs are expected with MLSE.

Next, we investigate the impact of bandwidth limitation and electrical channel loss on the sensitivity. Fig. 4(a) shows the spectra of received signals for 7 dB and 16 dB of

![](_page_2_Figure_7.jpeg)

Fig. 5 – Impact of MPI on the BER for Ch15 with FFE-65 + DFE-1. The electrical channel loss is ~ 7 dB.

electrical channel loss with and without driver peaking. With 7 dB of channel loss, the 6-dB E/O/E bandwidth of the system is ~ 20 GHz; in the case of 16 dB of channel loss it drops below 8 GHz, i.e., 15% of the symbol rate. The OE is designed for flexible implementation with various channel loss cases with an adjustable CTLE. One can see in Fig. 4(a) that by choosing a proper CTLE peaking (PKC = 15), 16 dB of electrical channel loss (Tx channel), can be compensated for. The impact of system bandwidth limitations is depicted in Fig. 4(b) for the case of 16 dB channel loss w/o compensation. A BER < 1E-6 is no longer possible even with an MLSE. With additional peaking from the integrated OE driver, however, much better performance is achieved, as shown in Fig. 4(c), where FFE-65 and DFE-1 lead to BER ~ 1.2E-8 at high OMA > -1 dBm. This result indicates high performance and low nonlinearity of the driver CTLE, even in the context of PAM6 transmission.

Finally, we study the impact of MPI on the performance of our PAM6 signals, which is depicted in Fig. 5 for Ch15 in a B2B case with FFE-65 and DFE-1. For MPI < -50 dB, only negligible impact on the BER is observed. As a result, with an IEEE DR4 return loss spec of -26 dB, we expect that MPI should not add significant performance penalty on optical PAM6 transmissions.

### **4. Conclusion**

We have shown for the first time that high-speed, highly-integrated SiPh PAM6 transmission is possible at BER < 1E-9. Albeit the measurements were only taken at 53.125 GBaud for which the hardware was designed, we expect PAM6 to lead to viable optical transmission at 170 GBaud to enable 425-Gb/s transmission. This enables the use of power efficient unretimed CPO interconnects should PAM6 electrical signalling be standardized for 400G copper interfaces.

#### **5. References**

- 1. https://www.ieee802.org/3/dj/index.html
- 2. [https://grouper.ieee.org/groups/802/3/ad\\_hoc/E4AI/public/25\\_0529/calvin\\_e4ai\\_01a\\_250529.pdf](https://grouper.ieee.org/groups/802/3/ad_hoc/E4AI/public/25_0529/calvin_e4ai_01a_250529.pdf)
- 3. [https://grouper.ieee.org/groups/802/3/ad\\_hoc/E4AI/public/25\\_0529/carusone\\_e4ai\\_01a\\_250529.pdf](https://grouper.ieee.org/groups/802/3/ad_hoc/E4AI/public/25_0529/carusone_e4ai_01a_250529.pdf)
- 4. T. Wettlin et al, "Comparison of PAM Formats for 200 Gb/s Short Reach Transmission Systems," OFC 2020, USA, pp. 1-3.
- 5. M. Han *et al*., "Deep Reservoir Computing for 100 Gbaud PAM6 IM/DD Transmission Impairment Mitigation," OFC 2023
- 6. A. Uchiyama *et al*., "Demonstration of 155-Gbaud PAM4 and PAM6 Using a Narrow High-Mesa Electro-Absorption Modulator Integrated Laser for 400 Gb/s Per Lane Transmission," in *Journal of Lightwave Technology*, vol. 43, no. 4, pp. 1868-1873
- 7. Guilhem de Valicourt et al, "1.6-Tbps low-power linear-drive high-density optical interface for machine learning/artificial intelligence," Opt. Express 33, 15338-15354 (2025)
- 8. <https://arxiv.org/pdf/2104.14304>