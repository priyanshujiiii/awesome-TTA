# Awesome Test-Time Adaptation (TTA)


A curated list of **Test-Time Adaptation (TTA)** methods, papers, and resources.  

---

## Summary Table of TTA Techniques

| Category                        | Description                                                             |
|-------------------------------|-------------------------------------------------------------------------|
| Self-supervision               | Uses auxiliary tasks (e.g., rotation, contrastive loss) for adaptation  |
| Information Entropy            | Minimizes entropy or maximizes mutual information                       |
| Batch Normalization            | Updates BN stats/parameters using test batches                          |
| Pseudo Labeling                | Uses confident predictions as labels for further learning               |
| Class Prototype                | Aligns test features to class centroids                                 |
| Feature Alignment              | Matches test and source feature distributions                           |
| Generative Modeling            | Uses generative models for feature alignment or synthesis               |
| Nearest Neighbors              | Uses feature similarity for decision making or propagation              |
| Augmentation Invariance        | Enforces consistency across augmented views                             |
| Meta-learning                  | Trains models for fast test-time adaptation                             |
| Time-varying / Online TTA      | Adapts to evolving test distributions in real-time                      |
| Source-Free Domain Adaptation  | Assumes no access to source data during inference                       |
| Test-Time Instance Adaptation  | Adapts to each test sample independently                                |
| Test-Time Prior Adaptation     | Leverages priors (e.g., class frequency) at test time                   |

---

## Detailed Descriptions and Papers

# Self-supervision
Leverages auxiliary tasks (e.g., rotation prediction, jigsaw puzzles, contrastive learning) to help the model adapt at test time.

