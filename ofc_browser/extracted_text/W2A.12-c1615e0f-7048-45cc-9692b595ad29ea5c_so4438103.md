#### **A 4 Tbps 16-Channel DWDM Transmitter Using Extended-Depletion Silicon Photonic Microdisk Modulator Array**

**Shenlei Bao1,2, Chao Cheng1,2, Xianglin Bu1,2 , Yihao Yang1,2, Houyou Lai1,2 , Jintao Xue1,2, Wenfu Zhang1,2 , and Binhao Wang1,2\***

*<sup>1</sup>State Key Laboratory of Ultrafast Optical Science and Technology, Xi'an Institute of Optics and Precision Mechanics, Chinese Academy of Sciences, Xi'an 710119, Shaanxi, China <sup>2</sup>University of Chinese Academy of Sciences, Beijing 101408, China [\\*wangbinhao@opt.ac.cn](mailto:*wangbinhao@opt.ac.cn)*

**Abstract:** We demonstrate a 16-channel silicon photonic microdisk modulator array with a 3 dB electro-optic bandwidth of 65 GHz. The transmitter supports 16 × 256 Gbps PAM4 transmission, delivering an aggregate data rate of 4 Tbps/fiber.

#### **1. Introduction**

In recent years, the growing interconnect demands in data centers and artificial intelligence applications have placed increasingly stringent requirements on the bandwidth density and energy efficiency of optoelectronic interconnect systems. To enhance data throughput within limited chip areas, wavelength-division multiplexing (WDM) on silicon photonics platforms has emerged as a key solution for both on-chip and chip-to-chip interconnects [1]. Among various modulator structures, microcavity modulators offer compact footprints, high modulation efficiencies, and excellent scalability, making them promising candidates for multi-channel high-speed transmitters. In particular, microring modulators (MRMs) have been widely applied in WDM systems, achieving large free spectral range (FSR) with small radii - for example, supporting 8-channel 200 GHz-spaced WDM [2][3]. However, scaling to 16 channels at the same spacing introduces significant engineering challenges: the resonance wavelength becomes highly sensitive to geometric dimensions and refractive index variations, and further reducing the radius to enlarge FSR exacerbates fabrication tolerances, compromising array uniformity. In contrast, microdisk modulators (MDMs) exhibit continuous optical field distributions and lower boundary scattering loss, enabling larger FSRs and improved fabrication tolerance at comparable radii [4][5].

In this work, we demonstrate a 16-channel MDM array operating with 200 GHz channel spacing in the O band, effectively overcoming FSR-related limitations. Each MDM has a radius of approximately 4.1 μm, achieving a FSR of 19.6 nm and an optical quality (Q) factor of ~3500, while maintaining a modulation efficiency of 25 pm/V and a 3 dB electro-optic (EO) bandwidth of 65 GHz under a -2 V bias. The MDM array supports 16 × 256 Gbps PAM4 signaling, achieving an aggregate data rate of 4 Tbps per fiber. Without full-link calibration from an arbitrary waveform generator (AWG), all channels exhibit transmitter and dispersion eye closure quaternary (TDECQ) values between 2.68 dB and 3.24 dB using a 9-tap feed-forward equalizer (FFE) implemented on the oscilloscope, confirming excellent channel uniformity and high-speed performance. These results establish a viable path toward large-scale, high-bandwidth-density silicon photonic WDM integration.

![](_page_0_Picture_9.jpeg)

Fig. 1. (a) Overview of the silicon photonic transmitter with 16-channel MDMs. (b) Cross-sectional view of PN junction. (c) Microscopic image of the 16-channel MDM array.

#### **2. Design and Characterization**

As shown in Fig. 1(a), the proposed 16-channel MDM transmitter array consists of 16 modulators sharing a common bus waveguide, each equipped with an independent metal heater for precise thermal tuning. The microscopic image

of the fabricated 16-channel MDM array is shown in Fig. 1(c). Each MDM has a radius of 4.1 μm, a waveguide width of 380 nm, a coupling gap of 180 nm, and an arc-shaped coupling region spanning ± 12°. This compact geometry provides a FSR of 19.6 nm, supporting 16 × 200 GHz WDM operation within the O-band.

