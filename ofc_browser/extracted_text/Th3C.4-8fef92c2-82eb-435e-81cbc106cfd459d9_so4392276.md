# **High Performing Photonics Systems – CPO, Towards Photonics Chiplets**

**Tolga Tekin, Bogdan Sirbu, Hermann Oppermann, Michail Symeonidis, David Antonio Hernandez Solarte, Michail Anastasiadis, Anil Palaci**

> *Fraunhofer Institute for Reliability and Microintegration IZM, Gustav-Meyer-Allee 25, 13353 Berlin, Germany. tolga.tekin@izm.fraunhofer.de*

**Abstract:** This invited paper presents integration‑centric, packaging‑enabled photonic architectures co‑packaged optics, interposers, and photonic chiplets—enabling low‑latency, high‑bandwidth, and high‑density optical I/O for scalable, energy‑efficient AI and B5G/6G systems beyond 100‑Tb/s and toward 204.8‑Tb/s‑class platforms.

### **1. System Drivers for Next‑Generation AI Infrastructure**

*Composable Data Centers and B5G/6G Networks*

The rapid expansion of artificial intelligence (AI) workloads is redefining digital infrastructure around XPU‑centric system architectures, where CPUs, GPUs, and domain‑specific accelerators are tightly coupled through high‑bandwidth, low‑latency fabrics. Modern AI training and inference are increasingly interconnect‑bound rather than compute‑bound, making connectivity a first‑order system constraint impacting energy efficiency, latency, scalability, and overall system performance.

In parallel, data‑center and communication infrastructures are evolving toward disaggregated and composable architectures, enabling dynamic assembly of heterogeneous XPU resources. This trend spans hyperscale AI data centers and emerging B5G/6G networks, driving a convergence between cloud, edge, and telecom domains.

A decisive inflection point originates from switch ASICs exceeding 100 Tb/s aggregate throughput, where electrical I/O scaling alone becomes unsustainable in terms of power, reach, and signal integrity. This transition has made co‑packaged optics (CPO) and photonic chiplet architectures mandatory [1, 2], enabling optical I/O to be brought directly into the package and minimizing electrical path lengths for scalable XPU‑centric fabrics.

This evolution marks a fundamental paradigm shift: from packaging for photonics toward photonics for packaging, where optical interconnects become a structural element shaping advanced system-level integration architectures for composable AI infrastructure and converged B5G/6G systems.

## **2. Photonic Interposers as the Backbone of Composable Systems**

*TSV‑Enabled Architectures for Co‑Packaged and Disaggregated Platforms*

As system architectures evolve toward XPU‑centric and composable designs, photonic interposers emerge as a key integration layer between compute, networking, and optical fabrics. Interposers provide a physically and electrically scalable substrate that decouples system functionality from individual dies, enabling heterogeneous integration without monolithic system‑on‑chip designs [3].

A critical enabler of this approach is the integration of through‑silicon vias (TSVs), supporting both high‑bandwidth electrical signaling and vertical optical routing. TSVs allow signals, power, and clocks to traverse the interposer thickness, enabling double‑side assembly of electronic and photonic components and significantly shortening high‑speed electrical paths. This vertical connectivity is essential for achieving the bandwidth density and energy efficiency required by next‑generation switch ASICs and XPU‑centric fabrics.

By combining dense electrical redistribution with integrated optical interfaces, silicon photonics interposers bridge board‑level systems and package‑level integration, forming a direct architectural pathway toward CPO and photonic chiplet solutions where optical I/O becomes an intrinsic part of the package fabric. These interposer‑centric integration schemes have been validated across successive European research programs [1, 4, 5], establishing a continuous technology path from early silicon photonics interposers to today's CPO and photonic chiplet platforms and positioning interposers as foundational building blocks for scalable, composable AI and converged network systems.

### **3. Optical I/O Architectures for Composable Compute and Network Fabrics**

*Passive Alignment and Scalable Coupling Concepts*

As optical interfaces migrate from pluggable modules toward package‑level integration, optical I/O architectures become a defining element of composable systems. The transition to co‑packaged optics and photonic chiplets introduces a wide design space encompassing edge coupling, grating coupling, and free‑space or relay‑based approaches, each offering distinct trade‑offs in bandwidth density, alignment tolerance, and thermal robustness.

For XPU‑centric and switch‑centric packages, scalability and manufacturability increasingly outweigh absolute coupling efficiency. Consequently, passive and self‑aligned optical coupling schemes are gaining prominence, enabling dense optical I/O integration with automated, high‑volume assembly [5, 6]. Optical interfaces thus become structural elements of the system-level integration fabric, co‑designed with interposers, redistribution layers, and thermal solutions to meet the bandwidth and energy demands of next‑generation AI and converged network infrastructures.

