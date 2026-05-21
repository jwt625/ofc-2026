# **A 4,096×4,096 Strictly Non-Blocking Optical Circuit Switch Delivering 819.2 Tb/s via Space-and-Wavelength Routing**

**Koki Mano<sup>1</sup> , Taisei Sekizuka<sup>1</sup> , Takuma Kuno<sup>1</sup> , Hiroshi Hasegawa<sup>1</sup> , Yojiro Mori2,1**

*<sup>1</sup>Nagoya University, Furo-cho, Chikusa, Nagoya, 464-8603 Japan <sup>2</sup>Toyota Technological Institute, 2-12-1 Hisakata, Tempaku, Nagoya, 468-8511 Japan mano.koki.j3@s.mail.nagoya-u.ac.jp*

**Abstract:** We propose non-blocking OCS architecture that combines space and wavelength routing, employing star couplers to avoid cascaded loss. Simulations show scalability, and experiments demonstrate 4,096×4,096 switching delivering 819.2 Tb/s in a single switching layer. © 2026 The Authors

## **1. Introduction**

The rapid growth of AI workloads has tightened datacenter power budgets, highlighting the need to reduce network energy consumption. Most transmission links use optical fiber, but the switching fabric remains largely electronic. This incurs repeated optical-to-electrical (O/E) and electrical-to-optical (E/O) conversions and associated power costs. To reduce this overhead, hybrid optical and electrical architectures replace some electronic stages with optical circuit switches (OCSs), thereby reducing the power consumed by O/E and E/O conversions [1-5].

To support growing datacenter traffic, an OCS should be strictly non-blocking and should scale in port count and throughput, for example, beyond 1,000 ports and 100 Tb/s. Two-dimensional architectures that combine a space switch and a wavelength-routing (WR) switch are strong candidates because the total port count scales as the product of the two sub-switch sizes, and can readily exceed these targets [6,7]. However, further scaling in port count and throughput is limited by internal optical loss. Despite many loss-reduction techniques, representative demonstrations with 32-Gbaud DP-16QAM remain around 1,536 ports and 300 Tb/s in a single switching layer [6]. Although threestage variants have also been investigated, achieving strict non-blocking in practice typically requires a large number of devices, and many reported systems are therefore rearrangeably non-blocking [8].

This paper proposes a strictly non-blocking OCS that reduces loss in two-dimensional designs while scaling port count and throughput. The architecture integrates concepts from two previously proposed two-dimensional configurations. By reordering switch components and introducing a star coupler, it lowers internal optical loss and enables larger fabrics. We evaluate scalability using system simulations assuming various modulation formats. Experiments verify feasibility with 64-wavelength 32-Gbaud DP-16QAM transmission and demonstrate 4,096×4,096 ports delivering 819.2 Tb/s in a single switching layer.

## **2. Proposed Switch Architecture**

We consider two-dimensional OCSs that combine a space switch with a wavelength-routing switch to realize a strictly non-blocking network. By leveraging wavelength-division multiplexing (WDM) and sharing erbium-doped fiber amplifiers (EDFAs) across multiple transceivers, these switches exploit both the spatial and wavelength dimensions cost-effectively, thereby enabling high port counts.

Figures 1 and 2 illustrate the conventional tunable-laser-type and tunable-filter-type switch configurations, respectively [4]. A basic tunable-laser-type switch consists of *MN* wavelength-tunable transmitters, *MN* 1×*M* selectors, *MN M*×1 couplers, *M N*×1 couplers, *M* EDFAs, *M* 1×*N* arrayed-waveguide gratings (AWGs), and *MN* wavelengthfixed receivers. A basic tunable-filter-type switch consists of *MN* wavelength-fixed transmitters, *M N*×1 AWGs, *M* EDFAs, *M* 1×*N* splitters, *MN* 1×*M* splitters, *MN M*×1 selectors, *MN* tunable filters, and *MN* wavelength-fixed receivers. As common advantages of both configurations, connecting the space and wavelength-routing stages yields a port count that scales with the product *M*×*N*, and placing EDFAs at WDM aggregation points efficiently restores optical power and enables low-cost compensation of internal loss. Although various techniques have been explored to reduce internal loss and increase the scale, both conventional designs are now constrained by coupler-dominated and splitterdominated loss.

