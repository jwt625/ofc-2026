# **Differential Drive EML with Tandem Modulator Structure for 200G/Lane and Beyond Applications**

**Hideki Oe, Kyohei Maekawa, Kenta Sugawara, Masahiro Honda, Kosuke Saito, Fumihiro Nakajima, Takamitsu Kitamura, Tohma Watanabe, Kazuki Torii, Hirohiko Kobayashi, Kan Takada, and Daisei Shoji**

> *Sumitomo Electric Device Innovations, Inc. 1, Toya-cho, Sakae-ku, Yokohama, 244-8588, Japan ooe-hideki@sei.co.jp*

**Abstract:** Differential drive EML with tandem modulator structure is reported. 3 dB bandwidth is 80 GHz and the device achieved 5.2 dB extinction ratio and 1.28 dB TDECQ at 113 Gbd PAM4 with 2.0 Vpp differential drive. © 2026 The Authors

### **1. Introduction**

As AI datacenters grow in scale, optical technologies that support high-bandwidth, high-density and long reach interconnect inside datacenters play a key role. 1.6T transceivers based on 8 channels of 200G/lane (113 Gbd PAM4) modulators are starting to be deployed [1], and in the future, 400G/lane (226 Gbd PAM4) modulators are expected to be used for 3.2T transceivers [2].

Electro-absorption modulated laser (EML) is an attractive solution, with its high-bandwidth, high optical output power and compact size. Several demonstrations achieving beyond 200G/lane modulation have been reported [3-5]. Most of the EMLs reported are single-ended drive modulators due to the common cathode configuration of the laser and the modulator. As the data rate goes up and high-density integration is required, differential-drive EMLs are attractive due to their low crosstalk and superior characteristics [6,7]. By adopting a semi-insulating InP substrate, and driving the anode and the cathode of the modulator each with the positive and the negative phase of the differential drive signal, 113 Gbd PAM4 eye with 4.8 dB extinction ratio has been reported [7]. Another approach to realize differential-drive EMLs is to use a tandem modulator structure and drive each modulator with the positive and the negative phase of the signal [8]. This approach realizes better impedance matching compared to the other approach, and is also advantageous for achieving high bandwidth due to the small parasitic capacitance of the modulator.

We report differential drive EML with a tandem modulator structure operating at 200G/lane for the first time. It achieved 80 GHz 3 dB bandwidth, differential return loss below -10 dB up to 60 GHz, and 5.2 dB extinction ratio at 113 Gbd PAM4.

### **2. Device Structure**

Fig. 1 (a) shows the schematic diagram of the conventional anode-cathode drive differential EML. While it can exploit twice as large drive signal as single-ended EMLs, actual extinction ratio improvement is limited. This is because EA modulators generally induce photocurrent and act as equivalent resistance, causing an impedance mismatch to the 100 Ω signal driver. It also suffers from narrow bandwidth, because RC time constant is twice as large as single-ended EMLs. Fig. 1 (b) shows the schematic diagram of the EML with a tandem modulator structure we report. It consists of a dual modulator that is connected in series, so it achieves higher total EA equivalent resistance, improving impedance matching to the 100 Ω signal driver. It also has wider bandwidth because of the small parasitic capacitance of the individual modulator.

![](_page_0_Picture_12.jpeg)

Fig. 1. Schematic diagram of differential EMLs. (a) Differential EML for anode-cathode drive, and (b) differential EML with tandem dual modulator.

Fig. 2 (a) shows the top view of the fabricated differential EML. The positive phase of the drive signal modulates the 1st modulator EA1 which is adjacent to the laser, and the negative phase of the drive signal modulates the cathode of the 2nd modulator EA2 which is adjacent to the 1st modulator. The cathode of the 1st modulator and the anode of the 2nd modulator are connected to a common pad, which is wire bonded to the ground.

All the core layers of laser, modulator, and interconnecting passive waveguide are connected by butt-joint regrowth on a semi-insulating InP substrate. After a regrowth of p-InP cladding layer, waveguide mesa was formed, and then epitaxially buried by semi-insulating InP. This buried heterostructure reduces both the thermal resistance of the laser section and the capacitance in the modulator section, at the same time.

Fig. 2 (b) shows the cross-sectional view of the laser section. n+ InP layer below the MQW acts as an access layer to the cathode electrode. The doping concentration and the distance between the LD mesa and the cathode electrode is carefully designed so that it does not cause excess series resistance.

![](_page_1_Picture_5.jpeg)

Fig. 2. (a) Top view of the differential EML. (b) Cross-sectional view of the DFB-LD.

As the optical input power to the 1st and the 2nd modulator is quite different in this EML, it causes an unbalanced modulation amplitude of the positive and the negative phase of the drive signal, degrading the common-mode rejection ratio (CMRR). We set the length of the 1st modulator longer than the 2nd modulator to balance the modulator characteristics. The EML chip was mounted and wire-bonded to a carrier with 150 Ω differential termination resistance.

### **3. Experimental results**