Compared with conventional MRMs, the MDM inherently suffers from higher cavity loss at the same radius, necessitating stronger coupling to reach critical coupling. To address this, an arc-shaped coupling region is introduced to replace the conventional racetrack structure. While the racetrack design can increase coupling efficiency, it also lengthens the optical path and introduces mode discontinuities at the straight-to-curved transitions, particularly under small radius conditions required to maintain a ≥3.2 THz FSR. The arc-shaped coupling design mitigates these discontinuities, suppresses boundary scattering, and maintains optical confinement, thereby achieving an optimal trade-off between Q-factor and modulation efficiency under ultra-compact, high-doped configurations.

As shown in Fig. 1(b), the MDM employs an extended-depletion lateral PN-junction to further reduce cavity loss and enhance EO performance [7]. A multi-level doping profile is engineered to align the electric-field distribution with the whispering-gallery-mode (WGM) optical field. Specifically, the N-type regions are doped at 1.0 × 10<sup>20</sup>, 1.0 × 10<sup>19</sup>, and 3.8 × 10<sup>17</sup> cm-3 , while the P-type regions are doped at 7.1 × 10<sup>19</sup>, 5.3 × 10<sup>18</sup>, and 2.1 × 10<sup>17</sup> cm-3 . The lightly doped n- and p- regions expand the depletion region overlapping with the optical mode, improving the carrier-induced refractive index modulation. Meanwhile, the disk center is doped with P++ rather than N++, with a lower P++ concentration to suppress free-carrier absorption and reduce optical loss. This spatially engineered junction design breaks the trade-off between modulation efficiency and EO bandwidth.

Following wavelength stabilization via the integrated thermal tuning scheme, as shown in Fig. 2(a), all 16 channels exhibit uniform resonance spacing of ~1.14 nm (corresponding to 200 GHz) and Q-factors ranging from 3200 to 3700 [6]. As presented in Fig. 2(b), the MDM design achieves a modulation efficiency of 25 pm/V and a Qfactor of ~3500. The extended depletion region effectively reduces junction capacitance, thereby mitigating RCrelated bandwidth degradation, as further verified by the reduced junction capacitance (8 fF) in the S<sup>11</sup> response shown in Fig. 2(c) compared to conventional racetrack MRMs (~14 fF). Under a -2 V bias, the MDM achieves a 3 dB EO bandwidth of 65 GHz (Fig. 2(d)), demonstrating that compact microcavity modulators can simultaneously deliver large FSR operation, high modulation efficiency, and high EO bandwidth.

![](_page_1_Figure_6.jpeg)

Fig. 2. (a) Transmission spectra of the 16-channel MDM array. (b) Measured transmission spectra under different bias voltages. (c) Measured small-signal S<sup>11</sup> responses on a Smith chart at a bias voltage of -2 V. (d) Measured EO responses of the MDM at a bias voltage of -2 V.

#### **3. Eye Diagram Measurement**

For eye diagram measurement, the 16-channel MDM array is driven by a 2 Vpp single-ended signal from a Keysight M8199B AWG, delivered to the devices via a bias-tee and RF probe pads. The optical outputs from each channel, with an average power of -8 dBm, are amplified to 2 dBm using a praseodymium-doped fiber amplifier (PDFA) to compensate for fiber-to-chip coupling loss prior to oscilloscope detection. Benefiting from the extended-depletion design, which enhances modulation efficiency and reduces junction capacitance, all 16 channels exhibit open and symmetric 256 Gbps PAM4 eye diagrams under a 2 Vpp drive without calibration. As shown in Fig. 3, the TDECQ values across the array range from 2.68 to 3.24 dB, demonstrating excellent channel uniformity and high-speed modulation performance.

![](_page_2_Figure_3.jpeg)

Fig. 3. Measured eye diagrams at 256 Gbps PAM4 for the 16-channel MDM.

#### **4. Conclusion**

The proposed 16-channel MDM array achieves a well-balanced performance in FSR, modulation efficiency, and EO bandwidth. By integrating an arc-shaped coupling region with an extended-depletion PN junction, the design effectively mitigates Q-factor degradation in compact MDMs and alleviates RC limitations. As a result, the transmitter supports 16 × 256 Gbps PAM4 operation, delivering an aggregate data rate of 4 Tbps per fiber. These results demonstrate the effectiveness of the proposed architecture for realizing high-bandwidth-density silicon photonic interconnects and its scalability toward large-scale WDM systems.

#### **5. Acknowledgement**

This work was supported by the National Key Research and Development Program of China (2022YFB2803100).

#### **References**

