# 450 Tb/s GMI, 42.4 THz, OESCL-Band Transmission Over a Field-Deployed Fiber

R. S. Luis,1,\* J. Yang,<sup>2</sup> R. Aparecido,<sup>2</sup> M. Jarmolovicius, ˇ <sup>2</sup> E. Sillekens,<sup>2</sup> R. Sohanpal,<sup>2</sup> Z. Gan,<sup>2</sup> A. Donodin,<sup>3</sup> V. Mikhailov,<sup>4</sup> J. Luo,<sup>4</sup> D. DiGiovanni,<sup>4</sup> N. Fontaine,<sup>5</sup> L. Dallachiesa,<sup>5</sup> M. Mazur,<sup>5</sup> R. Ryf,<sup>5</sup> H. Chen,<sup>5</sup> D. Neilson,<sup>4</sup> I. D. Phillips,<sup>3</sup> W. Forysiak,<sup>6</sup> S. K. Turitsyn,<sup>3</sup> D. Orsuti,<sup>1</sup> H. Furukawa,<sup>1</sup> R. I. Killey,<sup>2</sup> and P. Bayvel<sup>2</sup>

*National Institute of Information and Communications Technology, Koganei, Tokyo, Japan Optical Networks Group, University College London, London, U.K. Aston University, Birmingham, UK <sup>4</sup>Lightera Laboratories, Somerset, New Jersey, USA Nokia Bell Labs, New Providence, New Jersey, USA <sup>6</sup>University of Bristol, Bristol, UK \* rluis@nict.go.jp*

Abstract: We report the widest bandwidth SMF transmission, above 42.4 THz (1273 O/E/S/C/L-band channels) on a 39 km, field-deployed, metropolitan, ITU-T G.652-D link, to achieve a record SMF throughput >450 Tb/s (GMI)-418 Tb/s (decoded).

#### 1. Introduction

Ultra-wideband (UWB) transmission over deployed standard single-mode fibers (SMFs) has emerged as a promising approach to address the exponential growth in data traffic demands [\[1\]](#page-2-0) without incurring the prohibitive cost of new fiber infrastructure [\[2\]](#page-2-1). The expansion of wavelength-division multiplexing (WDM) systems beyond the conventional C and L bands has enabled laboratory demonstrations exceeding 37.5 THz of bandwidth and 400 Tb/s throughput, as shown in Fig. [1-](#page-0-0)a) [\[3](#page-2-2)[–14\]](#page-2-3). Although UWB systems target deployed fibers, such links may be constrained by power restrictions, excess loss from splices and connectors, and nonlinear impairments across extended spectra, which affect the signal power, bandwidth, and the use of distributed Raman amplification. In fact, the widest bandwidth with unidirectional transmission demonstrated in deployed SMFs is 30.4 THz, for a throughput of 300.3 Tb/s [\[4\]](#page-2-4), which leaves a large unexplored bandwidth in the low-loss region of silica fibers.

Here, we demonstrate unidirectional UWB transmission spanning 42.4 THz over a 39 km legacy field-deployed SMF link between University College London (UCL) and the Telehouse North datacenter in London, as shown in Fig. [1-](#page-0-0)b). The link is part of the UK National Dark Fibre Facility (NDFF) and comprises two 19.5 km fibers configured in loopback. The transmitted spectrum extends 353.8 nm, from 1264 nm to 1617.8 nm, covering the O, E, S, C, and L bands, see [1-](#page-0-0)c), with total launch power constrained to 23 dBm by laser safety regulations, using only doped-fiber amplifiers. This constitutes the widest bandwidth transmission in field-deployed or laboratory SMFs, achieving a record generalized mutual information (GMI)-estimated throughput of 450 Tb/s or 418 Tb/s after soft-decision forward error correction (FEC). These results are obtained in a field-deployed legacy link while accounting for stimulated Raman scattering (SRS) and four-wave mixing (FWM) and represent a 30% increase in throughput and bandwidth of 33% and 10% over prior field and laboratory demonstrations, respectively [\[3,](#page-2-2) [4\]](#page-2-4). This cements the use of legacy SMF links for UWB transmission well beyond their original design, providing a scalable and cost-effective pathway for metropolitan network upgrades with minimal new fiber deployment.

## 2. Experimental Demonstration

Figure [2](#page-1-0) shows the experimental setup. A sliding test band was produced with 3×33.3 GHz spaced channels by modulating the lightwaves from tunable external cavity lasers (ECLs) with dual-polarization IQ modulators (DPIQMs) for the SCL bands, or dual and single-polarization IQ modulators (IQMs) followed by a polarization

![](_page_0_Figure_11.jpeg)

<span id="page-0-0"></span>Fig. 1. a) Recent UWB throughput achievements above 200 Tb/s using SMFs. b) Location of the UCL and Telehouse stations in London, c) Spectrum of the 42.4 THz UWB transmitted signal.

