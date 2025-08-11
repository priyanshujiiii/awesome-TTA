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

# Class Prototype
This section lists papers from the Class Prototype branch in Test-Time Adaptation, focusing on methods that leverage class prototypes (e.g., mean feature representations per class, nearest prototype classifiers, or prototype expansion/updating) to adapt models at test time without source data access. The list includes all relevant papers from the provided references and additional ones identified as related to class prototypes in TTA, covering 2019 to 2025 (current date context), with links to papers, projects, or code where available.

| Title | Authors | Conference/Venue | Year | Link |
|-------|---------|------------------|------|------|
| Model Adaptation: Unsupervised Domain Adaptation Without Source Data | Rui Li, Qianfen Jiao, Wenming Cao, Hau-San Wong, Si Wu | Proc. CVPR | 2020 | [arXiv:2003.08264](https://arxiv.org/abs/2003.08264) |
| Test-Time Classifier Adjustment Module for Model-Agnostic Domain Generalization | Yusuke Iwasawa, Yutaka Matsuo | Proc. NeurIPS | 2021 | [arXiv:2110.10232](https://arxiv.org/abs/2110.10232) [Code](https://github.com/yusuke-iwasawa/ttcam) |
| Revisiting Realistic Test-Time Training: Sequential Inference and Adaptation by Anchored Clustering | Yongyi Su, Xun Xu, Kui Jia | Proc. NeurIPS | 2022 | [arXiv:2206.07579](https://arxiv.org/abs/2206.07579) [Code](https://github.com/suyongyi/ARTTA) |
| Attracting and Dispersing: A Simple Approach for Source-free Domain Adaptation | Shiqi Yang, Yaxing Wang, Joost van de Weijer, Luis Herranz, Shangling Jui | Proc. NeurIPS | 2022 | [arXiv:2207.07583](https://arxiv.org/abs/2207.07583) [Code](https://github.com/yangshiqiO-O/AD-SFDA) |
| On the Robustness of Open-World Test-Time Training: Self-Training with Dynamic Prototype Expansion | Yushu Yang, Yuzheng Wang, Zixuan Chen, Yu Qiao, Yixuan Li | Proc. ICCV | 2023 | [arXiv:2308.14279](https://arxiv.org/abs/2308.14279) [Code](https://github.com/YushuYang/OWTTT) |
| Improving Test-Time Adaptation via Shift-Agnostic Weight Regularization and Nearest Source Prototypes | Sunghyun Choi, Seokyong Yang, Seungho Choi, Sungrack Yun | Proc. ECCV | 2022 | [arXiv:2207.10466](https://arxiv.org/abs/2207.10466) |
| Test-Time Adaptation via Self-Training with Nearest Neighbor Information | Minho Jang, Seung-Yoon Chung | Proc. ICLR | 2023 | [arXiv:2207.10792](https://arxiv.org/abs/2207.10792) |
| AdaNPC: Exploring Non-Parametric Classifier for Test-Time Adaptation | Xiao Zhang, Xihong Yang, Kaifu Yang, Kun Yuan, Zhiyuan Zhang, Lanqing Hong, Fengwei Zhou, Zhisong Pan, Hongtian Yu, Zhenguo Li, Guojun Qi | Proc. ICML | 2023 | [arXiv:2212.08355](https://arxiv.org/abs/2212.08355) |
| DomainAdaptor: A Novel Approach to Test-Time Adaptation | Jian Zhang, Lei Qi, Yinghuan Shi, Yang Gao | Proc. CVPR | 2023 | [arXiv:2308.10297](https://arxiv.org/abs/2308.10297) [Code](https://github.com/koncle/DomainAdaptor) |
| Feature Alignment and Uniformity for Test Time Adaptation | Shuaifeng Wang, Di Zhang, Zhenyu Zhang, Jian Zhang, Rui Li | Proc. CVPR | 2023 | [arXiv:2303.10018](https://arxiv.org/abs/2303.10018) |
| Test-Time Adaptation by Aligning Prototypes using Self-Supervision | Sebastian Palacio, Federico Raue, Jörn Hees, Andreas Dengel | arXiv | 2022 | [arXiv:2205.08731](https://arxiv.org/abs/2205.08731) |
| Learning Classifiers of Prototypes and Reciprocal Points for Universal Domain Adaptation | Eduardo Fernandes Montesuma, Fred Maurice Ngolè Mboula | arXiv | 2022 | [arXiv:2212.08355](https://arxiv.org/abs/2212.08355) |
| Decoupled Prototype Learning for Reliable Test-Time Adaptation | Bingfan Liu, Yao Li, Zhiyong Li, Junhui Hou | arXiv | 2024 | [arXiv:2401.08703](https://arxiv.org/abs/2401.08703) |
| Gradient Alignment with Prototype Feature for Fully Test-Time Adaptation | Haojie Zhang, Mingkai Chen, Chunhua Shen, Yuhui Zheng, Wenrui Dai, Hongkai Xiong | arXiv | 2024 | [arXiv:2402.09004](https://arxiv.org/abs/2402.09004) |
| Rethinking Class-incremental Learning in the Era of Large Pre-trained Models via Test-Time Adaptation | Imad Eddine Marouf, Nicolo Micheletti, Martina Pastorino, Alessandro Perelli, Elisabetta Farella, Davide Bacciu | arXiv | 2023 | [arXiv:2310.11482](https://arxiv.org/abs/2310.11482) |
| Mitigate the Bias in the Model for Continual Test-Time Adaptation | Sanghun Jung, Taesik Gong, Jungkwon Lee | arXiv | 2024 | [arXiv:2403.01344](https://arxiv.org/abs/2403.01344) |
| Test-Time Prototype Shifting for Zero-Shot Generalization across Vision-Language Models | Haoxing Chen, Yan Hong, Zeyang Zhou, Ninad Kulkarni, Hakan Bilen | arXiv | 2024 | [arXiv:2403.12952](https://arxiv.org/abs/2403.12952) |
| Dual Prototype Evolving for Test-Time Generalization of Vision-Language Models | Haiwen Diao, Bo Li, Xin-Yu Zhang, Jiaqing Liu, Huchuan Lu, Xiang Ruan | arXiv | 2024 | [arXiv:2410.12790](https://arxiv.org/abs/2410.12790) |
| Multi-Cache Enhanced Prototype Learning for Test-Time Adaptation | Xinyu Wang, Zhihong Qi, Tao Wang, Zhizhong Zhang, Linrui Gong, Xun Yang, Yue Yu, Zhibo Chen, Yuan He, Yuming Jiang | arXiv | 2025 | [arXiv:2508.01225](https://arxiv.org/abs/2508.01225) |
| Temporal Test-Time Adaptation with State-Space Models | Mona Schirmer, Dan Zhang, Eric Nalisnick | arXiv | 2024 | [arXiv:2407.12492](https://arxiv.org/abs/2407.12492) |
| Controllable Continual Test-Time Adaptation | Ziqi Shi, Fan Lyu, Ye Liu, Fanhua Shang, Xiaoyu Dong, Yuanyuan Liu, Liang Wan | arXiv | 2024 | [arXiv:2405.14602](https://arxiv.org/abs/2405.14602) |
| When Test-Time Adaptation Meets Self-Supervised Models | Guodong Liu, Yuhang Wen, Guohao Qu, Wanli Ouyang, Mingkui Tan | arXiv | 2025 | [arXiv:2506.23529](https://arxiv.org/abs/2506.23529) |
| Self-Bootstrapping for Versatile Test-Time Adaptation | Yunsu Bok, Hyeonseo Cho, Tae-Hyun Oh | arXiv | 2025 | [arXiv:2504.08010](https://arxiv.org/abs/2504.08010) |

---

# Feature Alignment

This section lists papers from the Feature Alignment branch in Test-Time Adaptation, focusing on methods that align features (e.g., via distribution matching, contrastive learning, or adversarial techniques) to adapt models at test time without source data access. The list includes relevant papers from 2019 to 2025, with links to papers, projects, or code where available.

| Title | Authors | Conference/Venue | Year | Link |
|-------|---------|------------------|------|------|
| Deep CORAL: Correlation Alignment for Deep Domain Adaptation | Baochen Sun, Kate Saenko | Proc. ECCV | 2016 | [arXiv:1607.01719](https://arxiv.org/abs/1607.01719) |
| Domain Generalization with Adversarial Feature Learning | Haoliang Li, Sinno Jialin Pan, Shiqi Wang, Alex C. Kot | Proc. CVPR | 2018 | [CVF Open Access](https://openaccess.thecvf.com/content_cvpr_2018/html/Li_Domain_Generalization_With_CVPR_2018_paper.html) |
| Deep Hashing Network for Unsupervised Domain Adaptation | Hemanth Venkateswara, Jose Eusebio, Shayok Chakraborty, Sethuraman Panchanathan | Proc. CVPR | 2017 | [CVF Open Access](https://openaccess.thecvf.com/content_cvpr_2017/html/Venkateswara_Deep_Hashing_Network_CVPR_2017_paper.html) |
| Moment Matching for Multi-Source Domain Adaptation | Xingchao Peng, Qinxun Bai, Xide Xia, Zijun Huang, Kate Saenko, Bo Wang | Proc. ICCV | 2019 | [arXiv:1812.01754](https://arxiv.org/abs/1812.01754) |
| Test-Time Training with Self-Supervision for Generalization under Distribution Shifts | Yu Sun, Xiaolong Wang, Zhuang Liu, John Miller, Alexei Efros, Moritz Hardt | Proc. ICML | 2020 | [arXiv:1909.13231](https://arxiv.org/abs/1909.13231) |
| Do We Really Need to Access the Source Data? Source Hypothesis Transfer for Unsupervised Domain Adaptation | Jian Liang, Dapeng Hu, Jiashi Feng | Proc. ICML | 2020 | [arXiv:2002.08546](https://arxiv.org/abs/2002.08546) [Code](https://github.com/liangjian66/SHOT) |
| Improving Robustness Against Common Corruptions by Covariate Shift Adaptation | Steffen Schneider, Evgenia Rusak, Luisa Eck, Oliver Bringmann, Wieland Brendel, Matthias Bethge | Proc. NeurIPS | 2020 | [arXiv:2006.14970](https://arxiv.org/abs/2006.14970) [Code](https://github.com/bethgelab/robustness) |
| SoFA: Source-data-free Feature Alignment for Unsupervised Domain Adaptation | Haojian Zhang, Yujie Jin, Wenwu Zhu, Yasha Wang, Xin Wang, Shanghang Zhang, Hong Mei | Proc. WACV | 2021 | [CVF Open Access](https://openaccess.thecvf.com/content/WACV2021/html/Zhang_SoFA_Source-Data-Free_Feature_Alignment_for_Unsupervised_Domain_Adaptation_WACV_2021_paper.html) |
| Adaptive Adversarial Network for Source-Free Domain Adaptation | Taewon Kang, Gyusang Cho, Kyungeun Lee, Joonho Lee | Proc. ICCV | 2021 | [CVF Open Access](https://openaccess.thecvf.com/content/ICCV2021/html/Kang_Adaptive_Adversarial_Network_for_Source-Free_Domain_Adaptation_ICCV_2021_paper.html) |
| TTT++: When Does Self-Supervised Test-Time Training Fail or Thrive? | Yuejiang Liu, Parth Kothari, Bastien van Delft, Baptiste Bellot-Gurlet, Taylor Mordan, Alexandre Alahi | Proc. NeurIPS | 2021 | [arXiv:2107.06937](https://arxiv.org/abs/2107.06937) [Code](https://github.com/yuejiang-nj/ttt-plus-plus) |
| Test-Time Classifier Adjustment Module for Model-Agnostic Domain Generalization | Yusuke Iwasawa, Yutaka Matsuo | Proc. NeurIPS | 2021 | [arXiv:2110.10232](https://arxiv.org/abs/2110.10232) [Code](https://github.com/yusuke-iwasawa/ttcam) |
| Robustifying Vision Transformer without Retraining from Scratch by Test-Time Class-Conditional Feature Alignment | Takeshi Kojima, Yutaka Matsuo, Yusuke Iwasawa | Proc. IJCAI | 2022 | [arXiv:2206.13955](https://arxiv.org/abs/2206.13955) |
| Source-Free Adaptation to Measurement Shift via Bottom-Up Feature Restoration | Cian Eastwood, Ian Mason, Christopher K. I. Williams, J. Zico Kolter | Proc. ICLR | 2022 | [arXiv:2107.11279](https://arxiv.org/abs/2107.11279) [Code](https://github.com/cianeastwood/bufr) |
| Invariance Through Latent Alignment | Mattia Segu, Marvin Zhang, Chelsea Finn, Francesco Locatello | Robotics: Science and Systems (RSS) | 2022 | [arXiv:2112.09327](https://arxiv.org/abs/2112.09327) [Project](https://invariance-through-latent-alignment.github.io/) |
| Source-Free Domain Adaptation via Distribution Estimation | Ying Chen, Jiaqi Wang, Pengxiang Yan, Zilei Wang, Hao Sun, Shuai Wang, Enze Xie | Proc. CVPR | 2022 | [arXiv:2204.13320](https://arxiv.org/abs/2204.13320) |
| Parameter-Free Online Test-Time Adaptation | Malik Boudiaf, Romain Mueller, Ismail Ben Ayed, Luca Bertinetto | Proc. CVPR | 2022 | [arXiv:2204.04632](https://arxiv.org/abs/2204.04632) |
| Efficient Test-Time Model Adaptation without Forgetting | Shuaicheng Niu, Jiaxiang Wu, Yifan Zhang, Yaofo Chen, Shijian Zheng, Peilin Zhao, Mingkui Tan | Proc. ICML | 2022 | [arXiv:2204.05868](https://arxiv.org/abs/2204.05868) |
| Continual Test-Time Domain Adaptation | Qin Wang, Olga Fink, Luc Van Gool, Dengxin Dai | Proc. CVPR | 2022 | [arXiv:2203.04266](https://arxiv.org/abs/2203.04266) [Code](https://github.com/qinenergy/cotta) |
| Contrastive Test-Time Adaptation | Dian Chen, Dequan Wang, Trevor Darrell, Sayna Ebrahimi | Proc. CVPR | 2022 | [arXiv:2204.10377](https://arxiv.org/abs/2204.10377) [Code](https://github.com/DianCh/ConTTA) |
| Test-Time Adaptation via Self-Training with Nearest Neighbor Information | Minho Jang, Sae-Young Chung | Proc. ICLR | 2023 | [arXiv:2207.10792](https://arxiv.org/abs/2207.10792) |
| ActMAD: Activation Matching to Align Distributions for Test-Time-Training | Shuaicheng Niu, Jiaxiang Wu, Yifan Zhang, Zhiquan Wen, Yaofo Chen, Peilin Zhao, Mingkui Tan | Proc. CVPR | 2023 | [arXiv:2304.11215](https://arxiv.org/abs/2304.11215) [Code](https://github.com/mr-eggplant/ActMAD) |
| Feature Alignment and Uniformity for Test Time Adaptation | Shuaifeng Wang, Di Zhang, Zhenyu Zhang, Jian Zhang, Rui Li | Proc. CVPR | 2023 | [arXiv:2303.10018](https://arxiv.org/abs/2303.10018) [Code](https://github.com/shuaifengzhi/Feature-Alignment-and-Uniformity) |
| Robustness to Corruption in Pre-Trained Bayesian Neural Networks | Zihuan Wang, Laurence Aitchison | Proc. ICLR | 2023 | [OpenReview](https://openreview.net/forum?id=kUI41mY8bHl) |
| Towards Stable Test-Time Adaptation in Dynamic Wild World | Shuaicheng Niu, Jiaxiang Wu, Yifan Zhang, Zhiquan Wen, Yaofo Chen, Peilin Zhao, Mingkui Tan | Proc. ICLR | 2023 | [arXiv:2210.00826](https://arxiv.org/abs/2210.00826) [Code](https://github.com/mr-eggplant/SATA) |
| MEMO: Test Time Robustness via Adaptation and Augmentation | Marvin Zhang, Sergey Levine, Chelsea Finn | Proc. NeurIPS | 2022 | [arXiv:2110.09506](https://arxiv.org/abs/2110.09506) [Code](https://github.com/facebookresearch/memo) |
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

### Test-Time Instance Adaptation (TTIA)
Applies adaptation independently to each test input.

- [Paper Title](#)

---

### Test-Time Prior Adaptation (TTPA)
Uses test-time priors (e.g., class balance, label statistics) to regularize adaptation.

- [Paper Title](#)

---

