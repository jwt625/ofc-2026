# **A 256 Gb/s DWDM Optical I/O in a 3D-stacked EIC/PIC Silicon Photonics Platform**

**Nandish Mehta1 , Angad Rekhi1 , Nikola Nedovic1 , Sanquan Song1 , Benjamin G. Lee2 , Georgios Kalogerakis1 , Li Xu1 , Brian Zimmer1 , Steve Tell3 , Yoshi Nishi1 , Xi Chen1 , Ward Lopes1 , Trey Greer3 , Tom Gray3**

> *NVIDIA, Santa Clara, CA 95051, USA NVIDIA, Ridgefield, CT 06877 USA 3 NVIDIA, Durham, NC 27713 Author email address: nandishm@nvidia.com*

**Abstract:** We present an (8+1)×32 Gb/s/λ DWDM optical I/O comprising eight data and one bandpass-filtered forwarded-clock lane in a 3D-stacked 7 nm EIC/65 nm PIC Silicon-photonics platform. It achieves 7.14×10⁻¹⁴ BER and 1.33Tb/s/mm² areal bandwidth density.

#### **1. Introduction**

Recent trends in data center interconnects point towards use of short-reach optical links with co-packaged optics and 2.5D or 3D package integration to meet the growing bandwidth demands of AI and ML workloads. Microring resonator (MRR)-based DWDM optical I/O realizes a "slow and parallel" interface that provides perimeter and areal bandwidth density and energy efficiency, alleviating circuit area and fiber escape area constraints. Silicon Photonics (SiPh) provides a low-cost, high-volume solution due to the availability of SiPh foundry offerings that leverage silicon integrated circuits fabrication infrastructure, while recent advances in packaging enable integration of the SiPh engine with the core die on the same package (CPO) or interposer [1], Fig.1(a).

We present a 256 Gb/s per fiber DWDM link in O-band with eight 32 Gb/s/l data lanes and one half-rate clock forwarded lane in a 3D-integrated SiPh platform [2]. The forwarded clock is bandpass-filtered at the receiver (corresponding to a low-pass filter in phase domain) to remove most of the jitter associated with high-frequency uncorrelated random noise, while tracking low-frequency jitter correlated with the data. This simplifies the architecture, removing the need for per-lane clock and data recovery (CDR) and alleviating circuit requirements, resulting in a small footprint and highest areal bandwidth density reported to-date [3,4].

![](_page_0_Figure_9.jpeg)

Fig. 1: (a) Co-integrated optics on interposer using a silicon photonics engine. (b) MRR-based clock-forwarded DWDM link with nine 200GHz spaced wavelengths with one carrying the clock. (c) Fiber array unit (FAU) and 3D-stacked EIC/PIC packaged on a substrate. (d) Cross-section of electro-optic platform with FAU coupled through Si microlens and grating couplers [3].

### **2. Link Architecture**

The architecture of the MRR-based clock-forwarded DWDM link is shown in Fig. 1(b). The 7 nm FinFET CMOS EIC integrates circuits to drive MRR-based modulators (MRMs), RX analog front-end (AFE) for MRRs, thermal control for the MRMs/MRRs, and serialize/deserialize logic with built-in error detectors. The 65nm SiPh PIC is 3Dintegrated with the EIC via Cu-Cu hybrid bonding [2]. A permanently attached fiber array unit (FAU) connects optical fibers to the silicon-photonics engine which is assembled on an organic substrate (Fig. 1(c)). Vertical grating couplers (GCs) with 1 dB bandwidth of 20 nm (~1.5× the signal spectrum) and 1.3 dB loss enable 2D optical IO scaling, maximizing areal bandwidth density, unlike 1D edge-coupler arrays. Due to tight control of critical dimensions within wafer and wafer-to-wafer, the spread in central wavelength of the GC is <±1.7 nm. At the TX, the light passes through a series of MRMs tuned to one of the laser wavelengths using metal heaters and driven by a pseudodifferential driver placed directly above it on the EIC. At the RX, the series cascaded MRR filters, tuned to the target wavelength, drop the filtered signal onto a high-speed photodetector, which feed the EIC TIA positioned directly above the PIC.