| Title | Authors | Conference/Venue | Year | Link |
|-------|---------|------------------|------|------|
| Test-Time Training with Self-Supervision for Generalization under Distribution Shifts | Yu Sun, Xiaolong Wang, Zhuang Liu, John Miller, Alexei A. Efros, Moritz Hardt | Proc. ICML | 2020 | [arXiv:1909.13231](https://arxiv.org/abs/1909.13231) [Project](https://github.com/yueatsprograms/ttt_self_supervision) |
| Unsupervised Domain Adaptation through Self-Supervision | Yu Sun, Eric Tzeng, Trevor Darrell, Alexei A. Efros | arXiv preprint | 2019 | [arXiv:1909.11825](https://arxiv.org/abs/1909.11825) |
| Test-Time Training with Masked Autoencoders | Yossi Gandelsman, Yu Sun, Xinlei Chen, Alexei A. Efros | Proc. NeurIPS | 2022 | [arXiv:2209.07540](https://arxiv.org/abs/2209.07540) [Project](https://github.com/yossi-gandelsman/ttt-mae) |
| Self-Supervised Test-Time Learning for Reading Comprehension | Pratyay Banerjee, Tejas Gokhale, Chitta Baral | Proc. NAACL | 2021 | [ACL Anthology](https://aclanthology.org/2021.naacl-main.404/) |
| Self-Supervised Test-Time Adaptation on Video Data | Fatemeh Azimi, Sebastian Palacio, Federico Raue, Jörn Hees, Luca Bertinetto, Andreas Dengel | Proc. WACV | 2022 | [CVF Open Access](https://openaccess.thecvf.com/content/WACV2022/html/Azimi_Self-Supervised_Test-Time_Adaptation_on_Video_Data_WACV_2022_paper.html) |
| TTT++: When Does Self-Supervised Test-Time Training Fail or Thrive? | Yuejiang Liu, Parth Kothari, Bastien van Delft, Baptiste Bellot-Gurlet, Taylor Mordan, Alexandre Alahi | Proc. NeurIPS | 2021 | [arXiv:2106.14637](https://arxiv.org/abs/2106.14637) [Code](https://github.com/yuejiang-nj/ttt-plus-plus) |
| TEST: Test-Time Self-Training Under Distribution Shift | Samarth Sinha, Peter Gehler, Francesco Locatello, Bernt Schiele | Proc. WACV | 2023 | [CVF Open Access](https://openaccess.thecvf.com/content/WACV2023/html/Sinha_TEST_Test-Time_Self-Training_Under_Distribution_Shift_WACV_2023_paper.html) |
| If Your Data Distribution Shifts, Use Self-Learning | Evgenia Rusak, Steffen Schneider, George Pachitariu, Luisa Eck, Peter Vincent Gehler, Oliver Bringmann, Wieland Brendel, Matthias Bethge | Transactions on Machine Learning Research | 2022 | [TMLR](https://openreview.net/forum?id=1cNMcC3o4P) |
| Domain Alignment Meets Fully Test-Time Adaptation | Kowshik Thopalli, Pavan Turaga, Jayaraman J. Thiagarajan | Proc. ACML | 2023 | [PMLR](https://proceedings.mlr.press/v191/thopalli23a.html) |
| Autoencoder Based Self-Supervised Test-Time Adaptation for Medical Image Analysis | Yufan He, Aaron Carass, Lianrui Zuo, Blake E. Dewey, Jerry L. Prince | Medical Image Analysis | 2021 | [ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S1361841521002393) |
| Self-Supervised Test-Time Adaptation for Medical Image Segmentation | Hao Li, Han Liu, Dewei Hu, Jiacheng Wang, Hans Johnson, Omar Sherbini, Francesco Gavazzi, Russell D’Aiello, Adeline Vanderver, Jeffrey Long, Paulsen Jane, Ipek Oguz | Proc. MICCAI Workshops | 2022 | [SpringerLink](https://link.springer.com/chapter/10.1007/978-3-031-16452-1_44) (May require institutional access) |
| Re-Using Adversarial Mask Discriminators for Test-Time Training under Distribution Shifts | Gabriele Valvano, Andrea Leo, Sotirios A. Tsaftaris | Journal of Machine Learning for Biomedical Imaging | 2022 | [MELBA Journal](https://www.melba-journal.org/papers/2022:013.html) |
| Model Adaptation: Historical Contrastive Learning for Unsupervised Domain Adaptation without Source Data | Jiaxing Huang, Dayan Guan, Aoran Xiao, Shijian Lu | Proc. NeurIPS | 2021 | [arXiv:2110.03346](https://arxiv.org/abs/2110.03346) |
| Contrastive Test-Time Adaptation | Dian Chen, Dequan Wang, Trevor Darrell, Sayna Ebrahimi | Proc. CVPR | 2022 | [arXiv:2204.10377](https://arxiv.org/abs/2204.10377) [Code](https://github.com/DianCh/ConTTA) |
| Divide and Contrast: Source-free Domain Adaptation via Adaptive Contrastive Learning | Ziyi Zhang, Weikai Chen, Hui Cheng, Zhen Li, Siyuan Li, Liang Lin | Proc. NeurIPS | 2022 | [arXiv:2211.04003](https://arxiv.org/abs/2211.04003) |
| Improved Test-Time Adaptation for Domain Generalization | Liang Chen, Yong Zhang, Yibing Song, Ying Shan, Lingqiao Liu | Proc. CVPR | 2023 | [arXiv:2304.04448](https://arxiv.org/abs/2304.04448) [Code](https://github.com/michuangani/ITTA) |
| PromptStyler: Prompt-driven Style Generation for Source-free Domain Generalization | Junhyeong Cho, Gilhyun Nam, Sungyeon Kim, Hunmin Yang, Suha Kwak | Proc. ICCV | 2023 | [arXiv:2307.15199](https://arxiv.org/abs/2307.15199) |
| MATE: Masked Autoencoders are Online 3D Test-Time Learners | Muhammad Jehanzeb Mirza, Inkyu Shin, Wei Lin, Andreas Schuh, Xiantong Zhen, Unberath Mathias, Inyoung Kim, Hanspeter Pfister | Proc. ICCV | 2023 | [arXiv:2308.08012](https://arxiv.org/abs/2308.08012) |
| On the Robustness of Open-World Test-Time Training: Self-Training with Dynamic Prototype Expansion | Yushu Yang, Yuzheng Wang, Zixuan Chen, Yu Qiao, Yixuan Li | Proc. ICCV | 2023 | [arXiv:2308.14279](https://arxiv.org/abs/2308.14279) [Code](https://github.com/YushuYang/OWTTT) |



---



# Information Entropy
his section lists papers from the Information Entropy branch in Test-Time Adaptation and related unsupervised domain adaptation methods, focusing on entropy minimization or information-theoretic approaches to adapt models at test time without source data access. The list includes papers from 2019 to 2023, with links to papers, projects, or code where available.

| Title | Authors | Conference/Venue | Year | Link |
|-------|---------|------------------|------|------|
| Do We Really Need to Access the Source Data? Source Hypothesis Transfer for Unsupervised Domain Adaptation | Jian Liang, Dapeng Hu, Jiashi Feng | Proc. ICML | 2020 | [arXiv:2002.08546](https://arxiv.org/abs/2002.08546) [Code](https://github.com/liangjian66/SHOT) |
| Tent: Fully Test-Time Adaptation by Entropy Minimization | Dequan Wang, Evan Shelhamer, Shaoteng Liu, Bruno Olshausen, Trevor Darrell | Proc. ICLR | 2021 | [arXiv:2006.10726](https://arxiv.org/abs/2006.10726) [Code](https://github.com/DequanWang/tent) |
| Uncertainty Reduction for Model Adaptation in Semantic Segmentation | Cristiano Saltori, Niccolò Zanella, Fabio Galasso, Giuseppe Fiameni, Elisa Ricci, Nicu Sebe | Proc. CVPR | 2021 | [CVF Open Access](https://openaccess.thecvf.com/content/CVPR2021/html/Saltori_Uncertainty_Reduction_for_Model_Adaptation_in_Semantic_Segmentation_CVPR_2021_paper.html) [Code](https://github.com/saltoricristiano/URMA-SS) |
| Bayesian Adaptation for Covariate Shift | Aurick Zhou, Sergey Levine | Proc. NeurIPS | 2021 | [arXiv:2109.08247](https://arxiv.org/abs/2109.08247) |
| Efficient Test-Time Model Adaptation without Forgetting | Shixiang Tang, Hannah J. Kang, Peng Chen, Yifu Zhang, Xuezhou Zhang, Pengfei Liu, Ruslan Salakhutdinov | Proc. ICML | 2022 | [arXiv:2204.05868](https://arxiv.org/abs/2204.05868) |
| Confidence Score for Source-Free Unsupervised Domain Adaptation | Chenxi Liu, Linhua Yang, Haoling Li, Xuqian Li, Pengfei Liu, Jian Yang | Proc. ICML | 2022 | [arXiv:2203.06954](https://arxiv.org/abs/2203.06954) [Code](https://github.com/LC-2000/CSUDA) |
| Towards Stable Test-Time Adaptation in Dynamic Wild World | Shuaicheng Niu, Jiaxiang Wu, Yifan Zhang, Yaofo Chen, Shijian Lu, Peilin Zhao, Junzhou Huang, Peng Cui, Mingkui Tan | Proc. ICLR | 2023 | [arXiv:2210.00826](https://arxiv.org/abs/2210.00826) [Code](https://github.com/mr-eggplant/SATA) |
| Robust Test-Time Adaptation in Dynamic Scenarios | Longhui Wei, Lingxi Xie, Jianzhong He, Xiaopeng Zhang, Qi Tian | Proc. CVPR | 2023 | [CVF Open Access](https://openaccess.thecvf.com/content/CVPR2023/html/Wei_Robust_Test-Time_Adaptation_in_Dynamic_Scenarios_CVPR_2023_paper.html) |
| EcoTTA: Memory-Efficient Continual Test-Time Adaptation via Self-Distilled Regularization | Zhixiang Chi, Li Gu, Huan Liu, Feng Wei, Xing Tang, Yuanhao Yu, Yanan Wu, Zhi Wang, Yonghong Tian | Proc. CVPR | 2023 | [arXiv:2303.01958](https://arxiv.org/abs/2303.01958) |
| Revisiting Realistic Test-Time Training: Sequential Inference and Adaptation | Yongyi Su, Xun Xu, Kui Jia | Proc. NeurIPS | 2022 | [arXiv:2206.07579](https://arxiv.org/abs/2206.07579) |
---

### Batch Normalization
Updates BatchNorm statistics or affine parameters using test data for adaptation.

- [Paper Title](#)

---

### Pseudo Labeling
Uses confident test predictions as pseudo labels for further fine-tuning.

- [Paper Title](#)

---

### Class Prototype
Aligns test-time feature vectors with source-class centroids for improved classification.

- [Paper Title](#)

---

### Feature Alignment
Matches the feature distribution of test data to that of the source using domain adaptation techniques.

- [Paper Title](#)

---

### Generative Modeling
Uses models like GANs, VAEs, or diffusion models to enhance or translate test data into source-like representations.

- [Paper Title](#)

---

### Nearest Neighbors
Uses similarity in feature space for nearest-neighbor classification or consistency enforcement.

- [Paper Title](#)

---

### Augmentation Invariance
Promotes stable predictions across different augmented views of the same input.

- [Paper Title](#)

---

### Meta-learning
Trains models in a meta-learning framework to adapt quickly to new domains during testing.

- [Paper Title](#)

---

### Time-varying / Online TTA
Adapts continuously to streaming or temporally evolving test distributions.

- [Paper Title](#)

---

### Source-Free Domain Adaptation (SFDA)
Performs adaptation without access to source data; only the pretrained model is used.

- [Paper Title](#)

---

### Test-Time Batch Adaptation (TTBA)
Adapts the model using batches of test samples (e.g., updating BN stats or consistency objectives).

- [Paper Title](#)

---

### Test-Time Instance Adaptation (TTIA)
Applies adaptation independently to each test input.

- [Paper Title](#)

---

### Test-Time Prior Adaptation (TTPA)
Uses test-time priors (e.g., class balance, label statistics) to regularize adaptation.

- [Paper Title](#)

---

