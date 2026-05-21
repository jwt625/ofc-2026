# **Experimental Demonstration of O-Band 4×4x8 Wavelength Selective Switch at 100Gbps/ for Data Center Networks**

**Boyang Zheng<sup>1</sup> , Marijn Rombouts<sup>1</sup> , Robert Palmer<sup>2</sup> , Giuseppe Talli<sup>2</sup> , Nicola Calabretta<sup>1</sup>**

*<sup>1</sup>Eindhoven University of Technology and Eindhoven Hendrik Casimir Institute, Eindhoven, The Netherlands <sup>2</sup>Huawei Technologies Duesseldorf GmbH, Munich Research Center, Riesstrasse 25, 80992 Munich, Germany b.zheng@tue.nl*

**Abstract:** We experimentally demonstrate modular polarization-independent O-band 4×4x8 WSS using 400GHz 8-channel photonic integrated flat-top AWG and SOA array. Results show <3.5dB fiber-to-fiber loss, <–37dB crosstalk, OSNR>42dB, and 0.8dB power penalty for 100Gb/s-PAM4 data channel.© 2026 The Author(s)

### **1. Introduction**

Nowadays, the rapid proliferation of artificial intelligence (AI) and Internet of Things (IoT) applications has driven exponential growth in data center (DC) traffic and capacity demands [1]. This surge in data volume is accelerating the expansion of large-scale DC infrastructures; however, it also leads to significant increases in power consumption and operational costs. To ensure sustainable and energy-efficient growth, it has become imperative to develop nextgeneration optical interconnect and switching networks offering higher efficiency, lower power consumption, and improved architectural flexibility.

All-optical networking architectures have emerged as a promising solution for next-generation DCs. Among various approaches, optical circuit switching (OCS) has recently attracted extensive interest for its potential to overcome the electronic switching bottleneck. Representative examples include OPSquare [2], which introduces an optical DC fabric, and a disaggregated architecture employing wavelength, space and time optical switches [3]. Across these designs, wavelength-selective switches (WSS) serve as the key enabler, offering dynamic wavelength routing and flexible bandwidth allocation that form the foundation of reconfigurable all-optical topologies.

Several WSS architectures with enhanced performance have recently been demonstrated. For example, a 4 × 4 × 4λ space-and-wavelength selective switch in [4] exhibited an insertion loss (IL) of 2.3–8.6 dB and crosstalk between –35.3 and –59.7 dB, while a 1 × 2 WSS in [5] achieved an IL of 5.9–9.8 dB and an extinction ratio of 27.6 dB. Despite these advances, meeting the stringent average link budget requirement (7.7 dB) defined in standard specifications remains a challenge. Moreover, all existing implementations operate in C-band, while O-band is the dominant datacom band. Consequently, there is a strong demand for compact O-band WSS photonic circuits featuring low IL, low crosstalk, and high OSNR to support scalable IM-DD–based data center networks.

In this work, we design and experimentally demonstrate, for the first time, a modular and polarization independent O-band 4×4x8 WSS implemented by combining a novel photonic integrated 8-channel 400-GHz spaced flat-top arrayed waveguide grating (AWG) and semiconductor optical amplifier (SOA) arrays. The demonstrated WSS exhibits <3.5 dB fiber-to-fiber loss, accumulated crosstalk <–37 dB, OSNR >42 dB , and 0.8-dB power penalty at 100-Gb/s PAM4 data per channel.

#### **2. WSS architecture and main photonic functional blocks**

The proposed 4×4x8 modular and non-blocking O-band WSS architecture shown in Fig. 1 consists of four 1×4 WSS modules and four 4x1 passive power combiners. The functional blocks of the 1×4 WSS module shown in Fig. 1(b) consist of a 1x4 power splitter that broadcast the incoming 8 WDM channels to four wavelength selective

![](_page_0_Figure_13.jpeg)

Fig. 1: (a) Overview design of the proposed 4×4x8λ O-Band WSS. (b) Detailed design of the WSB.