To optimize the ring parameters such as quality factor (Q), coupling coefficients, and ring ordering on the bus, we use a statistical link modeling tool [5]. This tool captures important sources of signal impairment such as bandwidth limited intersymbol interference (ISI), crosstalk (XT), various types of interchannel interference (ICI), device nonlinearities and noise. It allows for optimizations or fast sweeps of various design parameters while predicting the link performance and energy efficiency. Due to limited choice of doping masks, we used ring modulator doping concentrations that resulted in Q of about 4500 (lower than the optimal value estimated by the modeling tool) and MRR Q of 4200. With the channel spacing above 200 GHz and 32 Gb/s/lane, the power penalty due to XT is negligible, as this effect is much more prominent at higher spectral efficiencies (i.e. lower channel spacing to data-rate ratio). At the incident optical power in the operating range of the link (around 0-3dBm/l), the MRMs operating near resonance produces non-negligible photocurrent due to single-photon absorption (e.g. due to defects) and two-photon absorption. The primary consequence of this photocurrent is that the driver circuit must be able to absorb it to avoid forward biasing the PN junction and distorting the modulated signal. We achieve this by using a broadband modulator driver that provides a DC connection to the ring and can sink up to 300µA of photocurrent.

![](_page_1_Figure_5.jpeg)

Fig. 2: (a) Test-setup of transceiver loop-back. (b) Evaluation board.

#### **3. Experimental Results**

The test setup diagram and the evaluation board are shown in Fig. (2). We use an external DFB array to provide nine wavelengths that are coupled to the board via an MPO array connector. The light is propagated through the TX PIC, out of the chip, and looped back to the RX. For simplicity, the loop-back is established on the same chip without any communication between TX and RX internally using a 4-meter-long polarization maintaining fiber.

In the clock forwarding architecture, the sensitivity depends both on the extinction ratio (ER) and the power of the forwarded clock. We can distinguish between the best achievable RX sensitivity, and the link-level sensitivity used to determine the laser power needed to power the link. To characterize the former, we use high ER and strong enough clock power to avoid penalizing data reception. For the latter, we must use an ER that the TX can deliver, clock OMA at the same level as the data OMA being characterized (unless the link architecture is such that the clock lane power is higher compared to that of the data lane), and an eye-opening margin. The measured sensitivity for PRBS31 sequence at 32Gbps (Fig. 3(a)) shows that the two are almost the same for our link – about -17 dBm at BER of 10-11, partly owing to the low-parasitic interface due to tight level of EIC/PIC integration (Fig.(1a)). Furthermore, since the injection-lock oscillators we use to bandpass-filter the forwarded clock can faithfully restore a weak incoming clock, the data sensitivity does not change even for the clock OMA well below the level of data OMA.

We use a DFB-array based commercial prototype DWDM external laser source with 3 dBm per wavelength of fiber-coupled optical power at 230 GHz channel-spacing. Figure 3(b) shows the bathtub diagrams for eight data lanes simultaneously running a 32Gbps PRBS31 data pattern, each with different seed. It shows the eye opening of 0.46UI at BER of 10-11. We demonstrate that the link robustly tracks ambient variations by measuring long-term BER of <10- <sup>13</sup> (Fig. 3(c)). As shown in Fig. 3(d), the total energy efficiency of the module excluding the laser is 2.02pJ/b.

![](_page_2_Figure_4.jpeg)

Fig. 3 (a) Measured RX sensitivity at 32 Gb/s. (b) Measured bathtub curves from all the 8 lanes with TX2 à RX6 being used for forwarding the clock. (c) Long-term BER measurement. (d) Breakdown of the link energy efficiency at 32 Gb/s.

#### **4. Conclusion**

We present a 256 Gb/s per fiber DWDM link employing eight 32 Gb/s data lanes and one clock-forwarding lane. The EIC and PIC are 3D-stacked using Cu–Cu hybrid bonding, while an external DFB laser array is coupled through surface grating couplers with vertical fiber attach. The link achieves an areal bandwidth density of 1.33 Tb/s/mm², a cumulative BER of 7.14 × 10⁻¹⁴ with a PRBS31 pattern, and an energy efficiency of 2.02 pJ/bit excluding the laser.

## **5. References**

- [1] B. Lee *et al.*, "Beyond CPO: A Motivation and Approach for Bringing Optics Onto the Silicon Interposer," in *IEEE JLT 2023.*
- [2] S. K. Yeh *et al*., "Silicon Photonics Platform for Next Generation Data Communication Technologies," in *IEEE IEDM 2024*, paper 23.3.
- [3] N. Mehta *et al.*, "A microring resonator-based clock-forwarded DWDM optical interconnect in a monolithic silicon photonics process", in *49th ECOC 2023,* pp. 1496-1499.
- [4] S. Song *et al.*, "A 32 Gbps/λ 256Gbps/Fiber Half-Rate Bandpass-Filtered Clock-Forwarding DWDM Optical Link in a 3D-Stacked 7nm EIC/65nm PIC Technology" To Appear in *IEEE ISSCC 2026.*
- [5] N. Nedovic, Methodology for Device, Circuit and Architecture Level Co-design and Optimization of Dense Wavelength Division Multiplexing Links," in *CLEO 2023*, San Jose, CA, USA, 2023, pp. 1-2.