Measurements were performed at 55°C carrier temperature and 100 mA laser bias current. Fig. 3 (a) shows the current-voltage and the output power versus laser current characteristics of the EML at 0 V EA bias voltage. The laser forward voltage at 100 mA is 1.4 V, which is 0.1 V higher than our single-ended drive EML. Fig. 3 (b) shows the lasing spectrum. Oscillating wavelength is 1311.1 nm, and side-mode suppression ratio is larger than 40 dB. Fig. 3 (c) shows the output power versus EA bias voltage of the differential EML. Bias voltage of each of the modulator is set to the same value but with an opposite sign, that is, -Vb for EA1 and +Vb for EA2 as shown in Fig. 1 (b). DC extinction ratio between 0V to -3V is 22 dB.

![](_page_1_Figure_10.jpeg)

Fig. 3. (a) I-V, I-L curve of the EML. (b) Lasing spectrum of the EML. (c) Output power versus EA bias voltage.

Fig. 4 show the frequency characteristics of the EML measured at the operating bias condition of -1.7 V, where linearity is the highest. 3 dB bandwidth of the EO response is 80 GHz and differential return loss is below -10 dB up to 60 GHz. The small return loss is achieved due to the series configuration of the dual EA modulator, resulting in a good impedance matching to the 100 Ω differential drive circuit. CMRR is over 15 dB up to 60 GHz. These characteristics are beyond what is necessary for 200G/lane application. The relatively large S<sup>21</sup> roll-off over 80 GHz

is attributed to the carrier design, and we expect it to get flatter by adopting more advanced carrier designs such as flip-chip carrier [9], which we expect to be necessary for 400G/lane application.

![](_page_2_Figure_3.jpeg)

Fig. 4. Frequency response of the differential EML. (a) EO response, (b) differential return loss, and (c) common mode rejection ratio defined as Ssd21 / Ssc21.

Fig. 5 (a) shows the 113 Gbd PAM4 test setup. Arbitrary Waveform Generator (Keysight M8199B) generates the 113.4375 Gbd PAM4 SSPRQ pattern, and it is amplified to 2.0 Vpp differential amplitude by amplifiers (SHF T850 C-04), which also include bias-tee. The differential signal is applied to the chip-on-carrier via a 110 GHz GSGSG probe. The optical output of the EML is coupled to a lensed fiber and measured via a sampling oscilloscope (Keysight N1030A). Fig. 5 (b) shows the measured optical waveform with 56.72 GHz Bessel-Thomson filter applied. Fig. 5 (c) shows the optical waveform after the 15-tap feed-forward equalizer (FFE). Extinction ratio is 5.2 dB, optical modulation amplitude is 8.6 dBm, and TDECQ is 1.28 dB at a symbol-error rate of 9.6 x 10-3 as defined in the standard [10].

![](_page_2_Figure_6.jpeg)

Fig. 5. (a) 113 Gbd PAM4 test setup. Optical waveform without FFE (b) and after FFE (c).

## **4. Conclusion**

Differential drive EML with tandem modulator structure shows 80 GHz 3 dB bandwidth. Differential return loss is below -10 dB and CMRR is over 15 dB up to 60 GHz. At 113 Gbd PAM4, 5.2 dB extinction ratio and 1.28 dB TDECQ is achieved with 2.0 Vpp differential drive. These characteristics show that the device is suitable for 200G/lane and beyond applications.

### **5. References**

- [1] X. Zhou, "IM-DD vs. Coherent in Datacenters: A Revisit in 2025," OFC 2025, M4C.1 (2025).
- [2] C. St-Arnault et al., "Net 3.2 Tbps 225 Gbaud PAM4 O-Band IM/DD 2 km Transmission Using FR8 and DR8 with a CMOS 3 nm SerDes and TFLN Modulators," OFC 2025, Th4B.1 (2025).
- [3] H. Asakura et al., "400 Gbps Semi-cooled Lumped-Electrode EA-DFB Laser Operating at 200 Gbaud PAM4 Modulation with 0.6 Vpp," ECOC2024, Th3A.1 (2024).
- [4] P. Bhasker et al., "413 Gbits/s PAM-6 O-band CWDM Electroabsorption Modulated Lasers for 400G per lane IM-DD Applications," OFC 2025, Tu2J.2 (2025).
- [5] S. Okuda et al., "High-speed 340 Gbps PAM4 and 450 Gbps PAM6 Operations of Narrow High-Mesa EML," OFC 2025, Tu2J.7 (2025).
- [6] Z. Zhang et al., "Differential Drive EML with P/N Electrode Isolated toward Low Vpp Application," OFC 2025, M3K.6 (2025).
- [7] S. Ohno et al., "226 Gbps PAM4 Operation Using Differential Drive EA-DFB Laser with 2.0-Vppd Swing over 10-km SSMF Transmission for 1.6TbE Transceivers," OFC 2025, M4K.6 (2025).
- [8] E. Ishimura, "Optical Modulator," United States Patent Application US2002/0195622 (2002).
- [9] T. Misawa et al., "High Power Compact EML Transmitter Module for 400G-FR4," ISLC 2018, MC6 (2018).
- [10] https://www.ieee802.org/3/dj/