blocks (WSB). Each 1x4 WSS module can let pass/select or block each individual channel to the designated output ports. The input WDM channels are first demultiplexed by an AWG, and each separated wavelength is then directed to an SOA that functions as an On–Off gate that selects or blocks the wavelength. The SOA has been chosen as gate because of its high (> 50dB) On-Off ratio and the simultaneous amplification of the signal in the On state. The selected wavelengths are subsequently multiplexed by a second AWG. The outputs from the four 1x4 WSS modules are finally merged by the four 4×1 power combiners to form the overall 4×4 switching matrix. Besides the high On-Off ratio of the SOA gates, critical for achieving low cross-talk, key required parameters of the AWGs in the WSB are the low insertion loss (<4 dB), the high contrast ratio (> 40 dB, critical for low cross-talk operation), the channel spacing (400 GHz) and count (8) covering the wavelength range from 1294.43 nm to 1312.27 nm compliant with next generation transceivers, and the flat-top operation mitigating power variation due to wavelength drifting of datacom transceivers as well as preventing high losses due to narrow filtering and wavelength mismatch in tandem Mux/Demux configuration as in the WSB architecture. We have designed a novel polarization independent with flat-top operation photonic integrated AWG compliant with the required parameters. The AWG has been fabricated using silica PLC technology and pigtailed as shown in Fig 3(b). Figure 2(a) presents the measured transmission spectrum, showing an IL < 3.5 dB, a uniform 400-GHz channel

![](_page_1_Figure_3.jpeg)

Fig. 2: (a) AWG spectrum. (b) Crosstalk spectrum of the AWG. (c) Measured SOA (CQF882-SN302).

spacing, and a 1-dB bandwidth of 1.7 nm. Figure 2(b) shows the measured crosstalk spectrum, where the interchannel crosstalk is as low as –46 dB for a single wavelength channel (the other channels have same performance). Moreover, the maximum polarization dependent loss (PDL) is 0.25 dB. These results confirm that the designed and fabricated AWG provides low-loss and low-crosstalk operation, meeting the key performance requirements for Oband WSS implementation.

#### **3. Experimental Setup and Results**

Due to the modular architecture shown in Fig. 1(a), the investigation of a single 1x4 WSS module with the 4x1 power combiner is representative to assess the performance of the WSS. Figure 3(a) illustrates the experimental setup comprising a 1x4 power splitter, the WSB formed by two novel packaged AWGs and commercial SOAs, and the 4x1 power combiner. The gain characterization of the O-band SOAs is reported in Fig. 2(c). The SOAs exhibit

![](_page_1_Figure_8.jpeg)

Fig. 3: (a) Experimental setup of the optical link with WSS. (b) Packaged photonic integrated AWG.

linear gain up to 18.7 dB, a saturation output power of 9 dBm, polarization dependent gain < 1 dB, and a noise figure (NF) of 7 dB. A 53-Gbaud bit-error-rate tester (BERT) generates PRBS15 PAM4 electrical signals, which are amplified by an SHF linear driver (Drv) and modulated by Mach–Zehnder modulators (MZMs) driven by tunable laser sources (Lasers) to form the transmitters (TX). Additionally, a commercial 4 channels 50Gb/s PAM4 optical transceivers and three additional tunable lasers provide continuous-wave (CW) tones are used to generate the other 7 channels to load the switch and comprehensively assess the power penalty caused by crosstalk. All the optical signals are multiplexed by the AWG\_1 to generate the 8 channel WDM signal with 1 dBm optical power per channel. After passing through a 1×4 splitter with 6.7 dB IL, the 8 WDM channels are demultiplexed by AWG\_2 (Fig. 1(b)) and the selected/blocked by its corresponding SOA gate. After the SOAs, the selected wavelengths are multiplexed by AWG\_3 (Fig. 1(b)). Then the outputs undergo a 4×1 power combiner with also 6.7 dB IL. The fourth AWG (AWG\_4) acts as the demultiplexer at the receiver side. A tunable attenuator (ATT) is placed for BER measurements varying the received optical power (ROP).

