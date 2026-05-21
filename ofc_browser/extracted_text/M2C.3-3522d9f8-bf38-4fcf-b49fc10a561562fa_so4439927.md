# **Real-time Unrepeatered Transmission of 400G/800G/1.2T over 726.1km/611.9km/436.1km HCF only Using EDFA**

**Lipeng Feng1\* , Anxu Zhang<sup>1</sup> , Peng Li<sup>2</sup> , Yuan Gao<sup>2</sup> , Hailin Yang<sup>3</sup> , Lei Zhang<sup>2</sup> , Wenzhe Chang<sup>1</sup> , Xishuo Wang<sup>1</sup> , Zhengyu Liu<sup>1</sup> , Jie Luo(2), Xiaoli Huo<sup>1</sup> , Tao Ma 4 , Songnian Fu<sup>3</sup> , Chengliang Zhang<sup>1</sup>**

*<sup>1</sup>China Telecom Research Institute, State Key Laboratory of Optical Fiber and Cable Manufacture Technology, Beijing, China. State Key Laboratory of Optical Fiber and Cable Manufacture Technology, Yangtze Optica Fibre and Cable Joint Stock Limited Company (YOFC), Wuhan, Hubei, China.*

*School of Information Engineering, Guangdong Provincial Key Laboratory of Information Photonics Technology, and Ministry of Education of China, Guangdong University of Technology, Guangdong, China*

*<sup>4</sup>China Telecom Corporation Limited, Beijing, China. Corresponding author email: fenglp@chinatelecom.cn*

**Abstract:** We demonstrate record unrepeatered transmissions of 400G/800G/1.2T over 726.1km/611.9km/436.1km HCF by only using high-power EDFA, confirming that the HCF link with the simplest structure achieves substantial reach extension over the SSMF link with complex structure. © 2024 The Author(s)

#### **1. Introduction**

The hollow core fibers (HCFs) provide a significant room for improving the unrepeatered transmission reach by reducing signal impairments and increasing the launched power, which benefits from the low-loss, low dispersion and low-nonlinearity characteristics. Recent results indicate that, the optimal launched power of HCF for the 1.2T/λ transmission systems can enhance up to 34.77dBm with an additional 0.2dB Q-value penalty, better than that of the standard single-mode fiber (SSMF) counterpart [1]. Currently, the attenuation coefficient of HCF over the C band has been decreased to 0.08±0.03 dB/km [2], which is below the theoretical limit of SSMF. With the attenuation coefficient reduction, it is possible to achieve ultra-long unrepeatered transmission by only using EDFA, which reduces system complexity, operation costs, maintenance difficulty, and improve reliability, avoiding the use of backward Raman amplifiers and multiple remote gain units (RGUs).

The current longest unrepeatered transmission distances are 746.69km, 730.83km and 701.52km at 100G, 200G, 400G PM-QPSK real-time transmission systems, by the use of high-order Raman pumps and four ROPAs with four dedicated fiber [3]. A record unrepeatered transmission of 800G 16QAM over 404.39km [4] and 437.7km [4] are, respectively, demonstrated under the real-time and offline operations with Raman amplification and RGUs. However, there have been no reports confirming the transmission performance in only EDFAs amplified HCF unrepeatered transmission systems with single wavelength.

In this paper, we demonstrate 726.1km, 611.9km and 436.1km real-time unrepeatered transmission for 400G QPSK, 800G PCS-16QAM, and 1.2T PCS-64QAM only using high-power EDFA. Thanks to the high launched power of 34dBm, 36dBm, and 40dBm, which are more than 23dB higher than that of SSMF counterpart, the fiber link loss budget is approximately 73.3dB, 60.9dB, and 43.6dB, respectively, without the observation of significant nonlinear impairments. Such HCF unrepeatered transmission system has a very simplify configuration and extend the reach by 24.58km and 172km, in term of transmission distance compared with previous records for 400G and 800G systems. Meanwhile, to the best of our knowledge, this is the first real-time experimental demonstration of more than 200km unrepeatered transmission system with 1.2T/λ signals.

#### **2. Experimental setup**

The experimental setup is shown in Fig. 1, which is configured to transmit 400G, 800G, and 1.2T at the central wavelength of 1557.4nm. This experiment chooses alternately two line cards. One is an integrated card that can enables multi code signals modulated at 138GBaud, which generate QPSK for 400G and PCS-16QAM for 800G located at the 150GHz channel spacing. The other one is modulated at 155GBaud, generating 1.2T signal with PCS-64QAM modulation format at the 175GHz channel spacing. At the transmitter side, the optical signals are amplified with a high-power EDFA (HP-EDFA) having a maximum saturation output power of 10W, following a direct connection with HCF by the fusion splicing technique. Fig. 2 shows the relationship between noise figure (NF) and operation wavelength at the output power of 40dBm, when the input power varies from -6dBm to 5dBm. It can be seen that, the NF performance is better at the low input power of HP-EDFA and longer operation wavelength. Therefore, the variable optical attenuator (VOA) between line card and HP-EDFA is used to adjust the input power of HP-EDFA to -3dBm, for the ease to secure better system performance. The unrepeatered link length can be

![](_page_1_Picture_2.jpeg)

Fig. 1. Experimental setup for real-time 400G/800G/1.2T unrepeatered transmission.

