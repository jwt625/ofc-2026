#### **Quasi-wavelength-agnostic photonic coupler using 3Dnanoprinting**

**Huiyu Huang<sup>1</sup> , Zhitian Shi<sup>1</sup> , Chunhui Yao1,2 , Richard Penty<sup>1</sup> , Qixiang Cheng1,2 \***

*<sup>1</sup>Electrical Engineering Division, Department of Engineering, University of Cambridge, Cambridge, United Kingdom, CB3 0FA, <sup>2</sup>GlitterinTech Ltd, China \* qc223@cam.ac.uk*

**Abstract:** We report a 3D-nanoprinted coupler with elliptical reflectors, achieving a 1 dB bandwidth across 800 nm. Aberration suppression and mode-size conversion enable quasiwavelength-agnostic, ultra-broadband coupling, validated with 980HP and UHNA1 fibers for scalable photonic integration. © 2024 The Author(s)

#### **1. Introduction**

Photonic integrated circuits (PICs) underpin modern technologies in data communications, optical computing, and optical sensing [1–3]. While standardized communication technologies typically operate within fixed frequency bands, a growing number of applications demand operations across broader spectral ranges, including advanced sensing, quantum photonics, biomedical imaging, etc. This spectral breadth is particularly vital given that molecular and material responses are often distributed across diverse wavelength bands. Whilst chip-scale sensors have evolved to operate over a few hundred nanometre spectral range [4], traditional in-plane and out-of-plane couplers typically suffer from restricted bandwidths, posing significant challenges in packaging, alignment, and spectral calibration, especially for the applications mentioned above. The disparities between application-driven bandwidth requirements and existing coupler capabilities are illustrated in Fig. 1(a).

In this work, we present a 3D-nanoprinted photonic coupler that is engineered to massively broaden the coupling bandwidth, approaching a wavelength-agnostic operation. The device, schematically illustrated in Fig. 1 (b), features a pair of ellipsoidal reflectors sharing a common focal point. Owing to its refined elliptical geometry that suppresses comatic aberration to a great extent, the coupler delivers a highly collimated output with minimal insertion loss across a broad spectral range. Simulations predict a record-high 1dB operational bandwidth exceeding 800 nm, and experimental results validate the efficient coupling over the 800 nm wavelength span with a loss as low as 1 dB.

#### **2. Design and Simulations**

The coupler is a co-designed opto-mechanical structure comprising two main components: an optical mode size converter for adjusting the mode field diameter (MFD), and a mechanical plug-in funnel that facilitates precise alignment. The optical converter consists of two ellipsoidal reflectors of differing sizes that share a common focal point. Light emitted from the input optical fibre is directed into the first reflector, undergoes two reflections at the polymer–air interfaces, and is subsequently guided into the on-chip waveguide. Due to the divergence of the unconfined optical beam emitted by the optical fibre, comatic aberration can arise as the light propagates through the polymer reflector. Therefore, effective aberration control is essential for minimizing optical loss, especially across a broad spectral range. In this design, the use of ellipsoidal reflectors effectively suppresses comatic aberration,

![](_page_0_Figure_11.jpeg)

Fig. 1 (a) Bandwidth requirements of advanced optical sensing applications compared to the limited range of existing photonic circuit couplers. (b) Schematic views of the elliptical photonics coupler.

mitigating losses due to misalignment and mode mismatch, thereby enabling nearly wavelength-agnostic performance. By approximating the incident beam as a point source located at one focal point, all rays are redirected through the second focal point, producing a collimated output at the symmetric position. Moreover, adjusting the dimensions of the reflector provides precise control of the output mode size. Although the elliptical geometry can be approximately predicted through theoretical modelling, adjustments are necessary to account for the limitations of the point-source approximation. To optimize and finalize the optical structure, coupling efficiency is evaluated using the Lumerical finite-difference time-domain (FDTD) solver under perfectly matched layer (PML) boundary conditions. Initially, a baseline reflector geometry is simulated to identify the minimum coupling loss under a 1:1 mode size ratio. Based on this, further optimization is conducted for mode size conversion. Fig. 2 (c)-(e) depict the optimal elliptical design over a large bandwidth, with a focal length of 60 μm along the x-direction, 55 μm along the y-direction, and an x-axis intercept of 80 μm, resulting in a coupling loss below 1dB for 980HP and UHNA1 fibre coupling. For further mode size conversion, the geometry of the elliptical reflector can be fine tuned for future applications. The plug-in funnel is co-designed with the optical component to ensure precise alignment between the fibre and the reflector. The funnel is designed with external dimensions of 500 μm × 300 μm × 300 μm and is truncated by a circular cone with a top diameter of 130 μm and a bottom diameter of 250 μm.

