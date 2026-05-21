# Ultra-Low Loss Compact SiP Polarization Compensator for CPO with an ELS

Aleksandar Nikic,1,†\* Weijia Li,1,† , Charles St. Arnault<sup>1</sup> , Santiago Bernal<sup>1</sup> , Benton Qiu<sup>1</sup> , Deng Mao<sup>1</sup> , Essam Berikaa<sup>1</sup> , Kaibo Zhang<sup>1</sup> , Codey Nackey<sup>1</sup> , Luhua Xu<sup>1</sup> , Max Zhang<sup>1</sup> , Ian Plant<sup>1</sup> , Alessandra Bigongiari<sup>2</sup> , Fabio Cavaliere<sup>2</sup> , Antonio D'Errico<sup>2</sup> , Luca Giorgi<sup>2</sup> , Stephane Lessard<sup>2</sup> , Roberto Sabella<sup>2</sup> , Stefano Stracca<sup>2</sup> , and David Plant<sup>1</sup>

† *Equal Contributions*

*<sup>1</sup>Department of Electrical and Computer Engineering, McGill University, Montreal, QC H3A 0E9, Canada ´ <sup>2</sup> Ericsson, 56124 Pisa, Italy*

*\*aleksandar.nikic@mail.mcgill.ca*

Abstract: We demonstrate a novel semi-deterministic SiP O-Band device, capable of compensating any ELS SOP from 1km distances, with an IL of 1.9-dB and PDL of 0.77 dB, enabling the ubiquitous use of ELS in CPO transceivers.

#### 1. Introduction

