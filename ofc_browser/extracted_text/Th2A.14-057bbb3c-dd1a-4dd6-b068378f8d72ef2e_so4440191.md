# Record-High 90-GHz Silicon Microring Modulator with Compact RLC Modeling and 224-Gb/s PAM4 Operation toward Co-Packaged Optics Integrations

Ming-Wei Lin<sup>1\*</sup>, Ching-Wei Peng<sup>1</sup>, Hsiang-Chih Kao<sup>2</sup>, Pei-En Huang<sup>2</sup>, Hann-Huei Tsai<sup>1</sup>, Ying-Zong Juang<sup>1</sup>, Ming-Chang Lee<sup>2</sup>

<sup>1</sup>National Institutes of Applied Research Taiwan Semiconductor Research Institute, 300091, Hsinchu 300, Taiwan <sup>2</sup>Institute of Photonics Technologies and Dept. of Electrical Engineering, National Tsing-Hua University, 300044, Hsinchu, Taiwan \*mwlin@niar.org.tw

**Abstract:** A high-speed silicon microring modulator with inductive and wavelength tuning achieves a 90-GHz EO bandwidth and 224-Gb/s PAM4 operation, validated by compact RLC modeling and experiment for next-generation CPO interconnects.

#### 1. Introduction

Silicon photonics has emerged as a key enabler for high-speed optical transceivers due to its scalability and CMOS compatibility. Among various modulation schemes, the silicon microring modulator (MRM) offers compact footprint, low drive voltage, and wavelength multiplexing capability, making it a promising candidate for next-generation short-reach interconnects. However, achieving both high modulation efficiency and wide electro-optic (EO) bandwidth remains challenging due to trade-offs between photon lifetime and junction capacitance [1].

In this work, we present a silicon microring modulator fabricated on the imec iSiPP200 platform with a 220 nm silicon device layer and two-metal interconnect process. Through optimized doping, electrode layout, and parasitic extraction, the device demonstrates a 3 dB EO bandwidth of 90 GHz and supports 224 Gb/s PAM4 optical transmission without equalization. These results highlight the potential of MRM-based transceivers for energy-efficient optical I/O and co-packaged photonics applications.

# 2. Si MRM Equivalent Circuit Model and Small-Signal Electro-Optic Transfer Function

![](_page_0_Picture_10.jpeg)

Fig. 1. (a) Equivalent parasitic component circuit of the silicon MRM, illustrating pad capacitance  $C_{pad}$ , interconnect inductance  $L_{int}$ , and substrate resistance  $R_{sub}$ . (b) Junction circuit model including series resistance  $R_{sp}$  and  $R_{sn}$ , junction capacitance  $C_{j}$ , and silicon parasitic elements  $R_{si}$  and  $C_{si}$ . (c) Optical field interaction diagram showing the coupled-mode dynamics between input  $S_{in}(t)$ , circulating field a(t), and throughport output  $S_{thru}(t)$ , with intrinsic and coupling lifetimes  $\tau_l$  and  $\tau_e$ .

The equivalent circuit parameters of the silicon microring modulator (MRM) were extracted and verified through both frequency-domain simulation and experimental measurement. The optical resonance fitting based on Equation 1:

$$\left| \frac{S_{thru}}{S_{in}} \right|^2 = \left| \frac{j(\omega_{in} - \omega_r) + 1/\tau_l - 1/\tau_e}{j(\omega_{in} - \omega_r) + 1/\tau_l + 1/\tau_e} \right|^2 \tag{1}$$

To analyze the high-frequency behavior of the silicon microring modulator (MRM), the device is modeled with three lumped sections: Fig. 1a the parasitic metal/via network, Fig. 1b the PN junction, and Fig. 1c the optical conversion element. Using small-signal analysis, the junction voltage V<sup>j</sup> is linked to the optical resonance detuning Δ(t) = − () via the electro-optic coefficient k = ωr/<sup>g</sup> (∂eff / ∂Vj). The derived transfer function H(s) = ΔOthru(s)/Vj(s) maps to an equivalent RLC circuit, correlating the RC-limited electrical response with photonlifetime optical dynamics for bandwidth prediction and circuit-level co-simulation. By introducing a dynamic detuning term Δ(t) and linearizing the intracavity field a(t), the optical through-port response can be expressed as

$$H(S) = \frac{\Delta O_{thru}(S)}{V_j(S)} = \frac{4}{n_g} \cdot \frac{\partial n_{eff}}{\partial V_j} \cdot \frac{\omega_r \Delta \tau_e}{\Delta^2 + \frac{1}{\tau^2}} \cdot \frac{S + \frac{2}{\tau_l}}{S^2 + \left(\frac{2}{\tau}\right)S + \left(\Delta^2 + \frac{1}{\tau^2}\right)}$$
(2)

Equation 2 describes the interaction between carrier modulation and photon-lifetime-limited resonance. Mapping H(s) to an equivalent RLC network links τ<sup>l</sup> and τ<sup>e</sup> to the reactive and resistive elements, providing a compact circuitbased view of EO bandwidth and resonance enhancement for high-speed MRM design.

## **3. Results and Discussion**

![](_page_1_Figure_6.jpeg)

Fig. 2. (a) Measured and simulated transmission spectra of the silicon microring resonator showing strong agreement between experiment and theory, with fitted lifetimes <sup>l</sup> and e; (b) Simulated EO frequency responses with inductive-peaking enhancement under different int values; (c) Simulated wavelength-dependent EO response of the third-stage equivalent circuit, highlighting resonance peaking variation from O\_–3 dB to O\_–8 dB detuning; (d) Extracted equivalent-circuit parameters (G, R1, C, L) showing systematic wavelength dependence consistent with the optical–electrical coupled model; (e) and (f) Experimental setup for EO response measurement and optical eye diagram; (g) Measured 200-224 Gb/s PAM4 optical eye diagram with TDECQ = 1.58 dB and 2.94dB, demonstrating the high-speed performance of the proposed microring modulator.

