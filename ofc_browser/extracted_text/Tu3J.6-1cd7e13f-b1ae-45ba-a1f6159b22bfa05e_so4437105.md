# **400G per lane Differential Drive Electroabsorption Modulated Lasers (EML) with 99GHz 6-dB EO BW for next generation 3.2T IM-DD Applications**

**Prashanth Bhasker, Sumeeta Arora, Hui Fu, Chris Fuchs, Ayman Kanan, John E. Johnson**

*Broadcom Inc., 9999 Hamilton Blvd., Breinigsville, PA 18031 USA \*prashanth.bhasker@broadcom.com*

**Abstract:** We report an O-band differential-drive EML achieving 99GHz 6-dB bandwidth and 3.8dB ER at 55 °C. Device delivers 6.5dBm modulated power and open 320 Gbits/s PAM-4 and 413 Gbits/s PAM-6 eyes suitable for 3.2T applications. © 2026 The Author(s)

#### **1. Introduction**

Single ended (SE) 200G per lane EMLs [1-3] have shown excellent performance in terms of electro-optic (EO) bandwidth (BW), compact size, low peak to peak swing and output power. Beyond 200G per lane, several groups [4- 8] have demonstrated SE EMLs with EO BW greater than 75GHz. However, at higher baud rates, driver swing and RF cross talk could be an issue with SE EMLs, affecting the overall bit error rate (BER). Switching to a differentialdrive (DD) EML can reduce the driver swing requirement along with reduced cross talk and common-mode noise suppression. There have been a few [9-11] DD EML demonstrations for 200G and 400G applications. Published work [10] on DD EML support ~56GHz 3-dB BW, only suitable for 200G application.

In this paper, we report an ultra-high-speed DD EML based on Indium Phosphide material system with 3-dB and 6-dB EO BW of 83GHz and 99GHz respectively at 55C using a lumped electrode design and a 90 ohms differential RF termination, suitable for next generation 400G per lane 3.2T applications. Back-to-back (BTB) PAM-4 (360 Gbits/s) and PAM-6 (413 Gbits/s) eyes are demonstrated at 1314nm with extinction ratio (ER) greater than 3.3dB and using 1.5Vppd (0.75Vpp SE) at 160GBd. This represents nearly 40% lower driver swing requirement than the SE EMLs (1.2Vpp). DC facet power with modulator at 0V exceeds 11.5 dBm at 55C, 120mA laser bias along with 6.5 dBm output power under modulation.

### **2. Device description**

The DD EML consists of a capped mesa buried heterostructure (CMBH) waveguide in the DFB integrated with a shallow ridge waveguide in the modulator, similar to our 200G EML [1]. The DD EML was fabricated on a semiinsulating Indium phosphide (InP) substrate to achieve cathode isolation between the DFB and the modulator. Measured anode and cathode isolation was greater than 10KΩ and was sufficient for high-speed measurements. Modulator length and epitaxial design were carefully optimized to have lower capacitance and higher extinction ratio. Measured DC ER was greater than 30 dB (Fig. 2) at 55C and 100mA laser bias.

![](_page_0_Figure_11.jpeg)

![](_page_0_Figure_12.jpeg)

![](_page_0_Figure_13.jpeg)

Figure 1: 3D Schematic of the high-speed DD EML Figure 2: DC modulator extinction Curve at 55C, 100mA

The DD EML chip was bonded to an Aluminum Nitride carrier (COC). Wire bonds were used to connect the modulator pads with the trace on the COC. RF signals were terminated with a 90ohms differential resistance.

#### **3. Results**

An L-I sweep at 55C with the modulator at 0V is shown in Fig 3. The L-I sweep shows excellent output power with minimum roll off up to 150mA. At a typical use condition of 55C, 120mA, measured broad area power exceeds 11.5dBm. A plot of the wavelength spectra is shown in Fig 4. The peak wavelength is measured to be around 1314nm with side mode suppression ratio exceeding 45 dB at 55C, 100mA.

Small signal measurements were performed using a 4-port 110GHz VNA and a high-speed photo detector. The CoC was mounted on a temperature-controlled fixture. The modulator section was probed using a 110GHz GSGSG probe which had been calibrated out using a calibration substrate. Modulator DC bias was set around the inflection voltage and applied through the VNA bias tees. EO measurements at 55C, 130mA are shown in Fig 5. Blue lines represent the measured mixed mode SSD21 (solid) and SDD11 (dotted). 3-dB and 6-dB EO BW are close to 83GHz and 99GHz respectively with SDD11 less than -5dB up to 110 GHz. SSD21 drop across high frequencies is likely related to the input wire bond inductance between the modulator pad and the COC trace as shown by the simulated SSD21 for both the wire bond (solid orange) and flip chip versions (solid green). Based on simulations with a similar chip design, switching to a flip chip version can extend the 3-dB BW beyond 100GHz.

![](_page_1_Figure_5.jpeg)

![](_page_1_Figure_7.jpeg)

Figure 3: LI sweep at 55C, modulator Vea=0V Figure 4: SMSR plot at 55C, 100mA laser bias

![](_page_1_Figure_9.jpeg)

Figure 5: Measured and simulated EO SSD21 at 55C, 130mA laser bias

