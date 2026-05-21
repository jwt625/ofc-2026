# 3D Hybrid Bonded EIC-PIC Integration and Packaging Technologies

## S. J. Ben Yoo<sup>1,2</sup>

University of California Davis, Davis, CA, United States.
 Lawrence Berkeley National Laboratory, Berkeley, CA, United States.
 Author e-mail address: sbyoo@ucdavis.edu

**Abstract:** Hybrid-bonding technique offers the most advanced 3D co-integration of photonic and electronic integrated circuits for power-efficient and high-throughput data systems. We will discuss the world's first 3D hybrid-bonded EPIC and review co-design and co-integration strategies. © 2026 The Author

#### 1. Introduction

The exponential growth of data-intensive applications, particularly in artificial intelligence (AI) and high-performance computing (HPC), has pushed traditional electrical interconnects to their physical limits. While Silicon Photonics (SiPh) has emerged as the solution to the "memory wall" and "I/O wall," but its integration with host electronics (EIC) has historically been bottlenecked by packaging parasitics. Traditional 2.5D integration, which places Electronic and Photonic Integrated Circuits (EICs and PICs) side-by-side on an interposer, or standard 3D flip-chip stacking using microbumps or copper pillars, imposes limitations on interconnect density and energy efficiency. The parasitic capacitance and resistance associated with solder bumps (typically 20–50 µm pitch) limit bandwidth density and require power-hungry electrostatic protection and equalization circuits. Very close cointegration and co-design of EICs and PICs are essential for AI, HPC, and many modern workloads as electrical signal attenuation and power consumption become prohibitive.

To address these challenges, 3D hybrid bonding—specifically direct Cu-Cu bonding—has emerged as the definitive enabling technology. By eliminating solder entirely and bonding dielectric-to-dielectric and metal-to-metal, hybrid bonding enables interconnect pitches below 10  $\mu$ m (even scaling down to <1  $\mu$ m), reduced parasitics by orders of magnitude. We will review the state-of-the-art in 3D hybrid-bonded EPICs, analyzing the "world's first" demonstrations and the critical co-design strategies required to make them viable.

### 2. Hybrid-Bonding Technologies and EIC-PIC Integration

![](_page_0_Figure_10.jpeg)

Fig. 1. Various co-integration methods of SiPh PIC and EIC

Hybrid-Bonding (commercially also called Direct Bonding Interconnects (DBI<sup>TM</sup>))[1] emerged from wafer-fusion [2](wafer-bonding by atomic rearrangement [3]) technique originally used for fusing dies or wafers of dissimilar materials. This method offers the lowest parasitic, closest, and the most robust EIC-PIC integration among many possible EIC-PIC integration methods illustrated in Fig. 1. The hybrid-bonding process typically follows a "Wafer-on-Wafer" (WoW) or "Die-to-Wafer" (D2W) approach starting with (a) **Surface Preparation:** Both EIC and PIC wafers undergo Chemical Mechanical Polishing (CMP) to achieve ultra-smooth surfaces (roughness nm). The copper pads are slightly recessed below the dielectric surface (dishing), (b) **Alignment & Bonding:** The dies are

aligned with high precision (<200 nm accuracy). Room temperature bonding connects the dielectric surfaces via van der Waals forces, (c) **Annealing:** The stack is heated (typically 250°C–350°C), causing the copper to expand (due to higher CTE than silicon oxide) and fuse, creating a permanent electrical connection.

As Table 1 summarizes, hybrid-bonding offers extremely low parasitic capacitance, high-yield copper-to-copper direction connection, high reliability, extremely high interconnect density, while avoiding the requirement of electrostatic protection damage (ESD) circuit inclusion at the EIC-PIC interface.

Table 1. Comparisons of 3D EIC-PIC integration methods utilizing C4 bump, Copper Pillar, and Hybrid bonding.

