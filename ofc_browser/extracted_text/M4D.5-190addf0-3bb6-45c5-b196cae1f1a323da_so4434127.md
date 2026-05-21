# **82-mm-long Optical Link using Micro-transfer-printed Directly Modulated Membrane Laser and Photodetector on SiN Waveguide: Toward Wafer-scale Optical Interconnects**

**Yoshiho Maeda1,2 , Tatsurou Hiraki1,2 , Takuma Aihara1,2 , Takuro Fujii1,2, Tomonari Sato1,2 , and Shinji Matsuo<sup>1</sup>**

*<sup>1</sup>Device Technology Labs, NTT, Inc., 3-1 Morinosato Wakamiya, Atsugi-shi, Kanagawa 243-0198, Japan. <sup>2</sup>Device Innovation Center, NTT, Inc., 3-1 Morinosato Wakamiya, Atsugi-shi, Kanagawa 243-0198, Japan. yoshiho.maeda@ntt.com*

**Abstract:** We demonstrate an optical link using micro-transfer-printed III-V directly modulated membrane laser and photodetector on an 82-mm-long SiN waveguide, achieving 48-Gbps NRZ operation with an energy cost of 0.24 pJ/bit at 50°C. © 2025 The Authors

## **1. Introduction**

The rapid growth of artificial intelligence (AI) and high-performance computing (HPC) have driven electrical interconnects to their fundamental limits in distance and speed. Wafer-scale optical interconnects are attracting significant attention to overcome these limitations, and several demonstrations have been reported on the basis of Si photonics technology [1]. Heterogeneous integration of III-V semiconductor lasers on Si is key to reducing energy costs, as it eliminates the large coupling losses between external lasers and photonic circuits [2]. Among various III-V devices on Si, membrane InP-based devices exhibit low power consumption due to strong optical confinement and small active volume [3]. We previously demonstrated an optical link on a Si wafer using membrane electro-absorptionmodulator-integrated distributed-feedback (DFB) laser on a 7.6-mm silica-based (SiOx) waveguide, achieving a low energy cost of 0.26 pJ/bit [4]. However, SiO<sup>x</sup> waveguides exhibit a large bending radius (250 m) and wide core width (3 m), which significantly limit the routing density and design flexibility for wafer-scale optical interconnects.

Silicon nitride (SiN) waveguides are highly promising for wafer-scale interconnects, offering low propagation loss and a compact bending radius that enable high routing density and flexible layout design. Although the large refractive-index mismatch between SiN waveguides and III-V devices complicates integration, membrane III-V devices mitigate this issue by using a simple tapered waveguide structure for efficient optical mode transfer [5].

In this work, we developed a low-energy optical link by integrating a directly modulated membrane laser (DML) [3] and a photodetector (PD) [6] onto a SiN waveguide which offers a small bending radius (~ 50 m) and low propagation loss (~ 0.2 dB/cm) on a Si wafer. To use commercial SiN waveguide circuits, the micro-transfer-printing (MTP) method [7] is utilized for III-V device integration because the devices can be fabricated separately using their own fabrication processes. Due to the low driving current of the membrane DML and low propagation loss of the SiN waveguide, we achieved 82-mm-long optical links at data rates of 32 and 48 Gbps with energy costs of 0.36 and 0.24 pJ/bit at 50°C, respectively.

![](_page_0_Figure_10.jpeg)

Fig. 1 Schematic (a) top view, (b) detailed top views of membrane DML and PD, (c) cross-sectional view of the fabricated SiN-based optical link, and simulated mode profile in the cross-section (d) of DML, and (e) of PD.

## **2. Design and fabrication**

