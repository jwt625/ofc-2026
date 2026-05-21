# **Ring resonator-based dynamic controller for precise wavelength separation of a DWDM laser source**

**Jahnavi Sharma1\* , Cooper Levy1\* , James Jaussi<sup>1</sup> , Zhe Xuan<sup>1</sup> , Duanni Huang<sup>2</sup> , Haisheng Rong<sup>2</sup> , Dan Lake<sup>1</sup> , Prathapa Puttaswamy<sup>1</sup> , Ranjeet Kumar2\***

*1 Intel Corporation, 2111 NE 25th Ave., Hillsboro, OR 97124, USA, Intel Corporation, 2200 Mission College Blvd., Santa Clara, CA 95054, USA \*These authors contributed equally to this work Author e-mail address: jahnavi.sharma@intel.com*

**Abstract:** We demonstrate a ring-resonator based controller that provides simultaneous and continuous control of the wavelength spacing of a distributed feedback laser array maintaining it within 201±4 GHz in the presence of ambient variations.

## **1. Introduction**

Recently, dense wavelength division multiplexing (DWDM) for optical transceivers (OTRX) that dramatically increases the per-fiber data rate of co-packaged silicon photonic interconnects has been shown [1-3]. Uniform power and precise spacing (Δλ) are critical for multi-wavelength laser (MWL) sources in DWDM. A 16-λ Distributed Feedback (DFB) laser array spaced at 200 GHz (Δλ) with ~16 GHz spacing error (σstd-dev) was shown in [4] and is compliant with the CW-WDM multi-source agreement specifying < 50 GHz grid spacing error [5]. However, such several tens of GHz of error between adjacent carriers will still limit the data rate per-λ due to channel crosstalk [6,7]. Another potential advantage of lower error in Δλ is simplifying the alignment of ring resonator-based receiverside demultiplexers [3,7]. If the incoming DWDM signal is on a fixed Δλ-grid, the periodic demux array can be collectively tuned [7], potentially reducing the complexity and tuning time of the ring thermal control logic.

Mode-locked and comb lasers [8,9] can enable precise Δλ defined by a single cavity, but have lower output power and greater power variation across their spectrum than DFB arrays. In this work, we demonstrate an electrooptic controller (Fig. 1) which aligns and actively locks the DFB array we presented in [10] to a 201±4GHz Δλ-grid defined by the free-spectral range (FSR) of a micro-ring resonator (MRR). The resulting MWL source provides the power uniformity of a DFB array with <2% spacing error without sub-nm precision in fabrication. Any residual power non-uniformity in the array can be corrected on a per-λ basis with a dedicated integrated optical amplifier [11] or variable attenuator.

An important feature of the proposed control scheme is to simultaneously and continuously control the λ of all the lasers in the array in the presence of external variations. To distinguish between lasers with all simultaneously incident on the same ring resonator, each laser is modulated (marked) with a unique tone to identify and continuously correct any misalignment from the desired Δλ-grid.

# **2. Wavelength-spacing controller description**

The eight laser outputs are combined and routed to the ring-based controller. A 60 µm radius MRR with 200 GHz FSR fabricable with ±3 GHz accuracy (due to its large feature size) defines a temperature invariant Δλ-grid. The controller objective is to align λ1-8 of all eight lasers (L1-8) to consecutive ring resonant peaks.

![](_page_0_Figure_12.jpeg)

Fig. 1. Block diagram of ring resonator-based wavelength-spacing controller for multi-λ DFB array.

First, one of the MRR peaks is aligned to laser L<sup>1</sup> by tuning the ring heater as shown in Fig. 2(a). Then the other lasers (λk=2-8) are locked to the resonant peak closest to their λ<sup>k</sup> by tuning the respective laser bias current. Given less than tens of GHz of native spacing error, each laser will lie within the capture range of the unique and consecutive MRR peaks. This controller does not define the absolute lasing λKfor any laser, but by locking adjacent lasers to consecutive ring resonances it reduces the error in Δλ of the DFB array in [10] to <2%.