| Feature                          | C4 bump bonding                  | Copper Pillar<br>bonding              | Hybrid Bonding (DBI)                | Benefit of Hybrid Bonding                                           |
|----------------------------------|----------------------------------|---------------------------------------|-------------------------------------|---------------------------------------------------------------------|
| Interconnect Type                | Solder (SnAg) +<br>Underfill     | Copper Pillar + microBump             | Direct Cu-Cu Fusion                 | Eliminates solder resistance and reliability issues.                |
| Typical Parasitic<br>Capacitance | ~70 fF                           | ~30 fF                                | ~5 fF                               | Achieves > 4x reduction in optical power and < 0.5pJ/bit efficiency |
| Typical Parasitic<br>Resistance  | 1 mΩ @DC/<br>11 mΩ @5Ghz         | $3~m\Omega$ @DC/ $18~m\Omega$ @5Ghz   | 7 mΩ@DC/<br>19 mΩ@5Ghz              | Reliable connection without solder bumps at high yield              |
| ESD Protection                   | Required for High<br>Yield       | Required for High<br>Yield            | Not Necessary & achieves high yield | Drastic reduction in dynamic power consumption.                     |
| Pitch Density                    | ~200µm (Limited by C4 bump size) | ~60µm (Limited by copper pillar size) | Scalable to < 1 µm pitch            | Allows massive parallel WDM channels (32+ in this demo).            |

### 3. Realizing 3D EPIC by Hybrid-Bonding

Although hybrid-bonding have been utilized for a variety of electronics-to-electronics integration for a number of years [4], [5], the hybrid-bonding to realize 3D EPIC of SiPh PIC and EIC demonstrated in 2023 [6] utilized wafer-scale PIC (300 mm SiPh wafers from AIM Photonics' ACT) and wafer-scale EIC (300 mm 12 nm CMOS wafers based on Multi-Project-Wafer (MPW) runs from GlobalFoundries' GF12LP) as illustrated in Fig. 2. As shown in Fig. 3, commercially demonstrated 3D hybrid-bonded EPIC engines have recently been solidified by major foundry, most notably the SiPh PIC-EIC switch announced by NVIDIA utilizing TSMC's COUPE technology in 2025[7].

![](_page_1_Figure_8.jpeg)

Fig. 2. (a) Hybrid bonded EIC dies on PIC wafer, (b) 32 wavelength 3D EPIC transceiver die including 32 microresonator modulators, 32 wavelength photodetectors on SiPh and co-designed 12 nm CMOS EIC designed for 1 Tb/s I/O, (c) packaged 3D EPIC transceivers, and (d) 6.1 dB reduction in photodetector sensitivity OMA thanks to hybrid-bonding vs. C4 bump bonding.

![](_page_1_Figure_10.jpeg)

Fig. 3. NVIDIA's silicon photonic switch utilizing TSMC's COUPE technology achieving 3D integration of EIC and PIC.

The breakthrough in 3D EPIC realization lies in the successful hybrid bonding of a high-performance CMOS EIC directly onto a Silicon Photonics PIC without the use of microbumps. As shown in Fig. 2 (d), reduction in total capacitance of 100 fF to 28 fF seen by the photodetector in the PIC to the transimpedance amplifier (TIA) in the EIC resulted in 6.1 dB reduction in optical power. Considering that the laser wall plug power efficiency is less than 10% when thermoelectric cooling is included, the total power reduction becomes significant when co-packaging of EIC and PIC is achieved. The vertical stacking drastically reduces the footprint compared to 2.5D lateral integration, enabling the "optical engine" to be placed directly on the accelerator substrate (Co-Packaged Optics, or CPO).

## 4. Co-Design and Co-Integration of EIC-PIC

The transition to 3D hybrid bonding requires a fundamental rethink of how EICs and PICs are designed together. **RF and Signal Integrity Co-Design:** The elimination of the  $50\Omega$  transmission line standard is a major paradigm shift enabled by hybrid bonding. Co-designs across EIC-PIC including TIA-Photodetector pairs and modulator driver-microresonator pairs are two of many examples of optimal co-designs necessary in 3D EPICs.

**Co-Layout and 3D LVS:** The bump pads on the EIC and PIC must be perfectly mirrored. Any misalignment not only risks open circuits but introduces capacitance variations that can degrade high-speed signal eyes.

*Mechanical and Stress Management:* Hybrid bonding is sensitive to warpage and stress.

*CTE Mismatch*: Although both substrates are silicon, the varying densities of metal (copper) and dielectric (SiO<sub>2</sub>/SiCN) can cause bowing. Co-design requires "dummy metal" filling to balance the pattern density across the wafer, ensuring flatness for the CMP process.

