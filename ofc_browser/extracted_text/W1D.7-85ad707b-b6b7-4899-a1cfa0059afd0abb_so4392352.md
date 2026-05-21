# **Co-Design of Electronic and Photonic Systems for Future LPO, NPO, and CPO**

**G. de Valicourt, D. Assumpcao, S. Abbaslou, L. Elsinger, A. Adibi, S. T. Le and P. Winzer** *Ciena US, 430 Mountain Avenue, Suite 301, NJ 07974, New Providence USA. gdevalic@ciena.com*

**Abstract:** Linear pluggable optics, near-packaged optics, and co-packaged optics provide lowpower I/O solutions for AI/ML clusters. In this paper, we review the co-design/package of electronic and photonic subsystems, discussing their principal benefits and the technical challenges.

**OCIS codes:** (060.2330) Fiber optics communications;

#### **1. Introduction**

Over the past few years, AI and ML models have grown in scale at unprecedented rates [1], accelerating the need for ultra-high-speed, low-power I/O solutions with longer reach than traditional copper links. Conventional retimed optical I/O solutions use a dedicated DSP in the module, which prevents meeting the stringent power and latency requirements of modern datacenter fabrics. In contrast, LPO implementations eliminate the DSP within the pluggable, thereby significantly reducing module power and latency. However, because the electrical channel between the host SerDes and the pluggable remains relatively long (fan-out, PCB traces, connector, etc.), LPO still faces constraints in electrical channel loss, impedance discontinuities, and signal-integrity challenges, which become more critical as the symbol rate increases. NPO and CPO push integration further: NPO brings the optical engine closer to the host ASIC (shorter electrical paths) with improved form factor (i.e., bandwidth edge density), and CPO integrates optics and electronics in a common package, thereby offering higher bandwidth (BW) edge density and lower power consumption [2-3]. Therefore LPO, NPO and CPO differ in terms of trade-offs of power consumption, BW edge density, cost, and serviceability. Figure 1(a) shows the key metrics of power consumption and BW edge density for the four solutions at ~200 Gb/s per lane, and Figure 1(b) outlines the different electrical-channel characteristics of those configurations. To match the Serdes BW edge density, the optics need to reach >1 Tbps/mm (Tx+Rx), at energy efficiencies <5 pJ/bit while still achieving low BER (<1e-8).

In this paper, we analyze the impact of the system architectures for LPO, NPO, and CPO, and the implications for the optical-engine design at 200G/lane. The analysis is restricted to a single optical channel (i.e., neglecting crosstalk).

#### **2. System design and implications**

Figure 2 shows schematic diagrams for (a) LPO and NPO and (b) CPO end-to-end transmission systems. The

![](_page_0_Figure_11.jpeg)

Fig. 1. Retimed optics, LPO, NPO and CPO (a) power consumption and edge density and (b) system architectures.

![](_page_1_Figure_2.jpeg)

Fig. 2. Schematic diagram (a) LPO and NPO and (b) CPO.

transmitter (Tx) and receiver (Rx) SerDes-package models used in this study are identical for all system designs, where the SerDes provides a 33.5 SNR with 6 taps (including 3 pre-cursor taps) and the SerDes Rx uses 33 taps (6 pre-cursor taps), DFE with 1 tap , MLSE and has a receiver noise of 4x10-9 V^2/GHz as described in [4]. The SerDes package has a ~ 6dB loss. For LPO, a 14, 17.5, 21 and 24.5 cm traces, OSFP cage model and 20 mm of paddle card routing are added, bringing the total loss to between 16.5 and 24dB. For NPO, we use a 7, 10.5 and 14 cm traces, the board-to-substrate connection uses a socket bringing the overall loss to a range of 10 to 13.5dB. Finally, CPO directly connects the substrate model to the SerDes package model. The optical engine (photonic integrated circuit, PIC) is assumed identical in all cases. The PIC is connected via wire-bonds. For the PIC model we assume (Tx): coupling loss from laser input = 1.5 dB; 1×4 splitter; MZM Vπ\_diff = 6 V; junction loss = 3 dB; junction capacitance = 200 pF/m; series resistance = 3 mΩ; 25 Ω single-ended / 50 Ω differential matched termination; coupling loss at output = 1.5 dB. For (Rx): coupling loss = 1.5 dB; polarization dependent loss = 0.5 dB; photodiode responsivity = 0.9 A/W; PD junction capacitance = 25 fF; series resistance = 30 Ω. The laser model has a RIN of -150dB/Hz and an output power of 20 dBm. The TIA model always has a transimpedance to achieve ~500mV output swing with 15 pA/sqrt (Hz) noise. More details on the individual model and test benches can be found in [5] and will be detailed during the presentation. We ran simulations at 200G PAM-4 for different loss scenarios and extracted BER as a function of electrical link loss and optical link loss. In Figure 3, one observes that the LPO case leads to a BER-floor of ~ 10-7 , attributed to the heavy impairments of the electrical channel. In the NPO and CPO cases, lower BERs (below 10⁻⁹ at low loss) are achieved, and even with ~3 dB link loss, BERs