#### **3. Fabrication**

The coupler was fabricated using a commercial direct laser writing system (Nanoscribe Professional GT2) equipped with a 25× objective lens and IP-n162 resin, which has the highest refractive index (~1.62 after polymerization) among the IP series provided by Nanoscribe. This combination of resin and objective lens enables rapid fabrication while maintaining high resolution. The printing file was manually modified to enable a one-step fabrication process. A coarse printing recipe which combines larger slicing and hatching parameters was applied to the mechanical section, where surface quality was not a primary concern. In contrast, a fine printing recipe was employed for the optical section to achieve smooth surfaces and minimize optical losses. The entire printing process took approximately 30 minutes. After polymerization, the structure was developed in propylene glycol monomethyl ether acetate (PGMEA) for 15 minutes to remove unpolymerized resin, followed by a 5-minute rinse in isopropanol (IPA) to remove residual PGMEA. Finally, the structure underwent UV curing to improve its mechanical stability. The schematic and corresponding images of the fabricated devices are shown in Fig. 3(a)–(c).

#### **3. Result and Discussion**

We experimentally validate the performance of the coupler using two types of optical fibres: 980HP and UHNA1

![](_page_1_Figure_7.jpeg)

Fig. 2 Schematic view of (a) on-chip printed elliptical reflectors, (b) on-chip printed funnel to secure stripped optical fibres, and (c)-(e) simulation results demonstrating fibre-to-fibre coupling losses across different wavelengths of 800 nm, 1200 nm and 1600 nm, respectively.

from Thorlabs. The test structures were fabricated on an ITO-coated silica substrate and mounted onto a highprecision optical stage (Thorlabs MAX313D) for characterization. Once secured on the stage, the optical fibres were inserted into the funnel; the entrance aperture, being twice the fibre diameter, enabled straightforward, alignmentfree insertion. The coupling efficiency was characterized across a wavelength range of 840–1670 nm. Multiple superluminescent diodes (SLDs) were employed as light sources, including Thorlabs 1050S, 1021S, 1550S, and DenseLight DL-CS43H4A-FP. Measured coupling losses across various spectral windows from 840–1670 nm were as low as 1 dB, as shown in Fig. 3(d). The coupling performance remained consistently stable over the full spectral span, demonstrating a record-high bandwidth with quasi-wavelength-agnostic character over 800nm. The slight variations in coupling loss are primarily attributed to fabrication imperfections, such as surface roughness and minor reflector misalignment, which could be mitigated through further refinement of the 3D-printing process.

![](_page_2_Figure_3.jpeg)

Fig. 3 SEM images of the (a) 3D-printed free-standing fibre-to-fibre coupler, scale bar 200 μm, (b) detailed view of 3D-printed elliptical reflectors, scale bar 50 μm, (c) on-chip printed photonic coupler, scale bar 150 μm, (d) ultra-broadband fibre-to-fibre coupling efficiency.

#### **4. Conclusion**

We present a 3D-nanoprinted quasi-wavelength-agnostic photonic coupler for ultra-broadband applications. The core optical structure comprises a pair of ellipsoidal reflectors that share a common focal point. Owing to its aberration-free geometry, this reflector configuration enables efficient mode size conversion with minimal insertion loss across an extended spectral range. The geometry of the elliptical reflectors is optimized by Lumerical FDTD under PML boundary condition. Simulation and experimental validation using optical fibres with differing MFDs demonstrates a coupling loss as low as 1 dB over an 800 nm range, which approaches wavelength-agnostic performance. With further improvements in fabrication techniques, this coupler can be monolithically integrated into photonic integrated circuit (PIC) platforms, offering a scalable and robust solution for ultra-broadband optical applications.