To achieve larger scale while preserving strictly non-blocking operation, we propose an architecture that combines the strengths of the tunable-laser design and the tunable-filter design, as shown in Fig. 3. In conventional designs, the received signal-to-noise ratio (SNR) is largely set by losses in the coupling and splitting network, and this accumulation worsens as *M* and *N* increase. Our design reorders the placement of components and introduces a star

![](_page_1_Figure_2.jpeg)

Fig. 1. Basic tunable-laser-type switch.

Fig. 2. Basic tunable-filter-type switch.

Fig. 3. Proposed switch.

coupler that performs coupling and splitting in a single element, which avoids additional cascaded loss and enables further scaling without sacrificing connectivity. This consolidation reduces per-path loss growth with M and N and increases the SNR margin for large fabrics. The switch comprises MN wavelength-tunable transmitters, MN  $1\times M$  selectors, MN  $M\times N$  star couplers, MN  $N\times 1$  selectors, M  $N\times 1$  AWGs for wavelength combining, M EDFAs, M  $1\times N$  AWGs for wavelength distribution, and MN wavelength-fixed receivers.

The switching operation proceeds as follows. A wavelength-tunable transmitter sends a signal to a  $1 \times M$  selector, which directs it to one of the  $M \times N$  star couplers. At the star coupler, up to M inputs are combined and the resulting WDM signal is broadcast to all  $N \times 1$  selectors connected to that coupler. Each  $N \times 1$  selector forwards one of up to N inputs to a combining AWG, which passes only the wavelength assigned to the intended output. Up to N wavelengths are then combined and amplified by an EDFA. A distributing AWG passes only the wavelength corresponding to each output port, and the signal is delivered to the designated receiver. In this way, any input can reach any output in a single hop while internal loss is mitigated by the revised placement and the star-coupler stage.

#### 3. Simulations

Computer simulations were carried out to assess the achievable port count of the proposed switch. Transmitters generated 32-Gbaud DP-QPSK (100 Gb/s), DP-8QAM (150 Gb/s), and DP-16QAM (200 Gb/s) signals. We assumed 96, 80, 64, 48, and 32 wavelengths on a 50-GHz grid in the C-band. The  $1\times M$  selector had an insertion loss of  $0.5\times\lceil\log_2 M\rceil$  dB and an extinction ratio of 35 dB. The  $M\times N$  star coupler had an insertion loss of  $10\times\log_{10}\{\max(M,N)\}+1$  dB. To capture a system-wide worst case, intra-band crosstalk was modeled by adding M-1 signals to the other input ports of the  $M\times N$  star coupler. The  $N\times 1$  selector had an insertion loss of  $0.5\times\lceil\log_2 N\rceil$  dB and an extinction ratio of 35 dB. The  $N\times 1$  AWG had an insertion loss of 5 dB and a 3-dB bandwidth of 26 GHz, with adjacent and non-adjacent crosstalk of -30 dB and -40 dB. The EDFA noise figure and output saturation power were 5 dB and 16 dBm. The  $1\times N$  AWG had the same insertion loss of 5 dB and the same 3-dB bandwidth of 26 GHz as the  $N\times 1$  AWG. The BER limit was set to  $10^{-2}$ , assuming forward error correction.

Figure 4 plots the maximum switch port count versus transmitter output power for each modulation format and wavelength count. As an example, with 0 dBm transmitter output power, the attainable switch sizes are 16,384×16,384 with 100 Gb/s DP-QPSK, 6,144×6,144 with 150 Gb/s DP-8QAM, and 4,096×4,096 with 200 Gb/s DP-16QAM. The corresponding total throughputs in a single switching layer are 1,638.4 Tb/s, 921.6 Tb/s, and 819.2 Tb/s, respectively.