![](_page_1_Figure_5.jpeg)

Fig. 3. Simulated BER versus electrical link loss at 200G and different optical link loss.

around 10⁻<sup>9</sup> are attainable. A small performance improvement is obtained when moving from NPO to CPO. Such results illustrate the strong coupling between electrical/optical link loss and achievable BER. Moving from LPO to NPO and ultimately to CPO enables higher performance while improving BW edge density and lowering power consumption.

#### **3. Outlook on 400G**

The next logical step in the evolution of Ethernet standards after 200G is 400G signaling per lane. At 400G, the debate on whether PAM4 or PAM6 is the best modulation format, for both copper and optical channels, is actively going on [6]. For existing electrical connector technologies, e.g. OSFP or NPO, where frequency notches and/or sharp roll-off are typically present around ~ 100

![](_page_2_Figure_5.jpeg)

Fig. 4 Optical PAM-4 versus optical PAM-6 performance comparison with XT1600 in a band-limited system.

GHz, 400G PAM-4 is challenging. On the other hand, traditional pn junction modulator technology in silicon photonic reaches its limitations and may need to evolve by introducing new materials, such as Thin Film Lithium Niobate (TFLN) or Barium titanate (BTO), for higher E/O bandwidth. Such integration is challenging as it is needed to introduce new materials into CMOS fabs but also compromise the BW edge density achieved by silicon photonic. In such case, PAM-6 can offer performance advantages due to its reduced bandwidth requirements, keeping current 200G hardware technology. On the other hand, PAM-6 requires ~ 3.5 dB higher SNR compared to PAM-4, which makes it a less attractive format for both the optical and copper channels, when the issue of electrical connectors and sharp roll-off in frequency response is resolved. A comparison of optical loop-back performance on a 16-channel fully integrated NPO engine with PAM-4 at 106 Gbps and PAM-6 at 132 Gbps in a bandwidth limited system is depicted in Figure 4 [6]. One can see that PAM-6 outperforms PAM-4 in terms of achieved BER. This indicates that PAM-6 can be a good choice for 400G if 3-dB E/O/E bandwidth of CPO/NPO/LPO link is < 60 GHz. A detailed analysis is presented in [6].

## **4. Conclusions**

The co-design and packaging of electronic and photonic subsystems is essential to meet the performance, BW edge density, and power demands of next-generation AI datacenters. LPO reduces power and latency by removing the retimer but remains limited by electrical-channel loss and its BW edge density. NPO shortens the electrical path, improves signal integrity and BW edge density, and keeps high serviceability, while CPO achieves the highest BW edge density and lowest power per bit through tight electronic–photonic integration (but with reduced serviceability). Beyond 200 Gb/s per lane, Silicon Photonics starts to reach its limitation and new materials need to be introduce such as TFLN, InP or BTO as the risk of compromising the BW edge density. PAM6 represents an alternative for optical transmission solutions with limited E/O bandwidth.

### **5. References**

- [1] P. J. Winzer," "The future of communications is massively parallel," J. Opt. Commun. Netw. 15, 783 (2023).
- [2] K. Papatryfonos et al., "Co-Package Technology Platform for Low-Power and Low-Cost Data Centers," Applied Sciences, vol. 11, no. 13, p. 6098, Jun. 2021, doi: 10.3390/app11136098.
- [3] G. de Valicourt et al., "1.6-Tbps low-power linear-drive high-density optical interface for machine learning/artificial intelligence," Opt. Express 33, 15338-15354 (2025).
- [4] E. Frlan et al., "224G Linear Follow-on System Analyses for New OSFP Channels", oif2025.322.00, Aug. 03 2025.
- [5] P. J. Pupalaikis, et al., "Simulation and Analysis of Electrical/Optical Communication Links Using OpenSource Software," in proc. DesignCon, Santa Clara, USA (2023).
- [6] S. T. Le, et al., "Highly-Integrated 16-channel Silicon-Photonics Optical Engine Enabling PAM6 Transmission with BER < 1E-9", in proc. OFC 2026, Los Angeles, USA (2026).