## **4. Light Source Integration for Distributed and Co-Packaged Optics**

*Hybrid and Heterogeneous Approaches Across AI and Network Systems*

As optical I/O is brought into the package, light source integration becomes a central architectural consideration, tightly coupled to thermal management, RF signal integrity, and power delivery. In co‑packaged and photonic chiplet systems, laser placement directly influences electrical parasitics, impedance control, crosstalk, electromagnetic coupling, heat dissipation, and reliability. Consequently, no single light‑source strategy universally dominates XPU‑centric compute fabrics and switch‑centric network platforms [1, 2, 7].

Hybrid and heterogeneous integration approaches, including flip-chip-bonded and wafer-bonded light sources, offer a pragmatic balance between performance, RF integrity, and manufacturability. By decoupling photonic and electronic process optimization, these schemes enable controlled high-speed RF interfaces between electronic drivers and optical modulators while supporting dense optical I/O integration at the microsystem level. At the same time, distributing light generation across multiple optical engines or chiplets supports modular system scaling, improved RF isolation, and fault containment—critical properties for large-scale AI infrastructures.

From a system-level integration perspective, light source integration reinforces the shift toward optical I/O as an intrinsic package function, co-designed with interposers, coupling interfaces, RF routing, power distribution, and thermal solutions. Such multi domain co-optimization is essential to realize energy efficient, scalable optical fabrics for next-generation data center and converged network systems.

## **5. Electronic–Photonic Integration Paradigms for Composable Platforms**

*2.5D, 3D, and Monolithic Integration*

The integration of electronic and photonic functions across composable systems spans a spectrum of 2.5D, 3D, and monolithic paradigms, each addressing different constraints in performance, power, and manufacturability. Rather than converging toward a single dominant approach, next-generation AI and network platforms increasingly adopt a heterogeneous mix of integration strategies, tailored to system-level requirements.

2.5D integration, typically based on interposers or embedded bridges, provides a flexible and manufacturable path to co-package electronic and photonic chiplets while preserving process optimization for each domain. More advanced 3D integration further shortens electrical paths, improves bandwidth density, and enables tighter cooptimization of RF, power delivery, and optical I/O, albeit with increased packaging complexity. Fully monolithic integration offers minimal parasitics but remains constrained by process compatibility and yield considerations.

From a system perspective, these paradigms should not be viewed as competing alternatives but as complementary building blocks within a composable architecture [1, 2, 5]. The ability to combine and scale them across systemlevel integration hierarchies is essential to realizing high performance, energy efficient optical fabrics for AI-centric and converged network infrastructures.

## **6. Manufacturability and Modularization of Photonic Subsystems**

*Toward High-Volume AI and Network Deployment*

As photonic integration moves into the package, manufacturability becomes the primary gating factor for large-scale deployment in AI and converged network systems. The transition from monolithic optical modules toward modular photonic subsystems, such as optical engines and photonic chiplets, enables reuse across platforms while decoupling system scaling from individual die complexity.

To support high-volume production, photonic subsystems must be designed for passive or self-aligned assembly, relaxed placement tolerances, and compatibility with automated packaging flows. Equally important is the co-design of optical interfaces with electrical routing, RF integrity, power delivery, and thermal management at the package level. In this context, packaging is no longer a back-end activity but a system-level design discipline.

By combining modular photonic building blocks with scalable assembly and test strategies, advanced packaging enables a practical path from laboratory demonstrators to deployable co-packaged and chiplet-based optical systems for next-generation AI infrastructure [5, 6].

### **7. Scaling Toward Extreme Bandwidth and Ultra‑Low Latency**

*AI Fabrics, Photonic–Wireless Convergence, and B5G/6G Systems*

The architectural trends discussed in the previous sections converge at the system scale, where aggregate bandwidth, latency, and energy efficiency define feasibility. In AI‑centric data centers, the transition toward switch ASICs beyond 100 Tb/s and emerging 204.8 Tb/s‑class platforms [7] places unprecedented pressure on off‑package I/O density and power budgets. Under these conditions, co‑packaged optics and photonic chiplets evolve from incremental optimizations into structural enablers of scalable AI fabrics.

Comparable scaling pressures arise in B5G and 6G systems, particularly in the context of massive MIMO and distributed radio architectures. Here, the integration of photonic transceivers at the photonic–wireless interface enables low‑loss, phase‑coherent distribution of high‑frequency signals between centralized processing units and large antenna arrays, supporting dense MIMO operation, tight synchronization, and ultra‑low‑latency transport.

