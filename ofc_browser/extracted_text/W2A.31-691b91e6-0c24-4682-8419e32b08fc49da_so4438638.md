## **OCS-based Double Resource Pooling for Flexible Intra- and Inter-rail Connectivity in AIDC Networks**

### **Yingxin Guo and Tong Ye\***

*State Key Laboratory of Photonics and Communications, Shanghai Jiao Tong University, Shanghai, China {guoyingxin, yetong}@sjtu.edu.cn, \* Corresponding Author*

**Abstract:** We propose ocs-DRP, an OCS-based flat and scalable AIDC network, supporting flexible intra- and inter-rail connectivity through double resource pooling. Compared to rail-optimized fattree, ocs-DRP delivers comparable delay performance while reducing power consumption by 40%. © 2026 The Author(s)

#### **1. Introduction**

The computational demands of training large models are witnessing explosive growth, necessitating the deployment of tens of thousands of GPU servers interconnected by AI data center (AIDC) network. Unlike traditional data centers networks (DCNs), AIDC networks typically produce sparse and semi-predictable traffic patterns, such as the traffic stemming from data parallelism (DP) and pipeline parallelism (PP). This feature enables efficient network design [1].

However, the rise of expert parallelism (EP) in recent years imposes a big challenge on network design to support all-to-all (a2a) traffic demand [2]. Rail-optimized Fat-tree (ROFT) networks have now been widely deployed [3,4]. In ROFT, a group of GPUs with the same label of different servers are connected to the same leaf switch to form a rail. Though ROFT can provide a full bisection bandwidth and support a2a traffic very well, it requires a dense high-layer interconnection when extending to a large scale. This leads to high cost, high power consumption [1], large hop-count routing and high hash-collision risks. To address these issues, Rail-Only [5] and its 2-layer derivatives[6] are proposed, which leverage the sparsity of AI traffic. Specifically, 2-layer Rail-Only provides only intra-rail connectivity, meaning that the spine layer only interconnects leaf switches in the same rail. Though two-layer Rail-Only is more scalable than ROFT [5], its reliance on GPU for inter-rail traffic relay significantly limits the efficiency of a2a communication, which is especially true when a2a traffic is intensive. Several optical circuit switch (OCS)-based architectures have been proposed for efficient networking. LEAN in [1] replaces the spine layer of 2-layer Rail-Only with an OCS layer, thereby inheriting similar issues to those of Rail-Only. Through the reconfiguration ability of OCS, TPU-v4 [7] can customize 3D-torus topologies according to various training demands. However, 3D-torus offers low TPU-to-TPU bandwidth and is less accommodating to large-scale a2a communication [8]. Similarly, the OCS-based regional connection constructed by MIX-Net [2] is only designed for small-size a2a communications.

In this paper, we propose a flat and scalable AIDC network, called OCS-based double resource pooling (ocs-DRP) network, capable of efficiently supporting different types of AI traffic. ocs-DRP consists of the leaf-GPU pool and the spine pool interconnected by an OCS layer. The leaf-GPU pool comprises a set of blocks where GPUs connect to leaf switches via dual-port links in a rail-optimized manner, and the spine pool is formed by a group of spine switches to provide cross-block connectivity. According to training demands, ocs-DRP can reconfigure the OCS layer to optimize resource scheduling across both pools, efficiently supporting intra-rail traffic from DP, PP, and EP and inter-rail traffic from EP. We compare ocs-DRP with previous AIDC networks under real-world models with a2a traffic via simulation, which shows that ocs-DRP can achieve a delay performance similar to that of ROFT, while reducing the power consumption by 40%. Moreover, ocs-DRP can support 16 times as many GPUs as ROFT with equal network layers.

#### **2. OCS-based Double Resource Pooling (ocs-DRP) Network**