![](_page_1_Figure_2.jpeg)

<span id="page-1-0"></span>Fig. 2. Experimental setup for the transmission of an OESCL-band signal over the 39 km fielddeployed SMF link. The inset shows OTDR traces of the link at 1310 nm and 1550 nm.

multiplexing emulator, for the OE bands. The modulators were driven by 92 GSa/s arbitrary waveform generators (AWGs) to produce 32.5 GBaud 4, 16, 64, or 256-QAM signals. The center channel was independently modulated whereas the neighbour channels were jointly modulated and combined with the center channel after optical decorrelation. The test band was amplified using erbium-doped fiber amplifiers (EDFAs) when tuned to the C and L bands, thulium-DFAs (TDFAs) for the S-band, and bismuth-DFAs (BDFAs) for the E and O bands.

A dummy band spanning the OESCL bands was generated by spectral shaping, amplifying, and combining the amplified-spontaneous emission (ASE) noise from E/T/BDFAs using commercial optical processors (OPs) for the OSCL bands and a custom E-band multiport OP [\[16\]](#page-2-5). The OPs also produced a sliding 100 GHz notch to accommodate the test band, which was combined with the dummy band at a 10 dB coupler. Figure [1-](#page-0-0)c) shows the final 42.43 THz signal and includes the equivalent channel count of each band for a total of 1273 channels.

After transmission, the bands were split by WDM couplers followed by two amplification stages with band-pass filters (BPFs) in-between to isolate the test channel. We used coherent receivers for the O, E, and the combined SCL bands. The O and E-bands receivers were followed by a 33 GHz, 80 GSa/s digital storage oscilloscope (DSO) whereas the SCL-band receiver used a 110 GHz, 256 GSa/s DSO. Digital signal processing was centered on a 4×4 real-valued, time-domain MIMO with 33 half-symbol duration tap equalizers implemented in MATLAB and C. The equalizers were initially estimated using a data-aided least-mean squares algorithm, which shifted to decision direction after convergence. Carrier recovery was performed within the MIMO loop [\[17\]](#page-2-6).

The NDFF link consisted of a 19.5 km, standard ITU-T G.652-D fiber pair with a loopback connection at the Telehouse station for a total transmission distance of 39 km. The inset of Fig. [2](#page-1-0) shows optical time-domain reflectometry (OTDR) traces of the link at 1550 nm and 1310 nm. The link had an excess loss above 4.5 dB due to splices and connectors. The launch power of the UWB signal was limited to 23 dBm due to laser safety restrictions, with per-band launch powers as indicated in Fig. [1-](#page-0-0)c). The linear link loss spectrum was measured

![](_page_1_Figure_8.jpeg)

<span id="page-1-1"></span>Fig. 3. a) Link loss estimated with 0 dBm and 23 dBm launch powers. b) Method for direct FWM measurement [\[15\]](#page-2-7). FWM-penalty dependency on the launch power (c) and notch wavelength (d).

![](_page_2_Figure_2.jpeg)

<span id="page-2-9"></span>Fig. 4. Wavelength dependent data rate estimated using the GMI and after FEC decoding.

using the dummy signal with a total launch power of 0 dBm and is shown in Fig. [3-](#page-1-1)a). It ranged from 13.6 dB at 1576.2 nm up to 21.8 dB at 1265 nm. With the maximum launch power of 23 dBm, the impact of SRS leads to a loss increase of <1.5 dB in the O, E, and short S bands and a decrease up to 1.5 dB for the C and L bands. No additional spectral pre-emphasis beyond amplifier gain flattening was applied.

The FWM-induced penalty in this link was estimated using a variation of the method proposed in [\[15\]](#page-2-7). We generated an O-band dummy signal with a 100 GHz notch, as shown in Fig. [3-](#page-1-1)b), which was launched into the fiber at varying powers. After transmission, the notch floor was degraded by the introduction of FWM power contributions, which were measured to estimate the corresponding power penalty. Figures [3-](#page-1-1)c) and d) show the penalty as a function of the O-band launch power and notch wavelength, respectively. The penalty was highest near the zero-dispersion wavelength of 1312.4 nm, as expected due to enhanced phase matching conditions. It exceeded 1 dB for O-band launch powers above 16.5 dBm. Hence, the O-band launch power in the main transmission experiment was set at 17.3 dBm to limit the FWM degradation whilst accommodating the SRS-induced excess loss. Figure [1-](#page-0-0)c) shows the launch power of each band, set to accommodate for FWM and fiber loss and conditioned by the power limits of the amplifiers and the 23 dBm laser safety restriction.

We evaluated the system performance by estimating the achievable data-rate using the GMI and after FEC decoding. For the latter, we employed the method previously used in [\[3\]](#page-2-2) among others, with FEC codes from the DVB-S2 standard and puncturing to increase the code rate granularity. We evaluated code rates until a bit-error rate below 10-5 was achieved and assumed a 1% overhead hard decision code to remove any residual errors [\[18\]](#page-2-8). Figure [4](#page-2-9) shows the wavelength-dependent data rate estimated with the average of five 10 µs acquisitions totaling 1.6·10<sup>6</sup> symbols. The modulation format for each channel was selected to achieve the highest throughput. The per channel data rates follow the received power spectrum, shown in Fig. [3-](#page-1-1)a), indicating that the performance was dominated by the impact of ASE, with the highest performance in the C-band and the lowest in the O-band, due to the link loss and launch powers as low as -9 dBm/channel in the O-band. We achieved a total data-rate of 450.08 Tb/s, estimated with GMI, or 418.75 Tb/s after FEC decoding, which corresponded to a 7% implementation penalty. These results show the potential of legacy fibers in deployed metropolitan networks to achieve significantly higher capacity than originally designed through the use of UWB systems, including tolerance for the impact of SRS and FWM.

### 3. Conclusion

We achieved the highest reported transmission bandwidth of 42.4 THz on a field-deployed 39 km metropolitan link using SMFs. This corresponded to a record GMI-estimated data-rate of 450.08 Tb/s and 418.75 Tb/s after FEC decoding in any laboratory or field-deployed SMF. Our results demonstrate the yet untapped potential of legacy deployed fiber links to support high-capacity ultra-wideband transmission.

This work was partly funded by EPSRC grants EP/R035342/1, EP/W015714/1, EP/V007734/1, EP/V000969/1, and EP/S028854/1. RA is supported by a UCL Research Excellence Studentship, ES and AD by RAEng Research Fellowships and PB by a Royal Society Research Professorship.

#### References

- <span id="page-2-0"></span>1. P. J. Winzer *et al.*, Opt. Express 26, 24190 (2018).
- <span id="page-2-1"></span>2. A. Ferrari *et al.*, J. Light. Technol. 38, 4279 (2020).
- <span id="page-2-2"></span>3. B. Puttnam *et al.*, in *OFC,* (2024), p. Th4A.3.
- <span id="page-2-4"></span>4. J. Yang *et al.*, in *IPC,* (2025), p. PD4.
- 5. J. Yang *et al.*, in *OFC,* (2026), p. M3C.2.
- 6. R. Luis *et al.*, in *ECOC,* (2025), p. Th.03.02.3.
- 7. J. Yang *et al.*, J. Light. Technol. 43, 6326 (2025).
- 8. B. Puttnam *et al.*, in *ECOC,* (2024), p. 43.
- 9. J. Yang *et al.*, in *ECOC,* (2024), p. M2B.1.

- 10. B. Puttnam *et al.*, in *OFC,* (2024), p. M1F.4.
- 11. B. J. Puttnam *et al.*, in *ECOC,* (2023), p. Th.C.2.4.
- 12. X. Zhao *et al.*, in *ECOC,* (2022), p. Th3C.4.
- 13. B. Puttnam *et al.*, Opt. Express 30, 10011 (2022).
- <span id="page-2-3"></span>14. B. Puttnam *et al.*, in *OFC,* (2021), p. Th4C.2.
- <span id="page-2-7"></span>15. J. Cai *et al.*, in *OFC,* (2013), p. OM3B.5.
- <span id="page-2-5"></span>16. N. K. Fontaine *et al.*, in *ECOC,* (2023), p. P86.
- <span id="page-2-6"></span>17. T. Pfau *et al.*, J. Light. Technol. 27, 989 (2009).
- <span id="page-2-8"></span>18. D. Millar *et al.*, J. Light. Technol. 34, 1453 (2016).