- [1] J. Xue et al., "Advances in Integration of Co-Packaged High-Density Optical Interconnection Chips," Acta Optica Sinica, 45, 17 (2025). [2] K. Omirzakhov et al., "Monolithically Integrated Sub-63 fJ/b 8-Channel 256Gb/s Optical Transmitter with Autonomous Wavelength Locking in 45nm CMOS SOI," ISSCC (2024).
- [3] J. Xue et al., "An 8×256 Gbps Silicon Photonic DWDM Transmitter with Thermally Stable Microring Modulators," OFC (2025).
- [4] A. Novick et al., "Ultra-Efficient Interleaved Vertical-Junction Microdisk Modulator with Integrated Heater," OFC (2024).
- [5] V. Rizzo et al., " Ultra-Efficient Foundry-Fabricated Resonant Modulators with Thermal Undercut," CLEO (2023).
- [6] S. Bao et al., "A Comprehensive Equivalent Circuit Model of Silicon Microring Modulators for Photonics-Electronics Codesign," Journal of Lightwave Technology, 42, 14 (2024).
- [7] J. Xue et al., " A 64 Gbaud/s Hybrid-Integrated Optical Transmitter Based on a 60 GHz Silicon Photonic Dual-Segment Microring Modulator and a CMOS Driver for High-Bandwidth DWDM Optical I/O," Journal of Lightwave Technology, 43, 10 (2025).

# **A 4Tbps 16-Channel DWDM Transmitter Using Extended-Depletion Silicon Photonic Microdisk Modulator Array**

Shenlei Bao1,2, Chao Cheng1,2 , Xianglin Bu1,2, Yihao Yang 1,2 , Houyou Lai 1,2 , Jintao Xue 1,2 , Wenfu Zhang 1,2 , and Binhao Wang 1,2\* <sup>1</sup>State Key Laboratory of Ultrafast Optical Science and Technology, Xi'an Institute of Optics and Precision Mechanics, Chinese Academy of Sciences, Xi'an 710119, Shaanxi, China <sup>2</sup>University of Chinese Academy of Sciences, Beijing 101408, China \*Correspondence: \*wangbinhao@opt.ac.cn

# **ABSTRACT**

We demonstrate a 16-channel silicon photonic microdisk modulator array with a 3 dB electro-optic bandwidth of 65 GHz. The transmitter supports 16 × 256 Gbps PAM4 transmission, delivering an aggregate data rate of 4 Tbps/fiber.

# **INTRODUCTION**

- ⚫ The rapid growth of data centers and AI applications demands higher bandwidth density and energy efficiency in optical interconnects. WDM on silicon photonics has emerged as a key solution for on-chip and chip-to-chip links. Among various modulator structures, microcavity modulators offer compact footprints and excellent scalability for multi-channel transmitters.
- ⚫ Microring modulators (MRMs) have been widely used in WDM systems, supporting up to 8-channel 200 GHz-spaced operation. However, scaling to 16 channels introduces critical challenges: resonance wavelengths become highly sensitive to dimensional variations, and further radius reduction exacerbates fabrication tolerances. In contrast, microdisk modulators (MDMs) exhibit continuous optical field distributions and lower boundary scattering loss, enabling larger FSRs and improved fabrication uniformity at comparable radii.
- ⚫ In this work, we demonstrate a 16-channel MDM array with 200 GHz channel spacing in the O-band. Each MDM achieves a FSR of 19.6 nm, Q-factor of ~3500, modulation efficiency of 25 pm/V, and 3 dB EO bandwidth of 65 GHz at −2 V. Supporting 16 × 256 Gbps PAM4 signaling, the array delivers 4 Tbps aggregate data rate with TDECQ values of 2.68–3.24 dB across all channels — confirming channel uniformity and establishing a viable path toward large-scale silicon photonic WDM integration.

# **DESIGN**

## ⚫ **Device Structure**

- a. MDM parameters: radius 4.1 μm, waveguide width 380 nm, coupling gap 180 nm, arc-shaped coupling region ±12°.
- b. FSR = 19.6 nm, supporting 16 × 200 GHz WDM operation across the O-band.

## ⚫ **Arc-Shaped Coupling Region**

a. Arc-shaped design suppresses boundary scattering and maintains optical confinement, achieving an optimal Q-factor/modulation efficiency trade-off in ultra-compact, high-doped configurations.

### ⚫ **Extended-Depletion Lateral PN Junction**