Figure 1 illustrates the fabricated membrane DML and PD integrated on a 0.8-m-thick SiN waveguide (82 mm long, 46 bends, 50-μm bending radius). The devices were fabricated on separate wafers and micro-transfer-printed onto a recess area of the wafer following our previous process [5,8]. The DML consists of a 140-m-long detuned-DFB structure [4] with a 6-periods InGaAlAs multiple-quantum well (6QW) core, while the PD features a 110-m-long 9QW core, buried in 340- and 230-nm-thick InP slabs, respectively (Figs. 1(b), (c)). The InP slab thickness (tInP) of the DML was thicker than that of the PD to reduce a series resistance and suppress self-heating, yielding an optical confinement factor (Γ) of 14.3% (Fig. 1(d)). On the other hand, tInP of the PD was optimized for a large Γ of 26.7% (Fig. 1(e)) and low capacitance, enabling a wide bandwidth and high responsivity. Although shorter cavities of a laser enable lower energy operation [9], a relatively longer cavity laser was used for the first experimental demonstration of the electrical-optical-electrical (E-O-E) optical link using a membrane DML.

The SiN waveguides were fabricated by a commercial foundry. Figure 2(a) shows a measured propagation loss of ~ 0.2 dB/cm for 0.8-m-wide SiN waveguide using the cutback method with the test sample on the same wafer. Optical coupling between the membrane devices and SiN waveguide was achieved using a 240-m-long InP inversetapered waveguide (tip width: 0.1 m) on a straight SiN waveguide, as shown in Figs. 1(b), (c). Figure 2(b) shows the simulated coupling loss versus lateral alignment-error obtained using the 3D finite-difference time-domain method. Increasing the SiN core width from 0.8 to 1.6 μm improved misalignment tolerance, maintaining <0.5-dB excess loss up to a 0.5-μm alignment error. Therefore, a 1.6-μm-wide SiN waveguide was adopted in the coupling section to ensure misalignment tolerance.

![](_page_1_Figure_5.jpeg)

Fig. 2 (a) Measured propagation loss, and (b) simulated alignment-error dependence of coupling loss and definition of alignment-error.

## **3. Experimental results**

The static characteristics of the membrane DML were measured before PD integration. The maximum on-chip output power was estimated to be approximately -1.0 dBm at the PD position at 25°C. Figure 3(a) shows the relationship between PD output photocurrent and laser input current (*I-I* curve) at PD bias voltage of 3.0 V at 50°C, where the DFB laser exhibited a low threshold current of ~2.4 mA. Higher PD output current was obtained at low laser injection current compared with our previous work [4], even after transmission through the 82-mm-long SiN waveguide. The small output fluctuations observed in this *I-I* curve are mainly attributed to the facet of recess region in front of the DML and PD, where the overcladding layer was partially etched, resulting in a SiO₂/Air/SiON structure. Therefore, it is considered that filling the recess with a polymer material whose refractive index is matched can suppress this reflection. The small-signal E-O-E response was measured using a vector network analyzer at various bias currents of the DML, while the bias voltage of the PD was fixed at 3.0 V. As shown in Fig. 3(b), clear relaxation oscillation frequency of about 12 GHz and E-O-E 3-dB-bandwidth of 17 GHz were obtained even at a low laser-injection current of 7.0 mA. Figure 3(c) shows a measured O-E small-signal response of the membrane PD at a bias voltage of 3.0 V by incident light from the chip facet using an external light source ( = 1295 nm) and lightwave component analyzer. The 3-dB-bandwidth of the membrane PD was around 30 GHz, which is sufficiently higher than DML.

Finally, E-O-E eye diagrams were measured for non-return-to-zero (NRZ) signals targeting low-latency computing applications. Figure 4(a) shows the experimental setup. The frequency response of the RF components, including the RF cables, amplifiers, and probes was de-embedded through calibration. An arbitrary waveform generator (AWG) supplied 0.35 Vpp and applied NRZ signals (pseudorandom binary sequence (PRBS) 2 11 -1) at data rates of 32 and 48 Gbps to the DML via an RF probe. The output signals from the PD were amplified using an RF amplifier then captured using a real-time oscilloscope. A 4th-order Bessel filter and linear equalizer (5 taps for 32 Gbps and 15 taps for 48 Gbps) were applied for compensating for linear distortion. As shown in Fig. 4(b) and (c), clear eye openings were obtained, with signal-to-noise ratios of 4.64 at 32 Gbps and 3.78 at 48 Gbps. The total static power consumption of the DML and PD was 11.6 mW, resulting in an energy cost of 0.36 pJ/bit at 32 Gbps and 0.24 pJ/bit at 48 Gbps (excluding driver electronics) at 50°C. By using a heterogeneously integrated membrane DML on a SiN waveguide, this link achieves an over tenfold increase in link length compared with our previous 7.6-mm-long SiOx-based device [4], avoiding the energy penalties of external modulators and reducing the propagation loss of a waveguide. These results indicate a viable pathway toward wafer-scale optical input/output (I/O) using membrane DMLs and PDs on a SiN, leveraging the combination of a compact SiN platform and high-performance membrane photonic devices. The energy cost can be further reduced by using shorter-cavity DMLs for lower driving currents.