Co-Packaged Optics (CPO) has emerged as a promising packaging solution for next generation short-reach Ethernet nodes in data centers [\[1\]](#page-2-0) and for 6G Radio Access Networks (RAN) systems [\[2,](#page-2-1) [3\]](#page-2-2). External Laser Sources (ELS) are currently being standardized to supply the optical carrier for CPO [\[4\]](#page-2-3), as they are more accessible, easier to replace, and can relax the cooling requirements [\[2,](#page-2-1) [4,](#page-2-3) [5\]](#page-2-4). In data centers, as the distance between the ELS and transmitter is in the cm range, thus, polarization-maintaining fiber (PMF) is used [\[4\]](#page-2-3). However, the adoption of micro-ring modulator Silicon Photonics (SiP) based transceivers in data centers use mass Wavelength-Division Multiplexing (WDM), implying a sharp increase in the quantity of expensive PMF.

In RAN applications, the ELS is separated from the transceiver by distances between 0.5 km and 1 km, necessitating the use of single-mode fiber (SMF). If SMF is used for CPO products, single polarization compensation circuits have been demonstrated to mitigate the polarization-dependent loss (PDL) [\[6](#page-2-5)[–8\]](#page-2-6), and can even do so in WDM systems [\[9,](#page-2-7) [10\]](#page-2-8). However, Fig. [1](#page-0-0) shows that when the State of Polarization (SOP) from an ELS is scrambled at a 1 kHz rate by a Keysight N7788C Optical Compenent Analyzer (OCA), the mean PDL is 5.01 dB, without polarization compensation. With an already tight optical power budget in place for ELS in CPO, the adoption of previous polarzation compensators can be challenging, as their insertion losses (> 8 dB) can be larger than the PDL of a transceiver even if no polarization circuity is used.

<span id="page-0-0"></span>![](_page_0_Figure_11.jpeg)

Here, we report a solution to this problem–the demonstration of a compact,

novel, semi-deterministic polarization compensator that compensates any injected SOP from an ELS over 1 km of SMF, with an insertion loss of 1.9 dB and a mean PDL of 0.77 dB. As discussed below, the semi-deterministic operation mode eliminates an optimization parameter, trading insertion loss to reduce the tracking time.

### 2. PIC Architecture

The silicon PIC (Fig. [2](#page-1-0) c)) was fabricated in the commercial AMF foundry. As shown in Fig. [2](#page-1-0) a), the circuit is composed of a metal thermo-optic phase shifter (PS1), a doped-Si phase shifter (PS2), a polarization beam splitter (PBS), polarization beam rotator (PBR), and three monitoring photodiodes (MPD1-3). The PIC uses edge couplers (ECs) to couple light onto and out of the chip. De-embedding the EC loss, the total insertion loss of the polarization compensator was measured to be 1.9 dB. The polarization extinction ratio is measured to be 19 dB (Fig. [2](#page-1-0) b)). This is enabled by packaging the PIC onto a printed circuit board and connecting the electric inputs and outputs of the PIC via wire bonding to manage the DC and low-speed connections.

The input light, *Ein*, with an arbitrary SOP (i.e., excites both TE and TM modes) first propagates through PS1, inducing more propagation loss. However, based on [\[11\]](#page-2-9), PS1 exhibits distinct thermo-optic coefficients (TOCs) for the TE and TM modes. Thus, PS1 can introduce a phase difference between the two modes of *Ein*. PS1 features a 0.29 µm waveguide width, a 5 µm taper length, a 200 µm waveguide length, and a 2 µm metal heater width. This geometry reduces the modal propagation loss and provides the most power-efficient design for introducing a phase difference between the TE and TM modes [\[11\]](#page-2-9). The light then passes through a 10:90 splitter.

The PBS separates the TE and TM modal intensities, which MPD1 and MPD2, respectively detect. These photocurrents are proportional to the intensity ratio of TE and TM components of *Ein*, enabling the semi-deterministic operation of the device. The PBR converts the TE+TM light into TE light, where it is then split by a 50:50 splitter into two branches. The combination of these two branches (including PS2) and the 2x2 MMI forms an interferometer, where MPD3 and  $E_{out}$  serve as complementary outputs. Thus, minimizing the current from MPD3 maximizes  $E_{out}$ , thereby reducing the PDL of the device.

#### 3. Semi-Deterministic Working Principle

Similar to previous polarization compensator demonstrations [6–8, 12], each PS compensates either the phase or intensity mismatch of  $E_{in}$ , while a feedback PD (MPD3 in our device) permits the use of a numerical optimization algorithm. Due to the PBS, MPD1 and MPD2 can only measure the TE and TM intensity ratio of  $E_{in}$ . Thus, if PS2 is solely dedicated to compensating the intensity mismatch of  $E_{in}$ , it can be shown with Jones' vector analysis that the photocurrent ratio between MPD1 and MPD2 photocurrent can be used to determine the ideal analytical phase shift value for PS2, as seen below:

<span id="page-1-1"></span> $\phi_2 = 2 \arctan\left(\sqrt{\frac{I_2}{I_1}}\right) + \frac{\pi}{2} + 2\pi n \tag{1}$ 

Where  $\phi_2$  is the phase shift applied to PS2, the  $I_2/I_1$  ratio is extracted from the MPD2 and MPD1 current ratio, and n is an integer to ensure periodicity. If  $\phi_2$  is correct, only PS1 needs to be numerically optimized with MPD3 to mitigate the phase mismatch in  $E_{in}$ , creating a semi-deterministic mode of operation. Using Eq. 1 and a quasi-empirical phase-to-voltage mapping, an analytical  $\phi_2$  is mapped to a voltage value for PS2.

Fig. 2 b) shows a heatmap of the output optical power of the polarization compensator as a function of the voltages applied to PS1 and PS2 for a purely TM input SOP. The theorized (dotted line) and measured PS2 voltages (solid line) that maximize the output power of the device are plotted. A small 0.03 V discrepancy is observed, indicating that our mapping can optimize PS2 without significant augmentation.

As PS2 corrected the intensity mismatch, PS1 needs to correct the phase mismatch. Although both the TE and TM modes are excited in the waveguide, the difference in their TOC [11] allows PS1 to correct the phase mismatch through numerical optimization with MPD3. This enables the semi-deterministic mode of operation, as PS2 can be directly mapped, shortening the SOP compensation time.

#### 4. Experimental Setup

Fig. 2 c) shows the experimental setup used to measure the performance of our polarization compensator and optimization algorithm. A tunable 8.5 dBm laser was sent through 1 km of SMF. The injected SOP was varied by an OCA. To compensate the oncoming SOP, the phase shifters are controlled by a gradient descent optimization algorithm (based on [6]), with feedback from the MPD's, to maximize the output power of the PIC. To highlight the semi-deterministic nature of the polarization compensator, the algorithm is run with two different sets of starting values for PS1 and PS2. The "Randomized Starting Point" randomly sets both voltage values of PS1 and PS2. The "Optimized Starting Point" sets PS1 to 6 V (half the permissible range), and PS2 according to Eq. 1. Once our optimization algorithm finishes, we record the PDL using a powermeter.

#### 5. Polarzation Compensation Performance and Results

The performance of our semi-deterministic polarization compensator and algorithm were evaluated over two 10-hour measurement cycles. Figs. 3 a) and b) show the normalized output optical power and number of iterations that the optimization algorithm needed to converge for the "Optimized Starting Point" and the "Randomized Starting Point", respectively.

Under the semi-deterministic operation, Fig. 3 a) shows a mean measured PDL of 0.77 dB, a standard deviation of 0.4 dB, and a mode of -0.34 dB. The optimization algorithm iteration convergence is characterized by a mean of 9.74, a standard deviation of 10.44, a mean-absolute deviation (MAD) of 7.3, and a mode of 0.

<span id="page-1-0"></span>Without the semi-deterministic operation, Fig. 3 b) shows a mean measured PDL of 0.84 dB, a standard deviation of 0.4 dB, and a mode of -0.46 dB. The optimization algorithm iteration convergence is characterized by a