![](_page_1_Figure_11.jpeg)

Fig. 4. The attainable port count versus transmitter power for each modulation format and wavelength count.

![](_page_2_Figure_2.jpeg)

## 4. Experiments

We conducted experiments to confirm feasibility. Figure 5 depicts the setup. An in-phase and quadrature (IQ) modulator driven by an arbitrary waveform generator modulated a continuous-wave (CW) output from a tunable laser to generate a 32-Gbaud 16QAM signal. A 32-Gbaud DP-16QAM signal was formed by a polarization-division-multiplexing (PDM) emulator composed of a polarization beam splitter, a delay element, and a polarization beam combiner. The signal was then split by a  $1\times2$  splitter: one tributary served as the target signal and the other as intraband crosstalk. The target-signal power at the switch input was set to 0 dBm with a variable optical attenuator (VOA), matching the simulation conditions.

The signal traversed a 1×64 selector (loss ~2.0 dB) and a 2×64 star coupler (loss ~20.5 dB), used as a surrogate for a 64×64 star coupler. Figure 6 shows the spectra before and after the 2×64 star coupler. Intra-band crosstalk, power-adjusted by a VOA, was injected at another input of the star coupler. The signal then passed through a 64×1 selector (loss ~2.0 dB), a 64×1 AWG (loss ~4.7 dB), and an EDFA. To emulate inter-band crosstalk, 63 non-target wavelengths were added at the other inputs of the 64×1 AWG, aggregating 64 wavelengths on a 50-GHz grid. The EDFA output saturation power was 16 dBm. Finally, after a 1×64 AWG (loss ~4.7 dB), the target signal was received by a digital coherent receiver. Figure 7 shows the BER measured for all wavelengths and an example of the recovered 16QAM constellation. All BER values met the 10<sup>-2</sup> target, in agreement with the simulation results, and the symbol states were clearly separated.

These proof-of-concept experiments, implementing a subset of the 4,096-port 819.2 Tb/s DP-16QAM configuration, confirm the effectiveness of the proposed approach.

## 5. Conclusion

We proposed a strictly non-blocking OCS that combines a space switch with a wavelength-routing switch and introduces a star coupler. The design reorders coupling and splitting so that a single star-coupler stage performs both, avoids cascaded loss, and preserves  $M \times N$  connectivity in one switching layer. EDFAs placed at WDM aggregation points restore power efficiently, enabling cost-effective scaling to high port counts. Simulations clarified the attainable port count and total throughput in a single switching layer: 16,384 ports with 100 Gb/s DP-QPSK for 1,638.4 Tb/s, 6,144 ports with 150 Gb/s DP-8QAM for 921.6 Tb/s, and 4,096 ports with 200 Gb/s DP-16QAM for 819.2 Tb/s. Experiments confirmed feasibility using 200 Gb/s DP-16QAM transmission. A prototype delivered 819.2 Tb/s in a single switching layer. Spatial parallelization can further multiply the total throughput without changing the switch topology.

Acknowledgment: JSPS/KAKENHI (JP24H00072 and JP25K01235) and JST/ACT-X (JPMJAX24M5).

### 6. References

- [1] S. J. Ben Yoo, J. Lightw. Technol. 40, 2214-2243 (2022).
- [2] F. Wang et al., IEEE Commun. Mag. 60, 90-96 (2022).
- [3] R. Urata et al., OFC, M2G.1 (2023).
- [4] K. Sato, J. Opt. Commun. Netw. 16, A1-A23 (2024).
- [5] G. Patronas et al., J. Opt. Commun. Netw. 17, A87-A95 (2025).
- [6] E. Honda et al., OFC, W1F.2 (2020).
- [7] R. Matsumoto et al., J. Lightw. Technol. 42, 1231-1241 (2024).
- [8] T. Mitsuya et al., J. Lightw. Technol. 43, 400-407 (2025).