#### **5. References**

- [1] Chengli Wang, Dengyang Fang, Junyin Zhang, Alexander Kotz, Grigory Lihachev, Mikhail Churaev, Zihan Li, Adrian Schwarzenberger, Xin Ou, Christian Koos, and Tobias J. Kippenberg, "Ultrabroadband thin-film lithium tantalate modulator for high-speed communications," Optica 11, 1614-1620 (2024), https://doi.org/10.1364/OPTICA.537730
- [2] Wang, Y., Chen, M., Yao, C. et al. Asymmetrical estimator for training encapsulated deep photonic neural networks. Nat Commun 16, 2143 (2025). https://doi.org/10.1038/s41467-025-57459-5
- [3] Yao, C., Xu, K., Zhang, W. et al. Integrated reconstructive spectrometer with programmable photonic circuits. Nat Commun 14, 6376 (2023). https://doi.org/10.1038/s41467-023-42197-3
- [4] Yao, C., Zhang, W., Bao, P., Ma, J., Zhuo, W., Chen, M., Shi, Z., Zhou, J., Ye, Y., Ming, L., Yan, T., Penty, R., & Cheng, Q. (2024). Chip-scale sensor for spectroscopic metrology. https://doi.org/10.1038/s41467-024-54708-x
- [5] Yang, K., Zong, S., Zhang, Y., Qian, Z., Liu, Y., Zhu, K., Li, L., Li, N., Wang, Z., & Cui, Y. (2020). Array-Assisted SERS Microfluidic Chips for High-ly Sensitive and Multiplex Gas Sensing. ACS Ap-plied Materials and Interfaces, 12(1), 1395–1403. https://doi.org/10.1021/acsami.9b19358
- [6] Pahlevaninezhad, H., Khorasaninejad, M., Huang, Y. W., Shi, Z., Hariri, L. P., Adams, D. C., Ding, V., Zhu, A., Qiu, C. W., Capasso, F., & Suter, M. J. (2018). Nano-optic endoscope for high-resolution optical coherence tomography in vivo. Nature Photonics, 12(9), 540–547. https://doi.org/10.1038/s41566-018-0224-2

# **Quasi-wavelength-agnostic photonic coupler using 3D-nanoprinting**

**Huiyu Huang¹, Zhitian Shi¹, Chunhui Yao¹˒², Jian Chen² , Richard Penty¹, Qixiang Cheng¹˒²\***

¹ University of Cambridge, Cambridge, United Kingdom · ² GlitterinTech Ltd, China · \* Corresponding author: qc223@cam.ac.uk *A generic 3D-nanoprinted coupler that combines aberration suppression, mode-size conversion and passive alignment for ultra-broadband photonic packaging.*

**1 dB** minimum measured coupling loss

**> 800 nm** 1 dB operational bandwidth **840–1670 nm**

experimental characterisation window

**980HP + UHNA1**

validated with mismatched fibre MFDs

#### **Motivation & challenge**

- Advanced optical sensing, quantum photonics and biomedical imaging demand operation far beyond narrow telecom windows.
- Conventional in-plane and out-of-plane couplers typically offer limited usable bandwidth and can require tighter alignment and recalibration.
- The objective here is a generic coupler that remains low loss while becoming far less wavelength sensitive.
- A 3D-nanoprinted approach enables optical and mechanical functions to be co-designed in a single printed structure.

#### **Why it matters**

A broadband, alignment-tolerant interface is critical for scalable heterogeneous photonic integration.

#### **Operating principle**

- The optical converter uses two ellipsoidal reflectors that share a common focal point.
- Elliptical geometry strongly suppresses comatic aberration, improving beam collimation across a broad spectral range.
- The reflector dimensions also provide a degree of mode-size conversion between dissimilar input and output modes.
- A co-printed plug-in funnel enables straightforward fibre insertion and passive alignment to the optical section.

