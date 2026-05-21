# **Rényi Divergence-based Nonlinear OLT-side Tomlinson-Harashima Precoding for 100G FTN PON**

**Geyang Wang1,2, Hao Deng3 , Xianwei Cheng2 , Zelu Wang1 , Hon Ki Tsang1 , Lian-Kuan Chen1 , Roberto Proietti4 , S. J. Ben Yoo2**

> *1 The Chinese University of Hong Kong, Hong Kong SAR, China University of California at Davis, Davis, CA, USA 3 South China University of Technology, Guangzhou, Guangdong, China. 4 Politecnico di Torino, Italy lkchen@ie.cuhk.edu.hk*

**Abstract:** We propose low-complexity FTN PONs using Rényi divergence-based universal nonlinear Tomlinson-Harashima precoding. The single OLT-side precoder experimentally demonstrates effectiveness for equalizing ONUs residing at different distances simultaneously and realizes up to 4dB sensitivity gain.

## **1. Introduction**

With the continuous growth in bandwidth requirements, ITU-T standardization groups have established specifications for 50 Gbps/λ passive optical networks (PONs) [1]. Investigations are ongoing into single-channel systems supporting data rates beyond 100G [2]. The C-band, owing to its mature device technology and lower attenuation, presents a strong candidate for next-generation PON systems targeting high power budgets. However, achieving such systems requires addressing critical issues, including dispersion, bandwidth constraints, and nonlinear effects introduced by both optoelectronic components and optical fiber. To combat these challenges, several digital signal processing (DSP) techniques have been adopted [3]-[4], such as feedforward equalizer (FFE), decision feedback equalizer (DFE), Volterra nonlinear equalizer (VNLE), and orthogonal frequency division multiplexing (OFDM)-based precoding schemes, aiming at mitigating both linear and nonlinear distortions in next-generation PON. Furthermore, faster-than-Nyquist (FTN) signaling has emerged as a promising solution to alleviate bandwidth limitations and mitigate spectral nulls induced by dispersion [5]. A common drawback of these schemes, however, is their reliance on computationally intensive DSP at the optical network unit (ONU), which unfavorably raises the per-user deployment cost.

Tomlinson-Harashima precoding (THP), via shifting interference cancellation from the ONU receiver to the optical line terminal (OLT), achieves better cost sharing, offering an attractive solution for high-speed low-cost PON. In this work, we first introduce a low-complexity exponential nonlinear equalizer-based (ENLE) THP FTN PON system, whose complexity is comparable to that of a linear equalizer. This design simultaneously compensates for inter-symbol interference (ISI) due to FTN transmission and mitigates both linear and nonlinear impairments at the OLT. Experimental validation in a 20-km 100G PON setup demonstrates a 4 dB improvement in receiver sensitivity (RS) over conventional THP-PON. In a practical PON with ONUs at different distances, the proposed scheme would require individual precoder parameters for different ONUs, significantly increasing system complexity and latency. To overcome this issue, this paper further proposes Rényi divergence-based universal THP design (RU-THP). Experimental results confirm that the proposed RU-THP scheme achieves ~3.7dB RS improvement while employing a single precoder configuration to accommodate ONUs across different fiber lengths.

## **2. Principle**

FTN can compress the signal spectrum to mitigate impairments caused by spectral nulls. However, the resulting ISI typically requires complex sequence estimation algorithms at the ONU, as illustrated in Fig. 1(a). Also, the linear and nonlinear equalization are typically implemented at the ONU, as shown in Fig. 1(b). The corresponding transmitter and receiver architectures are depicted in Fig. 1(c) and 1(d), respectively. Moreover, we introduce a low-complexity nonlinear equalizer, ENLE, whose complexity is comparable to an FFE. The significant reduction in complexity is achieved by implementing the exponential functions using the CORDIC algorithm, which requires only addition and shift operations [3]. Accordingly, the representation of the precoded signal after nonlinear THP (NTHP) is given by:

$$x(n) = s(n) + d(n) - \left[\sum_{k_1=0}^{N_1-1} w_1(k_1) x(n-k_1) + \sum_{k_2=0}^{N_2-1} w_2(k_2) e^{x(n-k_2)}\right]$$
 (1)

where *s*(*n*) is the original PAM-4 signal, *d*(*n*) is a correction term that describes the impact of the modulo operation, and *x*(*n*) is the pre-coded signal at the output of NTHP. The *wi* and *Ni* are the coefficients and memory length of the

![](_page_1_Figure_2.jpeg)

Fig. 1. At the ONU side, block diagram of (a) the FTN scheme employing sequence detection algorithm, (b) the nonlinear equalizer, and (d) the proposed scheme. (c) Block diagram of the proposed scheme at the OLT side. (e) Schematic diagram illustrating the virtual channel construction in the proposed RU-THP scheme. (f) System configuration and experimental setup of the proposed PON system.

i th-order kernel, respectively. If the OLT must store and employ different THP-FTN precoders for different ONUs, system complexity and latency increase. To overcome this, we propose RU-THP that employs a single THP-FTN precoder to serve ONUs at different fiber distances. Rényi divergence serves as a generalized measure of distributional similarity, extending beyond the Kullback-Leibler divergence to better quantify the difference between two probability distributions [6]. A virtual channel response is constructed by minimizing the weighted sum of Rényi divergence between this virtual channel and the actual channels with different lengths, as expressed in Eq. (2):

$$arg \min_{q_i} \sum_{j=1}^{J} \frac{1}{\alpha_j - 1} ln \sum_{i=1}^{I} (g_i)^{\alpha_j} (h_{i,j})^{1 - \alpha_j}$$
 (2)