As Fig. 1(a) plots, ocs-DRP includes a leaf-GPU pool, a spine pool, and an OCS layer in between. The basic unit of the leaf-GPU pool is a block consisting of 2 leaf switches and servers. Each leaf switch has down ports and /2 uplink ports, and the capacity of a down port is one-half of that of an uplink port. Each server contains GPUs interconnected via a high-bandwidth (HB) domain. ocs-DRP adopts a reliable design [3,4], where the th GPU in each server connects to two leaf switches labelled by Leaf via a dual-port network interface card (NIC), as the dark line and the gray line in Fig. 1(a) show, where = 1,2, ⋯ , . Accordingly, the leaf switches in each block are equally divided into two dual-port leaf sets, as the green and gray boxes in each block depict. / blocks form a plane, and the -th block in the -th plane is labelled by (",\$), where = 1,2, ⋯ , and = 1,2, ⋯ ,/. planes constitute the leaf-GPU pool, which totally contains & GPUs. On the top of Fig.1(a) is the spine pool, where -port spine switches are evenly divided into two dual-port spine sets to isolate the traffic from dual ports, as the blue and gray parallelograms illustrate. In each spine set, the spine switches are organized into K/2 spine groups (SGroups), each of which contains G spine switches. The spine switches in the i-th SGroup are labelled by  $S_{(i,1)}, S_{(i,2)}, \cdots, S_{(i,G)}$ , where  $i=1,2,\cdots,K/2$ . The OCS layer contains  $K^2/G$   $G^2\times G^2$  OCSs, which define the logical interconnection between two pools, according to training demands. These OCSs are divided into two equal dual-port OCS sets, as the yellow and gray cuboids plot. An OCS is labelled by  $O_{(i,j)}$  if it connects to spine switches  $S_{(i,1)}, S_{(i,2)}, \cdots, S_{(i,G)}$  via uplinks and blocks  $B_{(1,j)}, B_{(2,j)}, \cdots, B_{(G,j)}$  via downlinks, where  $i=1,2,\cdots,K/2$  and  $j=1,2,\cdots,K/G$ .

![](_page_1_Figure_3.jpeg)

Fig. 1. (a) overview of ocs-DRP network and two configurations of an ocs-DRP with K=4 and G=2: (b) R=0.5 for the whole network, (c)  $R_1=0.5$  for cluster 1 and  $R_2=0$  for cluster 2, where pink and cyan edges stand for intra- and inter-rail interconnections, respectively.

Through the configuration of OCSs, ocs-DRP can determine the connectivity between the spine switches and the leaf switches and thus provide logical networks for training tasks. In particular, under different OCS configurations, ocs-DRP can flexibly allocate bandwidth for inter-rail traffic and intra-rail traffic. Such an allocation is measured by the inter-rail connectivity ratio, denoted as R, which is defined as the ratio of the number of leaf uplinks used for interrail traffic to the total number of uplinks. Fig. 1(b) and (c) illustrate two use cases of an ocs-DRP with K=4 and G=2. For visual clarity, the figures only plot the logical topology as well as the spine and leaf switches in one dual-port set, while omitting the identical counterpart in another set.

- (1) Homogeneous configuration: The cyan edges in Fig. 1(b) show that spine switches  $S_{(1,1)}$  and  $S_{(1,2)}$  are connected to all leaf switches marked as Leaf 1 and Leaf 2, respectively, to provide intra-rail connectivity. The pink edges display that  $S_{(2,1)}$  and  $S_{(2,2)}$  are linked to all leaf switches in planes 1 and 2, respectively, to provide inter-rail connectivity. As a result, all the leaf switches share the same R = 0.5. Such a homogeneous configuration is suited for single-tenant scenario.
- (2) Heterogeneous configuration: In Fig. 1(c), 4 blocks are divided into 2 clusters. Spine switch  $S_{(1,1)}$  are connected to the leaf switches marked as Leaf 1 and Leaf 2 in  $B_{(1,1)}$  in cluster 1 to support inter-rail connectivity, and linked to the leaf switches marked as Leaf 1 in  $B_{(1,2)}$  and  $B_{(2,2)}$  in cluster 2 to provide intra-rail connectivity.  $S_{(1,2)}$  is connected to the leaf switches marked as Leaf 1 and Leaf 2 in  $B_{(2,1)}$  in cluster 1 for inter-rail connectivity, and linked to the leaf switches marked as Leaf 2 in  $B_{(1,2)}$  and  $B_{(2,2)}$  in cluster 2 for intra-rail connectivity. In the meanwhile,  $S_{(2,1)}$  and  $S_{(2,2)}$  are connected to all the leaf switches marked as Leaf 1 and Leaf 2, respectively, to provide intra-rail connectivity. As a result, the inter-rail connectivity ratio of cluster 1 is  $R_1 = 0.5$  and that of cluster 2 is  $R_2 = 0$ . Such a heterogeneous configuration can be applied to multi-tenant scenario.

#### 3. Performance Evaluation

Our simulations are conducted using SimAI platform [9], with a packet-level network simulation backend NS-3. We consider the setup of H100 GPU cluster, where each server contains G = 8 GPUs interconnected via 900-GB/s NVLinks. NICs are equipped with either 200-Gb/s dual ports or 400 Gb/s single ports. The network is configured with the DCQCN protocol and uses the dynamic load balancing (DLB) feature in switches and the load-balancing strategy [10] developed in NICs. To mitigate large-flow collisions during a2a communication, the data partitioning strategy in NCCL is employed to segment data into small units. We assess two transformer models that utilize EP and require 512 GPUs: (i) Mixtral 8×7B with DP = 16, PP = 1, EP = 8, and TP = 4, (ii) DeepSeek 16B with DP = 16, PP = 1, EP = 32, and EP = 1, which have different a2a communication scales. For comparison, we consider other AIDC

networks, ROFT, HPN [3], Astral [4], 2-layer Rail-Only, and LEAN [1] as baselines. When simulating 2-layer Rail-Only and LEAN, we account for an overhead of 20 streaming multiprocessors occupation [6] and a 50-μs latency [11] introduced by inter-rail traffic relay in each server.

![](_page_2_Figure_3.jpeg)

Fig. 2. (a1)~(a2) iteration times of models (i) and (ii), changing as a function of , (a3) inter-rail flow ratio of a2a traffic, (b1)~(b2) comparison of different AIDC networks for iteration times of models (i) and (ii), (b3) power consumption of different AIDC networks.

Fig. 2 presents the simulation results. We first demonstrate ocs-DRP can adapt to diverse communication demands via reconfiguration of OCS layer. Fig. 2(a1) and (a2) show that ocs-DRP can minimize the iteration time by selecting an optimal for different training tasks. As Fig. 2(a3) displays, 43% flows generated by the a2a communications of model (i) are inter-rail flows, and the remaining 57% flows can leverage the intra-rail uplinks to transfer. As a result, only a small number of uplinks of each leaf switch (i.e., = 0.25) is enough for inter-rail traffic. In contrast, the ratio of the inter-rail flows produced by a2a communications of model (ii) increases to 67%, which makes the optimal interrail connectivity ratio be = 0.875. Fig. 2(b1)~(b2) then compare ocs-DRP with an optimal against previous AIDC networksin terms of iteration time. Astral performs the worst due to its rail-optimized leaf-to-spine connections, which enforce all inter-rail a2a traffic to traverse the core layer, resulting in high hop counts and propagation delay. Both 2 layer Rail-Only and LEAN architectures face additional overhead from inter-rail traffic, and this issue is particularly severe for model (ii), which involves more inter-rail flows. In contrast, ocs-DRP achieves performance similar to that of ROFT and HPN. Moreover, ocs-DRP can even outperform HPN in model (i) and ROFT in model (ii). This advantage stems from its flat network architecture and a flexibly chosen . The hop count of the flows in ocs-DRP is up to 4, while that of the flows in HPN and ROFT can reach 6. Fig. 2(b3) compares the power consumptions of different AIDC networks. Following [12], we calculate the power consumption as the sum of power consumed by Ethernet ports, optical transceivers and OCS ports. Since the OCS layer of ocs-DRP contributes merely 0.28% to the total power, the power consumption of ocs-DRP is nearly identical to that of 2-layer Rail-Only. LEAN achieves the lowest power consumption, as its spine layer consists of OCSs only. Fig. 2(b3) exhibits that ocs-DRP achieves a 40% reduction in power consumption against ROFT, HPN and Astral. This is attributed to the fact that ocs-DRP only needs 60% electronic switches to support the same number of GPUs as ROFT.

Also, it is easy to show that ocs-DRP can support more GPUs than ROFT with the same network layer. Specially, ocs-DRP supports up to ² GPUs, while ROFT can carry only ²/2 GPUs, when the network layer is 2. Given the number of GPUs per servers is = 8, a 2-layer ocs-DRP can carry 16 times more GPUs than a 2-layer ROFT.

#### **4. Conclusion**

This paper presents a new AIDC network, ocs-DRP. This network pools spine switches, leaf switches, and GPUs via an OCS layer, and thus can support diverse AI traffic demands through reconfigurable intra- and inter-rail connectivity. Simulations confirm that ocs-DRP can achieve a comparable delay performance to ROFT, while reducing the power consumption by 40%. With the same network layers, ocs-DRP can support 16 times more GPUs than ROFT.

**Acknowledgement:** This work is supported by the National Natural Science Foundation of China (62271306, 62331017), and the National Key Research and Development Program of China (2024YFB2908301).

### **5. Reference**

- [1] G. Patronas, *et al.*, *J. Opt. Commun. Netw.*, 17(1), A95, 2025.
- [2] X. Liao, *et al.*, in *Proc. SIGCOMM*, 2025, pp. 554-574.
- [3] K. Qian, *et al.*, in *Proc. SIGCOMM*, 2024, pp. 691-706.
- [4] Q. Meng, *et al.*, in *Proc. SIGCOMM*, 2025, pp. 609-625.
- [5] W. Wang, *et al.*, in *Proc. HOTI*, 2024, pp. 1-10.
- [6] C. Zhao, *et al.*, in *Proc. ISCA*, 2025, pp. 1-14.
- [7] N. Jouppi, *et al.*, in *Proc. ISCA*, 2023, pp. 1-14.

- [8] H. Liao, *et al.*, in *Proc. Hot Chips*, 2025, pp. 1-14.
- [9] X. Wang, *et al.*, in *Proc. NSDI*, 2025, pp. 541-558.
- [10] P. Cao, *et al.*, in *Proc. NAIC*, 2024, pp. 18-25.
- [11] Lena Oden, in *Dissertation Thesis*, Ruprecht-Karls-Universität Heidelberg, 2015.
- [12] W. Wang, *et al*., in *Proc. NSDI*, 2022, pp. 1267-1288.

![](_page_3_Picture_0.jpeg)

# OCS-based Double Resource Pooling for

![](_page_3_Picture_2.jpeg)

# Flexible Intra- and Inter-rail Connectivity in AIDC Networks

Yingxin Guo and Tong Ye\*

State Key Laboratory of Photonics and Communications, Shanghai Jiao Tong University, \*Corresponding Author

## Abstract

We propose ocs-DRP, an OCS-based flat and scalable AIDC network, supporting flexible intra- and inter-rail connectivity through double resource pooling. Compared to rail-optimized fat-tree, ocs-DRP delivers comparable delay performance while reducing power consumption by 40%.

## Introduction

- Al data center (AIDC) network produces semi-predictable and sparse traffic patterns ⇒ efficient network design is possible
- However, current AIDC networks face the following difficulties:
  - Rail-optimized fat-tree (ROFT) by Nivida supports all-to-all (a2a) traffic but requires a dense high-layer interconnection
  - Rail-only by MIT and Multi-plane Fat-tree (MPFT) by DeepSeek are low-cost but rely on GPU for inter-rail traffic relay when supporting a2a traffic
  - Existing OCS-based AIDC networks cannot tackle these difficulties
- ⇒ A novel OCS-based AIDC network is needed

## OCS-based Double Resource Pooling (ocs-DRP) Network

![](_page_3_Figure_16.jpeg)

ocs-DRP = Leaf-GPU pool + spine pool + OCS layer  $G^2 \times G^2$  OCSs *K*-port EPSs + *G*-GPU servers *K*-port EPSs

# **Network Features**

- **Scalability**: can support up to  $GK^2$  GPUs
  - $GK^2 = 1,048,576$ , if K = 128 and G = 64
- Flat Network: only contain two EPS layers
  - # of hops of each flow ≤ 4
  - GPU Relay is not needed for a2a traffic
- Flexibility: allocate bandwidth for inter- and intra-rail traffic is enabled via reconfiguration of OCS layer

# Key parameter: inter-rail connectivity ratio

# of uplinks used for inter-rail traffic

total # of leaf uplinks

# Example

port count of each EPS is K = 4, and # of GPUs in each server is G = 2

![](_page_3_Picture_30.jpeg)

Network architecture

![](_page_3_Picture_32.jpeg)

Logical Config. 1: R = 0

![](_page_3_Figure_34.jpeg)

Logical Config. 2: R = 0.5

## **Performance Evaluation**

Consider two transformer models that utilize EP technique and need 512 GPUs in the simulation.

![](_page_3_Figure_38.jpeg)

![](_page_3_Figure_39.jpeg)

(each server has TP traffic) (each server has no TP traffic) • ocs-DRP can select an optimal R for different training tasks

![](_page_3_Figure_41.jpeg)

![](_page_3_Figure_42.jpeg)

ocs-DRP with optimal R can lead to a small iteration time

ocs-DRP achieves a 40% power savings compared to ROFT

## Conclusions

- ✓ Propose ocs-DRP, which can pool GPUs and EPSs at the same time, and can support diverse AI traffic demands.
- ✓ Compared with ROFT, ocs-DRP achieves similar iteration time, while cutting power consumption by 40%.

## References

- [1] G. Patronas, et al., J. Opt. Commun. Netw., 17(1), A95, 2025. [2] X. Liao, et al., in Proc. SIGCOMM, 2025, pp. 554-574.
- [3] K. Qian, et al., in Proc. SIGCOMM, 2024, pp. 691-706.
- [4] Q. Meng, et al., in Proc. SIGCOMM, 2025, pp. 609-625.
- [5] W. Wang, et al., in Proc. HOTI, 2024, pp. 1-10. [6] C. Zhao, et al., in Proc. ISCA, 2025, pp. 1-14.
- [7] N. Jouppi, et al., in Proc. ISCA, 2023, pp. 1-14.
- [8] H. Liao, et al., in Proc. Hot Chips, 2025, pp. 1-14.
- [9] X. Wang, et al., in Proc. NSDI, 2025, pp. 541-558. [10] P. Cao, et al., in Proc. NAIC, 2024, pp. 18-25.
- [11] Lena Oden, in *Dissertation Thesis*, Ruprecht-Karls Universität Heidelberg, 2015. [12] W. Wang, et al., in Proc. NSDI, 2022, pp. 1267-1288.