If a single laser is aligned to an MRR peak, the power absorbed in the MRR and the photocurrent (iPD) at the drop port Ge photodiode (PD) is maximized. However, with all lasers incident on the ring, maximizing the total dc photocurrent (iPD,DC) does not indicate an individual laser's misalignment from the desired Δλ-grid. To distinguish among the wavelengths, each laser L<sup>k</sup> is intensity modulated with a unique square wave of frequency fK, by an inline Si p-i-n junction modulator in the laser output to the controller (Fig. 1).

In Fig. 1, all of the laser power is sent to the controller. However, to use this controller with a DWDM OTRX, the laser outputs would be split between the controller (<10% power) and the desired application (e.g. >90% power to the 8-λ OTRX). By not modulating the lasers directly, the power split (>90%) to the OTRX is marker tone free. Fig. 2(b) shows the photonic IC (PIC) die with the laser array, p-i-n modulators and 60 um radius MRR. With all the laser power being routed to the MRR, we have included a per-λ variable optical attenuator (VOA) in the path to the controller and used this to equalize the laser power after the lasers are locked to the desired Δλ-grid while simultaneously mitigating ring self-heating. Semiconductor optical amplifiers (SOA) could instead be integrated [11] in the (>90%) path to the OTRX in future implementations to further equalize laser power.

The drop-port PD current consists of the dc current iPD,DC, and ac photocurrent (iPD,AC) from the intensity modulated lasers. iPD,AC has content at the fundamental tones f<sup>K</sup> (noted as iPH,K) and their harmonics, as well as mixing terms due to PD and other nonlinearities. The tones f<sup>K</sup> are planned to ensure no overlap of harmonics or intermodulation terms (≤ 3rd order) with any fundamental, and the fundamental component iPH,K is a unique indicator of the detuning ε<sup>K</sup> of laser L<sup>K</sup> from its closest resonance λ0K (ε<sup>K</sup> = λK- λ0K) (Fig. 2(c)). Each iPH,k can be detected by digitizing the photocurrent iPD,AC and analyzing its spectral content, or by using a dedicated lock-in amplifier (LIA<sup>K</sup> in Fig. 1). The wavelength error ε<sup>K</sup> for each laser can therefore be monitored continuously using the same MRR.

![](_page_1_Figure_6.jpeg)

Fig. 2. (a) 200±15 GHz spaced DFB array is tuned to align lasers with ring resonances, (b) PIC with optical components for λ-spacing controller, (c) iPH,K at f<sup>K</sup> measures laser L<sup>K</sup> detuning from ring (εK) (shown for K = 2), (d) slope-based alignment to ring peaks.

To align any laser to the closest ring resonance using its corresponding iPH,K, we employ slope-minimization as shown in Fig. 2(d). Based on the detuning of laser L<sup>k</sup> from the ring peak (εK), the amplitude of iPH,K at f<sup>K</sup> follows the MRR Lorentzian absorption spectrum closely. The slope at an absorption peak is zero. Therefore, a non-zero slope is a metric for εK, where the sign indicates either λ<sup>K</sup> < λ0K, or λ<sup>K</sup> > λ0K.

Slope-minimization enables laser λ alignment without a-priori knowledge of the laser power, and allows the laser bias current to be used as a laser wavelength control knob. For the DFB array in [10], correcting the Δλ-grid error can require a large change in the bias current with ~3 dB power variation, and aligning the laser to the ring by locking to an absolute iPH is not viable. Our slope-based locking method and algorithm are agnostic to power variation from laser current bias tuning.

# **3. Measured Results**

We demonstrate the proposed Δλ-controller with the PIC wirebonded to a PCB and external equipment to provide bias and control (Fig. 1). No TEC or heat sinks are included in the experiment. The laser on the PIC is an 8 λ III-V/Si hybrid DFB array [10] biased at 50 mA initially with 200±15 GHz spacing. The measured FSR of the 60 µm radius ring is 201 GHz , and is within the ±3 GHz expected spread due to fabrication. Eight marker tones (fK) at 25.3, 29.1, 31.2, 33.5, 37, 39.7, 44, 46.5 kHz modulate lasers 1-8 respectively. The control loop is closed using external lock-in amplifiers and the loop bandwidth is low. This bandwidth can be expected to improve significantly when paired with a CMOS based electronic IC for control.