Fig. 2a shows the measured and simulated transmission spectra of the microring resonator, revealing a clear resonance dip with strong experiment–theory agreement. Fitting based on Equation 1 yields intrinsic and external lifetimes of = 8.7 × 10⁻¹² s and = 9.01 × 10⁻¹² s. The 5-µm-radius microring exhibits eff = 2.5112 @ –2 V to 2.51113 @ –0.5 V, FSR = 19.5 nm, <sup>g</sup> = 3.95, and amplitude/coupling coefficients of 0.95305 and 0.95105, respectively. The fitted model accurately reproduces the loaded Q-factor and extinction ratio, confirming the extracted lifetimes describe both intrinsic loss and bus-waveguide coupling.

Fig. 2b shows the simulated EO frequency response of the silicon microring modulator with inductive-peaking design. The equivalent network includes two parasitic stages and the optical conversion branch. The first and second stages use pad = 4.35 fF, int = 1 Ω, ox = 0.11 fF, sub = 3893 Ω, c-c = 4 fF, si = 1380 Ω, si = 55 fF, <sup>j</sup> = 19.3 fF. As int increases from 130 pH to 350 pH, the response transitions from a smooth RC-limited roll-off to a distinct resonance-peaking shape, where proper int optimizes bandwidth while maintaining damping stability.

Fig. 2c shows the simulated third-stage EO response, exhibiting wavelength-dependent resonance behavior. As the detuning shifts from O\_–3 dB to O\_–8 dB, the response changes from flat to peaked, with bandwidth and gain governed by the optical–electrical coupling of the RLC circuit. Using parameters derived from prior analytical formulations [2], the fitted circuit shows R₂ ≈ 10 kΩ, R₁ decreasing from 10.96 kΩ to 2.20 kΩ, nearly constant L ≈ 45.15 nH, and C increasing from 0.395 fF to 1.97 fF. The EO gain G rises from 2.47×10⁻⁶ to 9.48×10⁻⁶, confirming that proper optical detuning balances bandwidth enhancement and stability for high-speed operation.

Fig. 2d compares the measured and simulated electro-optic (EO) frequency responses of the silicon microring modulator (MRM). The experimental data (black line) agree well with the simulated response (red circles) based on the equivalent-circuit model with an inductance int = 180 pH and an optical detuning bias of −6 dB. The simulated curve reproduces the resonance-peaking behavior and high-frequency roll-off observed in measurement, reflecting the interplay between intrinsic–extrinsic photon lifetimes and electrical parasitic effects. The measured −3 dB EO bandwidth reaches approximately 90 GHz, verifying that the inductive-peaking design effectively extends the modulation speed of the Si MRM.

Fig. 2e and 2f illustrates the experimental setup used for characterizing the high-speed electro-optic response and eye-diagram performance of the silicon microring modulator (MRM). Due to the extreme modulation bandwidth approaching 90 GHz/224 Gb/s, the measurement is sensitive to cable and connector losses as well as the noise floor of the RF instrumentation. Therefore, careful noise calibration and averaging are required to obtain reliable frequency-response data. In addition, a thermo-optic wavelength-tuning and 99:1 coupler control loop is implemented to stabilize the MRM resonance during measurement, ensuring consistent optical alignment and minimizing thermal drift effects.

Fig. 2g shows the measured optical eye diagram of a 200-224 Gb/s PAM4 signal obtained from the same device biased at −6 dB detuning. The acquisition was performed using a high-speed sampling oscilloscope with a Symbol Error Rate (SER) of 4.8 × 10⁻⁴, ensuring improved signal-to-noise ratio and measurement stability. The clear and symmetric PAM4 eyes confirm the device's excellent high-speed modulation capability, achieving a transmitter dispersion eye closure (TDECQ) of 1.58 dB/2.94 dB and an outer optical modulation amplitude (OMA) of 5.63 mW. These results verify that the co-optimized electro-optic design enables stable > 200 Gb/s-per-lane operation with low distortion and sufficient margin for digital equalization.

### **4. Conclusion**

This work represents a significant advancement in the design and modeling of high-speed silicon microring modulators (MRMs). A comprehensive equivalent-circuit framework was developed to unify parasitic effects, junction dynamics, and wavelength-dependent electro-optic conversion, accurately reproducing both resonance characteristics and high-frequency modulation behavior. Through inductive design and wavelength tuning mechanisms, the modulation bandwidth was substantially enhanced, achieving a remarkably high 3-dB EO bandwidth of ~90 GHz with excellent flatness and stability. High-speed transmission measurements further confirmed the generation of a 200-Gb/s PAM4 optical signal with a TDECQ of 1.58 dB, showing clear and symmetric eyes without equalization. These results demonstrate outstanding electro-optic performance and mark a major step toward ultra-high-speed, low-power silicon photonic transceivers for next-generation 200–400 Gb/sper-lane optical interconnects.

### **5. References**

[1] H. Li et al., "A 3-D-Integrated Silicon Photonic Microring-Based 112-Gb/s PAM-4 Transmitter With Nonlinear Equalization and Thermal Control," IEEE JSSC, VOL. 56, No. 1 (2021).

[2] H. C. Kao et al., "Study of Electrical and Optical Peaking of Si Ring Modulators for Tailoring Modulation Band," IEEE Photonics Journal, VOL. 15, No. 3 (2023).