#### **Design philosophy**

Co-design the optical path and the mechanical interface so the coupler is both broadband and easy to assemble.

#### **Experimental setup**

- Test structures were fabricated on an ITO-coated silica substrate and mounted on a high-precision Thorlabs MAX313D stage.
- The funnel entrance is roughly twice the fibre diameter, enabling alignment-free insertion of the stripped fibre.
- Characterisation covered 840–1670 nm using multiple superluminescent diode sources.
- Two different fibres from Thorlabs, 980HP and UHNA1, were used to validate the mode-sizeconversion concept.

#### **Measurement focus**

Demonstrate broadband low-loss coupling rather than a narrow optimum at a single wavelength.

## **Concept, co-design and simulation**

![](_page_3_Picture_35.jpeg)

![](_page_3_Picture_36.jpeg)

![](_page_3_Figure_37.jpeg)

![](_page_3_Figure_38.jpeg)

**Representative optimum reported in the paper: x-focus = 60 μm, y-focus = 55 μm, x-axis intercept = 80 μm.** FDTD optimisation under PML boundaries identifies an elliptical geometry that preserves low loss over a wide spectral span.

#### **Measured validation**

![](_page_3_Figure_41.jpeg)

*SEM images of the printed structures and detailed reflector region. Scale bars, 200 µm, 50 µm, 150 µm.* 

![](_page_3_Figure_43.jpeg)

*Measured fibre-to-fibre loss stays close to 1 dB across an >800 nm span.*

- Measured coupling losses across multiple spectral windows remain low and stable over an 800 nm span.
- The result approaches quasi-wavelength-agnostic operation while accommodating fibres with different MFDs.
- Residual variation is mainly attributed to fabrication roughness and minor reflector misalignment.

## **Key contributions**

![](_page_3_Figure_49.jpeg)

*The application bandwidth demand clearly extends beyond conventional coupler windows.*

- **1** Ultra-broadband optical coupling approaching wavelength-agnostic behaviour.
- **2** Single printed structure integrates optical routing, mode conversion and mechanical alignment.
- **3** A generic route towards scalable photonic packaging across dissimilar material platforms.

## **Take-home message**

Ellipsoidal free-form reflectors provide a practical way to extend coupling bandwidth while preserving a compact, manufacturable interface.

## **Fabrication details**

- Printed on a Nanoscribe Professional GT2 using a 25× objective and IP-n162 resin (n ≈ 1.62 after polymerisation).
- A coarse recipe was used for the mechanical section; a fine recipe was applied to the optical surfaces to minimise loss.
- Post-processing: PGMEA 15 min, IPA 5 min, then UV curing to improve mechanical stability.
- The entire fabrication process took approximately 30 minutes.

## **Key geometry and process parameters**

| x-focus                               | 60 μm              |
|---------------------------------------|--------------------|
| y-focus                               | 55 μm              |
| x-axis intercept                      | 80 μm              |
| Funnel size                           | 500 × 300 × 300 μm |
| Cone diameter                         | 130 → 250 μm       |
| Characterisation<br>range             | 840–1670 nm        |
| Representative fibres 980HP and UHNA1 |                    |

Manufacturing advantage: optical and mechanical features are produced in one aligned print step.

## **Conclusion & outlook**

- A quasi-wavelength-agnostic 3D-nanoprinted coupler has been demonstrated for ultra-broadband photonic applications.
- The ellipsoidal-reflector geometry delivers aberration suppression, mode-size conversion and low insertion loss across a very wide wavelength range.
- With improved print fidelity, the approach is well suited to monolithic integration with PIC platforms and heterogeneous chiplet-style packaging.

## **Acknowledgments**

Funded by UKRI–EPSRC QUDOS (EP/T028475/1) and the EU Horizon Europe project PUNCH (101070560).

## **Contact**

Qixiang Cheng qc223@cam.ac.uk University of Cambridge Huiyu Huang hh560@cam.ac.uk University of Cambridge

## **References**