To estimate the slope, a square wave of ±0.5 mW (ΔH) is applied to the ring heater (Fig. 2(d)) and is limited by the 0.2 mA resolution of the external current module. The resulting change in the photocurrent iPH,K at f<sup>K</sup> (from laser LK) is recorded from the output voltage change (ΔVLIA,K) of the corresponding LIA. For this measurement, laser L<sup>5</sup> in the center of the array is used as reference and its current stays at 50 mA. Based on ΔVLIA,5, the current to the ring heater is adjusted to drive the slope of VLIA,5 (or iPH,5) to zero, aligning an MRR absorption peak to laser L5. The other LIA outputs simultaneously adjust the bias current of lasers L1-4, 6-8 to also drive the slopes of their LIA outputs to '0'. The MRR heater current and laser bias are shown in Fig. 3(a). The relative spacing of lasers 1-8 are shown for the same time span in Fig. 3(b). Figs. 3(c) and (d) show the free-running spectrum and the spectrum at steady state with the laser array aligned to a 201 GHz ring FSR with ±4 GHz error due to finite loop gain and tracking bandwidth. The free running DFB array has < 2dB power variation without any VOA equalization. The per-λ VOA is adjusted to equalize the power of the Δλ-locked DFB array to achieve <2 dB variation as well.

![](_page_2_Figure_4.jpeg)

Fig. 3(a) Evolution of heater and laser bias as the controller locks the DFB array to a Δλ-grid defined by the ring FSR, (b) frequency spacing of the 8-laser array, and (c) initial free-running spectrum and steady state spectrum at 40 min, both with < 2dB power variation.

We have demonstrated a laser wavelength spacing controller for DWDM applications that aligns an 8-λ DFB array with 200±15 GHz nominal spacing to the 201±4 GHz Δλ-grid defined by the temperature-invariant FSR of a 60 µm radius MRR. We modulated each laser with a unique frequency, so the misalignment is uniquely identifiable when all lasers are incident on a single ring. Our approach eliminates any need for time-interleaved control when using a ring resonator with multiple lasers simultaneously, and enables continuous control of all lasers in the presence of ambient variations.

## **4. Acknowledgement**

We acknowledge Trang Nguyen and Denise Souza for lab support and PCB design, and Intel Fab11x for chip fabrication.

## **5. References**

- [1] C. Levy *et al*., "8-λ × 50 Gbps/λ heterogeneously integrated Si-Ph DWDM transmitter*,*" in IEEE J. Solid-State Circuits*,* **59** (3), (2024).
- [2] P. Bhargava *et al*., "A UCIe optical I/O retimer chiplet for AI scale-up fabrics," Optical Fiber Communications Conference (2025).
- [3] Z. Xuan *et al*.,"A 256 Gbps heterogeneously integrated SiPh microring-based DWDM receiver suitable for in-package optical I/O," IEEE Symp. VLSI Technol. Circuits (2023).
- [4] M. Sysak *et al*., "Multi-wavelength sources for Optical IO co-packaged optics," Optical Fiber Communications Conference (2024).
- [5] https://cw-wdm.org
- [6] J. Sharma *et al*., "Silicon photonic microring-based 4×112 Gb/s WDM transmitter with photocurrent-based thermal control in 28-nm CMOS," in IEEE J. Solid-State Circuits, **57** (4), (2024).
- [7] M. Raj *et al*., "A 0.96pJ/b 7×50Gb/s-per-fiber WDM receiver with stacked 7nm CMOS and 45nm silicon photonic dies," IEEE ISSCC (2023). [8] S. Liu *et al*., "High-channel-count 20  GHz passively mode-locked quantum dot laser directly grown on Si with 4.1  Tbit/s transmission
- capacity," Optica 6, 128-134 (2019) [9] B. Corcoran *et al*., "Overcoming low-power limitations on optical frequency combs using a micro-ring resonator," Optical Fiber Communications Conference (2020).
- [10] D. Huang *et al*., "8-channel hybrid III-V/silicon DFB laser array with highly uniform 200 GHz spacing and power," ISLC (2021).
- [11] S. Liu *et al*., "Silicon photonics DWDM transmitter with heterogeneously integrated multiwavelength DFB laser and SOA," Optical Fiber Communications Conference (2025).