![](_page_1_Figure_15.jpeg)

Figure 2: a): Block diagram of the polarization compensating device (PCD). b) The optical power as a function of the phase shifters for a TM SOP. c) The experimental setup and an inset of the packaged SiP chip where the location of the  $725x330 \mu m^2$  is shown.

<span id="page-2-11"></span>![](_page_2_Figure_2.jpeg)

Figure 3: (a) Output optical power relative to the max recorded power during the test. (b) Number of iterations taken to converge during the test. Relevant statistics are displayed.

mean of 21.31, a standard deviation of 31.89, a MAD of 19.32 (removes outliers), and a mode of 5.

When comparing the two modes of operation of our polarization compensator, we see: (a): for the relative optical power measurements the semi-deterministic mode is more optimized as it skews closer to a smaller PDL, signified by a 9% and 35% reduction in mean and mode PDL, respectively; (b): the iteration convergence statistics (related to the SOP tracking rate) are greatly improved in every measured statistic if the device uses the semideterministic mode of operation, even when the outliers are removed (from MAD). These results show that the semi-deterministic mode of operation aids in eliminating an optimization variable, or phase shifter, for the polarization compensation process. This is best signified by the mode value of 0, which means that no numerical optimization took place. Further, 17.75% of all tested SOPs did not require optimization.