**Controlled Co-Integration Process:** Unlike solder bonding, hybrid bonding requires wafer surfaces with < 1 nm rms roughness bonded in ~Class 10 cleanroom environments for high yield.

*Thermal Co-Design*: One of the most critical challenges in 3D EPICs is thermal management. Silicon photonic devices, particularly ring modulators and lasers, are highly temperature-sensitive. However, in a 3D stack, the EIC (which can generate significant heat) is placed directly on top of these sensitive components.

**Thermal Crosstalk Mitigation:** Co-design strategies involve creating "thermal maps" during the layout phase. Highpower blocks on the EIC (like TIAs) must be spatially offset from thermally sensitive components on the PIC (like Ring Resonators).

*Through-Silicon Vias (TSVs)*: In addition to higher utilization of TSVs in the 3D EPIC, TSVs can be used to conduct heat away from the EIC through the PIC substrate to a heat sink, bypassing the thermally resistive oxide layers.

## 5. Summary

The recent realization of the first 3D hybrid-bonded EPICs and commercial deployment marks a turning point in semiconductor packaging. By moving from "packaging" to "integration"—where the EIC and PIC effectively become a single monolithic-like functional block—we unlock the bandwidth and energy efficiency required for the Zettabyte era. While challenges in surface topology, thermal crosstalk, and high-precision alignment remain, the codesign strategies outlined above provide a robust framework for overcoming them. As pitch scaling continues down to the sub-micron regime, 3D hybrid bonding will undoubtedly become the standard for future high-performance optical transceivers and co-packaged photonic engines in many applications, in particular AI data systems.

## 3. References

- [1] P. Enquist, "High Density Direct Bond Interconnect (DBI) Technology for Three Dimensional Integrated Circuit Applications," MRS Proceedings, vol. 970, pp. 0970-Y01-04, Feb. 2006, doi: 10.1557/PROC-0970-Y01-04.
- [2] Z. L. Liau and D. E. Mull, "Wafer fusion: A novel technique for optoelectronic device fabrication and monolithic integration," *Appl. Phys. Lett.*, vol. 56, no. 8, pp. 737–739, Feb. 1990, doi: 10.1063/1.102697.
- [3] Y. H. Lo, R. Bhat, D. M. Hwang, M. A. Koza, and T. P. Lee, "Bonding by atomic rearrangement of InP/InGaAsP 1.5 μm wavelength lasers on GaAs substrates," *Appl. Phys. Lett.*, vol. 58, no. 18, pp. 1961–1963, May 1991, doi: 10.1063/1.105032.
- [4] C. Y. Lee, C. H. Won, S. Jung, E. S. Jung, T. M. Choi, H. R. Lee, J. Yoo, S. Yoon, and S. G. Pyo, "3D Integrated Process and Hybrid Bonding of High Bandwidth Memory (HBM)," *Electronic Materials Letters*, vol. 21, no. 3, pp. 395–419, May 2025, doi: 10.1007/s13391-025-00557-9.
- [5] J. H. Lau, "Current Advances and Outlooks in Hybrid Bonding," *IEEE Trans. Compon. Packaging Manuf. Technol.*, vol. 15, no. 4, pp. 651–681, Apr. 2025, doi: 10.1109/TCPMT.2025.3533926.
- [6] P.-H. Chang, A. Samanta, P. Yan, M. Fu, Y. Zhang, M. B. On, A. Kumar, H. Kang, I.-M. Yi, D. Annabattuni, D. Scott, R. Patti, Y.-H. Fan, Y. Zhu, S. Palermo, and S. J. Ben Yoo, "A 3D Integrated Energy-Efficient Transceiver Realized by Direct Bond Interconnect of Co-Designed 12 nm FinFET and Silicon Photonic Integrated Circuits," *Journal of Lightwave Technology*, pp. 1–15, 2023, doi: 10.1109/JLT.2023.3291704.
- [7] M. F. Chen, H. T. Cheng, C. H. Tsou, S. Y. Hou, T. H. Yu, S. Liu, R. Lu, and K. C. Hsu, "Optical and Electrical Characterization of a Compact Universal Photonic Engine," in 2025 IEEE 75th Electronic Components and Technology Conference (ECTC), May 2025, pp. 54–58. doi: 10.1109/ECTC51687.2025.00015.