For differential PAM-n measurements, a 2 channel AWG was used. The output electrical signal was amplified using 110GHz amplifiers with in-built bias tees to have an output swing of 1.5Vppd at 160 GBd. The output optical signal was measured on a DCA with a half baud rate BT filter. 15 taps FFE was used to equalize the eye at 160 GBd. BTB 160 GBd PAM-4 (320 Gbits/s) and PAM-6 (413 Gbits/s) eye measurements are shown in figures 6 and 7 respectively. Devices were tuned around the modulator inflection voltage resulting in a RF ER greater than 3.3dB at 160GBd. At the operating modulator voltage, measured facet power under modulation was high and close to 6.5 dBm with high RF ER of 3.8 dB at 160 GBd PAM-4. Open eyes are shown after equalization for both PAM-4 and PAM-6 at 160 GBd.

![](_page_2_Figure_3.jpeg)

Figure 6: BTB 160GBd PAM4 (320 Gbits/s) with 3.8dB ER Figure 7: BTB 160GBd PAM6 (413 Gbits/s) eyes with 3.3 dB ER

![](_page_2_Figure_5.jpeg)

and using 15 taps FFE, 1.5Vppd at 55C, 130mA and using 15 taps FFE, 1.5Vppd at 55C, 130mA

#### **4. Summary**

Very high BW differential drive EMLs with 6-dB EO BW reaching 99GHz at 55C have been demonstrated using lumped electrode design. Open BTB 160 GBd PAM-4 (320 Gbits/s) and PAM-6 (413 Gbits/s) eyes are shown with ER greater than 3.3dB and 1.5 Vppd, resulting in nearly 40% lower driver swing requirement than the SE EMLs. Devices show excellent output power with 6.5 dBm facet power under modulation and minimum roll over in L-I sweep up to 150mA. High frequency EO SSD21 can be further improved by switching to flip chip mounting. This combination of high power, high BW and high ER along with the low swing differential drive operation make these EMLs suitable for next generation short reach 3.2T ethernet applications.

## **Acknowledgement:** The Authors would like to thank Broadcom's Breinigsville, PA operations team for fab support. **References**

- [1] P. Bhasker, S. Arora, A. Robertson, T. McCaully, A. Ni, and J. Johnson, "200G per Lane Uncooled CWDM Hybrid CMBH-Ridge Electroabsorption Modulated Lasers for 2-km Transmission," in Optical Fiber Communication Conference (OFC) 2023, Technical Digest Series (Optica Publishing Group, 2023), paper M2D.3
- [2] S. Yamauchi, K. Adachi, H. Asakura, H. Takita, Y. Nakai, Y. Yamaguchi, M. Mitaki, R. Nakajima, S. Tanaka, and K. Naoe, "224-Gb/s PAM4 Uncooled Operation of Lumped-electrode EA-DFB Lasers with 2-km Transmission for 800GbE Application," in Optical Fiber Communication Conference (OFC) 2021, P. Dong, J. Kani, C. Xie, R. Casellas, C. Cole, and M. Li, eds., OSA Technical Digest (Optica Publishing Group, 2021), paper Tu1D.1
- [3] K. Nishimura, H. Asakura, S. Yamauchi, T. Suzuki, Y. Nakai, Y. Yamaguchi, T. Kageyama, M. Mitaki, Y. Endo, and K. Naoe, "225-Gb/s PAM4 Operation Using Lumped-Electrode-Type EA-DFB Laser for 5- and 10-km Transmission with Low TDECQ," in Optical Fiber Communication Conference (OFC) 2023, Technical Digest Series (Optica Publishing Group, 2023), paper M2D.4.
- [4] Asami Uchiyama, Shinya Okuda, Toshiya Tsuji, Yohei Hokama, Mizuki Shirao, Kenichi Abe, Takeshi Yamatoya and Yasuhiro Yamauchi, "Demonstration of 155 Gbaud PAM4 and PAM6 EML with Narrow High-Mesa EA Modulator for 400 Gbps per Lane Transmission, in Optical Fiber Communication Conference (OFC) 2024, Technical Digest Series (Optica Publishing Group, 2024), paper Tu2D.1
- [5] P. Bhasker, S. Arora, A. Robertson, T. McCaully, A. Ni and J. E. Johnson, "413 Gbits/s PAM-6 O-band CWDM Electroabsorption Modulated Lasers for 400G per lane IM-DD Applications," *2025 Optical Fiber Communications Conference and Exhibition (OFC)*, San Francisco, CA, USA, 2025, pp. 1-3
- [6] P. Bhasker *et al*., "75 GHz BW Ultra-High Speed O-band Hybrid CMBH Ridge EMLs for Next Generation Ethernet," *ECOC 2024; 50th European Conference on Optical Communication*, Frankfurt, Germany, 2024, pp. 596-598
- [7] S. Okuda *et al*., "High-speed 340 Gbps PAM4 and 450 Gbps PAM6 Operations of Narrow High-Mesa EML," in *Journal of Lightwave Technology*, doi: 10.1109/JLT.2025.3588689
- [8] M. Shirao *et al*., "High-Speed EML and Assembly Techniques for GPU Cluster System," *2025 Optical Fiber Communications Conference and Exhibition (OFC)*, San Francisco, CA, USA, 2025, pp. 1-3
- [9] S. Ohno *et al*., "226 Gbps PAM4 Operation Using Differential Drive EA-DFB Laser with 2.0-Vppd Swing over 10-km SSMF Transmission for 1.6TbE Transceivers," *2025 Optical Fiber Communications Conference and Exhibition (OFC)*, San Francisco, CA, USA, 2025, pp. 1-3.
- [10] Z. Zhang, W. Li, M. Li and W. Wang, "Differential Drive EML with P/N Electrode Isolated toward Low Vpp Application," *2025 Optical Fiber Communications Conference and Exhibition (OFC)*, San Francisco, CA, USA, 2025, pp. 1-3.
- [11] https://www.coherent.com/news/press-releases/400g-differential-emld