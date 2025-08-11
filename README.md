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

# Batch Normalization
This section lists papers from the Batch Normalization branch in Test-Time Adaptation, focusing on methods that leverage batch normalization techniques, such as adapting normalization statistics or layers, to improve model performance at test time without source data access. The list includes papers from 2019 to 2023, with select 2024 papers where specified, and includes links to papers, projects, or code where available.

| Title | Authors | Conference/Venue | Year | Link |
|-------|---------|------------------|------|------|
| Fully Test-Time Adaptation by Sampling | Yu Sun, Xiaolong Wang, Zhuang Liu, John Miller, Alexei A. Efros, Moritz Hardt | Proc. ICML | 2020 | [arXiv:2002.08782](https://arxiv.org/abs/2002.08782) |
| Improving Robustness Against Common Corruptions by Covariate Shift Adaptation | Steffen Schneider, Evgenia Rusak, Luisa Eck, Oliver Bringmann, Wieland Brendel, Matthias Bethge | Proc. NeurIPS | 2020 | [arXiv:2006.14970](https://arxiv.org/abs/2006.14970) [Code](https://github.com/bethgelab/robustness) |
| Revisiting Batch Normalization for Improving Corruption Robustness | Philipp Benz, Chaithanya Kumar Mummadi, Jan Hendrik Metzen, Volker Fischer | Proc. WACV | 2021 | [CVF Open Access](http://openaccess.thecvf.com/content/WACV2021/html/Benz_Revisiting_Batch_Normalization_for_Improving_Corruption_Robustness_WACV_2021_paper.html) [Code](https://github.com/phibenz/batch_norm_adaptation.pytorch) |
| Adaptive Risk Minimization: Learning to Adapt to Domain Shift | Marvin Zhang, Henrik Marklund, Nikita Arora, Yuheng Zhang, Sergey Levine, Chelsea Finn | Proc. NeurIPS | 2021 | [OpenReview](https://openreview.net/forum?id=-zgb2v8vV_w) [Code](https://github.com/henrikmarklund/arm) |
| Adaptive Methods for Real-World Domain Generalization | Abhimanyu Dubey, Vignesh Ramanathan, Alex Pentland, Dhruv Mahajan | Proc. CVPR | 2021 | [CVF Open Access](https://openaccess.thecvf.com/content/CVPR2021/html/Dubey_Adaptive_Methods_for_Real-World_Domain_Generalization_CVPR_2021_paper.html) [Code](https://github.com/abhimanyudubey/PrototypicalDomainGeneralization) |
| Limitations of Post-Hoc Feature Alignment for Robustness | David X. Li, Chenhan Yuan, Anima Anandkumar, Stefano Soatto | Proc. CVPR | 2021 | [CVF Open Access](https://openaccess.thecvf.com/content/CVPR2021/html/Li_Limitations_of_Post-Hoc_Feature_Alignment_for_Robustness_CVPR_2021_paper.html) [Code](https://github.com/davidli125/limitations_post_hoc) |
| AdaBN: Adaptive Batch Normalization for Domain Adaptation | Mattia Segu, Alessio Tonioni, Federico Tombari | Proc. CVPR | 2021 | [CVF Open Access](https://openaccess.thecvf.com/content/CVPR2021/html/Segu_AdaBN_Adaptive_Batch_Normalization_for_Domain_Adaptation_CVPR_2021_paper.html) |
| Covariate Shift Adaptation for Adversarially Robust Classifier | Jay Nandy, Sudipan Saha, Rishabh Iyer | Proc. ICLR Workshops | 2021 | [PDF](https://aisecure-workshop.github.io/aml-iclr2021/papers/2.pdf) |
| Test-Time Batch Normalization | Guanyu Cai, Lianghua Huang, Fengbin Chang, Yufei Wang | Proc. ECCV | 2022 | [arXiv:2203.17205](https://arxiv.org/abs/2203.17205) |
| Meta-DMoE: Adapting to Domain Shift by Meta-Distillation from Mixture-of-Experts | Tao Zhong, Feng Ji, Zhiyi He, Zihan Liu, Zhaowei Cai, Ming Liu, Nicu Sebe, Dacheng Tao | Proc. NeurIPS | 2022 | [OpenReview](https://openreview.net/forum?id=_ekGcr07Dsp) [Code](https://github.com/n3il666/Meta-DMoE) |
| Test-Time Adaptation with Principal Component Analysis | Nicolas Cordier, Amaury Habrard, Marc Sebban | Proc. ECML/PKDD Workshops | 2022 | [arXiv:2209.05779](https://arxiv.org/abs/2209.05779) |
| Learning Less Generalizable Patterns with an Asymmetrically Trained Double Classifier for Better Test-Time Adaptation | Matthieu Duboudin, Mohammad Rostami, Amaury Habrard, Marc Sebban | arXiv | 2022 | [arXiv:2210.09834](https://arxiv.org/abs/2210.09834) |
| TTN: A Domain-Shift Aware Batch Normalization in Test-Time Adaptation | Joonho Lee, Woo Jin Kim, Seunghyeon Seo, Seungyong Han, Seong-Jin Park, Seungkyu Lee | Proc. ICLR | 2023 | [OpenReview](https://openreview.net/forum?id=7X5t0v_6H_) |
| Delta: Degradation-Free Fully Test-Time Adaptation | Naoki Murata, Masaki Yamada, Takashi Shibata, Shota Saito | Proc. ICLR | 2023 | [OpenReview](https://openreview.net/forum?id=7N6V4YgCxh) |
| Towards Stable Test-Time Adaptation in Dynamic Wild World | Shuaicheng Niu, Jiaxiang Wu, Yifan Zhang, Yaofo Chen, Shijian Lu, Peilin Zhao, Junzhou Huang, Peng Cui, Mingkui Tan | Proc. ICLR | 2023 | [arXiv:2210.00826](https://arxiv.org/abs/2210.00826) [Code](https://github.com/mr-eggplant/SATA) |
| Test-Time Adaptation in the Dynamic World with Compound Domain Knowledge Management | Junha Song, Kwanyong Park, Inkyu Shin, Sanghyun Woo, Chaoning Zhang, In So Kweon | IEEE Robotics and Automation Letters | 2023 | [arXiv:2302.14760](https://arxiv.org/abs/2302.14760) |
| Robustness to Corruption in Pre-Trained Bayesian Neural Networks | Zihuan Wang, Laurence Aitchison | Proc. ICLR | 2023 | [OpenReview](https://openreview.net/forum?id=kUI41mY8bHl) |
| Test-Time Distribution Normalization for Contrastively Learned Vision-Language Models | Yifei Zhou, Yucheng Zhou, Mengnan Du, Junzhou Huang, Peng Liu, Yitao Liang | Proc. NeurIPS | 2023 | [arXiv:2302.11084](https://arxiv.org/abs/2302.11084) [Code](https://github.com/fengyuli-dev/distribution-normalization) |
| Adaptive Test-Time Personalization for Federated Learning | Wenxuan Bao, Tianxin Wei, Haohan Wang, Jingrui He | Proc. NeurIPS | 2023 | [arXiv:2310.18816](https://arxiv.org/abs/2310.18816) [Code](https://github.com/baowenxuan/ATP) |
| DomainAdaptor: A Novel Approach to Test-Time Adaptation | Rui Zhang, Jianming Zhang, Hong Chen, Min Li | Proc. ICCV | 2023 | [arXiv:2308.10297](https://arxiv.org/abs/2308.10297) [Code](https://github.com/koncle/DomainAdaptor) |
| ClusT3: Information Invariant Test-Time Training | Gustavo Vargas Hakim, David Osowiechi, Mehrdad Yaghoobi, Sotirios A. Tsaftaris | Proc. ICCV | 2023 | [CVF Open Access](https://openaccess.thecvf.com/content/ICCV2023/html/Hakim_ClusT3_Information_Invariant_Test-Time_Training_ICCV_2023_paper.html) [Code](https://github.com/dosowiechi/ClusT3) |
| TTTFlow: Unsupervised Test-Time Training with Normalizing Flow | David Osowiechi, Gustavo Vargas Hakim, Mehrdad Yaghoobi, Sotirios A. Tsaftaris | Proc. WACV | 2023 | [CVF Open Access](https://openaccess.thecvf.com/content/WACV2023/html/Osowiechi_TTTFlow_Unsupervised_Test-Time_Training_With_Normalizing_Flow_WACV_2023_paper.html) [Code](https://github.com/GustavoVargasHakim/TTTFlow) |
| Channel Selection for Test-Time Adaptation Under Distribution Shift | João Vianna, Rafael Padilha, Leonardo Ferreira, Bruce Magalhães, Nicolas Dobigeon | Proc. NeurIPS Workshops | 2023 | [OpenReview](https://openreview.net/forum?id=BTOBu7y2ZD) |
| Sit Back and Relax: Learning to Drive Incrementally in All Weather Conditions | Joachim Böhme Leitner, Simon Hecker, Stefan K. Schaub, Vasileios Belagiannis | Proc. IEEE Intelligent Vehicles Symposium | 2023 | [arXiv:2305.18953](https://arxiv.org/abs/2305.18953) [Code](https://github.com/jmiemirza/DILAM) |
| Dynamic Batch Norm Statistics Update for Natural Robustness | Saeed Rezaei, Mohammad Sadegh Norouzzadeh | arXiv | 2023 | [arXiv:2310.20649](https://arxiv.org/abs/2310.20649) |
| Test-Time Domain Adaptation by Learning Domain-Aware Batch Normalization | Yanan Wu, Zhixiang Chi, Guosheng Lin, Yonghong Tian, Xing Tang, Xianbin Cao, Haoli Bai | Proc. AAAI | 2024 | [arXiv:2312.10165](https://arxiv.org/abs/2312.10165) [Code](https://github.com/ynanwu/MABN) |

---

# Pseudo Labeling
This section lists papers from the pseudo labeling branch in Test-Time Adaptation, focusing on methods that leverage pseudo-labels generated at test time (often via self-training or related techniques) to adapt models without source data access. The list includes relevant papers from 2019 to 2023 identified from the provided references and queries, with available links to papers, projects, or code where specified.

| Title | Authors | Conference/Venue | Year | Link |
|-------|---------|------------------|------|------|
| Do We Really Need to Access the Source Data? Source Hypothesis Transfer for Unsupervised Domain Adaptation | Jian Liang, Dapeng Hu, Jiashi Feng | Proc. ICML | 2020 | [arXiv:2002.08546](https://arxiv.org/abs/2002.08546) [Code](https://github.com/liangjian66/SHOT) |
| Generative Pseudo-label Refinement for Unsupervised Domain Adaptation | Pietro Morerio, Riccardo Volpi, Ruggero Ragonesi, Vittorio Murino | Proc. WACV | 2020 | [CVF Open Access](https://openaccess.thecvf.com/content_WACV_2020/html/Morerio_Generative_Pseudo-label_Refinement_for_Unsupervised_Domain_Adaptation_WACV_2020_paper.html) |
| A Free Lunch for Unsupervised Domain Adaptive Object Detection without Source Data | Xianfeng Li, Weijie Chen, Di Xie, Shicai Yang, Peng Yuan, Shiliang Pu, Yueting Zhuang | Proc. AAAI | 2021 | [AAAI](https://ojs.aaai.org/index.php/AAAI/article/view/17029) [arXiv:2012.05400](https://arxiv.org/abs/2012.05400) |
| Uncertainty Reduction for Model Adaptation in Semantic Segmentation | Cristiano Saltori, Niccolò Zanella, Fabio Galasso, Giuseppe Fiameni, Elisa Ricci, Nicu Sebe | Proc. CVPR | 2021 | [CVF Open Access](https://openaccess.thecvf.com/content/CVPR2021/html/Saltori_Uncertainty_Reduction_for_Model_Adaptation_in_Semantic_Segmentation_CVPR_2021_paper.html) [Code](https://github.com/saltoricristiano/URMA-SS) |
| Self-Supervised Test-Time Learning for Reading Comprehension | Pratyay Banerjee, Tejas Gokhale, Chitta Baral | Proc. NAACL | 2021 | [ACL Anthology](https://aclanthology.org/2021.naacl-main.404/) |
| If Your Data Distribution Shifts, Use Self-Learning | Evgenia Rusak, Steffen Schneider, George Pachitariu, Luisa Eck, Peter Vincent Gehler, Oliver Bringmann, Wieland Brendel, Matthias Bethge | Transactions on Machine Learning Research | 2022 | [TMLR](https://openreview.net/forum?id=1cNMcC3o4P) [arXiv:2104.12928](https://arxiv.org/abs/2104.12928) [Code](https://domainadaptation.org/selflearning) |
| Continual Test-Time Domain Adaptation | Qin Wang, Olga Fink, Luc Van Gool, Dengxin Dai | Proc. CVPR | 2022 | [arXiv:2203.04266](https://arxiv.org/abs/2203.04266) [Code](https://github.com/qinenergy/cotta) |
| Contrastive Test-Time Adaptation | Dian Chen, Dequan Wang, Trevor Darrell, Sayna Ebrahimi | Proc. CVPR | 2022 | [arXiv:2204.10377](https://arxiv.org/abs/2204.10377) [Code](https://github.com/DianCh/ConTTA) |
| Test-Time Adaptation via Conjugate Pseudo-labels | Sachin Goyal, Mingjie Sun, Aditi Raghunathan, J. Zico Kolter | Proc. NeurIPS | 2022 | [arXiv:2207.09640](https://arxiv.org/abs/2207.09640) [Code](https://github.com/locuslab/tta_conjugate) |
| Towards Understanding GD with Hard and Conjugate Pseudo-labels for Test-Time Adaptation | Jun-Kun Wang, Andre Wibisono | Proc. ICLR | 2023 | [arXiv:2210.10019](https://arxiv.org/abs/2210.10019) |
| TeSLA: Test-Time Self-Learning With Automatic Adversarial Augmentation | Devavrat Tomar, Guillaume Vray, Behzad Bozorgtabar, Jean-Philippe Thiran | Proc. CVPR | 2023 | [arXiv:2303.09870](https://arxiv.org/abs/2303.09870) [Code](https://github.com/devavratTomar/TeSLA) |
| Cycle Self-Training for Domain Adaptation | Hong Liu, Jianmin Wang, Mingsheng Long | Proc. NeurIPS | 2021 | [arXiv:2103.03571](https://arxiv.org/abs/2103.03571) |
| Understanding Self-Training for Gradual Domain Adaptation | Ananya Kumar, Tengyu Ma, Percy Liang | Proc. ICML | 2020 | [arXiv:2002.11361](https://arxiv.org/abs/2002.11361) |
| Confidence Regularized Self-Training | Yang Zou, Zhiding Yu, Xiaofeng Liu, B. V. K. Vijaya Kumar, Jinsong Wang | Proc. ICCV | 2019 | [arXiv:1908.09822](https://arxiv.org/abs/1908.09822) |
| Domain Adaptation for Semantic Segmentation via Class-Balanced Self-Training | Yang Zou, Zhiding Yu, B. V. K. Vijaya Kumar, Jinsong Wang | Proc. ECCV | 2018 | [arXiv:1710.07969](https://arxiv.org/abs/1710.07969) |

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