where *gi* and *hi,j* are the coefficients of the desired virtual channel and the measured channel of the *j* th ONU (out of *J* total ONUs), respectively, and *αⱼ* is a weighting factor for the *j* th ONU. Optimization algorithms can be employed to solve the above problem. The solution yields the virtual channel, which is then used to derive the THP parameters. Subsequently, this approach yields a single optimal THP-FTN parameter set that best matches all ONU channels.

## **3. Experimental setup and results**

The experimental configuration of the proposed nonlinear THP FTN PON system is depicted in Fig. 1(f). At the transmitter, a 256-GSa/s arbitrary waveform generator (AWG, Keysight M8199A) produces the electrical driving signal, which is subsequently amplified by an electrical amplifier (EA) before driving an on-chip silicon microring modulator (MRM). The optical signal propagates through 15 km or 20 km of standard single-mode fiber (SSMF), with received power controlled by a variable optical attenuator (VOA). Detection is performed using a photodiode (PD), and the output waveform is captured by a digital storage oscilloscope (DSO, Keysight UXR0702AP) for offline processing. At the transmitter, MATLAB generate 50G Baud PAM-4 symbols, followed by NTHP. The pulse shaping employs a square-root raised-cosine filter (SRRC) with roll-off = 0.01, and subsequently the spectrum is truncated by a brick-wall filter with compression ratio *γ* to realize FTN. At the receiver, synchronized data undergoes Volterra nonlinear DFE processing to extract appropriate feedback coefficients for the transmitter-side NTHP. With NTHP activated at the transmitter, the receiver implements FFE and modulo operations for signal recovery. In the following, we set *γ*=0.6, *N*<sup>1</sup> =73 and *N*2=11. The parameters of OFDM discrete Fourier transform (OFDM-DFT) and OFDM precoder-based FTN (OFDM-pFTN) follow reference [4], while all schemes maintain equal data rates.

Fig. 2(a) presents the BER under different received optical power (ROP) for various THP schemes implemented at the OLT-side, compared to equalizers deployed at ONU-side. In the figures, the labels "(ONU)", "(OLT)", and "(Both)" denote that the algorithm is implemented at the ONU side, the OLT side, and both sides, respectively. The results show that all OLT-side THP variants achieve better performance than ONU-side equalizers, owing to the ability

![](_page_2_Figure_2.jpeg)

Fig. 2. BER of 100G PAM-4 versus ROP (a) under conventional equalizers at Rx and THP-based linear and nonlinear precoder at Tx, and (b) under different OFDM precoders and FTN-based schemes where the fiber length is 20 km.

![](_page_2_Figure_4.jpeg)

Fig. 3. BER of 100G PAM-4 versus ROP (a) under different OFDM precoders and FTN-based schemes where the fiber length is 15km, and (b) under different THP schemes with various parameters where the fiber length is 15 km and 20 km.

of THP to avoid error propagation. It is also observed that the proposed THP-ENLE attains performance comparable to VNLE with lower computational complexity. Fig. 2(b) and 3(c) depict the BER under varying ROP for the proposed nonlinear THP combined with FTN, along with conventional single- and multi-carrier schemes, in 20-km and 15-km PON scenarios, respectively. Due to severe spectral nulls induced by chromatic dispersion, OFDM-based precoding and FTN schemes exhibit poor performance. In contrast, the proposed FTN-based linear and nonlinear THP schemes consistently achieve further performance gains. Specifically, in the 20-km PON, the proposed approach provides ~ 4 dB improvement in receiver sensitivity at the 20% SD-FEC threshold of 2.4×10⁻² compared to the THP-only scheme. Fig. 3(b) compares the BER of the proposed RU-THP-ENLE-FTN and other benchmark schemes in a hybrid-reach PON containing both 15-km and 20-km optical paths. The proposed RU-THP scheme supports both 15 km and 20 km ONUs using a single parameter set, achieving ~3.7dB RS gain, showing its adaptability in multi-reach PON scenarios.

## **4. Conclusion**

In this paper, we experimentally demonstrate a Rényi divergence-based universal THP scheme for 100G FTN PON. The proposed RU-THP enables a single OLT-side precoder to support ONUs at different fiber lengths (15-20 km) with up to ~4 dB sensitivity gain. By centralizing both THP and FTN processing at the OLT, the complexity and cost are effectively shared among all ONUs, providing a cost-effective solution for multi-reach PON deployments. This work was in part by HKSAR RGC GRF 14206123, 14201324.

## **5. Reference**

- [1] E. Harstead, et al. "Technology roadmap for time-division multiplexed passive optical networks (TDM PONs)" JLT.37(2), pp. 657–664, 2019 [2] L. Xue, R. Lin, J. Van Kerrebrouck, L. Yi, J. Chen and X. Yin, "100G PAM-4 PON with 34 dB Power Budget Using Joint Nonlinear Tomlinson-Harashima Precoding and Volterra Equalization," *2021 ECOC*, Bordeaux, France, 2021
- [3] G. Wang et al., "96% Complexity-Reduced Nonlinear Equalizer for a C+L-band 1.13Tb/s/pol Coexistent IM/DD- and Comb-based Coherent-PON System," 2024 IEEE Photonics Conference (IPC), Rome, Italy, 2024, pp. 1-2,
- [4] Song, Peiji et al. "Nonlinear Distortion Mitigation of DML-Based OFDM Optical Systems with Non-Orthogonal DFT-Precoding." Optics letters 48.17 (2023)
- [5] Che, Di, and Xi Chen. "Modulation Format and Digital Signal Processing for IM-DD Optics at Post-200G Era." Journal of Lightwave Technology 42.2 (2024)
- [6] Van Erven, Tim, and Peter Harremoes. "Rényi Divergence and Kullback-Leibler Divergence." *IEEE transactions on information theory* 60.7 (2014): 3797–3820.