extended by increasing 326.1km/211.9km/36.1km HCF in together with 397.3km HCF, which is fusion splicing among multiple 5km spool. As shown in Fig. 3, the loss spectrum of longest fiber link over the CE band (4.8THz) is characterized, finding an average loss coefficient of 0.1dB/km, including 2 pairs of HCF-SMF adaptors with each 0.6dB insertion loss and HCF-HCF splice points with an average splicing loss of 0.08 dB. In particular, the lowest loss wavelength region is located at the span from 1549nm to 1561nm. The fiber employs the Support Tube HCF (ST-HCF) with 5 elements, whose end-face structure is illustrated at the inset of Fig. 3. The PMD and chromatic dispersion coefficient are 0.3ps/√km and 3.27ps/nm/km at the wavelength of 1550nm. The intermodal interference (IMI) of fiber link is characterized and calculated by using a swept wavelength-scanning scheme with a wavelength resolution of 0.02nm [5], giving a result of -54dB/km. At the receiver side, another EDFA is used to amplify the received signals with -34dBm received sensitivity and a wavelength selective switch (WSS) set the channel grid to match the signal bandwidth, which is used to filter out the amplified spontaneous emission (ASE) from EDFA. For the ease of performance comparison, another 150km G.654.E fiber is used to replace the HCF link to get the optimal launched power, which has a loss coefficient of approximately 0.168dB/km.

![](_page_1_Figure_5.jpeg)

Fig. 2. (a) NF vs Wavelength for the HP-EDFA. (b) Measured loss spectrum of 726.1km HCF with an inset displaying its cross-sectional view.

#### **3. Experimental results**

The relationship between the Pre-FEC BER and launched power are shown in Fig. 4(a), when the launched power gradually increases from 30dBm to 40dBm for the HCF unreapeatered system and from 0dBm to 15dBm for the SMF unrepeatered system. The peaks of Pre-FEC BER of SSMF are located at the 11~12dBm input fiber power, while the transmission performance is optimal when the launched powers are 34dBm and 36dBm for 800G and 1.2T signals for the HCF link, respectively. However, the optimal launched power cannot be detected, due to the limited maximum output power of HP-EDFA for the 400G unreapeatered transmission. Therefore, as for three kinds of bitrate per wavelength, the optical launch power of 34dBm, 36dBm, and 40dBm are chosen, respectively. The variation BER curves with OSNR, under scenarios of the optical back-to-back (OBTB) and after transmission are shown in Fig. 3(b). As for the 400G unreapeateerd transmission system, it still has a 1dB system margin, mainly limited by the received sensitivity. The 800G and 1.2T unreapeatered transmission systems are OSNR limited transmission, with 1.68dB and 5.8dB OSNR penalties, respectively. The inset of Fig. 3(c) shows the input and output spectra.

![](_page_2_Figure_2.jpeg)

Fig. 3. (a) The Pre-FEC BER of 400G/800G/1.2T transmission system through HCF at various launched power. (b) The variation curves of BER with OSNR over the optical back-to-back (OBTB) and after transmission. (c) Signal spectra at the transmitter and receiver sides.

The results of a 30min BER stability test have been recorded in Fig. 4, with an interval of 30 seconds. The BER values remain stable and always below the FEC threshold. The Pre-FEC BER of the 400G unreapeateder transmission system is lower than that of 800G/1.2T systems is mainly due to the system power margin. Meanwhile, the post-FEC errors on the client side is also monitored by the use of BER-analyzer.

![](_page_2_Figure_5.jpeg)

Fig. 4. BER monitoring of real-time unrepeatered transmission.

## **4. Conclusion**

Record real-time unrepeatered transmission over 726.1km, 611.9km and 436.1km HCF link is demonstrated for the single-carrier 400G QPSK, 800G PCS-16QAM, and 1.2T PCS-64QAM signals, with the only use of EDFA. The launch power values of three unrepeatered transmission systems can increase from 11dBm/11dBm/12dBm of G.654.E fiber to 34dBm/36dBm/40dBm+ of HCF, without significant nonlinear impairments. Moreover, the HCF link achieves an extremely low loss of 0.1dB/km, including both splicing loss and HCF-SMF adaptors. The experiment demonstrates that unrepeatered transmission based on HCF link can break the current SMF records.

### **5. References**

[1] Y. Chen, A. I. Adamu, M. R. A. Hassan, E. N. Fokoua, D. J. Richardson, and F. Poletti, "Hollow core DNANF optical fiber with <0.11 dB/km loss," in Optical Fiber Communications Conference and Exhibition (OFC), San Diego, CA, USA, 2024, pp. 1–3.

*This work is supported by the National Key R&D Program of China (2023YFB2906300)*

- [2] B. Yan, et al., "Towards Ultra-High-Capacity Long-Haul Fibre Communication: First Demonstration of Real-time 1.2Tb/s OTN Transmission at 3-Watt/Channel Launch Power over 20-km AR-HCF," in ECOC 2024; 50th European Conference on Optical Communication, Frankfurt, Germany, 2024, pp. 1781-1784.
- [3] T. Qiu, et al., "Record Unrepeatered Transmission of 100G, 200G, 400G PM-QPSK Over 746.69km, 730.83km and 701.52km," 2025 Conference on Lasers and Electro-Optics (CLEO), Long Beach, CA, USA, 2025, pp. 1-2.
- [4] H. Bissessur, A. Busson, D. Kravchenko, F. Hedaraly, J. Esparza, "Ultra-long Single Carrier Unrepeatered Transmission of 400 Gb/s over 542 km, 600Gb/s over 489 km, and 800 Gb/s over 437 km," in Asia Communications and Photonics Conference (ACP) and International Conference on Information Photonics and Optical Communications (IPOC), IEEE, 2022.
- [5] S. Ramachandran, J. W. Nicholson, S. Ghalmi and M. F. Yan, "Measurement of multipath interference in the coherent crosstalk regime," in IEEE Photonics Technology Letters, **15**, 1171-1173 (2003).