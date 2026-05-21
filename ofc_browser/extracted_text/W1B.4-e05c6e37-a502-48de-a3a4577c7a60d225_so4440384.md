# **A 53-Gbaud NRZ/PAM4 × 8-Channel 1060-nm Single-Mode VCSEL-Based Ultra-Compact and High-Energy-Efficient CPO Transceiver for Full-Reach Datacenter Links**

**Wataru Yoshida1\*, Yuto Iwane2\*, Kazuya Nagashima1\* , Kazutaka Takeda2\*, Hideyuki Nasu1\*, and Fumio Koyama3\***

*<sup>1</sup>Photonics Laboratory, Furukawa Electric Co., Ltd., 6, Yawata-Kaigandori, Ichihara, Chiba, 290-8555 Japan <sup>2</sup>FUJIFILM Business Innovation Corp., 2274 Hongo, Ebina, Kanagawa, 243-0494, Japan 3 Institute of Science Tokyo, 4259 Nagatsutacho, Midori Ward, Yokohama, Kanagawa, 226-8501, Japan Author e-mail: wataru.yoshida@furukawaelectric.com*

**Abstract:** We demonstrate an ultra-compact (1.22 cm² footprint), high-energy-efficient (4.5 pJ/bit), 53-Gbaud × 8-channel 1060-nm SM VCSEL-based CPO transceiver enabling 2-km SMF parallel links. A newly designed two-microlens-array coupling system achieves <2 dB loss.

#### **1. Introduction**

The rapid proliferation of artificial intelligence (AI) and machine learning (ML) requires a highly parallelized training architecture. To achieve this, high energy-efficient, high-speed, and long-reach interconnects are needed between graphics processing units (GPUs) and switch ASICs in such AI/ML systems. Optical Internetworking Forum (OIF) issued a system vendor requirements document where a transmission distance spanning from 0 to 500 m and even extending up to 2 km in some cases, with low link energy of <10 pJ/bit as a front-end interconnect (FEI) [1]. It is critical to ensure interoperability between FEI optical transceivers supplied from multiple vendors, noted as the first priority in Ref. [1]. To realize long-reach, and interoperable optical links, an 800-Gb/s linear-drive pluggable optics (LPO) transceiver employing 1060-nm single-mode (SM) transverse-coupled-cavity VCSELs was demonstrated with low link energy of 5 pJ/bit [2, 3]. However, its large form factor prevents high-density mounting near GPUs and switch ASICs, and it results in limiting the total system bandwidth. To address this issue, we have proposed and demonstrated an ultra-compact 1060-nm SM VCSEL-based 106-Gb/s PAM4 16-channel transceiver employing multi-core fibers (MCFs) for Co-Packaged Optis (CPO) [4]. The CPO transceiver realized a 2-km MCF link with record low link energy of 3.95 pJ/bit. However, to aim for social implementation, it is desirable to adopt a standardized optical interface and use a commercially available single mode fiber (SMF).

In this paper, we design and fabricate an ultra-compact 1060-nm top-emitting SM VCSEL-based 106-Gb/s PAM4 8-channel CPO transceiver which has an interoperable optical interface in compliant with a standard 24-lane MT ferrule. To increase link budget, it is much preferable to minimize the optical coupling loss between the optical transceiver and SMFs. We newly design an optical coupling system using two glass microlens arrays, which realize a low coupling loss of <2dB. The CPO transceiver realizes a 2-km parallel-optical link with a good signal quality and low link energy to meet the OIF requirement for FEI.

### **2. 1060-nm SM VCSEL-based 53-Gbaud NRZ/PAM4 8-channel CPO transceiver**

Fig. 1 shows a schematic cross-sectional illustration for a 1060-nm SM top-emitting VCSEL. The n-type semiconductor distributed Bragg reflector (DBR), the active layer, and the p-type semiconductor DBR are grown on the GaAs substrate. The p-type DBR contains a high Al composition layer for oxide confinement. The oxide confinement layer is formed by high temperature wet oxidation. A metal-aperture is formed by a ring-shaped p-type electrode fabricated under the dielectric DBR, and it enables transverse resonance for single mode operation and bandwidth enhancement. A dielectric DBR consists of Ta2O5/SiO<sup>2</sup> pairs. Fig. 2 shows a measured lasing spectrum of the SM VCSEL at a bias current of 7 mA. A side-mode suppression ratio is as high as 40 dB. Fig. 3 shows a measured electro-optic (E/O) response of the SM VCSEL at a bias current of 7 mA as well. 3-dB bandwidth of the