Figure 4 illustrates the optical spectra captured at different point of the setup. Figure 4(a) shows the target optical signal at 100Gb/s PAM4, while Figure 4(b) presents the multiplexed 8 WDM channels. Figure 4(c) shows the signal after AWG\_2 demultiplexer. Low crosstalk components < –46 dB are measured which indicate the good performance of the proposed AWG. After amplification by the gate SOA, as depicted in Fig. 4(d), the crosstalk components are almost buried in the amplified spontaneous emission (ASE) noise of the SOA. Figure 4(e) shows the output spectrum of the WSS, where wavelengths at 1295.56 nm, 1297.72 nm, 1302.24 nm, and 1306.62 nm are combined into a single output channel—demonstrating the system's capability for dynamic wavelength routing and flexible bandwidth allocation. Figure 4(f) shows the received optical spectrum after AWG\_4 of the target channel with a measured OSNR of 42.2 dB. The bit error rate (BER) was subsequently evaluated under three conditions: (1) back-to-back (BTB) baseline, (2) WSS with full 8 channels load, and (3) WSS with only a single input channel. The BER curves reported in Fig. 5 indicate that the overall power penalty of the proposed WSS under full-load operation is 0.8 dB at KP4. Notably, the penalty induced solely by crosstalk is limited to 0.15 dB, confirming that its impact on system performance is negligible.

![](_page_2_Figure_4.jpeg)

![](_page_2_Figure_5.jpeg)

Fig. 4: Optical spectrum of (a) 53GB/s PAM4 channel. (b) 8 channel input to WSS. (c) after AWG\_2 demux. (d) SOA gate output. (e) WSS output. (f) Receiver input after AWG\_4.

Fig. 5: BER measured curves.

## **4. Conclusion**

We have proposed and experimentally demonstrated a modular polarization-independent O-band 4×4x8 WSS using 400GHz 8-channel photonic integrated flat-top AWG and SOA array. The design enables dynamic wavelength routing and flexible bandwidth allocation for future all-optical network topologies. Experimental results show that the proposed WSS achieves a 3.5 dB fiber-to-fiber loss operation with an accumulated crosstalk of –37 dB. The output OSNR is 42 dB, resulting in only a 0.8 dB power penalty for 53-Gbaud PAM4 transmission.

#### **5. Acknowledgements**

The work is partially supported by the Dutch National Growth Fund for Photonics 'PhotonDelta' and also by the EU research and innovation program ADOPTION grant agreement 101070178.

#### **6. References**

- [1] "Global Networking Trends Report: Networking strategies to advance digital business (2024)", [online] Available: https://www.cisco.com/c/dam/global/en\_uk/solutions/enterprise-networks/2024-global-networking-trends.pdf
- [2] N. Calabretta, F. Yan and W. Miao, "OPSquare: Towards petabit/s optical data center networks based on WDM cross-connect switches with flow control," 2017 19th International Conference on Transparent Optical Networks (ICTON), Girona, Spain, 2017, pp. 1-4, doi: 10.1109/ICTON.2017.8024740.
- [3] N. Calabretta et al., "Photonic networks with nanoseconds switching and control for distributed machine learning systems," 2023 Opto-Electronics and Communications Conference (OECC), Shanghai, China, 2023, pp. 1-6, doi: 10.1109/OECC56963.2023.10209812.
- [4] Z. Zhang, B. Sun, M. Chen, R. Ma, T. Li, R. Penty, and Q. Cheng, "Dilated crosspoint 4×4×4λ optical switch," in Optical Fiber Communication Conference (OFC) 2025, Technical Digest Series (Optica Publishing Group, 2025), paper W3F.5.
- [5] Yu Wang, Srivathsa Bhat, Timo Aalto, Nicola Calabretta; Nanoseconds low-polarization-sensitivity wideband 1 × 2 photonic integrated wavelength selective switch on 3-μm silicon platform. APL Photonics 1 June 2025; 10 (6): 066116. <https://doi.org/10.1063/5.0256830>