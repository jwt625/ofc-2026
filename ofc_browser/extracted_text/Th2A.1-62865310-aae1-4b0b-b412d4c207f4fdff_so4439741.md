# **Hybrid Integration of O-band InP SOA array and PLC using PLC/SiN Spot-Size Converter**

#### **M.Rombouts, <sup>1</sup> A.K. Tesfa, 1\* and N. Calabretta<sup>1</sup>**

*<sup>1</sup> Eindhoven University of Technology and Eindhoven Hendrik Casimir Institute, PO Box 513, 5600 MB Eindhoven, The Netherlands \*[a.k.tesfa@tue.nl](mailto:a.k.tesfa@tue.nl)*

**Abstract:** We design,fabricate and demonstrate O-bandhybrid integration of PLC/SiN spotsize converter (SSC) and InP U-shaped SOA array PICs. The results show broadband operation and efficient coupling, achieving ~1.5 dB loss per facet.

#### **1. Introduction**

Hybrid photonic integration combining an efficient platform for passive devices and active on-chip amplifiers/switches enables high-performance and large-scale photonic integrated circuits (PICs). As an example, shown in Fi[g.1a](#page-0-0), a PIC wavelength selective switch (WSS) requires high-performance passive WDM Multiplexer/Demultiplexer and optical switches. Silica Planar Lightwave Circuit (PLC) offers low loss, polarization-independent arrayed waveguide grating (AWG) as Mux/Demux as well as very low coupling loss to single-mode fiber (SMF), while InP-based SOAs provide efficient amplification and switching. However, achieving efficient and broadband optical coupling between those passive and active platforms remains a major challenge.

 The primary challenge lies in the significant mode-size mismatch between waveguides across different platforms. For example, direct butt coupling of InP waveguides to SMFs typically results in losses exceeding 10 dB [\[1\]](#page-2-0). Various techniques have been investigated to solve this problem. Grating couplers [\[2\]](#page-2-1), [\[3\]](#page-2-2) support waferscale testing but are limited by narrow bandwidth and strong polarization sensitivity, making them less suitable for WDM systems. Additionally, their vertical coupling nature makes them inconvenient for chip-to-chip coupling. Edge (or butt) coupling offers low insertion loss, less polarization dependence, and broad bandwidth [\[4\]](#page-2-3), which makes it better suited for WDM applications and chip-level integration.

 In this work, we investigate and assess O-band edge-coupled hybrid integration of InP SOA arrays with a PLC platform using PLC-silicon nitride (SiN) spot size converter (SSC). The SiN cointegrated on the PLC is chosen for its low loss and adaptable mode profile, enabling efficient coupling to SOA waveguides and large-mode silica devices.

![](_page_0_Figure_10.jpeg)

<span id="page-0-0"></span>Fig 1. (a) 1×2 WSS schematic. (b) Fabricated PLC/SiN SSC chip. (c) Fabricated SOA chip. (d) Hybrid PLC/SiN SSC–SOA alignment layout. F: Fiber array, WG: waveguide, MFD: mode field diameter; MFD numbers indicate different WG width of the SSC

# **2. Simulation and Design Analysis**

Fig. 1(b-d) shows the PLC co-integrated with SiN and the SiN SSC to enable low loss coupling between silica waveguides and InP Multi-quantum Well (MQW) SOA arrays. On the left side, the silica PLC is coupled to SMFs, while on the SiN SSC side it couples light into SOA array with efficient mode matching. As the mature PLC to SMF coupling loss is very low, the overall performance is mainly determined by the edge coupling between the SiN SSC and SOA waveguides. We use the Lumerical 3D FDTD solver to design and simulate mode field diameter (MFD) and evaluate the coupling efficiency.

 The SOA waveguide features a ridge structure with a 2 µm ridge width and a 0.4 µm core thickness. The SiN SSC has a fixed thickness of 0.2 µm, and its width is varied from 1.6 to 3.0 µm to identify the waveguide width that maximizes coupling efficiency.

 Fig. [2a](#page-1-0) shows the simulated MFDs for SiN SSC, at λ=1310 nm, where MFD is defined as the diameter at which intensity drops to 1/ <sup>2</sup> of its peak. The horizontal MFDs (TEy and TMy) increase with waveguide width, while vertical MFDs (TEzand TMz) remain constant due to the fixed core thickness. For the SOA with fixed dimensions, the horizontal and vertical MFDs are 2.74 × 0.68 µm for the TE mode and 2.43 x 0.77 µm for the TM mode, respectively. Fig. [2c](#page-1-0) shows the absolute value of the horizontal MFD difference between the SiN SSC and SOA, representing the mode mismatch between them that affects coupling efficiency.

 The power coupling coefficient is calculated using the overlap integral [5], where 1and 2denote the electric field distributions of the SSC and SOA waveguides at the coupling interface. Optimal alignment and better mode matching enhance the overlap integral thereby maximizing and minimizing the power coupling loss, which is given by Loss (dB) = −10 log10().

$$\eta = \frac{|\iint E_1(x, y)E_2(x, y) \ dA|^2}{(\iint |E_1(x, y)|^2 \ dA)(\iint |E_2(x, y)|^2 \ dA)}$$
(1)

 Fig. 2c presents the simulated power coupling efficiency at λ = 1310 nm, expressed in dB. The S-parameters (|S21|² and |S12|²), equivalent to η, represent bidirectional coupling between the SSC and SOA in dB. The corresponding power loss is calculated as Loss (dB) = –|S|². TE mode coupling improves with increasing SSC width due to reduced MFD mismatch, as shown in Fig. 2b (blue line), where |∆TEy| decreases monotonically, indicating that higher width results in lower loss. In contrast, the coupling of the TM mode remains relatively uniform (optimal at 2.4 µm), consistent with the small variation in |∆TMy| as clearly shown in Fig. [2b](#page-1-0) (red line). Since vertical MFDs remain constant across all SSC widths, they don't contribute to coupling variation and are therefore omitted from Fig. [2b](#page-1-0) for clarity. Fig. 2d illustrates the broadband performance of the SSC (plotted for a waveguide width of 2.6 µm). The simulation shows that the coupling remains stable over a 100 nm wavelength range, with a loss variation of less than 0.1 dB, demonstrating the SSC's suitability for broadband operation.

![](_page_1_Figure_6.jpeg)

<span id="page-1-0"></span>Fig.2. Simulation results: (a) SiN SSC MFD. (b) Horizontal MFD difference between SSC and SOA in absolute value that indicates their mode mismatch. (c) power coupling between SSC and SOA. (d) Bandwidth for the entire O-band coupling.

 To experimentally investigate the impact of different MFD variations, the PLC-SiN SSC and InP SOA array PICs have been fabricated as shown in Fig.1(b-d). The PLC-SiN SSC includes 26 waveguides, 16 of which are pigtailed to SMFs (see Fig. 3c) on the left side and grouped into eight MFD variants (MFD01–MFD08), where each variant corresponds to a distinct waveguide width from 1.6 to 3.0 µm in 0.2 µm increments (e.g., MFD01 = 1.6 µm, MFD02 = 1.8 µm, ... MFD08 = 3.0 µm) on the InP SOA side. This pattern is mirrored (MFD08–MFD01), ensuring symmetric coupling: light entering, propagating through the U-shaped SOA, and exiting the opposite SSC experiences identical waveguides at both facets (see Fig.1d). As we simulate, all SSC waveguides share a uniform 0.2 µm core thickness. Each SOA consists of a 0.4 µm-thick core, 2 µm ridge width, and 900 µm-long active region, forming 12 active devices and 24 coupling facets. The SSC and SOA active elements are both spaced at 250 µm pitch to ensure alignment, while the SOA waveguides are spaced at 125 µm except at the center, thereby their U-shaped configuration matches the SSC layout.

### **3. Experimental Results**

First, we characterize the MFDs of all SSC and SOA waveguides using the setup illustrated in Fig. [3a](#page-2-4). Light from a tunable laser source (TLS) is coupled into the PIC (PLC-SiN SSC and SOA array) and collimated by a lens (1= 2.8 mm). A 50/50 beam splitter (BS) directs the beam along two paths: one focused by a second lens (<sup>2</sup> = 75 mm) and imaged by a camera for mode analysis, and the other passed through a polarizer into a power meter allowing both TE and TM measurements. The measured SSC MFDs for all variants are shown in Fig. [3d](#page-2-4) and follow simulation trends, with horizontal MFDs increasing with waveguide width and vertical MFDs remaining constant. SOA MFDs, measured across all 24 facets using ASE noise (only TE modes are measured as MQW SOAs do not support TM), has horizontal MFDs ranging from 2.4-2.7 µm and vertical MFDs from 2.2–2.5 µm, with an average of 2.52 x 2.31 µm. These variations are attributed to fabrication nonuniformities despite nominally identical waveguides. Fig. [3e](#page-2-4) shows the MFD difference between each SSC variant and the SOA (average) in absolute value. Overall, horizontal MFDs are aligned with simulation, though noticeable variations appear specially at smaller widths where the fabricated modes expand slightly more than the ideal. However, the vertical MFDs appear clearly larger than the simulated values. This happens due to stronger beam divergence caused by

the small waveguide thickness and the limited numerical aperture (NA) of the lens, which is unable to fully capture the vertical field profile besides the fabrication effect.

 Second, the coupling efficiency between the PLC-SiN SSC and SOAs is measured using the setup shown in Fig. [3\(](#page-2-4)b, c), where SOAs are used as photodetectors, reversed biased with V = −0.5 V. First, we use lensed fiber as a reference to calibrate the SOA at different input optical power. The light from TLS at λ = 1310 nm is coupled into the SOA via a lensed fiber. The input optical power is swept from –15 to 5 dBm, and the resulting photocurrent is measured using a source meter (SM) at each input power. Fig. [3f](#page-2-4) (blue line) reports the measured photocurrent (Ref) on a logarithmic scale and fitted to a linear function = + , where y is Ref, is the slope, is the input power and b is the y-intercept that determines the coupling performance. Then the lensed fiber is replaced with the PLC-SiN SSC edge coupled to the SOA using high precision 6-axis stages as shown in Fig. 3b schematic and 3c lab setup.

![](_page_2_Figure_4.jpeg)

<span id="page-2-4"></span>Fig.3. Experimental setups and results: (a) MFD measurement setup. (b) PLC/SiN SSC–SOA coupling schematic setup. (c) PLC/SiN SSC - SOA lab setup: PCB-electrical printed circuit board to bias SOAs. (d) Measured SSC MFD. (e) SSC and SOA MFD difference in absolute value. (f) Photocurrent in log scale for reference and SSC. (g) coupling relative to lensed fiber.

 The measured photocurrent (SSC) is reported in Fig. [3f](#page-2-4) (orange line). The coupling difference is calculated using the relation, ∆ () = 10 − )/. Fig. [3g](#page-2-4) presents the results as a box-and-whisker plot, showing the minimum, maximum, and average values for each MFD variant. Each data point is averaged from four measurements per MFD variant, taken by sliding across two different SOAs. The SSC shows an improvement of up to 0.5 dB relative to lensed fiber, corresponding to a coupling loss of ∼2.0 dB per facet (given a reference loss of ∼2.5 dB for the lensed fiber–SOA interface). After accounting for the ∼0.5 dB PLC-SiN SSC to the SMF packaging loss, the intrinsic PLC-SiN SSC to SOA coupling loss up to ∼1.5 dB per facet is achieved.

Although simulations indicate a slight improvement in coupling with increasing SSC width, the measured results show that MFD variants 7 and 8 (2.8 and 3.0 µm widths) perform slightly worse on average. However, it is consistent with the measured MFD mismatch shown in Fig. [3e](#page-2-4). While the overall performance differences across all variants are not significant, SSC waveguides widths up to 2.6 µm can be chosen for slightly improved coupling to SOA.

#### **4. Conclusion**

We demonstrated an O-band hybrid PLC–InP integration using a PLC-SiN SSC with low coupling loss ~1.5 dB and over 100 nm broadband operation, confirming its suitability for high channel count and scalable photonic integration. The hybrid PLC-SiN SSC-InP SOA platform enables efficient integration between passive silica and active InP components, supporting next-generation PICs for WDM transmission and switching systems.

## **Acknowledgement**

The work is partially supported by the Dutch National Growth Fund for Photonics 'PhotonDelta' and by the EU research and innovation program ADOPTION grant agreement 101070178.

#### **References**

- <span id="page-2-0"></span>[1] B.-H. V. Borges *et al.*, "Coupling from a single mode fiber to a iii—v thin-film waveguide via monolithic integration of a polymeric optical waveguide," *J. The Frankl. Institute-engineering Appl. Math.*, 1998.
- <span id="page-2-1"></span>[2] L. Chen *et al.*, "Efficient membrane grating couplers on inp," *IEEE Photonics Technol. Lett.*, 2010.
- <span id="page-2-2"></span>[3] F. Van Laere *et al.*, "Compact and highly efficient grating couplers between optical fiber and nanophotonic waveguides," *J.L.T.*, 2007.
- <span id="page-2-3"></span>[4] M. Papes *et al.*, "Fiber-chip edge coupler with large mode size for silicon photonic wire waveguides," *Opt. Express*, 2016.
- [5] K. Okamoto, "Fundamentals of Optical Waveguides," Tech. Rep., 2022.