![](_page_1_Figure_2.jpeg)

![](_page_1_Figure_3.jpeg)

![](_page_1_Figure_4.jpeg)

Fig. 1. Schematic cross-sectional illustration of the SM VCSEL

Fig. 2. Lasing spectrum of the SM VCSEL

Fig. 3. E/O response of the SM VCSEL

![](_page_1_Figure_8.jpeg)

![](_page_1_Figure_9.jpeg)

Fig. 4. Schematic cross-sectional illustration for the 1060-nm SM top-emitting VCSEL-based 53-Gbaud NRZ/PAM4 8-channel CPO transceiver.

Fig. 5. Coupling loss characteristics for the TX as a function of optical axis displacement in the horizontal axis.

E/O response is wider than 28 GHz. It is sufficiently wider than 26.5 GHz, which corresponds to the Nyquist frequency of the 53-Gbaud modulation format.

Fig. 4 shows a schematic cross-sectional illustration of the 1060-nm SM top-emitting VCSEL-based 53-Gbaud NRZ/PAM4 8-channel CPO transceiver. The CPO transceiver has an ultra-small footprint of 7.7 mm × 15.9 mm (i.e., 1.22 cm² footprint), which is the same with that of previously reported CPO transceivers [4, 5]. We precisely mounted two pairs of 4-channel SM VCSEL and PD arrays onto an organic substrate and connected those to two pairs of 4-channel VCSEL drivers (VDs) and 4-chanel trans-impedance amplifiers (TIAs), respectively [5]. 3-dB bandwidth of the PD array is >26.5 GHz. The 4-channel VCSEL and PD arrays have an aperture pitch of 250 m, which is compliant with an optical fiber allocation of a standard 24-lane MT ferrule. The CPO transceiver employs commercially available 53-Gbaud linear-drive VDs and TIAs, which do not have any retiming functionalities to prevent the increase of power consumption. A SM optical coupling system was newly designed with two microlens arrays, which are precisely attached to a precision-machined lens spacer. Fig. 5 shows measured and calculated coupling loss characteristics for the TX as a function of optical axis displacement in the horizontal axis. The calculated and the measured results are in good agreement, and it indicate that the optical coupling loss can be decreased to about 1 dB. Since the optical axis displacement can be controlled within 1.0 m in the assembly process, the optical coupling loss of <2 dB can be obtained.

#### **3. Evaluation of a parallel-optical link employing the CPO transceiver**

To build a parallel-optical link test system, we employed a dedicated 50-Gbaud testing station, which exhibits 3-dB bandwidth of >25 GHz [6]. Fig. 6 shows a block diagram of the test system where the CPO transceiver is attached to the testing station through an electrical pluggable interface. Commercially available 980-nm SMFs were connected to the CPO transceiver to build a loop-back parallel-optical link. The 980-nm SMFs used in this experiment have been widely used for 980-nm pump lasers and its cut-off wavelength is specified below 970 nm. The CPO transceiver was operated with a bit stream of 53.125-Gb/s NRZ 2<sup>13</sup> -1 PRBS or 106.25-Gb/s PAM4 2 13 -1 PRBSQ. Fig. 7 shows optical eye diagrams when the TX was operated with a 53.125-Gb/s NRZ signal for back-to-back and an SMF link of 2 km, respectively. Even transmitting an optical signal over an SMF of 2 km, the optical eye diagram is sufficiently opening. The eye diagram of a 2-km SMF link has a slight amount of noise due to the low received optical power caused by a transmission loss of the SMF. The transmission loss of the 2-km SMF was approximately 3.2 dB with a wavelength of 1060 nm. Next, we performed 106.25-Gb/s PAM4 optical link tests. Fig. 8 shows optical eye diagrams when the TX was operated with a 106.25-Gb/s PAM4 signal for back-to-back and an SMF link of 2 km, respectively. Both optical eye diagrams are filtered by a 9-tap linear-equalizer at the digital communication analyzer (DCA). The optical eye diagram for the 2-km SMF link is opening sufficiently. TDECQ values were 1.04 dB and 1.99 dB for back-to-back and 2-km SMF link, respectively. Both TDECQ values were sufficiently lower than 3.4 dB specified in IEEE802.3df [7]. All 8 channels were operated with an individual 106.25- Gb/s PAM4 signal. The 2-km loop-back SMF link measures a BER of 1.9 10-6 , which is lower than the KP4-FEC threshold. The total power consumption of the CPO transceiver is as low as 3.8 W, which corresponds to link energy of 4.5 pJ/bit.

