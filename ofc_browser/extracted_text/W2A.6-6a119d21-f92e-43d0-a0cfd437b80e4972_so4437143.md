# **Encoder-Decoder Codesign of Lightweight 3D Surface Profiler via Integrated Photonic Sampler**

**Yizhi Wang1,† , Ziyao Zhang1,† , Chunhui Yao1,2 , Huiyu Huang1 , Wanlu Zhang1 , Ting Yan2 , Liang Ming2 , Yuxiao Ye2 , Richard Penty1 , Qixiang Cheng1,2,\***

> <sup>1</sup>Electrical Engineering Division, Department of Engineering, University of Cambridge, UK <sup>2</sup>GlitterinTech Limited, Xuzhou, China Author e-mail address[: qc223@cam.ac.uk;](mailto:qc223@cam.ac.uk) †These authors contributed equally.

**Abstract:** Deep learning enables geometric sensing for efficient profiling applications. We present a surface profiler based on a codesigned encoder-decoder pair consisting of reconfigurable integrated sampler and 1D-CNN, achieving ~17µm vertical and ~30µm lateral accuracy, respectively. © 2025 The Author(s)

# **1. Introduction**

Fast and accurate high-resolution 3D surface topography is widely applicable to industrial processes for quality checking and characterization [1]. However, commonly used interferometric techniques conventionally involve bulky benchtop set-ups and the requirement for a reference arm. These restrictions limit the potential for their transfer to insitu or on-the-fly portable measurement devices. Unlike the traditional optical spectrum-based sensing workflow that involves sampling-preprocessing-reconstruction-postprocessing-identification, geometric sensing [2] encompasses a class of sensing techniques that channels a direct sampling-identification pathway with the aid of deep learning. With the selection of a compatible encoder (sampler)-decoder (identifier) pair (Fig. 1(b)), optical information related to a physical parameter can be efficiently extracted without the need to reconstruct the spectrum first.

 In this paper, we present a fast and robust 3D surface profiling system for rapid identification while eliminating the requirement of a reference arm in traditional interferometric methods. The optical encoder is based on a reconstructive micro-ring resonator (MRR) sampler; and the decoder is a 1D-CNN network. We experimentally demonstrated thickness identification for a slow changing slope sample achieving thickness prediction accuracy of 17.5 µm. The trained profiler is used for surface pattern identification of a complex emblem shape, resulting in lateral feature identification as small as ~30 µm in a grid scan. Our codesigned profiling system demonstrates the importance of creating a compatible encoder-decoder pair and the potential of next-generation data-driven sensing devices.

![](_page_0_Figure_9.jpeg)

Fig.1 The concept of deep sensing profiler and experimental setup. (a) The experimental setup of the system. (b) The deep sensing workflow consisting of the collection, encoding, and decoding stages. (c) The principle of a pseudo-random encoder to extract maximum information from the spectrum. (d) The decoder network consisting of 1D-CNN layers and fully connected layers.

![](_page_1_Figure_2.jpeg)

Fig.2 Encoder and designs. (a) The sampler is based on six cascaded MRRs, with its packaging shown. (b) The choice of six MRR stages is a good balance between encoding complexity (from more stages) and fidelity degradation (also from more stages). (c, d) The six rings' transmission in (c) combine for a pseudo-random transmission matrix in (d).

# **2. Experimental Setup and Photonic Encoder Design**

The optical system can be roughly divided into two parts: the detection system and the encoder system. In the detection system, a super luminescent diode (SLD) is used as the light source. Lenses and stepper motors control the scanning across the sample. After the light is reflected by the sample, it enters the encoder (a reconfigurable cascaded MRR sampler), the transmission reading is recorded by a photodetector (PD) (Fig. 1(a-c)). For the training stage, a 50:50 splitter diverts half of the light to a benchtop spectrometer for comparison. In the testing stage, this path connected to the spectrometer is omitted and only the integrated sampler's output is detected. The packaging and enlarged picture of the reconfigurable profiler is shown in Fig. 2(a).

 The encoder-decoder strategy creates a mapping between the function spaces of the sample's reflected spectrum and the physical parameter (thickness). The ideal encoder should extract maximum information out of the original sample's reflected continuous spectrum, pointing to a random kernel given the finite detection kernel size. However, the trade-off is naturally the repeatability for commercial and industrial applications. Consequently, a pseudo-random kernel based on the cascading of standard components (Fig. 1(c)) is considered a good balance between information richness and controllability[3, 4].

 We chose varying MRRs as the building component of our sampler [5]. The information richness grows with lower cross-correlation, which can be acquired with an increased number of component stages. However, this shouldn't be a brute force approach as the error accumulation from hardware control deviation can quickly accumulate and undermine the user's interpretation of the overall transformation, leading to failed training [6]. Based on our theoretical analysis, a six-stage system with three phase tuning states for each MRR offers the overall best balance between encoding complexity and robustness (resilience to noise and error) (Fig. 2(b)). This encoder design reflects in the 729 pseudo-random channels as shown in Fig. 2(c) and 2(d). Since the only feature pending prediction is the sample thickness (feature size of 1), it creates an oversampling scenario (729 ≫ 1), allowing for the neural network to extract the underlying physical correlation.