![](_page_2_Figure_3.jpeg)

Fig. 3 Measured (a) relationship between PD output current and laser input current, (b) normalized E-O-E small signal response of DML-PD optical link, and (c) normalized O-E small signal response of membrane PD at 50C.

![](_page_2_Figure_5.jpeg)

Fig. 4 (a) Measurement setup and measured eye diagrams of (b) 32- and (c) 48-Gbps NRZ signal at 50C.

## **4. Conclusion**

We demonstrated an 82-mm-long optical link on a SiN platform by integrating a membrane DML and PD using MTP. The link successfully achieved 48-Gbps operation with an energy cost of 0.24 pJ/bit at 50°C. This corresponds to more than a tenfold increase in transmission distance compared with our previous SiOx-based demonstration, while maintaining low energy cost. These results validate the combination of membrane III-V devices and SiN platforms via MTP as a powerful approach for achieving the wafer-scale optical I/O required for future AI and HPC systems.

### **Acknowledgements**

This paper is partially based on results obtained from the project, "Research and Development Project of the Enhanced Infrastructures for Post-5G Information and Communication Systems" (JPNP20017), commissioned by the New Energy and Industrial Technology Development Organization (NEDO).

### **References**

- [1] N. C. Harris, et al., "Passage: A Wafer-Scale Programmable Photonic Communication Substrate," *in IEEE Hot Chips 34 Symposium (HCS) 2022*, Cupertino, CA, USA, pp. 1-26 (2022).
- [2] N. M. Fahrenkopf, et al., "The AIM photonics MPW: a highly accessible cutting edge technology for rapid prototyping of photonic integrated circuits," J. Sel. Top. Quant. Electron. 25, 8201406 (2019).
- [3] S. Matsuo, et al., "Directly modulated buried heterostructure DFB laser on SiO2/Si substrate fabricated by regrowth of InP using bonded active layer," Opt. Exp. **22**, 12139 (2014).
- [4] T. Hiraki, et al., "Integrated Optical Link on Si Wafer Using Low Energy Membrane InP-based Photonic Devices," in *Optical Fiber Communication Conference (OFC) 2025*, San Francisco, CA USA, 2025, paper M2K (2025).
- [5] T. Aihara, et al., "Micro-transfer Printed Widely Tunable Membrane Laser on a SiN. Platform," in *European Conference on Optical Communications (ECOC) 2025*, Copenhagen, Denmark, paper W.03.02.4 (2025).
- [6] T. Aihara, et al., "O-band membrane photodetector with InGaAsP-bulk absorption core using Franz–Keldysh effect," Opt. Exp. **33**, issue 1, pp. 1509-1516 (2025).
- [7] G. Roelkens, et al., "Present and future of micro-transfer printing for heterogeneous photonic integrated circuits," APL Photonics 9.1 (2024).
- [8] Y. Maeda, et al., "Micro-transfer-printed membrane distributed reflector lasers on Si waveguide modulated with 50-Gbit/s NRZ signal," J. Lightwave Technol., vol. 41, no. 12, pp. 3866-3873 (2023).
- [9] T. Fujii, et al., "Heterogeneously Integrated Membrane Lasers on Si Substrate for Low Operating Energy Optical Links," J. Sel. Top. Quant., vol. 24, no. 1, pp. 1-8, (2018).