# Robot Morphology, Cross-Embodiment Policies & Robot Dataset Resources

A curated and **year-sorted** reading list for universal morphology control, cross-embodiment robot learning, robot foundation models / VLAs, embodiment co-design, and robot datasets / benchmarks.

> Last updated: **2026-11-06**  
> Sorting rule: entries are grouped by topic, then sorted by **publication/venue year**. For arXiv-only papers, the first arXiv submission year is used; standalone technical reports and dataset releases use their release year.  

---

## Table of Contents

- [0. Reading Map](#0-reading-map)
- [1. Papers](#1-papers)
  - [1.1 Universal Morphology Control / Morphology-Agnostic RL](#11-universal-morphology-control--morphology-agnostic-rl)
  - [1.2 Cross-Embodiment Generalist Policies / Robot Foundation Models](#12-cross-embodiment-generalist-policies--robot-foundation-models)
  - [1.3 Cross-Robot Adaptation and Cross-Embodiment Manipulation](#13-cross-robot-adaptation-and-cross-embodiment-manipulation)
  - [1.4 Embodiment Co-design and Morphology Generation](#14-embodiment-co-design-and-morphology-generation)
- [2. Datasets and Benchmarks](#2-datasets-and-benchmarks)
  - [2.1 Real-Robot Datasets and Collection Platforms](#21-real-robot-datasets-and-collection-platforms)
  - [2.2 Manipulation / Language / VLA Benchmarks](#22-manipulation--language--vla-benchmarks)
  - [2.3 Morphology and Cross-Embodiment Benchmarks](#23-morphology-and-cross-embodiment-benchmarks)
- [3. Suggested Reading Paths](#3-suggested-reading-paths)
- [4. Verification Notes](#4-verification-notes)

---

## 0. Reading Map

| Topic | Representative Works | Why it matters |
|---|---|---|
| Universal morphology control | NerveNet, MetaMorph, ModuMorph, HyperDistill, GET-Zero, RecMorph | One controller across robot bodies, body graphs, kinematic trees, or modular robots. |
| Universal legged locomotion across robots | RMA, GenLoco, ManyQuadrupeds, LocoFormer, Multi-Loco, X-WBC, MorphMimic | Shared locomotion and whole-body tracking across bodies; distinguish joint training, online adaptation, and held-out embodiment transfer. |
| Cross-embodiment generalist policy | RT-X, Octo, CrossFormer, OpenVLA, π0 / π0.5, AnyWorld, EXE | Scaling robot policies across datasets, action spaces, sensors, robots, and tasks. |
| Cross-robot adaptation | Intention alignment, CEI, MOTIF, ZETA, GOTT, Hourglass | Transfer behavior across robots with incompatible embodiment/action spaces. |
| Embodiment co-design | NGE, DERL, BodyGen, House of Dextra, Learning to Reconfigure, Transformer Transformer, Dogger | Jointly optimize body morphology and controller. |
| Datasets / benchmarks | Open X-Embodiment, DROID, RoboMIND, AGIBOT WORLD 2026, RoboCasa365, X2Real, Co-design Gym | Data substrate and evaluation suites for generalist robot learning. |

### Recent additions at a glance

| Work | Public date / status | Focus |
|---|---|---|
| [RecMorph](https://arxiv.org/abs/2609.18359) | 2026-09-16 · arXiv | Topology-guided spatial recurrence for generalized morphology control. |
| [EXE](https://arxiv.org/abs/2610.33685) | 2026-10-24 · arXiv | Factorized latent actions for egocentric cross-embodiment pretraining. |
| [MorphMimic](https://lzyang2000.github.io/morphmimic/) | 2026-10-29 · technical-report project v0.1 | Shared morphology-conditioned world model and humanoid tracking policy. |
| [Hourglass](https://arxiv.org/abs/2610.41330) | 2026-10-30 · arXiv | Cross-embodiment planning through camera motion and differentiable ego-dynamics. |
| [Learning Purposeful Co-designs / Dogger](https://arxiv.org/abs/2611.02462) | 2026-11-02 · arXiv | Geometry, passive compliance, and control co-design with hardware validation. |
| [One-shot printable soft-robot co-design](https://arxiv.org/abs/2611.03216) | 2026-11-02 · arXiv | Joint material, actuation, and control optimization with monolithic fabrication. |

See [Verification Notes](#4-verification-notes) for all additions, metadata corrections, and code-release distinctions.

---

# 1. Papers

## 1.1 Universal Morphology Control / Morphology-Agnostic RL

### 2017

- **Learning Invariant Feature Spaces to Transfer Skills with Reinforcement Learning**. [[pdf](https://arxiv.org/pdf/1703.02949)] [[openreview](https://openreview.net/forum?id=Hyq4yhile)]  
  [![Conference](https://img.shields.io/badge/Conference-ICLR-green)](https://iclr.cc/)  
  · Abhishek Gupta, Coline Devin, YuXuan Liu, Pieter Abbeel, Sergey Levine. *ICLR, 2017*

### 2018

- **Hardware Conditioned Policies for Multi-Robot Transfer Learning**. [[pdf](https://arxiv.org/pdf/1811.09864)] [[web](https://sites.google.com/view/robot-transfer-hcp)] [[code](https://github.com/taochenshh/hcp)]  
  [![Conference](https://img.shields.io/badge/Conference-NeurIPS-green)](https://neurips.cc/)  
  · Tao Chen, Adithyavairavan Murali, Abhinav Gupta. *NeurIPS, 2018*

- **NerveNet: Learning Structured Policy with Graph Neural Networks**. [[pdf](https://openreview.net/pdf?id=S1sqHMZCb)] [[web](https://www.cs.toronto.edu/~tingwuwang/nervenet.html)] [[code](https://github.com/WilsonWangTHU/NerveNet)]  
  [![Conference](https://img.shields.io/badge/Conference-ICLR-green)](https://iclr.cc/)  
  · Tingwu Wang, Renjie Liao, Jimmy Ba, Sanja Fidler. *ICLR, 2018*

### 2020

- **Hierarchically Decoupled Imitation for Morphological Transfer**. [[pdf](https://proceedings.mlr.press/v119/hejna20a/hejna20a.pdf)] [[web](https://sites.google.com/berkeley.edu/morphology-transfer)] [[code](https://github.com/jhejna/hierarchical_morphology_transfer)]  
  [![Conference](https://img.shields.io/badge/Conference-ICML-green)](https://icml.cc/)  
  · Donald J. Hejna III, Lerrel Pinto, Pieter Abbeel. *ICML, 2020*

### 2021

- **RMA: Rapid Motor Adaptation for Legged Robots**. [[pdf](https://arxiv.org/pdf/2107.04034)] [[web](https://ashish-kmr.github.io/rma-legged-robots/)] [[proceedings](https://roboticsproceedings.org/rss17/p011.html)]  
  [![Conference](https://img.shields.io/badge/Conference-RSS-green)](https://roboticsconference.org/)  
  · Ashish Kumar, Zipeng Fu, Deepak Pathak, Jitendra Malik. *RSS, 2021*

- **My Body is a Cage: the Role of Morphology in Graph-Based Incompatible Control**. [[pdf](https://openreview.net/pdf?id=N3zUDGN5lO)] [[code](https://github.com/yobibyte/amorpheus)]  
  [![Conference](https://img.shields.io/badge/Conference-ICLR-green)](https://iclr.cc/)  
  · Vitaly Kurin, Maximilian Igl, Tim Rocktäschel, Wendelin Böhmer, Shimon Whiteson. *ICLR, 2021*

- **Snowflake: Scaling GNNs to High-Dimensional Continuous Control via Parameter Freezing**. [[pdf](https://openreview.net/pdf?id=REjT_c1Eejk)] [[code](https://github.com/thecharlieblake/snowflake)]  
  [![Conference](https://img.shields.io/badge/Conference-NeurIPS-green)](https://neurips.cc/)  
  · Charlie Blake, Vitaly Kurin, Maximilian Igl, Shimon Whiteson. *NeurIPS, 2021*

- **Tool as Embodiment for Recursive Manipulation**. [[pdf](https://arxiv.org/pdf/2112.00359)] [[web](https://sites.google.com/view/recursivemanipulation)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2112.00359-red)](https://arxiv.org/abs/2112.00359)  
  · Yukiyasu Noguchi, Tatsuya Matsushima, Yutaka Matsuo, Shixiang Shane Gu. *ArXiv, 2021*

### 2022

- **Structure-Aware Transformer Policy for Inhomogeneous Multi-Task Reinforcement Learning**. [[pdf](https://openreview.net/pdf?id=fy_XRVHqly)] [[code](https://github.com/sunghoonhong/SWAT)]  
  [![Conference](https://img.shields.io/badge/Conference-ICLR-green)](https://iclr.cc/)  
  · Sunghoon Hong, Deunsol Yoon, Kee-Eung Kim. *ICLR, 2022*

- **MetaMorph: Learning Universal Controllers with Transformers**. [[pdf](https://arxiv.org/pdf/2203.11931)] [[openreview](https://openreview.net/forum?id=Opmqtk_GvYL)] [[web](https://metamorph-iclr.github.io/site/)] [[code](https://github.com/agrimgupta92/metamorph)]  
  [![Conference](https://img.shields.io/badge/Conference-ICLR-green)](https://iclr.cc/)  
  · Agrim Gupta, Linxi Fan, Surya Ganguli, Li Fei-Fei. *ICLR, 2022*

- **GenLoco: Generalized Locomotion Controllers for Quadrupedal Robots**. [[pdf](https://proceedings.mlr.press/v205/feng23a/feng23a.pdf)] [[pmlr](https://proceedings.mlr.press/v205/feng23a.html)] [[web](https://xbpeng.github.io/projects/GenLoco/index.html)] [[code](https://github.com/HybridRobotics/GenLoco)]  
  [![Conference](https://img.shields.io/badge/Conference-CoRL-green)](https://www.corl.org/)  
  · Gilbert Feng, Hongbo Zhang, Zhongyu Li, Xue Bin Peng, Bhuvan Basireddy, Linzhu Yue, Zhitao Song, Lizhi Yang, Yunhui Liu, Koushil Sreenath, Sergey Levine. *CoRL, 2022; PMLR, 2023*
  > Uses morphology randomization to train generalized quadrupedal locomotion controllers deployable to unseen simulated and real quadrupeds with similar morphology families.

### 2023

- **Learning Modular Robot Control Policies**. [[pdf](https://arxiv.org/pdf/2105.10049)] [[doi](https://doi.org/10.1109/TRO.2023.3284362)] [[code](https://github.com/biorobotics/learning_modular_policies)]  
  [![Journal](https://img.shields.io/badge/Journal-IEEE_TRO-blue)](https://ieeexplore.ieee.org/xpl/RecentIssue.jsp?punumber=8860)  
  · Julian Whitman, Matthew Travers, Howie Choset. *IEEE Transactions on Robotics, 2023*

- **Universal Morphology Control via Contextual Modulation**. [[pdf](https://arxiv.org/pdf/2302.11070)] [[pmlr](https://proceedings.mlr.press/v202/xiong23a.html)] [[code](https://github.com/MasterXiong/ModuMorph)]  
  [![Conference](https://img.shields.io/badge/Conference-ICML-green)](https://icml.cc/)  
  · Zheng Xiong, Jacob Beck, Shimon Whiteson. *ICML, 2023*

### 2024

- **MAT: Morphological Adaptive Transformer for Universal Morphology Policy Learning**. [[ieee](https://ieeexplore.ieee.org/document/10485641)]  
  [![Journal](https://img.shields.io/badge/Journal-IEEE_TCDS-blue)](https://ieeexplore.ieee.org/xpl/RecentIssue.jsp?punumber=7274989)  
  · Boyu Li, Haoran Li, Yuanheng Zhu, Dongbin Zhao. *IEEE Transactions on Cognitive and Developmental Systems, 2024*

- **Distilling Morphology-Conditioned Hypernetworks for Efficient Universal Morphology Control**. [[pdf](https://arxiv.org/pdf/2402.06570)] [[pmlr](https://proceedings.mlr.press/v235/xiong24c.html)] [[code](https://github.com/MasterXiong/Universal-Morphology-Control)]  
  [![Conference](https://img.shields.io/badge/Conference-ICML-green)](https://icml.cc/)  
  · Zheng Xiong, Risto Vuorio, Jacob Beck, Matthieu Zimmer, Kun Shao, Shimon Whiteson. *ICML, 2024*

- **ManyQuadrupeds: Learning a Single Locomotion Policy for Diverse Quadruped Robots**. [[pdf](https://arxiv.org/pdf/2310.10486)] [[web](https://miladshafiee.github.io/ManyQuadrupeds/)] [[dblp](https://dblp.org/rec/conf/icra/ShafieeBI24.html)]  
  [![Conference](https://img.shields.io/badge/Conference-ICRA-green)](https://www.ieee-ras.org/conferences-workshops/fully-sponsored/icra)  
  · Milad Shafiee, Guillaume Bellegarda, Auke Jan Ijspeert. *ICRA, 2024; arXiv, 2023*

- **MetaLoco: Universal Quadrupedal Locomotion with Meta-Reinforcement Learning and Motion Imitation**. [[pdf](https://arxiv.org/pdf/2407.17502)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2407.17502-red)](https://arxiv.org/abs/2407.17502)  
  · Fatemeh Zargarbashi, Fabrizio Di Giuro, Jin Cheng, Dongho Kang, Bhavya Sukhija, Stelian Coros. *ArXiv, 2024*

- **One Policy to Run Them All: An End-to-End Learning Approach to Multi-Embodiment Locomotion**. [[paper](https://mlanthology.org/corl/2024/bohlinger2024corl-one/)]  
  [![Conference](https://img.shields.io/badge/Conference-CoRL-green)](https://www.corl.org/)  
  · Nico Bohlinger, Grzegorz Czechmanowski, Maciej Piotr Krupka, Piotr Kicki, Krzysztof Walas, Jan Peters, Davide Tateo. *CoRL, 2024*
  > Introduces URMA, a morphology-agnostic encoder/decoder architecture for a single locomotion policy across quadrupeds, humanoids, and hexapods, with transfer to unseen simulated and real robots.

### 2025

- **GET-Zero: Graph Embodiment Transformer for Zero-shot Embodiment Generalization**. [[pdf](https://arxiv.org/pdf/2407.15002)] [[web](https://get-zero-paper.github.io/)] [[code](https://github.com/real-stanford/get_zero)]  
  [![Conference](https://img.shields.io/badge/Conference-ICRA-green)](https://www.ieee-ras.org/conferences-workshops/fully-sponsored/icra)  
  · Austin Patel, Shuran Song. *ICRA, 2025*

- **GCNT: Graph-Based Transformer Policies for Morphology-Agnostic Reinforcement Learning**. [[pdf](https://arxiv.org/pdf/2505.15211)]  
  [![Conference](https://img.shields.io/badge/Conference-IJCAI-green)](https://2025.ijcai.org/)  
  · Yingbo Luo, Meibao Yao, Xueming Xiao. *IJCAI, 2025*

- **GRoQ-LoCO: Generalist and Robot-agnostic Quadruped Locomotion Control using Offline Datasets**. [[pdf](https://arxiv.org/pdf/2505.10973)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2505.10973-red)](https://arxiv.org/abs/2505.10973)  
  · Narayanan PP, Sarvesh Prasanth Venkatesan, Srinivas Kantha Reddy, Shishir Kolathaya. *ArXiv, 2025*

- **Shared Modular Recurrence in Contextual MDPs for Universal Morphology Control**. [[pdf](https://arxiv.org/pdf/2506.08630)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2506.08630-red)](https://arxiv.org/abs/2506.08630)  
  · Laurens Engwegen, Max Weltevrede, Caroline Horsch, Daan Brinks, Wendelin Böhmer. *ArXiv, 2025; v4 revised 2026-10-30*

- **Multi-Loco: Unifying Multi-Embodiment Legged Locomotion via Reinforcement Learning Augmented Diffusion**. [[pdf](https://arxiv.org/pdf/2506.11470)] [[pmlr](https://proceedings.mlr.press/v305/yang25a.html)] [[web](https://multi-loco.github.io/)]  
  [![Conference](https://img.shields.io/badge/Conference-CoRL-green)](https://www.corl.org/)  
  · Shunpeng Yang, Zhen Fu, Zhefeng Cao, Guo Junde, Patrick Wensing, Wei Zhang, Hua Chen. *CoRL, 2025*

- **UniLegs: Universal Multi-Legged Robot Control through Morphology-Agnostic Policy Distillation**. [[pdf](https://arxiv.org/pdf/2507.22653)] [[dblp](https://dblp.org/rec/conf/iros/XiCMZZ25.html)]  
  [![Conference](https://img.shields.io/badge/Conference-IROS-green)](https://www.iros25.org/)  
  · Weijie Xi, Zhanxiang Cao, Chenlin Ming, Jianying Zheng, Guyue Zhou. *IROS, 2025*
  > Distills morphology-specific teacher policies into a single Transformer student across five legged morphologies, including generalization to unseen robot designs.

- **Towards Embodiment Scaling Laws in Robot Locomotion**. [[pdf](https://arxiv.org/pdf/2505.05753)] [[pmlr](https://proceedings.mlr.press/v305/ai25a.html)] [[web](https://embodiment-scaling-laws.github.io/)] [[code](https://github.com/BoAi01/embodiment-scaling-laws)]  
  [![Conference](https://img.shields.io/badge/Conference-CoRL-green)](https://www.corl.org/)  
  · Bo Ai, Liu Dai, Nico Bohlinger, Dichen Li, Tongzhou Mu, Zhanxin Wu, K. Fay, Henrik I. Christensen, Jan Peters, Hao Su. *CoRL, 2025*
  > Studies embodiment scaling on roughly 1,000 procedurally generated humanoid, quadruped, and hexapod embodiments and shows improved zero-shot generalization as the number of training embodiments grows.

- **Multi-Embodiment Locomotion at Scale with extreme Embodiment Randomization**. [[pdf](https://arxiv.org/pdf/2509.02815)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2509.02815-red)](https://arxiv.org/abs/2509.02815)  
  · Nico Bohlinger, Jan Peters. *ArXiv, 2025*
  > Combines URMAv2 with extreme embodiment randomization over 50 legged robot bases and millions of morphology variations, with zero-shot transfer to unseen real humanoids and quadrupeds.

- **LocoFormer: Generalist Locomotion via Long-context Adaptation**. [[pdf](https://arxiv.org/pdf/2509.23745)] [[pmlr](https://proceedings.mlr.press/v305/liu25a.html)] [[web](https://generalist-locomotion.github.io/)]  
  [![Conference](https://img.shields.io/badge/Conference-CoRL-green)](https://www.corl.org/)  
  · Min Liu, Deepak Pathak, Ananye Agarwal. *CoRL, 2025*  
  > Trains a generalist locomotion policy on procedurally generated bodies with Transformer-XL memory spanning trials, enabling online adaptation to unseen legged and wheeled robots and changed dynamics.

### 2026

- **Knowledge Diversion for Efficient Morphology Control and Policy Transfer**. [[pdf](https://arxiv.org/pdf/2512.09796)] [[pmlr](https://proceedings.mlr.press/v306/feng26n.html)]  
  [![Conference](https://img.shields.io/badge/Conference-ICML-green)](https://icml.cc/)  
  · Fu Feng, Ruixiao Shi, Yucheng Xie, Jianlu Shen, Jing Wang, Xin Geng. *ICML, 2026; arXiv, 2025*

- **Scalable and General Whole-Body Control for Cross-Humanoid Locomotion**. [[pdf](https://arxiv.org/pdf/2602.05791)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2602.05791-red)](https://arxiv.org/abs/2602.05791)  
  · Yufei Xue, YunFeng Lin, Wentao Dong, Yang Tang, Jingbo Wang, Jiangmiao Pang, Ming Zhou, Minghuan Liu, Weinan Zhang. *ArXiv, 2026*

- **Embedding Morphology into Transformers for Cross-Robot Policy Learning**. [[pdf](https://arxiv.org/pdf/2603.00182)] [[openreview](https://openreview.net/forum?id=WVEdIvUSqp)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2603.00182-red)](https://arxiv.org/abs/2603.00182)  
  · Kei Suzuki, Jing Liu, Ye Wang, Chiori Hori, Matthew Brand, Diego Romeres, Toshiaki Koike-Akino. *ArXiv / ES-Reasoning @ ICLR, 2026*

- **DexGrasp-Zero: A Morphology-Aligned Policy for Zero-Shot Cross-Embodiment Dexterous Grasping**. [[pdf](https://arxiv.org/pdf/2603.16806)] [[code](https://github.com/YliangWu/DexGrasp-Zero)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2603.16806-red)](https://arxiv.org/abs/2603.16806)  
  · Yuliang Wu, Yanhan Lin, WengKit Lao, Yuhao Lin, Yi-Lin Wei, Wei-Shi Zheng, Ancong Wu. *ArXiv, 2026*

- **Morphology-Conditioned World Model for Cross-Embodiment Quadrupedal Locomotion**. [[pdf](https://arxiv.org/pdf/2604.08780)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2604.08780-red)](https://arxiv.org/abs/2604.08780)  
  · Mohamad H. Danesh, Chenhao Li, Amin Abyaneh, Anas Houssaini, Kirsty Ellis, Glen Berseth, Marco Hutter, Hsiu-Chin Lin. *ArXiv, 2026*

- **Rapid Embodiment Adaptation for Quadrupedal Locomotion**. [[pdf](https://arxiv.org/pdf/2608.01506)] [[web](https://embodiment-adaptation.github.io/)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2608.01506-red)](https://arxiv.org/abs/2608.01506)  
  · Dichen Li, Bo Ai, Nico Bohlinger, Jan Peters, Hao Su, Henrik I. Christensen. *ArXiv, 2026*
  > Infers changing embodiment parameters online from short interaction histories and adapts a generalist quadruped locomotion policy to joint-range changes and payload variations.

- **WestWorld: A Knowledge-Encoded Scalable Trajectory World Model for Diverse Robotic Systems**. [[pdf](https://arxiv.org/pdf/2603.14392)] [[pmlr](https://proceedings.mlr.press/v306/wang26dc.html)] [[openreview](https://openreview.net/forum?id=ncRRCG4BfP)] [[web](https://westworldrobot.github.io/)] [[code](https://github.com/511205787/WestWorld)]  
  [![Conference](https://img.shields.io/badge/Conference-ICML-green)](https://icml.cc/)  
  · Yuchen Wang, Jiangtao Kong, Sizhe Wei, Xiaochang Li, Haohong Lin, Hongjue Zhao, Tianyi Zhou, Lu Gan, Huajie Shao. *ICML, 2026*  
  > Combines system-aware mixture-of-experts dynamics with robot structural embeddings for cross-system trajectory prediction and model-based control.

- **X-WBC: A Cross-Embodiment Foundation Model for Humanoid Whole-Body Control**. [[pdf](https://arxiv.org/pdf/2609.15213)] [[web](https://logosintelligencelab.github.io/x-wbc/)] [[repo](https://github.com/LogosRoboticsGroup/x-wbc)]  
  [![Conference](https://img.shields.io/badge/Conference-CoRL-green)](https://www.corl.org/)  
  · Juntong Zhang, Chun Gu, Li Zhang. *CoRL, 2026; author-reported acceptance*  
  > Shares a temporal motion backbone across humanoids while using embodiment-specific input and action modules and aligned human, robot and sparse-VR command tokens. Implementation release is forthcoming as of this update.

- **RecMorph: Topology-Guided Spatial Recurrence for Generalized Morphology Control**. [[pdf](https://arxiv.org/pdf/2609.18359)] [[code](https://github.com/quanruirao/RecMorph)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2609.18359-red)](https://arxiv.org/abs/2609.18359)  
  · Quanrui Rao, Yong Liu, Xueming Xiao, Yingbo Luo, Kun Wu, Zhenyu Xu, Meibao Yao. *ArXiv, 2026*  
  > Uses bidirectional spatial recurrence over a depth-first kinematic-tree ordering for efficient cross-limb communication, evaluated on UNIMAL morphologies and shared Go1/Go2 control.

- **CrossBFM: Distilling a Shared Latent Behavior Space Across Humanoid Embodiments**. [[pdf](https://arxiv.org/pdf/2609.38087)] [[web](https://dotandung.github.io/crossbfm/)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2609.38087-red)](https://arxiv.org/abs/2609.38087)  
  · Tan-Dzung Do, Tuan Dat Phuong, Nico Bohlinger, Cuc T. Trinh, Siwei Ju, Vien Anh Ngo, Jan Peters, Xinchao Wang, An Thai Le. *ArXiv, 2026*  
  > Distills a common behavior latent space from cross-embodiment motion correspondence, then trains robot-specific latent-conditioned trackers for motion, pose and reward prompts. Implementation release is forthcoming as of this update.

- **Higher-Order Morphology Priors for Quadruped Reinforcement Learning Under Actuator Degradation**. [[pdf](https://arxiv.org/pdf/2610.10934)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2610.10934-red)](https://arxiv.org/abs/2610.10934)  
  · Derek You, Zafir Shamsi, Keqin Wang, Christine Allen-Blanchette. *ArXiv, 2026*  
  > Represents the Go1 morphology as a cell complex and uses Hodge message passing to improve coordinated compensation for unseen actuator degradation. Scope: morphology-informed robustness on a quadruped, rather than arbitrary cross-body transfer.

- **MimicAll: Structured Embodiment Conditioning for Cross-Humanoid Whole-Body Motion Tracking**. [[pdf](https://arxiv.org/pdf/2610.33508)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2610.33508-red)](https://arxiv.org/abs/2610.33508)  
  · Jia Li, Lingyun Xu, Yitang Li, Hao Zhao. *ArXiv, 2026*  
  > Conditions a shared humanoid motion-tracking policy on structured body descriptors and trains with physics-consistent embodiment randomization across multiple humanoid families.

- **MorphMimic: Morphology-Conditioned World Model and Policy Sharing Across Humanoids**. [[paper](https://lzyang2000.github.io/morphmimic/static/morphmimic.pdf)] [[web](https://lzyang2000.github.io/morphmimic/)] [[code](https://github.com/lzyang2000/morphmimic)]  
  [![Technical report](https://img.shields.io/badge/Technical_report-2026-lightgrey)](https://lzyang2000.github.io/morphmimic/)  
  · Lizhi Yang, Fengze Xie, Yuyang Wang, Lu Gan, Yisong Yue, Aaron D. Ames. *Technical report, 2026; v0.1 released 2026-10-29*  
  > Extends an independent SuperMimic reimplementation with morphology conditioning and canonical joint alignment to share a differentiable world model and tracking policy across G1, X2 Ultra and T2.

---

## 1.2 Cross-Embodiment Generalist Policies / Robot Foundation Models

### 2021

- **BC-Z: Zero-Shot Task Generalization with Robotic Imitation Learning**. [[pdf](https://arxiv.org/pdf/2202.02005)] [[web](https://sites.google.com/view/bc-z/home)]  
  [![Conference](https://img.shields.io/badge/Conference-CoRL-green)](https://www.corl.org/)  
  · Eric Jang, Alex Irpan, Mohi Khansari, Daniel Kappler, Frederik Ebert, Corey Lynch, Sergey Levine, Chelsea Finn. *CoRL, 2021*

### 2022

- **Gato: A Generalist Agent**. [[pdf](https://arxiv.org/pdf/2205.06175)] [[web](https://www.deepmind.com/publications/a-generalist-agent)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2205.06175-red)](https://arxiv.org/abs/2205.06175)  
  · Scott Reed, Konrad Zolna, Emilio Parisotto, Sergio Gómez Colmenarejo, Alexander Novikov, Gabriel Barth-Maron, Mai Giménez, Yury Sulsky, Jackie Kay, Jost Tobias Springenberg, et al. *ArXiv, 2022*

### 2023

- **RT-1: Robotics Transformer for Real-World Control at Scale**. [[pdf](https://arxiv.org/pdf/2212.06817)] [[web](https://robotics-transformer1.github.io/)]  
  [![Conference](https://img.shields.io/badge/Conference-RSS-green)](https://roboticsconference.org/)  
  · Anthony Brohan, Noah Brown, Justice Carbajal, Yevgen Chebotar, Joseph Dabis, Chelsea Finn, Keerthana Gopalakrishnan, Karol Hausman, Alex Herzog, Jasmine Hsu, et al. *RSS, 2023; arXiv, 2022*

- **VIMA: General Robot Manipulation with Multimodal Prompts**. [[pdf](https://arxiv.org/pdf/2210.03094)] [[web](https://vimalabs.github.io/)] [[code](https://github.com/vimalabs/VIMA)]  
  [![Conference](https://img.shields.io/badge/Conference-ICML-green)](https://icml.cc/)  
  · Yunfan Jiang, Agrim Gupta, Zichen Zhang, Guanzhi Wang, Yongqiang Dou, Yanjun Chen, Li Fei-Fei, Anima Anandkumar, Yuke Zhu, Linxi Fan. *ICML, 2023*

- **Diffusion Policy: Visuomotor Policy Learning via Action Diffusion**. [[pdf](https://arxiv.org/pdf/2303.04137)] [[web](https://diffusion-policy.cs.columbia.edu/)] [[code](https://github.com/real-stanford/diffusion_policy)]  
  [![Conference](https://img.shields.io/badge/Conference-RSS-green)](https://roboticsconference.org/)  
  · Cheng Chi, Zhenjia Xu, Siyuan Feng, Eric Cousineau, Yilun Du, Benjamin Burchfiel, Russ Tedrake, Shuran Song. *RSS, 2023*

- **PaLM-E: An Embodied Multimodal Language Model**. [[pdf](https://arxiv.org/pdf/2303.03378)] [[web](https://palm-e.github.io/)]  
  [![Conference](https://img.shields.io/badge/Conference-ICML-green)](https://icml.cc/)  
  · Danny Driess, Fei Xia, Mehdi S. M. Sajjadi, Corey Lynch, Aakanksha Chowdhery, Brian Ichter, Ayzaan Wahid, Jonathan Tompson, Quan Vuong, Tianhe Yu, et al. *ICML, 2023*

- **RT-2: Vision-Language-Action Models Transfer Web Knowledge to Robotic Control**. [[pdf](https://arxiv.org/pdf/2307.15818)] [[web](https://robotics-transformer2.github.io/)] [[pmlr](https://proceedings.mlr.press/v229/zitkovich23a.html)]  
  [![Conference](https://img.shields.io/badge/Conference-CoRL-green)](https://www.corl.org/)  
  · Anthony Brohan, Noah Brown, Justice Carbajal, Yevgen Chebotar, Xi Chen, Krzysztof Choromanski, Tianli Ding, Danny Driess, Avinava Dubey, Chelsea Finn, et al. *CoRL, 2023*

- **RoboCat: A Self-Improving Generalist Agent for Robotic Manipulation**. [[pdf](https://arxiv.org/pdf/2306.11706)] [[openreview](https://openreview.net/forum?id=vsCpILiWHu)] [[published pdf](https://openreview.net/pdf?id=vsCpILiWHu)]  
  [![Journal](https://img.shields.io/badge/Journal-TMLR-blue)](https://jmlr.org/tmlr/)  
  · Konstantinos Bousmalis, Giulia Vezzani, Dushyant Rao, Coline Devin, Alex X. Lee, Maria Bauza, Todor Davchev, Yuxiang Zhou, Agrim Gupta, Akhil Raju, et al. *TMLR, 2023*

### 2024

- **Open X-Embodiment: Robotic Learning Datasets and RT-X Models**. [[pdf](https://arxiv.org/pdf/2310.08864)] [[web](https://robotics-transformer-x.github.io/)] [[data](https://github.com/google-deepmind/open_x_embodiment)]  
  [![Conference](https://img.shields.io/badge/Conference-ICRA-green)](https://www.ieee-ras.org/conferences-workshops/fully-sponsored/icra)  
  · Open X-Embodiment Collaboration. *ICRA, 2024; arXiv, 2023*

- **Octo: An Open-Source Generalist Robot Policy**. [[pdf](https://arxiv.org/pdf/2405.12213)] [[web](https://octo-models.github.io/)] [[code](https://github.com/octo-models/octo)]  
  [![Conference](https://img.shields.io/badge/Conference-RSS-green)](https://roboticsconference.org/)  
  · Octo Model Team, Dibya Ghosh, Homer Walke, Karl Pertsch, Kevin Black, Oier Mees, Sudeep Dasari, Joey Hejna, Tobias Kreiman, Charles Xu, et al. *RSS, 2024*

- **OpenVLA: An Open-Source Vision-Language-Action Model**. [[pdf](https://arxiv.org/pdf/2406.09246)] [[web](https://openvla.github.io/)] [[code](https://github.com/openvla/openvla)] [[pmlr](https://proceedings.mlr.press/v270/kim25c.html)]  
  [![Conference](https://img.shields.io/badge/Conference-CoRL-green)](https://www.corl.org/)  
  · Moo Jin Kim, Karl Pertsch, Siddharth Karamcheti, Ted Xiao, Ashwin Balakrishna, Suraj Nair, Rafael Rafailov, Ethan P. Foster, Pannag R. Sanketi, Quan Vuong, et al. *CoRL, 2024; PMLR, 2025*

- **Scaling Cross-Embodied Learning: One Policy for Manipulation, Navigation, Locomotion and Aviation**. [[pdf](https://arxiv.org/pdf/2408.11812)] [[web](https://crossformer-model.github.io/)] [[openreview](https://openreview.net/forum?id=AuJnXGq3AL)] [[code](https://github.com/rail-berkeley/crossformer)]  
  [![Conference](https://img.shields.io/badge/Conference-CoRL_Oral-green)](https://www.corl.org/)  
  · Ria Doshi, Homer Walke, Oier Mees, Sudeep Dasari, Sergey Levine. *CoRL, 2024 Oral*

### 2025

- **π0: A Vision-Language-Action Flow Model for General Robot Control**. [[pdf](https://arxiv.org/pdf/2410.24164)] [[web](https://www.physicalintelligence.company/blog/pi0)] [[code](https://github.com/Physical-Intelligence/openpi)] [[proceedings](https://www.roboticsproceedings.org/rss21/p010.html)]  
  [![Conference](https://img.shields.io/badge/Conference-RSS-green)](https://roboticsconference.org/)  
  · Kevin Black, Noah Brown, Danny Driess, Adnan Esmail, Michael Equi, Chelsea Finn, Niccolo Fusai, Lachy Groom, Karol Hausman, Brian Ichter, et al. *RSS, 2025; arXiv, 2024*

- **FAST: Efficient Action Tokenization for Vision-Language-Action Models**. [[pdf](https://arxiv.org/pdf/2501.09747)] [[web](https://www.physicalintelligence.company/research/fast)] [[code](https://github.com/Physical-Intelligence/openpi)] [[proceedings](https://roboticsproceedings.org/rss21/p012.html)]  
  [![Conference](https://img.shields.io/badge/Conference-RSS-green)](https://roboticsconference.org/)  
  · Karl Pertsch, Kyle Stachowicz, Brian Ichter, Danny Driess, Suraj Nair, Quan Vuong, Oier Mees, Chelsea Finn, Sergey Levine. *RSS, 2025*

- **GR00T N1: An Open Foundation Model for Generalist Humanoid Robots**. [[pdf](https://arxiv.org/pdf/2503.14734)] [[code](https://github.com/NVIDIA/Isaac-GR00T)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2503.14734-red)](https://arxiv.org/abs/2503.14734)  
  · NVIDIA, Johan Bjorck, Fernando Castañeda, Nikita Cherniadev, Xingye Da, Runyu Ding, Linxi “Jim” Fan, Yu Fang, Dieter Fox, Fengyuan Hu, et al. *ArXiv, 2025*

- **Gemini Robotics: Bringing AI into the Physical World**. [[pdf](https://arxiv.org/pdf/2503.20020)] [[web](https://deepmind.google/discover/blog/gemini-robotics-brings-ai-into-the-physical-world/)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2503.20020-red)](https://arxiv.org/abs/2503.20020)  
  · Gemini Robotics Team / Google DeepMind. *ArXiv, 2025*

- **π0.5: a Vision-Language-Action Model with Open-World Generalization**. [[pdf](https://arxiv.org/pdf/2504.16054)] [[web](https://www.physicalintelligence.company/blog/pi05)]  
  [![Conference](https://img.shields.io/badge/Conference-CoRL_Oral-green)](https://www.corl.org/)  
  · Physical Intelligence, Kevin Black, Noah Brown, James Darpinian, Karan Dhabalia, Danny Driess, Adnan Esmail, Michael Equi, Chelsea Finn, Niccolo Fusai, et al. *CoRL, 2025 Oral; arXiv, 2025*

- **SmolVLA: A Vision-Language-Action Model for Affordable and Efficient Robotics**. [[pdf](https://arxiv.org/pdf/2506.01844)] [[code](https://github.com/huggingface/lerobot)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2506.01844-red)](https://arxiv.org/abs/2506.01844)  
  · Mustafa Shukor, Dana Aubakirova, Francesco Capuano, Pepijn Kooijmans, Steven Palma, Adil Zouitine, Michel Aractingi, Caroline Pascal, Martino Russi, Andres Marafioti, et al. *ArXiv, 2025*

- **Mimic-Video: Video-Action Models for Generalizable Robot Control Beyond VLAs**. [[pdf](https://arxiv.org/pdf/2506.07976)] [[web](https://mimic-video.github.io/)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2506.07976-red)](https://arxiv.org/abs/2506.07976)  
  · Jiaheng Hu, Zihang Chen, Xin Ye, Ling Pan, Qingnan Fan, Tony W. Zhang, Xinlong Wang, et al. *ArXiv, 2025*

- **RDT-1B: a Diffusion Foundation Model for Bimanual Manipulation**. [[paper](https://proceedings.iclr.cc/paper_files/paper/2025/hash/49f80e4d2471ad4f2edf4f5f1ab62339-Abstract-Conference.html)] [[web](https://rdt-robotics.github.io/rdt-robotics/)]  
  [![Conference](https://img.shields.io/badge/Conference-ICLR-green)](https://iclr.cc/)  
  · Songming Liu, Lingxuan Wu, Bangguo Li, Hengkai Tan, Huayu Chen, Zhengyi Wang, Ke Xu, Hang Su, Jun Zhu. *ICLR, 2025*
  > Introduces a physically interpretable unified action space for pretraining a diffusion foundation model on heterogeneous multi-robot data.

- **Universal Actions for Enhanced Embodied Foundation Models**. [[paper](https://openaccess.thecvf.com/content/CVPR2025/html/Zheng_Universal_Actions_for_Enhanced_Embodied_Foundation_Models_CVPR_2025_paper.html)] [[code](https://github.com/2toinf/uniact)]  
  [![Conference](https://img.shields.io/badge/Conference-CVPR-green)](https://cvpr.thecvf.com/)  
  · Jinliang Zheng, Jianxiong Li, Dongxiu Liu, Yinan Zheng, Zhihao Wang, Zhonghong Ou, Yu Liu, Jingjing Liu, Ya-Qin Zhang, Xianyuan Zhan. *CVPR, 2025*
  > UniAct learns a Universal Action Space that captures generic behaviors shared by heterogeneous robot embodiments and translates them back to embodiment-specific commands.

- **Learning to Act Anywhere with Task-centric Latent Actions — UniVLA**. [[pdf](https://arxiv.org/pdf/2505.06111)] [[code](https://github.com/OpenDriveLab/UniVLA)]  
  [![Conference](https://img.shields.io/badge/Conference-RSS-green)](https://roboticsconference.org/)  
  · Qingwen Bu, Yanting Yang, Jisong Cai, Shenyuan Gao, Guanghui Ren, Maoqing Yao, Ping Luo, Hongyang Li. *RSS, 2025*
  > Uses task-centric latent actions to exploit heterogeneous human and robot video data for cross-task and cross-embodiment policy learning.

### 2026

- **X-VLA: Soft-Prompted Transformer as Scalable Cross-Embodiment Vision-Language-Action Model**. [[pdf](https://arxiv.org/pdf/2510.10274)] [[openreview](https://openreview.net/forum?id=kt51kZH4aG)] [[code](https://github.com/2toinf/X-VLA)]  
  [![Conference](https://img.shields.io/badge/Conference-ICLR-green)](https://iclr.cc/)  
  · Jinliang Zheng, Jianxiong Li, Zhihao Wang, Dongxiu Liu, Xirui Kang, Yuchun Feng, Yinan Zheng, Jiayin Zou, Yilun Chen, Jia Zeng, Ya-Qin Zhang, Jiangmiao Pang, Jingjing Liu, Tai Wang, Xianyuan Zhan. *ICLR, 2026*
  > Uses embodiment/data-source-specific soft prompts with a shared Transformer backbone for scalable cross-embodiment VLA training.

- **LAP: Language-Action Pre-Training Enables Zero-shot Cross-Embodiment Transfer**. [[pdf](https://arxiv.org/pdf/2602.10556)] [[web](https://lap-vla.github.io/)] [[code](https://github.com/lihzha/lap)]  
  [![Conference](https://img.shields.io/badge/Conference-RSS-green)](https://roboticsconference.org/)  
  · Lihan Zha, Asher J. Hancock, Mingtong Zhang, Tenny Yin, Yixuan Huang, Dhruv Shah, Allen Z. Ren, Anirudha Majumdar. *RSS, 2026*
  > Represents low-level robot actions directly in natural language and achieves zero-shot transfer to previously unseen robot embodiments without embodiment-specific fine-tuning.

- **Embodied Navigation Foundation Model**. [[paper](https://proceedings.iclr.cc/paper_files/paper/2026/hash/ceb45c48e29e7f49b0b47edb98e43691-Abstract-Conference.html)]  
  [![Conference](https://img.shields.io/badge/Conference-ICLR-green)](https://iclr.cc/)  
  · Jiazhao Zhang, Anqi Li, Yunpeng Qi, Minghan Li, Jiahang Liu, Shaoan Wang, Haoran Liu, Gengze Zhou, Yuze Wu, Xingxing Li, Yuxin Fan, Wenjun Li, Zhibo Chen, Fei Gao, Qi Wu, Zhizheng Zhang, He Wang. *ICLR, 2026*
  > NavFoM is trained on eight million navigation samples spanning quadrupeds, drones, wheeled robots, and vehicles across multiple navigation tasks.

- **Universal Pose Pretraining for Generalizable Vision-Language-Action Policies**. [[pdf](https://arxiv.org/pdf/2602.19710)] [[web](https://hetolin.github.io/PoseVLA/)] [[code](https://github.com/hetolin/PoseVLA)]  
  [![Conference](https://img.shields.io/badge/Conference-RSS-green)](https://roboticsconference.org/)  
  · Haitao Lin, Hanyang Yu, Jingshun Huang, He Zhang, Yonggen Ling, Ping Tan, Xiangyang Xue, Yanwei Fu. *RSS, 2026*
  > Pose-VLA uses discrete 3D pose tokens in a unified camera-centric space and separates universal spatial pretraining from embodiment-specific action alignment.

- **Cross-Embodiment Robot Foundation World Models with Latent Actions**. [[pdf](https://openreview.net/pdf/5c8fa1532215f2ea0717ed9db11ee805185dc7d3.pdf)] [[icml](https://icml.cc/virtual/2026/poster/63978)] [[arXiv](https://arxiv.org/abs/2610.10846)] [[pmlr](https://proceedings.mlr.press/v306/huang26bv.html)] [[web](https://lacwm.github.io/)] [[code](https://github.com/qingh097/Latent_action_world_model)]  
  [![Conference](https://img.shields.io/badge/Conference-ICML-green)](https://icml.cc/)  
  · Huang Huang, Sriram Yenamandra, Arjun Majumdar, Elie Aljalbout, Tushar Nagarajan, Tsung-Yen Yang, Akshara Rai, Michael Rabbat, Li Fei-Fei, Jiajun Wu, Tingfan Wu, Franziska Meier. *ICML, 2026*
  > LAC-WM learns a unified latent action space shared across robot embodiments for cross-embodiment world-model pretraining and adaptation.

- **UniDex: A Robot Foundation Suite for Universal Dexterous Hand Control from Egocentric Human Videos**. [[paper](https://openaccess.thecvf.com/content/CVPR2026/html/Zhang_UniDex_A_Robot_Foundation_Suite_for_Universal_Dexterous_Hand_Control_CVPR_2026_paper.html)] [[code](https://github.com/unidex-ai/UniDex)]  
  [![Conference](https://img.shields.io/badge/Conference-CVPR-green)](https://cvpr.thecvf.com/)  
  · Gu Zhang, Qicheng Xu, Haozhe Zhang, Jianhan Ma, Long He, Yiming Bao, Zeyu Ping, Zhecheng Yuan, Chenhao Lu, Chengbo Yuan, Tianhai Liang, Xiaoyu Tian, Maanping Shao, Feihong Zhang, Mingyu Ding, Yang Gao, Hao Zhao, Hang Zhao, Huazhe Xu. *CVPR, 2026*
  > Introduces Function-Actuator-Aligned Space for cross-hand action alignment and a 50K+ trajectory dataset spanning eight dexterous hands.

- **DyPES-VLA: Learning Shared Dynamics Priors and Embodiment-Specific Control for Cross-Embodiment Manipulation**. [[pdf](https://arxiv.org/pdf/2608.06374)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2608.06374-red)](https://arxiv.org/abs/2608.06374)  
  · Junfeng Li, Junjie He, Zhide Zhong, Yangyang Zheng, Pingyue Sheng, Jiayu Dong, Ruixin Li, Haodong Yan, Jiaguan Zhu, Tianran Zhang, et al. *ArXiv, 2026*  
  > Combines future-prediction pretraining with an embodiment-specific mixture-of-experts action head to share interaction dynamics while retaining each robot's native action space.

- **The Embodiment Gap in Robot Foundation Models**. [[pdf](https://arxiv.org/pdf/2608.18433)] [[openreview](https://openreview.net/forum?id=D0XcH9Cso4)]  
  [![Journal](https://img.shields.io/badge/Journal-TMLR-blue)](https://www.jmlr.org/tmlr/)  
  · Yukiyasu Domae, Keisuke Shirai, Hanbit Oh, Ryoichi Nakajo, Tomohiro Motoda, Koshi Makihara, Masaki Murooka, Takuma Yagi, Yoshiaki Bando, Ryo Hanai. *TMLR, 2026; Survey*  
  > Surveys reusable cross-embodiment structure and the adaptation work that remains on a target robot, proposing a reporting framework beyond final task success.

- **AnyWorld: Factorized Egocentric World Models for Cross-Embodiment Generalization**. [[pdf](https://arxiv.org/pdf/2608.29242)] [[web](https://xpeng-robotics.github.io/anyworld/)] [[code](https://github.com/xpeng-robotics/AnyWorld)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2608.29242-red)](https://arxiv.org/abs/2608.29242)  
  · Cheng Chen, Jerry Bai, Jiacheng Wei, Boyu Chen, Xiaoji Zheng, Fan Wu, Minghao Yang, Tianrun Chen, Ruibo Li, Xiaoyu Yue, et al. *ArXiv, 2026*  
  > Factorizes action, camera motion, and embodiment to recompose unpaired human interactions into robot-native video-action experience for policy learning.

- **Multi-View Latent Action Pretraining for Cross-Embodiment Robot Learning from Videos**. [[pdf](https://arxiv.org/pdf/2610.27794)] [[web](https://learnsyslab.github.io/multiview_latent_action_pretraining/)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2610.27794-red)](https://arxiv.org/abs/2610.27794)  
  · Oliver Hausdörfer, Felix Minzenmay, Mani Majd, Maximilian P. Christof, Shiyuan Zhang, Angela P. Schoellig. *ArXiv, 2026*  
  > Learns latent actions from synchronized camera views to resolve depth ambiguity and improve robot skill transfer from action-free videos across embodiments. The linked project is a supplementary website; implementation release was not verified.

- **EXE: Egocentric Cross-Embodiment Pretraining via Factorized Latent Actions for VLA Models**. [[pdf](https://arxiv.org/pdf/2610.33685)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2610.33685-red)](https://arxiv.org/abs/2610.33685)  
  · Qingyuan Cai, Bo Zhang, Yongzhen Huang, Jianyu Chen. *ArXiv, 2026*  
  > Separates transferable manipulation priors from human-specific motion in egocentric-video latent actions, supporting transfer to parallel grippers and dexterous hands.

---

## 1.3 Cross-Robot Adaptation and Cross-Embodiment Manipulation

### 2025

- **Latent Action Diffusion for Cross-Embodiment Manipulation**. [[pdf](https://arxiv.org/pdf/2506.14608)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2506.14608-red)](https://arxiv.org/abs/2506.14608)  
  · Erik Bauer, Elvis Nava, Robert K. Katzschmann. *ArXiv, 2025*

- **Cross-Embodiment Dexterous Hand Articulation Generation via Morphology-Aware Learning**. [[pdf](https://arxiv.org/pdf/2510.06068)] [[web](https://connor-zh.github.io/cross_embodiment_dexterous_grasping/)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2510.06068-red)](https://arxiv.org/abs/2510.06068)  
  · Heng Zhang, Kevin Yuchen Ma, Mike Zheng Shou, Weisi Lin, Yan Wu. *ArXiv, 2025*

- **UniBYD: A Unified Framework for Learning Robotic Manipulation Across Embodiments Beyond Imitation of Human Demonstrations**. [[pdf](https://arxiv.org/pdf/2512.11609)] [[code](https://github.com/zhanheng-creator/UniBYD)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2512.11609-red)](https://arxiv.org/abs/2512.11609)  
  · Tingyu Yuan, Biaoliang Guan, Wen Ye, Ziyan Tian, Yi Yang, Weijie Zhou, Yan Huang, Peng Wang, Chaoyang Zhao, Jinqiao Wang. *ArXiv, 2025*

- **Cross-Embodiment Dexterous Grasping with Reinforcement Learning**. [[paper](https://proceedings.iclr.cc/paper_files/paper/2025/hash/ca8c6f28d8ba1e732e3f217ab05c4ec0-Abstract-Conference.html)] [[web](https://sites.google.com/view/crossdex)]  
  [![Conference](https://img.shields.io/badge/Conference-ICLR-green)](https://iclr.cc/)  
  · Haoqi Yuan, Bohan Zhou, Yuhui Fu, Zongqing Lu. *ICLR, 2025*
  > Uses a human-hand eigengrasp action space and unified fingertip/palm observations to train one dexterous grasping policy across multiple robot hands.

- **LEGATO: Cross-Embodiment Imitation Using a Grasping Tool**. [[pdf](https://arxiv.org/pdf/2411.03682)] [[web](https://ut-hcrl.github.io/LEGATO/)] [[code](https://github.com/UT-HCRL/LEGATO)]  
  [![Journal](https://img.shields.io/badge/Journal-IEEE_RA--L-blue)](https://www.ieee-ras.org/publications/ra-l)  
  · Mingyo Seo, H. Andy Park, Shenli Yuan, Yuke Zhu, Luis Sentis. *IEEE Robotics and Automation Letters, 2025*
  > Uses a handheld gripper as a common action and observation interface and retargets learned motions to heterogeneous robot embodiments.

- **Object-centric 3D Motion Field for Robot Learning from Human Videos**. [[paper](https://proceedings.neurips.cc/paper_files/paper/2025/hash/50f91c82158baed92e9b7e5491a6d997-Abstract-Conference.html)]  
  [![Conference](https://img.shields.io/badge/Conference-NeurIPS-green)](https://neurips.cc/)  
  · Zhao-Heng Yin, Sherry Yang, Pieter Abbeel. *NeurIPS, 2025*
  > Uses an object-centric 3D motion field as an embodiment-agnostic action representation for transferring manipulation skills from human videos to robots.

- **3DFlowAction: Learning Cross-Embodiment Manipulation from 3D Flow World Model**. [[pdf](https://arxiv.org/pdf/2506.06199)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2506.06199-red)](https://arxiv.org/abs/2506.06199)  
  · Hongyan Zhi, Peihao Chen, Siyuan Zhou, Yubo Dong, Quanxi Wu, Lei Han, Mingkui Tan. *ArXiv, 2025*
  > Predicts object-centric 3D flow as an embodiment-independent constraint for cross-embodiment manipulation.

### 2026

- **CEI: A Unified Interface for Cross-Embodiment Visuomotor Policy Learning in 3D Space**. [[pdf](https://arxiv.org/pdf/2601.09163)] [[web](https://cross-embodiment-interface.github.io/)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2601.09163-red)](https://arxiv.org/abs/2601.09163)  
  · Tong Wu, Shoujie Li, Junhao Gong, Changqing Guo, Xingting Li, Shilong Mu, Wenbo Ding. *ArXiv, 2026*

- **Being-H0.5: Scaling Human-Centric Robot Learning for Cross-Embodiment Generalization**. [[pdf](https://arxiv.org/pdf/2601.12993)] [[web](https://research.beingbeyond.com/being-h05)] [[code](https://github.com/BeingBeyond/Being-H)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2601.12993-red)](https://arxiv.org/abs/2601.12993)  
  · Hao Luo, Ye Wang, Wanpeng Zhang, Sipeng Zheng, Ziheng Xi, Chaoyi Xu, Haiweng Xu, Haoqi Yuan, Chi Zhang, Yiqing Wang, et al. *ArXiv, 2026*

- **MOTIF: Learning Action Motifs for Few-shot Cross-Embodiment Transfer**. [[pdf](https://arxiv.org/pdf/2602.13764)] [[code](https://github.com/buduz/MOTIF)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2602.13764-red)](https://arxiv.org/abs/2602.13764)  
  · Heng Zhi, Wentao Tan, Lei Zhu, Fengling Li, Jingjing Li, Guoli Yang, Heng Tao Shen. *ArXiv, 2026*

- **Cross-Embodiment Offline Reinforcement Learning for Heterogeneous Robot Datasets**. [[pdf](https://arxiv.org/pdf/2602.18025)] [[openreview](https://openreview.net/forum?id=GrsoLVNy3Y)]  
  [![Conference](https://img.shields.io/badge/Conference-ICLR-green)](https://iclr.cc/)  
  · Haruki Abe, Takayuki Osa, Yusuke Mukuta, Tatsuya Harada. *ICLR, 2026*

- **Cross-robot behavior adaptation through intention alignment**. [[paper](https://www.science.org/doi/10.1126/scirobotics.adv2250)] [[pubmed](https://pubmed.ncbi.nlm.nih.gov/41849566/)]  
  [![Journal](https://img.shields.io/badge/Journal-Science_Robotics-blue)](https://www.science.org/journal/scirobotics)  
  · Xi Chen, Yuan Gao, Hangxin Liu, Fangkai Yang, Ali Ghadirzadeh, Jun Yang, Bin Liang, Chongjie Zhang, Tin Lun Lam, Song-Chun Zhu. *Science Robotics, 2026*

- **CE-Nav: Flow-Guided Reinforcement Refinement for Cross-Embodiment Local Navigation**. [[paper](https://proceedings.iclr.cc/paper_files/paper/2026/hash/514bdfb12b318ad02c6f28dc68f2feea-Abstract-Conference.html)]  
  [![Conference](https://img.shields.io/badge/Conference-ICLR-green)](https://iclr.cc/)  
  · Kai Yang, Tianlin Zhang, Zhengbo Wang, Zedong Chu, Xiaolong Wu, Yang Cai, Mu Xu. *ICLR, 2026*
  > Separates embodiment-agnostic geometric reasoning from embodiment-specific dynamics adaptation for quadrupeds, bipeds, and quadrotors.

- **X-Diffusion: Training Diffusion Policies on Cross-Embodiment Human Demonstrations**. [[web](https://portal-cornell.github.io/X-Diffusion/)]  
  [![Conference](https://img.shields.io/badge/Conference-ICRA-green)](https://www.ieee-ras.org/conferences-workshops/fully-sponsored/icra)  
  · Maximus A. Pace, Prithwish Dan, Chuanruo Ning, Atiksh Bhardwaj, Audrey Du, Edward W. Duan, Wei-Chiu Ma, Kushal Kedia. *ICRA, 2026*
  > Uses progressively noised human actions so task-level behavior can transfer from human demonstrations while low-noise supervision remains robot-compatible.

- **One-Policy-Fits-All: Geometry-Aware Action Latents for Cross-Embodiment Manipulation**. [[pdf](https://arxiv.org/pdf/2603.14522)]  
  [![Conference](https://img.shields.io/badge/Conference-ICRA-green)](https://www.ieee-ras.org/conferences-workshops/fully-sponsored/icra)  
  · Juncheng Mu, Sizhe Yang, Hojin Bae, Feiyu Jia, Qingwei Ben, Boyi Li, Huazhe Xu, Jiangmiao Pang. *ICRA, 2026*
  > OPFA learns a Geometry-Aware Latent Representation and a unified retargeting decoder for heterogeneous grippers and dexterous hands.

- **Cross-Embodiment Transfer via Behavior-Aligned Representations**. [[pdf](https://arxiv.org/pdf/2607.27549)] [[web](https://ajaysridhar.com/barx/)] [[code](https://github.com/ajaysridhar0/barx)]  
  [![Conference](https://img.shields.io/badge/Conference-ICRA-green)](https://www.ieee-ras.org/conferences-workshops/fully-sponsored/icra)  
  · Ajay Sridhar, Jensen Gao, Jonathan Yang, Jean Mercat, Suneel Belkhale, Dorsa Sadigh. *ICRA, 2026*
  > BARX studies behavior-aligned intermediate representations such as object boxes, language motions, and end-effector traces for cross-embodiment VLA transfer.

- **Cross-Hand Latent Representation for Vision-Language-Action Models**. [[paper](https://openaccess.thecvf.com/content/CVPR2026/html/Jiang_Cross-Hand_Latent_Representation_for_Vision-Language-Action_Models_CVPR_2026_paper.html)]  
  [![Conference](https://img.shields.io/badge/Conference-CVPR-green)](https://cvpr.thecvf.com/)  
  · Guangqi Jiang, Yutong Liang, Jianglong Ye, Jia-Yang Huang, Changwei Jing, Rocky Duan, Pieter Abbeel, Xiaolong Wang, Xueyan Zou. *CVPR, 2026*
  > Learns a shared latent action space across dexterous robot hands and integrates it into VLA models for cross-hand training and transfer.

- **GraspGen-X: Cross-Embodiment 6-DOF Diffusion-based Grasping**. [[paper](https://openaccess.thecvf.com/content/CVPR2026/html/Han_GraspGen-X_Cross-Embodiment_6-DOF_Diffusion-based_Grasping_CVPR_2026_paper.html)]  
  [![Conference](https://img.shields.io/badge/Conference-CVPR-green)](https://cvpr.thecvf.com/)  
  · Beining Han, Yu-Wei Chao, Erwin Coumans, Clemens Eppner, Jia Deng, Stan Birchfield, Adithyavairavan Murali. *CVPR, 2026*
  > Conditions a diffusion grasp generator on gripper morphology and trains on 395M simulated grasps for zero-shot generalization to novel grippers.

- **TraceGen: World Modeling in 3D Trace Space Enables Learning from Cross-Embodiment Videos**. [[web](https://tracegen.github.io/)]  
  [![Conference](https://img.shields.io/badge/Conference-CVPR-green)](https://cvpr.thecvf.com/)  
  · Seungjae Lee, Yoonkyo Jung, Inkook Chun, Yao-Chih Lee, Zikui Cai, Hongjia Huang, Aayush Talreja, Tan Dat Dao, Yongyuan Liang, Jia-Bin Huang, Furong Huang. *CVPR, 2026*
  > Uses 3D trace-space world modeling to learn transferable motion representations from heterogeneous human and robot videos.

- **Any2Any: Efficient Cross-Embodiment Transfer for Humanoid Whole-Body Tracking**. [[pdf](https://arxiv.org/pdf/2605.23733)] [[web](https://any2any.top/)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2605.23733-red)](https://arxiv.org/abs/2605.23733)  
  · Ming Yang, Tao Yu, Feng Li, Hua Chen. *ArXiv, 2026*  
  > Transfers pretrained humanoid whole-body trackers through kinematic alignment and parameter-efficient adaptation of dynamics-sensitive policy components.

- **ZETA: A Controlled Study of Zero-Shot Cross-Embodiment VLA Transfer for Tabletop Manipulation**. [[pdf](https://arxiv.org/pdf/2609.02546)] [[web](https://theone2006.github.io/ZETA-Web/)] [[repo](https://github.com/MiYanDoris/ZETA)]  
  [![Conference](https://img.shields.io/badge/Conference-CoRL-green)](https://www.corl.org/)  
  · Mi Yan, Wenhao Zhang, Zhiqi Zhang, Yu Peng, Tangxinyu Wang, Lingfei Zhai, Jiayi Su, Shengliang Deng, Lin Peng, Yaowei Liu, et al. *CoRL, 2026; author-reported acceptance*  
  > Distinguishes strict from pretrain-exposed zero-shot transfer and isolates representation, embodiment diversity, and co-training effects across held-out tabletop robot embodiments. Implementation release is forthcoming as of this update.

- **A4A: Cross-Embodiment Transfer of Action-Oriented 4D Affordances from Human Demonstrations**. [[pdf](https://arxiv.org/pdf/2609.05892)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2609.05892-red)](https://arxiv.org/abs/2609.05892)  
  · Yifan Han, Litao Liu, Yuqi Gu, Ye Lu, Hanqing Wang, Sidney Wai, Ishaan Myrie, Qi Zhang, Jingjin Yu, Gen Li. *ArXiv, 2026*  
  > Transfers language-conditioned future trajectories of interaction-relevant 3D points from human demonstrations to robot policies through action-oriented 4D affordance pretraining.

- **Improving Cross-embodiment Transfer in Latent Action Models with Action-Similarity Supervision**. [[pdf](https://arxiv.org/pdf/2609.19846)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2609.19846-red)](https://arxiv.org/abs/2609.19846)  
  · Maxime Alvarez, Renzo Caballero, Tatsuya Matsushima, Yusuke Iwasawa, Yutaka Matsuo. *ArXiv, 2026*  
  > Supervises latent-action similarities using end-effector motion similarity, encouraging transferable actions without requiring direct reconstruction of embodiment-specific controls.

- **GOTT: Object-centric Dexterous Manipulation with a Reusable Cross-Embodiment Primitive**. [[pdf](https://arxiv.org/pdf/2610.03861)] [[web](https://dex-gott.github.io/)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2610.03861-red)](https://arxiv.org/abs/2610.03861)  
  · Yulin Liu, Lai Wei, Yen-Jen Wang, Akash Sharma, Pieter Abbeel, Henrik I. Christensen, Haozhi Qi. *ArXiv, 2026*  
  > Uses a shared closed-loop contact-acquisition primitive and object-motion tracking to execute dexterous manipulation across different arm-hand platforms and unseen hand morphologies.

- **Cross-Embodiment Motion Planning by Coupling Body-Agnostic World Model with Differentiable Ego-Dynamics**. [[pdf](https://arxiv.org/pdf/2610.41330)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2610.41330-red)](https://arxiv.org/abs/2610.41330)  
  · Zhidong Wang, Zirui Li, Haoran Xu, Yujie Yan, Zitong Shan, Jingsong Liang, Han Yu, Chen Lv. *ArXiv, 2026*  
  > Couples a body-agnostic visual world model with differentiable robot ego-dynamics through camera motion for cross-embodiment local motion planning.

---

## 1.4 Embodiment Co-design and Morphology Generation

### 2019

- **Neural Graph Evolution: Towards Efficient Automatic Robot Design**. [[pdf](https://arxiv.org/pdf/1906.05370)] [[web](https://www.cs.toronto.edu/~henryzhou/NGE_website/)] [[code](https://github.com/WilsonWangTHU/neural_graph_evolution)]  
  [![Conference](https://img.shields.io/badge/Conference-ICLR-green)](https://iclr.cc/)  
  · Tingwu Wang, Yuhao Zhou, Sanja Fidler, Jimmy Ba. *ICLR, 2019*

### 2021

- **Embodied Intelligence via Learning and Evolution**. [[pdf](https://www.nature.com/articles/s41467-021-25874-z.pdf)] [[code](https://github.com/agrimgupta92/derl)]  
  [![Journal](https://img.shields.io/badge/Journal-Nature_Communications-blue)](https://www.nature.com/ncomms/)  
  · Agrim Gupta, Silvio Savarese, Surya Ganguli, Li Fei-Fei. *Nature Communications, 2021*

### 2023

- **DiffuseBot: Breeding Soft Robots With Physics-Augmented Generative Diffusion Models**. [[pdf](https://arxiv.org/pdf/2311.17053)] [[web](https://diffusebot.github.io/)]  
  [![Conference](https://img.shields.io/badge/Conference-NeurIPS-green)](https://neurips.cc/)  
  · Tsun-Hsuan Wang, Juntian Zheng, Pingchuan Ma, Yilun Du, Byungchul Kim, Andrew Everett Spielberg, Joshua B. Tenenbaum, Chuang Gan, Daniela Rus. *NeurIPS, 2023*

### 2024

- **Dynamics-Guided Diffusion Model for Sensor-less Robot Manipulator Design**. [[pdf](https://arxiv.org/pdf/2402.15038)] [[web](https://dgdm-robot.github.io/)] [[code](https://github.com/real-stanford/dgdm)]  
  [![Conference](https://img.shields.io/badge/Conference-CoRL-green)](https://www.corl.org/)  
  · Xiaomeng Xu, Huy Ha, Shuran Song. *CoRL, 2024*

- **CUDA-Accelerated Soft Robot Neural Evolution with Large Language Model Supervision**. [[pdf](https://arxiv.org/pdf/2405.00698)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2405.00698-red)](https://arxiv.org/abs/2405.00698)  
  · Lechen Zhang. *ArXiv, 2024*

### 2025

- **LASeR: Towards Diversified and Generalizable Robot Design with Large Language Models**. [[pdf](https://openreview.net/pdf?id=7mlvOHL6qJ)] [[openreview](https://openreview.net/forum?id=7mlvOHL6qJ)] [[code](https://github.com/WoodySJR/LASeR)]  
  [![Conference](https://img.shields.io/badge/Conference-ICLR-green)](https://iclr.cc/)  
  · Junru Song, Yang Yang, Huan Xiao, Wei Peng, Wen Yao, Feifei Wang. *ICLR, 2025*

- **BodyGen: Advancing Towards Efficient Embodiment Co-Design**. [[pdf](https://arxiv.org/pdf/2503.00533)] [[web](https://genesisorigin.github.io/)] [[code](https://github.com/GenesisOrigin/BodyGen)]  
  [![Conference](https://img.shields.io/badge/Conference-ICLR_Spotlight-green)](https://iclr.cc/)  
  · Haofei Lu, Zhe Wu, Junliang Xing, Jianshu Li, Ruoyu Li, Zhe Li, Yuanchun Shi. *ICLR, 2025 Spotlight*

- **Generating Freeform Endoskeletal Robots**. [[pdf](https://arxiv.org/pdf/2412.01036)] [[openreview](https://openreview.net/forum?id=awvJBtB2op)] [[code](https://github.com/iffiX/endoskeletal)]  
  [![Conference](https://img.shields.io/badge/Conference-ICLR_Spotlight-green)](https://iclr.cc/)  
  · Muhan Li, Lingji Kong, Sam Kriegman. *ICLR, 2025 Spotlight*

- **Morphology Evolution for Embodied Robot Design With a Classifier-Guided Diffusion Model**. [[ieee](https://ieeexplore.ieee.org/document/11003187)] [[code](https://github.com/HandingWangXDGroup/CDMEO)]  
  [![Journal](https://img.shields.io/badge/Journal-IEEE_TEC-blue)](https://ieeexplore.ieee.org/xpl/RecentIssue.jsp?punumber=4235)  
  · Shulei Liu, Junchi Yan, Handing Wang, Yaochu Jin. *IEEE Transactions on Evolutionary Computation, 2025*

- **Morphological Design Methodologies of Soft Robots**. [[pdf](https://www.the-innovation.org/data/article/informatics/preview/pdf/TII-2025-0022.pdf)] [[web](https://www.the-innovation.org/article/doi/10.59717/j.xinn-inform.2025.100012)]  
  [![Journal](https://img.shields.io/badge/Journal-The_Innovation_Informatics-blue)](https://www.the-innovation.org/)  
  · Beijia Zhang, Jie Shen, Zhenyu He, et al. *The Innovation Informatics, 2025*

- **Learning to Design Soft Hands using Reward Models**. [[pdf](https://arxiv.org/pdf/2510.17086)] [[web](https://hakuna25.github.io/softhand/)] [[code](https://github.com/Hakuna25/Learning_to_design_softhands)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2510.17086-red)](https://arxiv.org/abs/2510.17086)  
  · Xueqian Bai, Nicklas Hansen, Adabhav Singh, Michael T. Tolley, Yan Duan, Pieter Abbeel, Xiaolong Wang, Sha Yi. *ArXiv, 2025*

### 2026

- **RoboMorph: Evolving Robot Morphology using Large Language Models**. [[pdf](https://arxiv.org/pdf/2407.08626)] [[doi](https://doi.org/10.1109/ICRA57385.2026.11696020)] [[web](https://robomorph.github.io/)] [[code](https://github.com/kevinxqiu/robomorph)]  
  [![Conference](https://img.shields.io/badge/Conference-ICRA-green)](https://www.ieee-ras.org/conferences-workshops/fully-sponsored/icra)  
  · Kevin Qiu, Władysław Pałucki, Krzysztof Ciebiera, Paweł Fijałkowski, Marek Cygan, Łukasz Kuciński. *ICRA, 2026; earlier RSS workshop version, 2024*

- **Efficient Robot Design with Multi-Objective Black-Box Optimization and Large Language Models**. [[pdf](https://arxiv.org/pdf/2511.17178)] [[web](https://haraduka.github.io/urdf-llm-opt/)] [[doi](https://doi.org/10.1109/ACCESS.2026.3664844)]  
  [![Journal](https://img.shields.io/badge/Journal-IEEE_Access-blue)](https://ieeeaccess.ieee.org/)  
  · Kento Kawaharazuka, Yoshiki Obinata, Naoaki Kanazawa, Haoyu Jia, Kei Okada. *IEEE Access, 2026; arXiv, 2025*

- **Accelerated Co-design of Robots through Morphological Pretraining**. [[pdf](https://arxiv.org/pdf/2502.10862)] [[openreview](https://openreview.net/forum?id=WVliGyFwZv)]  
  [![Conference](https://img.shields.io/badge/Conference-ICLR-green)](https://iclr.cc/)  
  · Luke Strgar, Sam Kriegman. *ICLR, 2026*

- **House Of Dextra: Cross-Embodied Co-Design for Dexterous Hands**. [[pdf](https://arxiv.org/pdf/2512.03743)] [[web](https://an-axolotl.github.io/co-design-for-dexterity.github.io/)] [[openreview](https://openreview.net/forum?id=k8ovuXEQQu)]  
  [![Conference](https://img.shields.io/badge/Conference-ICLR-green)](https://iclr.cc/)  
  · Kehlani Fay, Darin Anthony Djapri, Anya Zorin, James Clinton, Ali El Lahib, Hao Su, Michael T. Tolley, Sha Yi, Xiaolong Wang. *ICLR, 2026*

- **Efficient Morphology-Control Co-Design via Stackelberg Proximal Policy Optimization**. [[pdf](https://arxiv.org/pdf/2603.15388)] [[web](https://yanningdai.github.io/stackelberg-ppo-co-design/)] [[openreview](https://openreview.net/forum?id=sJ0vOOkclw)] [[code](https://github.com/YanningDai/StackelbergPPO)]  
  [![Conference](https://img.shields.io/badge/Conference-ICLR-green)](https://iclr.cc/)  
  · Yanning Dai, Yuhui Wang, Dylan R. Ashley, Jürgen Schmidhuber. *ICLR, 2026*

- **Shape Your Body: Value Gradients for Multi-Embodiment Robot Design**. [[pdf](https://arxiv.org/pdf/2606.00702)] [[web](https://nico-bohlinger.github.io/shape-your-body/)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2606.00702-red)](https://arxiv.org/abs/2606.00702)  
  · Nico Bohlinger, Jan Peters. *ArXiv, 2026*
  > Reuses a multi-embodiment value function as a differentiable surrogate for optimizing morphology and control parameters through value gradients.

- **Learning to Reconfigure: Configuration-Control Co-optimization of Reconfigurable Robots for Heterogeneous Locomotion**. [[paper](https://proceedings.mlr.press/v306/xiong26h.html)] [[web](https://ltrweb.github.io/learning_to_reconfigure/)] [[code](https://github.com/Xiaoyu-Xiong/Learning-to-Reconfig)]  
  [![Conference](https://img.shields.io/badge/Conference-ICML-green)](https://icml.cc/)  
  · Xiaoyu Xiong, Kehan Liu, Huiyi Yan, Shengjie Wang, Yang Gao, Tao Du. *ICML, 2026*  
  > Co-optimizes reconfigurable robot configurations and low-level control primitives, with a learned high-level scheduler selecting configurations across heterogeneous locomotion subtasks.

- **When Search Becomes Memory: Accelerating Robot Design Discovery with Self-Evolving Skills**. [[paper](https://aclanthology.org/2026.emnlp-main.368/)] [[code](https://github.com/wangyf9/Auto-Robotist)] [[arXiv](https://arxiv.org/abs/2605.25832)]  
  [![Conference](https://img.shields.io/badge/Conference-EMNLP-green)](https://aclanthology.org/2026.emnlp-main.368/)  
  · Yunfei Wang, Xiaohao Xu, Yang Li, Xiaonan Huang. *EMNLP, 2026*  
  > Auto-Robotist turns morphology-search experience into an explicit natural-language skill library that is retrieved and revised during evolutionary design, evaluated across seven EvoGym tasks with transfer from smaller to larger design spaces.

- **Transformer Transformer: A Unified Model for Motion-Conditioned Robot Co-design**. [[pdf](https://arxiv.org/pdf/2607.25798)] [[web](https://transformer-transformer.github.io/)] [[code](https://github.com/real-stanford/transformer-transformer)]  
  [![Conference](https://img.shields.io/badge/Conference-CoRL-green)](https://www.corl.org/)  
  · Huy Ha, C. Karen Liu, Shuran Song. *CoRL, 2026; author-reported acceptance*  
  > Uses RoboTokens and a diffusion transformer to jointly represent embodiments, states and actions, guiding complete robot design generation toward target motions and validating a redesigned ALOHA platform.

- **LACE-CRAFT: Robot Co-Design with Actor Inheritance and Blackboard Collaboration**. [[pdf](https://arxiv.org/pdf/2610.09283)] [[web](https://deemostech.github.io/lace-craft/)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2610.09283-red)](https://arxiv.org/abs/2610.09283)  
  · Yuhan Wen, Jiawei Wang, Qixuan Zhang, Yusen Qin, Lan Xu. *ArXiv, 2026*  
  > Reuses incumbent policy experience during morphology-reward search and coordinates LLM design roles through shared experiment records and behavioral replays, with locomotion evaluations and a fabricated prototype.

- **Learning Purposeful Co-designs of Bio-inspired Quadrupedal Robots**. [[pdf](https://arxiv.org/pdf/2611.02462)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2611.02462-red)](https://arxiv.org/abs/2611.02462)  
  · Fabio Boekel, Jiatao Ding, Cosimo Della Santina. *ArXiv, 2026*  
  > Combines a morphology-conditioned RL policy with task-specific Bayesian design selection for Dogger, a modular quadruped with adjustable geometry and passive knee compliance, and validates the resulting designs on hardware.

- **Towards end-to-end co-design for one-shot printable task-specific soft robots**. [[pdf](https://arxiv.org/pdf/2611.03216)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2611.03216-red)](https://arxiv.org/abs/2611.03216)  
  · James Wood, André Farinha, Will Browne, Josh Pinskier, Krishna Manaswi Digumarti. *ArXiv, 2026*  
  > Jointly optimizes material distribution, pneumatic actuator placement and control in a differentiable simulator, then fabricates task-specific soft arms in one monolithic FDM print and evaluates them physically.

---

# 2. Datasets and Benchmarks

## 2.1 Real-Robot Datasets and Collection Platforms

Includes both multi-embodiment datasets and single-platform data sources or collection systems used in generalist robot learning. Multiple tasks or scenes do not by themselves imply multiple robot embodiments.

### 2023

- **BridgeData V2: A Dataset for Robot Learning at Scale**. [[paper](https://arxiv.org/pdf/2308.12952)] [[web](https://rail-berkeley.github.io/bridgedata/)]  
  [![Conference](https://img.shields.io/badge/Conference-CoRL-green)](https://www.corl.org/)  
  · Homer Walke, Kevin Black, Abraham Lee, Moo Jin Kim, Max Du, Chongyi Zheng, Tony Zhao, Philippe Hansen-Estruch, Quan Vuong, Andre He, Vivek Myers, Kuan Fang, Chelsea Finn, Sergey Levine. *CoRL, 2023*  
  > 60,096 trajectories collected across 24 environments on a publicly available low-cost robot.

### 2024

- **RH20T: A Comprehensive Robotic Dataset for Learning Diverse Skills in One-Shot**. [[paper](https://arxiv.org/pdf/2307.00595)] [[web](https://rh20t.github.io/)] [[doi](https://doi.org/10.1109/ICRA57147.2024.10611615)]  
  [![Conference](https://img.shields.io/badge/Conference-ICRA-green)](https://www.ieee-ras.org/conferences-workshops/fully-sponsored/icra)  
  · Hao-Shu Fang, Hongjie Fang, Zhenyu Tang, Jirong Liu, Chenxi Wang, Junbo Wang, Haoyi Zhu, Cewu Lu. *ICRA, 2024; arXiv, 2023*  
  > 110k+ contact-rich manipulation sequences with visual, force, audio, action, human demonstration video, and language description.

- **Open X-Embodiment Dataset**. [[paper](https://arxiv.org/pdf/2310.08864)] [[web](https://robotics-transformer-x.github.io/)] [[data](https://github.com/google-deepmind/open_x_embodiment)]  
  [![Conference](https://img.shields.io/badge/Conference-ICRA-green)](https://www.ieee-ras.org/conferences-workshops/fully-sponsored/icra)  
  · Open X-Embodiment Collaboration. *ICRA, 2024*  
  > 1M+ real robot trajectories spanning 22 robot embodiments, assembled from 60 datasets contributed by 34 labs.

- **DROID: A Large-Scale In-the-Wild Robot Manipulation Dataset**. [[paper](https://arxiv.org/pdf/2403.12945)] [[web](https://droid-dataset.github.io/)] [[data](https://droid-dataset.github.io/)]  
  [![Conference](https://img.shields.io/badge/Conference-RSS-green)](https://roboticsconference.org/)  
  · Alexander Khazatsky, Karl Pertsch, Suraj Nair, Ashwin Balakrishna, Sudeep Dasari, Siddharth Karamcheti, Soroush Nasiriany, Mohan Kumar Srirama, et al. *RSS, 2024*  
  > 76k demonstration trajectories / 350 hours, collected across 564 scenes and dozens of tasks by 50 data collectors.

- **Mobile ALOHA: Learning Bimanual Mobile Manipulation using Low-Cost Whole-Body Teleoperation**. [[paper](https://arxiv.org/pdf/2401.02117)] [[web](https://mobile-aloha.github.io/)] [[code](https://github.com/MarkFzp/mobile-aloha)] [[pmlr](https://proceedings.mlr.press/v270/fu25b.html)]  
  [![Conference](https://img.shields.io/badge/Conference-CoRL-green)](https://www.corl.org/)  
  · Zipeng Fu, Tony Z. Zhao, Chelsea Finn. *CoRL, 2024; PMLR, 2025; arXiv, 2024*  
  > Low-cost bimanual mobile manipulation platform and demonstrations.

- **ALOHA Unleashed: A Simple Recipe for Robot Dexterity**. [[paper](https://arxiv.org/pdf/2410.13126)] [[pmlr](https://proceedings.mlr.press/v270/zhao25b.html)]  
  [![Conference](https://img.shields.io/badge/Conference-CoRL-green)](https://www.corl.org/)  
  · Tony Z. Zhao, Jonathan Tompson, Danny Driess, Pete Florence, Seyed Kamyar Seyed Ghasemipour, Chelsea Finn, Ayzaan Wahid. *CoRL, 2024; PMLR, 2025*  
  > Large-scale bimanual manipulation setup for dexterous tasks.

- **RoboSet / RoboAgent**. [[paper](https://arxiv.org/abs/2309.01918)] [[web](https://robopen.github.io/)] [[data](https://robopen.github.io/roboset/)] [[code](https://github.com/robopen/roboagent/)]  
  [![Conference](https://img.shields.io/badge/Conference-ICRA-green)](https://www.ieee-ras.org/conferences-workshops/fully-sponsored/icra)  
  · Homanga Bharadhwaj, Jay Vakil, Mohit Sharma, Abhinav Gupta, Shubham Tulsiani, Vikash Kumar. *Dataset associated with RoboAgent, ICRA, 2024; arXiv, 2023*  
  > Real-world kitchen manipulation data collected on Franka-Emika hardware with Robotiq grippers. The dataset page lists 28,500 trajectories; RoboAgent uses a 7,500-trajectory subset.

### 2025

- **RoboMIND: Benchmark on Multi-embodiment Intelligence Normative Data for Robot Manipulation**. [[paper](https://arxiv.org/pdf/2412.13877)] [[web](https://x-humanoid-robomind.github.io/)] [[data](https://huggingface.co/datasets/x-humanoid-robomind/RoboMIND)] [[proceedings](https://roboticsproceedings.org/rss21/p152.html)]  
  [![Conference](https://img.shields.io/badge/Conference-RSS-green)](https://roboticsconference.org/)  
  · Kun Wu, Chengkai Hou, Jiaming Liu, Zhengping Che, Xiaozhu Ju, Zhuqin Yang, Meng Li, Yinuo Zhao, Zhiyuan Xu, Guang Yang, et al. *RSS, 2025; arXiv, 2024*  
  > 107k demonstration trajectories across 479 tasks, 96 object classes, and four robotic embodiments.

- **RoboMIND 2.0: A Multimodal, Bimanual Mobile Manipulation Dataset for Generalizable Embodied Intelligence**. [[paper](https://arxiv.org/pdf/2512.24653)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2512.24653-red)](https://arxiv.org/abs/2512.24653)  
  · Chengkai Hou, Kun Wu, Jiaming Liu, Zhengping Che, Di Wu, Fei Liao, Guangrun Li, Jingyang He, Qiuxuan Feng, Zhao Jin, et al. *ArXiv, 2025*  
  > 310k+ dual-arm manipulation trajectories across six robot embodiments and 739 tasks, plus tactile and mobile-manipulation episodes.

### 2026

- **AGIBOT WORLD 2026**. [[web](https://agibot-world.com/)] [[data](https://huggingface.co/datasets/agibot-world/AgiBotWorld2026)] [[release](https://www.agibot.com/article/231/detail/129.html)]  
  [![Dataset](https://img.shields.io/badge/Dataset-2026-purple)](https://huggingface.co/datasets/agibot-world/AgiBotWorld2026)  
  · AGIBOT. *Dataset release, 2026; Release 4: Physical Reasoning, 2026-10-22*  
  > Real-world AGIBOT G2 interaction data with hierarchical task/action annotations; the October 2026 Physical Reasoning release links high-level Q&A and decisions to low-level execution trajectories across alternative task conditions.

---

## 2.2 Manipulation / Language / VLA Benchmarks

### 2020

- **RLBench: The Robot Learning Benchmark & Learning Environment**. [[paper](https://arxiv.org/pdf/1909.12271)] [[web](https://sites.google.com/view/rlbench)] [[code](https://github.com/stepjam/RLBench)]  
  [![Journal](https://img.shields.io/badge/Journal-IEEE_RA--L-blue)](https://www.ieee-ras.org/publications/ra-l)  
  · Stephen James, Zicong Ma, David Rovick Arrojo, Andrew J. Davison. *IEEE Robotics and Automation Letters, 2020; arXiv, 2019*  
  > 100 language-conditioned robot manipulation tasks in simulation.

### 2021

- **robomimic / What Matters in Learning from Offline Human Demonstrations for Robot Manipulation**. [[paper](https://arxiv.org/pdf/2108.03298)] [[web](https://robomimic.github.io/)] [[code](https://github.com/ARISE-Initiative/robomimic)]  
  [![Conference](https://img.shields.io/badge/Conference-CoRL-green)](https://www.corl.org/)  
  · Ajay Mandlekar, Danfei Xu, Josiah Wong, Soroush Nasiriany, Chen Wang, Rohun Kulkarni, Li Fei-Fei, Silvio Savarese, Yuke Zhu, Roberto Martín-Martín. *CoRL, 2021*

### 2022

- **CALVIN: A Benchmark for Language-Conditioned Policy Learning for Long-Horizon Robot Manipulation Tasks**. [[paper](https://arxiv.org/pdf/2112.03227)] [[web](http://calvin.cs.uni-freiburg.de/)] [[code](https://github.com/mees/calvin)]  
  [![Journal](https://img.shields.io/badge/Journal-IEEE_RA--L-blue)](https://www.ieee-ras.org/publications/ra-l)  
  · Oier Mees, Lukas Hermann, Erick Rosete-Beas, Wolfram Burgard. *IEEE Robotics and Automation Letters, 2022; arXiv, 2021*

### 2023

- **LIBERO: Benchmarking Knowledge Transfer for Lifelong Robot Learning**. [[paper](https://arxiv.org/pdf/2306.03310)] [[web](https://libero-project.github.io/)] [[code](https://github.com/Lifelong-Robot-Learning/LIBERO)]  
  [![Conference](https://img.shields.io/badge/Conference-NeurIPS-green)](https://neurips.cc/)  
  · Bo Liu, Yifeng Zhu, Chongkai Gao, Yihao Feng, Qiang Liu, Yuke Zhu, Peter Stone. *NeurIPS Datasets and Benchmarks, 2023*  
  > Four procedural task suites, 130 tasks, and human-teleoperated demonstrations.

### 2025

- **ManiSkill3: GPU Parallelized Robotics Simulation and Rendering for Generalizable Embodied AI**. [[paper](https://arxiv.org/pdf/2410.00425)] [[docs](https://maniskill.readthedocs.io/)] [[code](https://github.com/haosulab/ManiSkill)] [[data](https://huggingface.co/datasets/haosulab/ManiSkill_Demonstrations)] [[proceedings](https://roboticsproceedings.org/rss21/p021.html)]  
  [![Conference](https://img.shields.io/badge/Conference-RSS-green)](https://roboticsconference.org/)  
  · Stone Tao, Fanbo Xiang, Arth Shukla, Yuzhe Qin, Xander Hinrichsen, Xiaodi Yuan, Chen Bao, Xinsong Lin, Yulin Liu, Tse-kai Chan, et al. *RSS, 2025; arXiv, 2024*
  > The RSS proceedings version is titled *Demonstrating GPU Parallelized Robot Simulation and Rendering for Generalizable Embodied AI with ManiSkill3*.

- **RoboVerse: Towards a Unified Platform, Dataset and Benchmark for Scalable and Generalizable Robot Learning**. [[paper](https://arxiv.org/pdf/2504.18904)] [[web](https://roboverseorg.github.io/)] [[code](https://github.com/RoboVerseOrg/RoboVerse)]  
  [![Conference](https://img.shields.io/badge/Conference-RSS-green)](https://roboticsconference.org/)  
  · Haoran Geng, Feishi Wang, Songlin Wei, Yuyang Li, Bangjun Wang, Boshi An, Charlie Tianyue Cheng, Haozhe Lou, Peihao Li, Yen-Jen Wang, et al. *RSS, 2025*  
  > Simulation platform, synthetic dataset, and unified benchmarks for scalable robot learning.

### 2026

- **RoboTwin 2.0: A Scalable Data Generator and Benchmark with Strong Domain Randomization for Robust Bimanual Robotic Manipulation**. [[paper](https://arxiv.org/pdf/2506.18088)] [[web](https://robotwin-platform.github.io/)] [[code](https://github.com/robotwin-Platform/RoboTwin)] [[pmlr](https://proceedings.mlr.press/v306/chen26j.html)]  
  [![Conference](https://img.shields.io/badge/Conference-ICML-green)](https://icml.cc/)  
  · Tianxing Chen, Zanxin Chen, Baijun Chen, Zijian Cai, Yibin Liu, Zixuan Li, Qiwei Liang, Xianliang Lin, Yiheng Ge, Zhenyu Gu, et al. *ICML, 2026; arXiv, 2025*  
  > 50 dual-arm tasks, five robot embodiments, and RoboTwin Object Dataset with 731 objects / 147 categories.

- **RoboCasa365: A Large-Scale Simulation Framework for Training and Benchmarking Generalist Robots**. [[pdf](https://arxiv.org/pdf/2603.04356)] [[web](https://robocasa.ai/)] [[code](https://github.com/robocasa/robocasa)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2603.04356-red)](https://arxiv.org/abs/2603.04356)  
  · Soroush Nasiriany, Sepehr Nasiriany, Abhiram Maddukuri, Yuke Zhu. *ArXiv, 2026*  
  > Expands RoboCasa to 365 household manipulation tasks and 2,500 kitchen environments, with human and synthetic demonstrations for systematic generalist-policy and lifelong-learning evaluation.

- **X2Real: an eXtensive simulation benchmark for real-world generalist policies**. [[pdf](https://arxiv.org/pdf/2609.27449)] [[web](https://x2robot.com/en/pages/x2real)] [[code](https://github.com/X-Square-Robot/x2real)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2609.27449-red)](https://arxiv.org/abs/2609.27449)  
  · Lian Ruan, Jade Yang, Sherphylan Gao, Felix Gao, Kyson Liang, Galen Liu, Ligo Wu, Lane Jin, Guu Gu, Bevan Xie, et al. *ArXiv, 2026*  
  > Evaluates generalist manipulation policies with 44 long-horizon simulation tasks, hardware-calibrated visual and physical properties, disjoint training/evaluation pipelines and annotated simulation trajectories.

---

## 2.3 Morphology and Cross-Embodiment Benchmarks

Resources for morphology generalization, locomotion, co-design, and manipulation across different robot bodies or hands.

### 2019

- **Modular Robot / NGE Environments**. [[paper](https://arxiv.org/pdf/1906.05370)] [[code](https://github.com/WilsonWangTHU/neural_graph_evolution)]  
  [![Conference](https://img.shields.io/badge/Conference-ICLR-green)](https://iclr.cc/)  
  · Used by Neural Graph Evolution for graph-based robot body evolution and control.

### 2021

- **UNIMAL / DERL Morphology Suite**. [[paper](https://www.nature.com/articles/s41467-021-25874-z.pdf)] [[code](https://github.com/agrimgupta92/derl)]  
  [![Journal](https://img.shields.io/badge/Journal-Nature_Communications-blue)](https://www.nature.com/ncomms/)  
  · Used by DERL and MetaMorph-style universal morphology control; modular morphology evolution and locomotion-control benchmark.

### 2025

- **AnyBody: A Benchmark Suite for Cross-Embodiment Manipulation**. [[paper](https://arxiv.org/pdf/2505.14986)] [[web](https://princeton-vl.github.io/anybody/)] [[code](https://github.com/meenalparakh/anybody)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2505.14986-red)](https://arxiv.org/abs/2505.14986)  
  · Meenal Parakh, Alexandre Kirchmeyer, Beining Han, Jia Deng. *ArXiv, 2025*
  > Standardized reach/push benchmark for cross-embodiment manipulation, with interpolation, extrapolation, and composition generalization axes.

- **GENBOT-1K**. [[paper](https://arxiv.org/pdf/2505.05753)] [[web](https://embodiment-scaling-laws.github.io/)] [[code](https://github.com/BoAi01/embodiment-scaling-laws)]  
  [![Conference](https://img.shields.io/badge/Conference-CoRL-green)](https://www.corl.org/)  
  · Introduced with *Towards Embodiment Scaling Laws in Robot Locomotion*. *CoRL, 2025*
  > Roughly 1,000 procedurally generated humanoid, quadruped, and hexapod embodiments for studying embodiment scaling and zero-shot morphology generalization.

### 2026

- **RoboCasa-X**. [[code](https://github.com/ajaysridhar0/barx)] [[web](https://ajaysridhar.com/barx/)]  
  [![Conference](https://img.shields.io/badge/Conference-ICRA-green)](https://www.ieee-ras.org/conferences-workshops/fully-sponsored/icra)  
  · Introduced with *Cross-Embodiment Transfer via Behavior-Aligned Representations*. *ICRA, 2026*
  > Simulation benchmark designed to measure transfer from heterogeneous source embodiments to held-out robot embodiments.

- **UniDex-Dataset**. [[paper](https://openaccess.thecvf.com/content/CVPR2026/html/Zhang_UniDex_A_Robot_Foundation_Suite_for_Universal_Dexterous_Hand_Control_CVPR_2026_paper.html)] [[code](https://github.com/unidex-ai/UniDex)]  
  [![Conference](https://img.shields.io/badge/Conference-CVPR-green)](https://cvpr.thecvf.com/)  
  · Introduced with *UniDex*. *CVPR, 2026*
  > 50K+ robot-centric trajectories across eight dexterous hands with 6–24 DoF, derived from egocentric human videos through retargeting.

- **CEDex Cross-Embodiment Grasp Dataset**. [[code](https://github.com/jangys99/CEDex)]  
  [![Conference](https://img.shields.io/badge/Conference-ICRA-green)](https://www.ieee-ras.org/conferences-workshops/fully-sponsored/icra)  
  · Introduced with *CEDex: Cross-Embodiment Dexterous Grasp Generation at Scale from Human-like Contact Representations*. *ICRA, 2026*
  > 20M grasps across 500K objects and four gripper types.

- **TraceForge-123K**. [[web](https://tracegen.github.io/)]  
  [![Conference](https://img.shields.io/badge/Conference-CVPR-green)](https://cvpr.thecvf.com/)  
  · Introduced with *TraceGen*. *CVPR, 2026*
  > 123K videos and 1.8M observation–3D-trace–language triplets for cross-embodiment world-model learning.

- **Co-design Gym: A Unified Benchmark for Embodiment-Policy Co-optimization**. [[pdf](https://arxiv.org/pdf/2610.02366)] [[web](https://camral.github.io/codesigngym/)]  
  [![ArXiv](https://img.shields.io/badge/ArXiv-2610.02366-red)](https://arxiv.org/abs/2610.02366)  
  · Aviraj Newatia, Yordan Tsvetkov, Leonard Pleiss, Andrew Spielberg, Rika Antonova. *ArXiv, 2026*  
  > Provides a unified benchmark for joint embodiment-policy optimization across 20 environment families and over 85 presets, including robot locomotion, manipulation, soft dynamics and multi-robot cooperation. Code is pending release approval.

---

# 3. Suggested Reading Paths

## 3.1 Universal Morphology Control

1. NerveNet → My Body is a Cage / Amorpheus → Snowflake  
2. SWAT → MetaMorph → ModuMorph  
3. HyperDistill → GET-Zero → GCNT → Shared Modular Recurrence → RecMorph  
4. 2026 extensions: Embedding Morphology into Transformers → DexGrasp-Zero → Morphology-Conditioned World Model → WestWorld

## 3.1b Universal / Generalist Legged Locomotion

1. Shared locomotion: GenLoco → ManyQuadrupeds → URMA / One Policy to Run Them All → Multi-Loco  
2. Online adaptation: RMA → LocoFormer → Rapid Embodiment Adaptation  
3. Cross-humanoid whole-body control: XHugWBC → X-WBC → CrossBFM → MimicAll  
4. Shared differentiable models: MorphMimic; distinguish jointly trained bodies from unseen-body transfer.

## 3.2 Cross-Embodiment Generalist Robot Policy

1. BC-Z → RT-1 → RT-2  
2. Open X-Embodiment / RT-X → Octo → CrossFormer → OpenVLA  
3. π0 → FAST → π0.5 → SmolVLA / GR00T / Gemini Robotics  
4. Latent actions and world models: LAC-WM → AnyWorld → Multi-View Latent Action Pretraining → EXE  
5. Evaluation and reporting: The Embodiment Gap in Robot Foundation Models → ZETA. Track **observation heterogeneity**, **action-space heterogeneity**, **target-robot exposure**, and **adaptation effort**.

## 3.3 Cross-Robot Adaptation

1. Hardware Conditioned Policies → Hierarchically Decoupled Imitation  
2. Cross-robot behavior adaptation through intention alignment  
3. CEI → MOTIF → Cross-Embodiment Offline RL → Latent Action Diffusion / UniBYD  
4. Object and affordance transfer: A4A → GOTT; whole-body transfer: Any2Any  
5. Embodiment-aware navigation: CE-Nav → Hourglass

## 3.4 Embodiment Co-design

1. Neural Graph Evolution → DERL  
2. DiffuseBot → DGDM → LASeR / BodyGen  
3. Morphological Pretraining → House of Dextra → Stackelberg PPO  
4. Reconfigurable and generative design: Learning to Reconfigure → Transformer Transformer  
5. Search experience reuse: Auto-Robotist → LACE-CRAFT  
6. Hardware validation and benchmarking: Dogger → one-shot printable soft robots → Co-design Gym

---

# 4. Verification Notes

## 4.1 Additions in the 2026-11-06 Update

Added **29 resources**: 27 research, survey, or benchmark papers, one technical report (MorphMimic), and one dataset release (AGIBOT WORLD 2026). Coverage focuses on August–November 2026, with selected earlier omissions. The newest confirmed first submissions included here are dated **2026-11-02**.

| Section | Added resources | Entries |
|---|---:|---|
| 1.1 Morphology control | 8 | RecMorph; X-WBC; CrossBFM; Higher-Order Morphology Priors; MimicAll; MorphMimic; WestWorld; LocoFormer. |
| 1.2 Generalist policies and world models | 5 | DyPES-VLA; AnyWorld; Multi-View Latent Action Pretraining; EXE; The Embodiment Gap in Robot Foundation Models. |
| 1.3 Cross-robot transfer | 6 | Any2Any; ZETA; A4A; Action-Similarity Supervision; GOTT; Hourglass. |
| 1.4 Embodiment co-design | 6 | Learning to Reconfigure; Transformer Transformer; Auto-Robotist; LACE-CRAFT; Learning Purposeful Co-designs / Dogger; one-shot printable soft-robot co-design. |
| 2.1 Real-robot data | 1 | AGIBOT WORLD 2026, including Release 4: Physical Reasoning. |
| 2.2 Generalist-policy benchmarks | 2 | RoboCasa365; X2Real. |
| 2.3 Morphology and cross-embodiment benchmarks | 1 | Co-design Gym. |


## 4.2 Additions in the 2026-08-28 Update

- Added One Policy to Run Them All, UniLegs, Towards Embodiment Scaling Laws in Robot Locomotion, Multi-Embodiment Locomotion at Scale, and Rapid Embodiment Adaptation.
- Added RDT-1B, Universal Actions / UniAct, UniVLA, X-VLA, LAP, NavFoM, Pose-VLA, LAC-WM, and UniDex.
- Added CrossDex, LEGATO, Object-centric 3D Motion Field, 3DFlowAction, CE-Nav, X-Diffusion, OPFA, BARX, Cross-Hand Latent Representation, GraspGen-X, and TraceGen.
- Added Shape Your Body: Value Gradients for Multi-Embodiment Robot Design.
- Added GENBOT-1K, RoboCasa-X, UniDex-Dataset, CEDex Cross-Embodiment Grasp Dataset, and TraceForge-123K.