At these extreme scales, the evolution toward photonic chiplet-based architectures becomes unavoidable [2, 8- 11]. Whether in AI-centric data centers or B5G/6G systems, optical I/O must be modular, distributed, and tightly cointegrated with electronic and RF functions. Photonic chiplets—including optical engines and photonic transceivers at the photonic–wireless interface—provide a natural mechanism to decouple device optimization from system scaling while enabling dense bandwidth, phase-coherent signal distribution, and low latency operation. As such, photonic chiplets emerge not merely as implementation choices, but as structural building blocks for composable, high-performance computing and communication fabrics, realized through packaging enabled system-level integration.

## **8. Discussion: Towards a European Photonics Chiplet Ecosystem**

*Integration, Packaging, and Manufacturing as Strategic Differentiators*

The developments discussed across the previous sections reveal a growing gap between technology readiness and manufacturability in advanced photonic systems. While device‑level performance in silicon photonics continues to advance rapidly, the transition from laboratory demonstrators to deployable AI and B5G/6G platforms is increasingly constrained by integration complexity, assembly yield, and scalable test. In this context, photonic chiplets provide a pragmatic pathway toward modularity, reuse, and system‑level scalability—provided that integration and packaging challenges are addressed in a coherent and standardized manner [12].

A central requirement for such an ecosystem is the availability of standardized electrical and optical interfaces, enabling photonic and electronic chiplets to be composed across vendors, applications, and technology nodes. Here, advanced packaging emerges as a strategic lever, transforming heterogeneous components into interoperable and manufacturable system building blocks rather than bespoke solutions.

From a European perspective, this shift carries particular significance. Leadership in photonic chiplets will be determined less by absolute device performance and more by excellence in integration, packaging, and scalable manufacturing [1, 2, 6, 8]. Positioning packaging as an integration discipline—rather than a housing step—enables the ecosystem to leverage strengths in heterogeneous integration, manufacturing infrastructure, and system co‑design to build a competitive and sovereign foundation for next‑generation AI and communication infrastructures.

## **9. Conclusions and Outlook**

This paper has outlined the evolution of photonics from device‑level innovation toward integration‑centric, packaging‑enabled system architectures. Driven by the scaling limits of electrical I/O, next‑generation AI data centers and emerging B5G/6G infrastructures increasingly rely on co‑packaged optics and photonic chiplets as structural building blocks for extreme bandwidth, low latency, and energy‑efficient operation. Across both domains, advanced packaging emerges not as a back‑end activity but as the primary layer where electronic, photonic, RF, power‑delivery, and thermal functions are co‑designed and physically composed.

Looking forward, the success of photonic chiplets will depend less on incremental device improvements and more on standardized interfaces, scalable manufacturing, and system‑level co‑design and integration strategies. In this context, the European ecosystems strengths in heterogeneous integration, packaging technologies, and manufacturing infrastructure position it well to play a leading role in shaping a sustainable and competitive photonics chiplet ecosystem for future AI and communication platforms.

# **References**

- [1] PhoxTroT (*EU FP7 Project ID 318240*), [www.phoxtrot.eu](http://www.phoxtrot.eu/) ; <https://cordis.europa.eu/project/id/318240>
- [2] L3MATRIX (*EU H2020 Project ID 688544*), [www.l3matrix.eu](http://www.l3matrix.eu/) ; <https://doi.org/10.3030/688544>
- [3] B. Sirbu, et al., DOI: 10.1109/ECTC.2019.00165.
- [4] PLATON (*EU FP7 Project ID 249135*), <https://cordis.europa.eu/project/id/249135/results>
- [5] MASSTART (*EU H2020 Project ID 825109*), [www.masstart.eu](http://www.masstart.eu/) ; <https://doi.org/10.3030/825109>
- [6] APPLAUSE (*EU H2020 Project ID 826588*), <https://doi.org/10.3030/826588>
- [7] B. Sirbu, et al., *Proc. SPIE 13903*, 1390332 (2026).
- [8] ALLEGRO (*EU Horizon Europe Project ID 101092766*)[, www.allegro](http://www.allegro-he.eu/)-he.eu ; <https://doi.org/10.3030/101092766>
- [9] 5G-PHOS (*EU H2020 Project ID 761989*), <https://doi.org/10.3030/761989>
- [10] 6G-MUSICAL (*EU Horizon Europe Project ID 101139176*), <https://doi.org/10.3030/101139176>
- [11] ADOPTION (*EU Horizon Europe Project ID 101070178*), <https://doi.org/10.3030/101070178>
- [12] T, Tekin, DOI: 10.1109/JSTQE.2011.2113171.