![](_page_2_Picture_3.jpeg)

Fig. 6. Block diagram of the optical link test system. Fig. 8. Optical eye diagrams when the TX was operated a 106.25-Gb/s PAM4 signal. (a) back-to-back. (b) 2-km SMF link.

## **4. Conclusion**

We demonstrated a 1060-nm SM VCSEL-based 53-Gbaud NRZ/PAM4 8-channel CPO transceiver which enables a 2-km transmission distance. A standard 24-lane MT-ferrule is employed as an optical interface ensuring interoperability with other optical transceivers. A 4-channel top-emitting SM VCSEL array has a 3-dB bandwidth of 28 GHz. An SM optical coupling system employing two microlens arrays achieves an optical coupling loss of <2 dB. Even transmitting an optical signal of 53.125-Gb/s NRZ or 106.25-Gb/s PAM4 over 2 km, the optical eye diagrams were sufficiently opened. The measured TDECQ value was 1.99 dB for a 2-km SMF link, which was sufficiently lower than the specified value of 3.4 dB. The optical link performed a BER of less than the KP4-FEC threshold and low link energy of 4.5 pJ/bit under a 106.25-Gb/s PAM4 signal operation.

#### **5. References**

- [1]. Optical Internetworking Forum, "System Vendor Requirements Document for Energy Efficient Interfaces," OIF-EEI-Requirements-RD-01.0, Mar. 2024. [Online] Available: https://www.oiforum.com/wp-content/uploads/OIF-EEI-Requirements-RD-01.0.pdf
- [2]. Y. Iwama, T. Yagisawa, S. Ide, K. Takeda, C. Ge, X. Gu, and F. Koyama, "SM-TCC-VCSEL-based 800 Gbps Linear Drive Pluggable Transceiver," OFC2024, Th4C.7, Mar. 2024.
- [3]. K. Takeda, Y. Iwane, T. Minamiru, T. Hamada, K. Mizuno, K. Suzuki, H. Fukunaga, A. Murakami, H. Nakayama, C. Ge, X. Gu., and F. Koyama, "100Gbps/ch 1060nm Single-mode Metal Aperture VCSEL Array at 85 °C Operation," ISLC2024, WC1, Oct. 2024.
- [4]. W. Yoshida, T. Azuma, L. Dong, K. Nagashima, S. Yoneyama, K. Nishizaki, J. Miike, M. Miyoshi, X. Gu, S. Ide, H. Nasu, and F. Koyama, "An Ultra-Compact 50-Gbaud × 16-Channel CPO Transceiver employing a 1060-nm Single-Mode VCSEL array and Multicore Fibres," ECOC2025, Tu. 01. 03. 1, Sept. 2025.
- [5]. W. Yoshida, K. Nagashima, K. Nishizaki, S. Yoneyama, and H. Nasu, "An Ultra-Compact 8-Channel Linear-Drive VCSEL-Based CPO Transceiver for Networks and AI/ML Applications in a Data Center," ECTC2025, 15-2, May 2025.
- [6]. K. Nishizaki, K. Nagashima. W. Yoshida, Sho Yoneyama, and H. Nasu, "Over 25-GHz Bandwidth Testing Station Using a 0.3-mm-Pitch LGA Interface for a 50-Gbaud × 16-Channel CPO Transceiver," ICSJ2024, 01-03, Nov. 2024.
- [7]. IEEE802.3df, [online] Available: https://www.ieee802.org/3/df/