# **3. Decoder Training and Results**

Decoder construction is equally important as the encoder design for physical parameter prediction. Unlike most modern deep learning tasks where the underlying physical interpretation between encoder and decoder is unclear, we

![](_page_2_Figure_2.jpeg)

Fig.3 Decoder results. (a) The decoder shows good performance convergence for both the training and testing process. (b) Applying the system as a surface profiler to predict complicated emblem shape of a lion.

have taken a systematic approach to the encoder design for the pseudo-random kernels. An incremental change in control setting for two successive channels should result in traceable variation between PD readings with physical interpretation for the change, suggesting a good fit of convolutional networks (Fig. 1(d)) as the decoder foundation. Our interpretation is validated via decoder model comparison (shown in Table 1) by conducting training and testing on a 3D-printed slope sample [7]. The optimized network contains three convolutional layers and three fully connected layers. 1D-CNN decoder training on the slow-varying sample yields good converging results (Fig. 3(a)). Testing the profiler on another 3D-printed slope structure reveals testing accuracy of ~17µm vertically (thickness).

Table 1. Performance comparison between different decoders

| Model     | 1D-CNN | LNN[8] | XGBoost[9] | Ensemble GP[10] |
|-----------|--------|--------|------------|-----------------|
| RMSE (µm) | 17.49  | 31.64  | 28.76      | 49.95           |

 The trained surface profiler is then used for a grid scan of a complex 3D-printed emblem shape of a lion (Fig. 3(b)), the pattern can be clearly identified with the scan. Lateral features as small as 30 µm are identifiable (around the face of the lion), illustrating the system's good accuracy in both vertical (thickness) and lateral (pattern) measurements.

# **4. Discussion, Conclusion and Outlook**

We demonstrated physically informed encoder-decoder construction for fast surface profiling with integrated photonic sampler and 1D-CNN. The vertical and lateral measurements show good performances. Performances can be further improved with higher precision mechanical control systems and higher quality free-space optics components (for reduced focal size on sample). The system's performance highlights the potential of geometric sensors based on nextgeneration miniature photonic samplers for widened application scenarios and portable devices' commercialization.

# **5. Acknowledgement**

This work was supported by the European Union's Horizon 2020 research and innovation programme, project INSPIRE (101017088), and UK EPSRC, project QUDOS (EP/T028475/1).

# **References**

- [1] Y. Shimizu, L. C. Chen, D. W. Kim, X. Chen, X. Li, and H. Matsukuma, "An insight on optical metrology in manufacturing," *Meas. Sci. Technol.*, Oct. 2020, doi: 10.1088/1361-6501/abc578.
- [2] S. Yuan *et al.*, "Geometric deep optical sensing," *Science*, vol. 379, no. 6637, p. eade1220, Mar. 2023, doi: 10.1126/science.ade1220.
- [3] C. Yao, K. Xu, W. Zhang, M. Chen, Q. Cheng, and R. Penty, "Integrated reconstructive spectrometer with programmable photonic circuits," *Nat. Commun.*, vol. 14, no. 1, p. 6376, Oct. 2023, doi: 10.1038/s41467-023-42197-3.
- [4] C. Yao, M. Chen, T. Yan, L. Ming, Q. Cheng, and R. Penty, "Broadband picometer-scale resolution on-chip spectrometer with reconfigurable photonics," *Light Sci. Appl.*, vol. 12, no. 1, p. 156, Jun. 2023, doi: 10.1038/s41377-023-01195-2.
- [5] C. Yao *et al.*, "Chip-scale sensor for spectroscopic metrology," *Nat. Commun.*, vol. 15, no. 1, p. 10305, Nov. 2024, doi: 10.1038/s41467- 024-54708-x.
- [6] Y. Wang *et al.*, "Asymmetrical estimator for training encapsulated deep photonic neural networks," *Nat. Commun.*, vol. 16, no. 1, p. 2143, Mar. 2025, doi: 10.1038/s41467-025-57459-5.
- [7] H. Huang, Z. Shi, G. Talli, M. Kuschnerov, R. Penty, and Q. Cheng, "Photonic chiplet interconnection via 3D-nanoprinted interposer," *Light Adv. Manuf.*, vol. 5, no. 4, p. 1, 2024, doi: 10.37188/lam.2024.046.
- [8] R. Hasani, M. Lechner, A. Amini, D. Rus, and R. Grosu, "Liquid Time-constant Networks," *Proc. AAAI Conf. Artif. Intell.*, vol. 35, no. 9, pp. 7657–7666, May 2021, doi: 10.1609/aaai.v35i9.16936.
- [9] T. Chen and C. Guestrin, "XGBoost: A Scalable Tree Boosting System," in *Proceedings of the 22nd ACM SIGKDD International Conference on Knowledge Discovery and Data Mining*, San Francisco California USA: ACM, Aug. 2016, pp. 785–794. doi: 10.1145/2939672.2939785.
- [10] Q. Lu, G. V. Karanikolas, Y. Shen, and G. B. Giannakis, "Ensemble Gaussian Processes with Spectral Features for Online Interactive Learning with Scalability," *Proc. Twenty Third Int. Conf. Artif. Intell. Stat.*, vol. 108, pp. 1910–1920.