- a. Multi-level doping profile engineered to align electric-field distribution with the whispering-gallery-mode (WGM) optical field.
- b. Lightly doped n⁻/p⁻ regions expand depletion overlap with the optical mode, enhancing carrier-induced index modulation.
- c. P⁺⁺ (rather than N⁺⁺) at disk center with lower concentration suppresses free-carrier absorption and reduces optical loss.

![](_page_3_Figure_18.jpeg)

Fig. 1. (a) Overview of the silicon photonic transmitter with 16-channel MDMs. (b) Cross-sectional view of PN junction. (c) Microscopic image of the 16-channel MDM array.

# **RESULTs**

## ⚫ **Wavelength & Q-Factor Uniformity**

- a. All 16 channels exhibit uniform resonance spacing of ~1.14 nm (200 GHz) after thermal tuning.
- b. Q-factors range from 3200 to 3700 across the full array, confirming fabrication consistency.

## ⚫ **Modulation Efficiency & Bandwidth**

- a. Modulation efficiency: 25 pm/V.
- b. Extended depletion region reduces junction capacitance to 8 fF (vs. ~14 fF for conventional racetrack MRMs), mitigating RC-related bandwidth degradation.
- c. 3 dB EO bandwidth: 65 GHz at −2 V bias.
- d. Simultaneously achieves large FSR, high modulation efficiency, and high EO bandwidth.

## ⚫ **Eye Diagram Measurement Setup**

- a. Drive signal: 2 Vpp single-ended PAM4 from Keysight M8199B AWG, delivered via bias-tee and RF probe pads.
- b. Optical output: −8 dBm per channel, amplified to 2 dBm via PDFA to compensate fiber-to-chip coupling loss.

## ⚫ **256 Gbps PAM4 Performance**

- a. All 16 channels show open and symmetric eye diagrams at 256 Gbps PAM4 under 2 Vpp drive without calibration.
- b. TDECQ values: 2.68 3.24 dB across all channels.
- c. Confirms excellent channel uniformity and high-speed modulation performance

# **CONCLSION**

The proposed 16-channel MDM array achieves a well-balanced performance in FSR, modulation efficiency, and EO bandwidth. By integrating an arc-shaped coupling region with an extended-depletion PN junction, the design effectively mitigates Q-factor degradation in compact MDMs and alleviates RC limitations. As a result, the transmitter supports 16 × 256 Gbps PAM4 operation, delivering an aggregate data rate of 4 Tbps per fiber. These results demonstrate the effectiveness of the proposed architecture for realizing high-bandwidth-density silicon photonic interconnects and its scalability toward large-scale WDM systems.

![](_page_3_Figure_38.jpeg)

Fig. 2. (a) Transmission spectra of the 16-channel MDM array. (b) Measured transmission spectra under different bias voltages. (c) Measured small-signal S<sup>11</sup> responses on a Smith chart at a bias voltage of -2 V. (d) Measured EO responses of the MDM at a bias voltage of -2 V.

![](_page_3_Figure_40.jpeg)

Fig. 3. Measured eye diagrams at 256 Gbps PAM4 for the 16-channel MDM.

## REFERENCES

- 1. J. Xue et al., "Advances in Integration of Co-Packaged High-Density Optical Interconnection Chips," Acta Optica Sinica, 45, 17 (2025).
- 2. K. Omirzakhov et al., "Monolithically Integrated Sub-63 fJ/b 8-Channel 256Gb/s Optical Transmitter with Autonomous Wavelength Locking in 45nm CMOS SOI," ISSCC (2024).
- 3. J. Xue et al., "An 8×256 Gbps Silicon Photonic DWDM Transmitter with Thermally Stable Microring Modulators," OFC (2025). 4. A. Novick et al., "Ultra-Efficient Interleaved Vertical-Junction Microdisk Modulator with Integrated Heater," OFC (2024).

a CMOS Driver for High-Bandwidth DWDM Optical I/O," Journal of Lightwave Technology, 43, 10 (2025).

- 5. V. Rizzo et al., " Ultra-Efficient Foundry-Fabricated Resonant Modulators with Thermal Undercut," CLEO (2023). 6. S. Bao et al., "A Comprehensive Equivalent Circuit Model of Silicon Microring Modulators for Photonics-Electronics Codesign," Journal of
- Lightwave Technology, 42, 14 (2024). 7. J. Xue et al., " A 64 Gbaud/s Hybrid-Integrated Optical Transmitter Based on a 60 GHz Silicon Photonic Dual-Segment Microring Modulator and