The SOP tracking time relies on both the number of voltage steps taken per iteration, and the number of iterations needed to converge. With two voltage steps taken per PS [\[6\]](#page-2-5) and the respective theoretical response times of PS1 and PS2 are 5.5 µs and 2.2 µs [\[13,](#page-2-12) [14\]](#page-2-13), each iteration consumes 15.4 µs. Multiplying this by the mean of 9.74 iterations, the tracking time can be estimated to be 150 µs. It was shown that a tracking time of 30 µs yielded an SOP scrambling rate of 22 krad/s [\[7\]](#page-2-14), meaning the device can support a scramble rate of ≈ 4.4 krad/s, which is consistent with prior reports [\[6,](#page-2-5) [8\]](#page-2-6).

The two outcomes from the work are: (1): Utilizing a PS with a different TOC for the TE and TM modes leads to a simplified semi-deterministic polarization compensator, which improves the SOP tracking rate and achieved PDL; and (2): Combining the largest measured PDL (1.8 dB) and the insertion loss (1.9 dB) of the polarization compensator, the total loss (3.70 dB) is 1.31 dB smaller than the measured PDL from an uncompensated MZM (Fig. [1\)](#page-0-0). These results show that if this compact, low-loss, and novel semi-deterministic polarization compensator is used in a CPO solution, any SOP from an ELS can be successfully compensated for in real-time, without PMF.

## 6. Conclusion

Our work aims to enable the use of ELS in CPO, without using PMF, for next-generation tranceivers in data centers and 6G RANs. To this end, we demonstrated a novel SiP O-Band polarization compensator, using only two-phase shifers, that can connect an ELS to a transceiver up to a distance of 1 km of SMF. We further achieved a mean PDL of 0.77 dB, an IL of 1.9 dB, showed that the combined losses are less than that of an uncompensated MZM.

## References

- <span id="page-2-0"></span>1. M. G. Saber *et al.*, "Physical Layer Standardization for AI Data Centers: Challenges, Progress and Perspectives," *IEEE Network*, 2025.
- <span id="page-2-1"></span>2. A. Tartaglia *et al.*, "Perspectives for co-packaged optics in Radio Access Networks," *ICTON*, 2023.
- <span id="page-2-2"></span>3. F. Cavaliere *et al.*, "Integrated Photonics for Radio Access: Where We Are," *Journal of Lightwave Technology*, 2025.
- <span id="page-2-3"></span>4. OIF, "Co-Packaging Framework Document," https://www.oiforum.com/wp-content/uploads/OIF-Co-Packaging-FD-01.0.pdf. 2022.
- <span id="page-2-4"></span>5. C. Minkenberg *et al.*, "Co-packaged Datacenter Optics: Opportunities and challenges," *IET Optoelectronics*, 2021.
- <span id="page-2-5"></span>6. A. Nikic *et al.*, "A WDM Capable SiP Polarization Compensator That Isolates the Carrier Laser," *Journal of Lightwave Technology*, 2025.
- <span id="page-2-14"></span>7. W. Liu *et al.*, "High-Speed Silicon Integrated Polarization Stabilizer Assisted By a Polarimeter," *Journal of Lightwave Technology*, 2022.

- <span id="page-2-6"></span>8. Y. Zhao *et al.*, "Dual-Polarization IMDD System for Data-Center Connectivity," *Journal of Lightwave Technology*, 2025.
- <span id="page-2-7"></span>9. A. Nikic *et al.*, "Demonstration of the WDM Performance of a SiP Polarization Compensator and Modulator operating at 300 Gbps in the O-band Over 2 km," in *OFC 2025*.
- <span id="page-2-8"></span>10. A. Nikic *et al.*, "Polarization Agnostic Frequency-Comb WDM Transmission Enabling Net 1.6 Tbps," in *ECOC 2025*.
- <span id="page-2-9"></span>11. W. Li *et al.*, "Broadband Polarization-Insensitive Thermo-Optic Switches on a 220-nm Silicon-on-Insulator Platform," *IEEE Photonics Journal*, 2022.
- <span id="page-2-10"></span>12. A. Nikic *et al.*, "A SiP O-Band Transmitter Implementing Polarization Compensation Enabling Remote Operation of the Carrier Laser," in *OFC 2025*.
- <span id="page-2-12"></span>13. W. Li *et al.*, "Silicon Photonic Broadband Polarization-Insensitive Switch Based on Polarization-Mode Diversity Conversion," *Opt. Letters*, 2023.
- <span id="page-2-13"></span>14. M. Jacques *et al.*, "Optimization of Thermo-Optic Phase-Shifter Design and Mitigation of Thermal Crosstalk on the SOI Platform," *Opt. Express*, 2019.