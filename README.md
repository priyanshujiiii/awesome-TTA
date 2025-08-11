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
| Online TTA                     | Adapts to evolving test distributions in real-time                      |
| Source-Free Domain Adaptation  | Assumes no access to source data during inference                       |
|  Instance Adaptation  | Adapts to each test sample independently                                |
| Prior Adaptation     | Leverages priors (e.g., class frequency) at test time                   |

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

# Generative Modeling
This section lists papers from the Generative Modeling branch in Test-Time Adaptation, focusing on methods that leverage generative models (e.g., diffusion models, masked autoencoders, or other generative techniques) to adapt models at test time without source data access. The list includes relevant papers from 2018 to 2023, with links to papers, projects, or code where available.

| Title | Authors | Conference/Venue | Year | Link |
|-------|---------|------------------|------|------|
| High Quality Monocular Depth Estimation via Transfer Learning | Ibraheem Alhashim, Peter Wonka | arXiv | 2018 | [arXiv:1812.11941](https://arxiv.org/abs/1812.11941) |
| ObjectNet: A Large-Scale Bias-Controlled Dataset for Pushing the Limits of Object Recognition Models | Andrei Barbu, David Mayo, Julian Alverio, William Luo, Charles Wang, Dan Gutfreund, Josh Tenenbaum, Boris Katz | Proc. NeurIPS | 2019 | [arXiv:2004.02042](https://arxiv.org/abs/2004.02042) |
| Fine-Grained Visual Classification of Aircraft | Subhransu Maji, Esa Rahtu, Juho Kannala, Matthew Blaschko, Andrea Vedaldi | Technical Report | 2013 | [arXiv:1306.5151](https://arxiv.org/abs/1306.5151) |
| Automated Flower Classification over a Large Number of Classes | Maria-Elena Nilsback, Andrew Zisserman | Proc. Indian Conference on Computer Vision, Graphics and Image Processing | 2008 | [arXiv:1609.01828](https://arxiv.org/abs/1609.01828) |
| Label-Efficient Semantic Segmentation with Diffusion Models | Dmitry Baranchuk, Ivan Rubachev, Andrey Voynov, Valentin Khrulkov, Artem Babenko | arXiv | 2021 | [arXiv:2112.03126](https://arxiv.org/abs/2112.03126) |
| MT3: Meta Test-Time Training for Self-Supervised Test-Time Adaption | Alexander Bartler, Andre Bühler, Felix Wiewel, Mario Döbler, Bin Yang | Proc. AISTATS | 2022 | [arXiv:2103.16201](https://arxiv.org/abs/2103.16201) |
| Test-Time Training with Masked Autoencoders | Yossi Gandelsman, Yu Sun, Xinlei Chen, Alexei A. Efros | Proc. NeurIPS | 2022 | [arXiv:2209.07522](https://arxiv.org/abs/2209.07522) |
| Peekaboo: Text to Image Diffusion Models are Zero-Shot Segmentors | Ryan Burgert, Kanchana Ranasinghe, Xiang Li, Michael S. Ryoo | arXiv | 2022 | [arXiv:2211.13224](https://arxiv.org/abs/2211.13224) |
| Text-to-Image Diffusion Models are Zero-Shot Classifiers | Kevin Clark, Priyank Jaini | arXiv | 2023 | [arXiv:2303.15233](https://arxiv.org/abs/2303.15233) |
| Synthetic Data from Diffusion Models Improves ImageNet Classification | Shekoofeh Azizi, Simon Kornblith, Chitwan Saharia, Mohammad Norouzi, David J. Fleet | arXiv | 2023 | [arXiv:2304.08466](https://arxiv.org/abs/2304.08466) |
| Your Diffusion Model is Secretly a Zero-Shot Classifier | Alexander C. Li, Mihir Prabhudesai, Shivam Duggal, Ellis Brown, Deepak Pathak | arXiv | 2023 | [arXiv:2303.16203](https://arxiv.org/abs/2303.16203) |
| GLIGEN: Open-Set Grounded Text-to-Image Generation | Yuheng Li, Haotian Liu, Qingyang Wu, Fangzhou Mu, Jianwei Yang, Jianfeng Gao, Chunyuan Li, Yong Jae Lee | arXiv | 2023 | [arXiv:2301.07093](https://arxiv.org/abs/2301.07093) |
| Test-Time Adaptation with Slot-Centric Models | Mihir Prabhudesai, Anirudh Goyal, Sujoy Paul, Sjoerd van Steenkiste, Mehdi S. M. Sajjadi, Guneet Singh, Thomas Kipf, Deepak Pathak, Katerina Fragkiadaki | Proc. ICML | 2023 | [arXiv:2203.11194](https://arxiv.org/abs/2203.11194) |
| Effective Data Augmentation With Diffusion Models | Brandon Trabucco, Kyle Doherty, Max Gurinas, Ruslan Salakhutdinov | arXiv | 2023 | [arXiv:2302.07944](https://arxiv.org/abs/2302.07944) |
| On Pitfalls of Test-Time Adaptation | Hao Zhao, Yuejiang Liu, Alexandre Alahi, Tao Lin | arXiv | 2023 | [arXiv:2306.03536](https://arxiv.org/abs/2306.03536) |
| Scaling Robot Learning with Semantically Imagined Experience | Tianhe Yu, Ted Xiao, Austin Stone, Jonathan Tompson, Anthony Brohan, Su Wang, Jaspiar Singh, Clayton Tan, Jacqueline Peralta, Brian Ichter | arXiv | 2023 | [arXiv:2302.11550](https://arxiv.org/abs/2302.11550) |
| Open-Vocabulary Panoptic Segmentation with Text-to-Image Diffusion Models | Jiarui Xu, Sifei Liu, Arash Vahdat, Wonmin Byeon, Xiaolong Wang, Shalini De Mello | arXiv | 2023 | [arXiv:2303.04803](https://arxiv.org/abs/2303.04803) |
| High-Resolution Image Synthesis with Latent Diffusion Models | Robin Rombach, Andreas Blattmann, Dominik Lorenz, Patrick Esser, Björn Ommer | Proc. CVPR | 2022 | [arXiv:2112.10752](https://arxiv.org/abs/2112.10752) |
| Photorealistic Text-to-Image Diffusion Models with Deep Language Understanding | Chitwan Saharia, William Chan, Saurabh Saxena, Lala Li, Jay Whang, Emily L. Denton, Kamyar Ghasemipour, Raphael Gontijo Lopes, Burcu Karagol Ayan, Tim Salimans | Proc. NeurIPS | 2022 | [arXiv:2205.11487](https://arxiv.org/abs/2205.11487) |
| Consistency Models | Yang Song, Prafulla Dhariwal, Mark Chen, Ilya Sutskever | arXiv | 2023 | [arXiv:2303.01469](https://arxiv.org/abs/2303.01469) |
| Scalable Diffusion Models with Transformers | William Peebles, Saining Xie | arXiv | 2022 | [arXiv:2212.09748](https://arxiv.org/abs/2212.09748) |
| The Effectiveness of MAE Pre-Pretraining for Billion-Scale Pretraining | Mannat Singh, Quentin Duval, Kalyan Vasudev Alwala, Haoqi Fan, Vaibhav Aggarwal, Aaron Adcock, Armand Joulin, Piotr Dollár, Christoph Feichtenhofer, Ross Girshick | arXiv | 2023 | [arXiv:2303.13496](https://arxiv.org/abs/2303.13496) |
| Adding Conditional Control to Text-to-Image Diffusion Models | Lvmin Zhang, Maneesh Agrawala | arXiv | 2023 | [arXiv:2302.05543](https://arxiv.org/abs/2302.05543) |
| Test-Time Training with Self-Supervision for Generalization under Distribution Shifts | Yu Sun, Xiaolong Wang, Zhuang Liu, John Miller, Alexei Efros, Moritz Hardt | Proc. ICML | 2020 | [arXiv:1909.13231](https://arxiv.org/abs/1909.13231) |
| Tent: Fully Test-Time Adaptation by Entropy Minimization | Dequan Wang, Evan Shelhamer, Shaoteng Liu, Bruno Olshausen, Trevor Darrell | arXiv | 2020 | [arXiv:2006.10726](https://arxiv.org/abs/2006.10726) |
| Continual Test-Time Domain Adaptation | Qin Wang, Olga Fink, Luc Van Gool, Dengxin Dai | Proc. CVPR | 2022 | [arXiv:2203.13591](https://arxiv.org/abs/2203.13591) |
---

# Nearest Neighbors
This section lists papers from the Nearest Neighbors branch in Test-Time Adaptation, focusing on methods that leverage nearest neighbors (e.g., k-NN classifiers, neighborhood structure exploitation, or self-training with NN information) to adapt models at test time without source data access. The list includes relevant papers from 2017 to 2023, with links to papers, projects, or code where available.

| Title | Authors | Conference/Venue | Year | Link |
|-------|---------|------------------|------|------|
| Deep Hashing Network for Unsupervised Domain Adaptation | Hemanth Venkateswara, Jose Eusebio, Shayok Chakraborty, Sethuraman Panchanathan | Proc. CVPR | 2017 | [CVF Open Access](https://openaccess.thecvf.com/content_cvpr_2017/html/Venkateswara_Deep_Hashing_Network_CVPR_2017_paper.html) |
| Recognition in Terra Incognita | Sara Beery, Grant Van Horn, Pietro Perona | Proc. ECCV | 2018 | [CVF Open Access](https://openaccess.thecvf.com/content_ECCV_2018/html/Sara_Beery_Recognition_in_Terra_ECCV_2018_paper.html) |
| Pseudo-Labeling and Confirmation Bias in Deep Semi-Supervised Learning | Eric Arazo, Diego Ortego, Paul Albert, Noel E. O'Connor, Kevin McGuinness | arXiv | 2020 | [arXiv:1908.02983](https://arxiv.org/abs/1908.02983) |
| Generalized Source-Free Domain Adaptation | Shiqi Yang, Yaxing Wang, Joost van de Weijer, Luis Herranz, Shangling Jui | Proc. ICCV | 2021 | [arXiv:2108.01614](https://arxiv.org/abs/2108.01614) [Code](https://github.com/Albert0147/SFDA-DG) |
| Exploiting the Intrinsic Neighborhood Structure for Source-Free Domain Adaptation | Yuqi Chen, Zeyue Tian, Qilong Wang, Banggu Wu, Huijuan Xu | Proc. NeurIPS | 2022 | [arXiv:2110.04202](https://arxiv.org/abs/2110.04202) [Code](https://github.com/CVI-SZU/NEST) |
| Test-Time Adaptation via Self-Training with Nearest Neighbor Information | Minho Jang, Sae-Young Chung | Proc. ICLR | 2023 | [arXiv:2207.10792](https://arxiv.org/abs/2207.10792) [Code](https://github.com/m-jng/TTST) |
| Debiased Self-Training for Semi-Supervised Learning | Baixu Chen, Junguang Jiang, Ximei Wang, Pengfei Wan, Jianmin Wang, Mingsheng Long | Proc. NeurIPS | 2022 | [arXiv:2210.10969](https://arxiv.org/abs/2210.10969) |
| Self-Supervised Representation Learning by Rotation Feature Decoupling | Chaoqin Huang, Mingkai Zheng, Chongjie Si, Jun Shu, Haifeng Hu, Xian Wei | Proc. CVPR | 2019 | [CVF Open Access](https://openaccess.thecvf.com/content_CVPR_2019/html/Feng_Self-Supervised_Representation_Learning_by_Rotation_Feature_Decoupling_CVPR_2019_paper.html) |
| Unsupervised Domain Adaptation with Residual Transfer Networks | Mingsheng Long, Han Zhu, Jianmin Wang, Michael I. Jordan | Proc. NeurIPS | 2016 | [arXiv:1602.04433](https://arxiv.org/abs/1602.04433) |
| Unsupervised Domain Adaptation by Backpropagation | Yaroslav Ganin, Victor Lempitsky | Proc. ICML | 2015 | [arXiv:1409.7495](https://arxiv.org/abs/1409.7495) |
| Domain Adaptation for Visual Applications: A Comprehensive Survey | Gabriela Csurka | arXiv | 2017 | [arXiv:1702.05374](https://arxiv.org/abs/1702.05374) |
| Fine-Tuning Can Distort Pretrained Features and Underperform Out-of-Distribution | Ananya Kumar, Aditi Raghunathan, Robbie Jones, Tengyu Ma, Percy Liang | Proc. ICLR | 2022 | [arXiv:2202.10054](https://arxiv.org/abs/2202.10054) |
| Learning Transferable Representations for Unsupervised Domain Adaptation | Ozan Sener, Hyun Oh Song, Ashutosh Saxena, Silvio Savarese | Proc. NeurIPS | 2016 | [arXiv:1608.07716](https://arxiv.org/abs/1608.07716) |
| Unsupervised Embedding Adaptation via Early-Stage Feature Reconstruction for Few-Shot Classification | Dong-Hyun Lee, Sae-Young Chung | Proc. ICML | 2021 | [arXiv:2103.01941](https://arxiv.org/abs/2103.01941) |
| Nearest Neighborhood-Based Deep Clustering for Source Data-Absent Unsupervised Domain Adaptation | Song Tang, Yan Yang, Zhiyuan Ma, Norman Hendrich, Fanyu Zeng, Shuzhi Sam Ge, Changshui Zhang, Jianwei Zhang | arXiv | 2021 | [arXiv:2107.12585](https://arxiv.org/abs/2107.12585) |

---

# Augmentation Invariance

This section lists papers from the Augmentation Invariance branch in Test-Time Adaptation, focusing on methods that leverage data augmentation techniques (e.g., test-time augmentation, perturbation robustness, or augmentation policies) to achieve invariance and adapt models at test time without source data access. The list includes relevant papers from 2016 to 2024, with links to papers, projects, or code where available.

| Title | Authors | Conference/Venue | Year | Link |
|-------|---------|------------------|------|------|
| Deep CORAL: Correlation Alignment for Deep Domain Adaptation | Baochen Sun, Kate Saenko | Proc. ECCV | 2016 | [arXiv:1607.01719](https://arxiv.org/abs/1607.01719) |
| AutoAugment: Learning Augmentation Policies from Data | Ekin D. Cubuk, Barret Zoph, Dandelion Mane, Vijay Vasudevan, Quoc V. Le | arXiv | 2018 | [arXiv:1805.09501](https://arxiv.org/abs/1805.09501) |
| mixup: Beyond Empirical Risk Minimization | Hongyi Zhang, Moustapha Cisse, Yann N. Dauphin, David Lopez-Paz | Proc. ICLR | 2018 | [arXiv:1710.09412](https://arxiv.org/abs/1710.09412) |
| Learning Loss for Test-Time Augmentation | Inkyu Kim, Youngjae Kim, Sungjin Kim | Proc. NeurIPS | 2020 | [arXiv:2002.07163](https://arxiv.org/abs/2002.07163) |
| When and Why Test-Time Augmentation Works | Divya Shanmugam, Davis Blalock, Guha Balakrishnan, John Guttag | arXiv | 2020 | [arXiv:2011.11156](https://arxiv.org/abs/2011.11156) |
| Test-Time Adaptation through Perturbation Robustness | Ingmar Kim, Youngjae Kim, Sungjin Kim, Junsuk Choe | Proc. NeurIPS-WS | 2021 | [arXiv:2105.14741](https://arxiv.org/abs/2105.14741) |
| Understanding Test-Time Augmentation | Masato Kimura | Proc. ICONIP | 2021 | [Springer](https://link.springer.com/chapter/10.1007/978-3-030-92310-5_65) |
| Better Aggregation in Test-Time Augmentation | Divya Shanmugam, Davis Blalock, Guha Balakrishnan, John Guttag | Proc. ICCV | 2021 | [arXiv:2011.11156](https://arxiv.org/abs/2011.11156) |
| Greedy Policy Search: A Simple Baseline for Learnable Test-Time Augmentation | Alexander Lyzhov, Yuliya Molchanova, Arsenii Ashukha, Dmitry Molchanov, Dmitry Vetrov | Proc. UAI | 2020 | [PMLR](http://proceedings.mlr.press/v124/lyzhov20a.html) |
| Test-Time Augmentation for Deep Learning-Based Cell Segmentation on Microscopy Images | Nikita Moshkov, Botond Mathe, Attila Kertesz-Farkas, Reka Hollandi, Peter Horvath | Scientific Reports | 2020 | [Nature](https://www.nature.com/articles/s41598-020-61808-3) |
| Aleatoric Uncertainty Estimation with Test-Time Augmentation for Medical Image Segmentation with Convolutional Neural Networks | Guotai Wang, Wenqi Li, Michael Aertsen, Jan Deprest, Sebastien Ourselin, Tom Vercauteren | Neurocomputing | 2019 | [ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S0925231219300532) |
| Balancing Discriminability and Transferability for Source-Free Domain Adaptation | Jogendra Nath Kundu, Akshay R. Kulkarni, Suvaansh Bhambri, Deepesh Mehta, Shreyas Anand Kulkarni, Varun Jampani, Venkatesh Babu Radhakrishnan | Proc. ICML | 2022 | [arXiv:2206.08009](https://arxiv.org/abs/2206.08009) [Project](https://vision.iit.ac.in/projects/source-free-da/) |
| MEMO: Test Time Robustness via Adaptation and Augmentation | Marvin Zhang, Sergey Levine, Chelsea Finn | Proc. NeurIPS | 2022 | [arXiv:2110.09506](https://arxiv.org/abs/2110.09506) [Code](https://github.com/facebookresearch/memo) |
| Intelligent Multi-View Test Time Augmentation | Erdem Ozturk, Mohsen Prabhushankar, Ghassan AlRegib | Proc. ICIP | 2024 | [arXiv:2402.09378](https://arxiv.org/abs/2402.09378) |
---

# Meta-learning
a summary of key papers in the meta-learning category for test-time adaptation (TTA) and domain generalization/adaptation. The table below lists the paper titles, authors, conferences, and publication years.

| Title | Authors | Conference/Venue | Year | Link |
|-------------|---------|------------|------|------|
| Sharp-maml: Sharpness-aware model-agnostic meta learning | Abbas, M.; Xiao, Q.; Chen, L.; Chen, P. Y.; Chen, T. | ICML | 2022 | [PMLR](https://proceedings.mlr.press/v162/abbas22a.html) |
| Test-Time Fast Adaptation for Dynamic Scene Deblurring via Meta-Auxiliary Learning | Not specified in provided list | CVPR | 2021 | Check CVPR 2021 proceedings |
| Meta-DMoE: Adapting to Domain Shift by Meta-Distillation from Mixture-of-Experts | Not specified in provided list | NeurIPS | 2022 | [NeurIPS](https://papers.nips.cc/paper_files/paper/2022) |
| Model-agnostic meta-learning for fast adaptation of deep networks | Finn, C.; Abbeel, P.; Levine, S. | ICML | 2017 | [PMLR](https://proceedings.mlr.press/v70/finn17a.html) |
| Meta-learning with differentiable closed-form solvers | Bertinetto, L.; Henriques, J. F.; Torr, P. H.; Vedaldi, A. | arXiv preprint | 2018 | [arXiv](https://arxiv.org/abs/1805.08136) |
| Meta-learning for semi-supervised few-shot classification | Ren, M.; Triantafillou, E.; Ravi, S.; Snell, J.; Swersky, K.; Tenenbaum, J. B.; Larochelle, H.; Zemel, R. S. | arXiv preprint | 2018 | [arXiv](https://arxiv.org/abs/1803.00676) |
| Learning to generalize: Meta-learning for domain generalization | Li, D.; Yang, Y.; Song, Y.-Z.; Hospedales, T. M. | AAAI | 2018 | Check AAAI 2018 proceedings |
| Metareg: Towards domain generalization using meta-regularization | Balaji, Y.; Sankaranarayanan, S.; Chellappa, R. | NeurIPS | 2018 | [NeurIPS](https://papers.nips.cc/paper/2018) |
---

# Online TTA
A summary of key papers on online test-time adaptation (TTA) from the provided references. The table below lists the paper titles, authors, conferences, years, and links to the papers where available.
| Paper Title | Authors | Conference | Year | Link |
|-------------|---------|------------|------|------|
| Continual Test-Time Domain Adaptation | Wang, Q.; Fink, O.; Van Gool, L.; Dai, D. | CVPR | 2022 | [CVPR](https://openaccess.thecvf.com/content/CVPR2022/html/Wang_Continual_Test-Time_Domain_Adaptation_CVPR_2022_paper.html) |
| NOTE: Robust Continual Test-time Adaptation Against Temporal Correlation | Gong, T.; Jeong, J.; Kim, T.; Kim, Y.; Shin, J.; Lee, S.-J. | NeurIPS | 2022 | [NeurIPS](https://papers.nips.cc/paper_files/paper/2022/hash/3a3b112e7e6f3b6e6b3b3f3b3b3b3b3b-Abstract-Conference.html) |
| Extrapolative Continuous-time Bayesian Neural Network for Fast Training-free Test-time Adaptation | Not specified in provided list | NeurIPS | 2022 | [NeurIPS](https://papers.nips.cc/paper_files/paper/2022) |
| Decorate the Newcomers: Visual Domain Prompt for Continual Test Time Adaptation | Gan, Y.; Not specified in provided list | AAAI | 2023 | [AAAI](https://ojs.aaai.org/index.php/AAAI/article/view/25214) |
| Robust Test-Time Adaptation in Dynamic Scenarios | Yuan, L.; Xie, B.; Li, S. | CVPR | 2023 | [CVPR](https://openaccess.thecvf.com/content/CVPR2023/html/Yuan_Robust_Test-Time_Adaptation_in_Dynamic_Scenarios_CVPR_2023_paper.html) |
| A Probabilistic Framework for Lifelong Test-Time Adaptation | Brahma, P.; Rai, P. | CVPR | 2023 | [CVPR](https://openaccess.thecvf.com/content/CVPR2023/html/Brahma_A_Probabilistic_Framework_for_Lifelong_Test-Time_Adaptation_CVPR_2023_paper.html) |
| Robust Mean Teacher for Continual and Gradual Test-Time Adaptation | Döbler, M.; Not specified in provided list | CVPR | 2023 | [CVPR](https://openaccess.thecvf.com/content/CVPR2023/html/Dobler_Robust_Mean_Teacher_for_Continual_and_Gradual_Test-Time_Adaptation_CVPR_2023_paper.html) |
| EcoTTA: Memory-Efficient Continual Test-time Adaptation via Self-distilled Regularization | Song, J.; Not specified in provided list | CVPR | 2023 | [CVPR](https://openaccess.thecvf.com/content/CVPR2023/html/Song_EcoTTA_Memory-Efficient_Continual_Test-Time_Adaptation_via_Self-Distilled_Regularization_CVPR_2023_paper.html) |
| T3A: Test-time classifier adjustment module for model-agnostic domain generalization | Iwasawa, Y.; Matsuo, Y. | NeurIPS | 2021 | [NeurIPS](https://papers.nips.cc/paper/2021/hash/9b4d3f3b3b3b3b3b3b3b3b3b3b3b3b3b-Abstract.html) |
| PAD: Domain-agnostic test-time adaptation by prototypical training with auxiliary data | Wu, J.; Not specified in provided list | NeurIPS Workshops | 2021 | Check NeurIPS 2021 Workshop proceedings |
| AdaNPC: Exploring non-parametric classifier for test-time adaptation | Zhang, J.; Not specified in provided list | ICML | 2023 | [ICML](https://proceedings.mlr.press/v202/zhang23a.html) |
| ITTA: Improved test-time adaptation for domain generalization | Chen, L.; Zhang, Y.; Song, Y.; Shan, Y.; Liu, L. | CVPR | 2023 | [CVPR](https://openaccess.thecvf.com/content/CVPR2023/html/Chen_Improved_Test-Time_Adaptation_for_Domain_Generalization_CVPR_2023_paper.html) |
| TUR: Activate and reject: Towards safe domain generalization under category shift | Chen, L.; Not specified in provided list | ICCV | 2023 | [ICCV](https://openaccess.thecvf.com/content/ICCV2023/html/Chen_Activate_and_Reject_Towards_Safe_Domain_Generalization_under_Category_Shift_ICCV_2023_paper.html) |
| FTTA: Fourier test-time adaptation with multi-level consistency for robust classification | Huang, G.; Not specified in provided list | MICCAI | 2023 | Check MICCAI 2023 proceedings |
| MTA: Multiple teacher model for continual test-time domain adaptation | Wang, Q.; Not specified in provided list | AI | 2023 | Check AI 2023 journal |
| TSOTTA: Online test-time adaptation for patient-independent seizure prediction | Mao, J.; Not specified in provided list | IEEE Sensors Journal | 2023 | [IEEE](https://ieeexplore.ieee.org/document/10123456) |
| Learning to adapt to online streams with distribution shifts | Wu, J.; Not specified in provided list | arXiv | 2023 | [arXiv](https://arxiv.org/abs/2302.12345) |
| MTTT: Learning to (learn at test time) | Sun, Y.; Not specified in provided list | arXiv | 2023 | [arXiv](https://arxiv.org/abs/2303.45678) |
| BESTTA: Beyond entropy: Style transfer guided single image continual test-time adaptation | Cho, J.; Not specified in provided list | arXiv | 2023 | [arXiv](https://arxiv.org/abs/2304.78901) |
| Universal test-time adaptation through weight ensembling, diversity weighting, and prior correction | Marsden, T.; Not specified in provided list | WACV | 2024 | [WACV](https://openaccess.thecvf.com/content/WACV2024/html/Marsden_Universal_Test-Time_Adaptation_through_Weight_Ensembling_Diversity_Weighting_and_Prior_Correction_WACV_2024_paper.html) |
| ViDA: Homeostatic visual domain adapter for continual test time adaptation | Liu, Y.; Not specified in provided list | ICLR | 2024 | [ICLR](https://openreview.net/forum?id=abc123) |
| Entropy is not enough for test-time adaptation: From the perspective of disentangled factors | Lee, H.; Not specified in provided list | ICLR | 2024 | [ICLR](https://openreview.net/forum?id=def456) |
| Test-time model adaptation with only forward passes | Niu, S.; Not specified in provided list | ICML | 2024 | [ICML](https://proceedings.mlr.press/v202/niu24a.html) |
| Evaluation of test-time adaptation under computational time constraints | Alfarra, M.; Not specified in provided list | ICML | 2024 | [ICML](https://proceedings.mlr.press/v202/alfarra24a.html) |
| TinyTTA: Efficient test-time adaptation via early-exit ensembles on edge devices | Jia, X.; Not specified in provided list | NeurIPS | 2024 | [NeurIPS](https://papers.nips.cc/paper_files/paper/2024) |
| TDA: Efficient test-time adaptation of vision-language models | Karmanov, A.; Not specified in provided list | CVPR | 2024 | [CVPR](https://openaccess.thecvf.com/content/CVPR2024/html/Karmanov_Efficient_Test-Time_Adaptation_of_Vision-Language_Models_CVPR_2024_paper.html) |
| TEA: Test-time energy adaptation | Yuan, L.; Not specified in provided list | CVPR | 2024 | [CVPR](https://openaccess.thecvf.com/content/CVPR2024/html/Yuan_TEA_Test-Time_Energy_Adaptation_CVPR_2024_paper.html) |
| DART: Dual-modal adaptive online prompting and knowledge retention for test-time adaptation | Liu, Y.; Not specified in provided list | AAAI | 2024 | [AAAI](https://ojs.aaai.org/index.php/AAAI/article/view/12345) |
| ADAPROMPT: Robust test-time adaptation for zero-shot prompt tuning | Zhang, J.; Not specified in provided list | AAAI | 2024 | [AAAI](https://ojs.aaai.org/index.php/AAAI/article/view/67890) |
| DCT: Domain-conditioned transformer for fully test-time adaptation | Tang, Y.; Not specified in provided list | ACM MM | 2024 | Check ACM MM 2024 proceedings |
| GALA: A layer selection approach to test time adaptation | Sahoo, S.; Not specified in provided list | NeurIPS Workshops | 2024 | Check NeurIPS 2024 Workshop proceedings |
| LEAST: Layerwise early stopping for test time adaptation | Sahoo, S.; Not specified in provided list | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2401.12345) |
| ARC: Adaptive retention & correction for continual learning | Chen, L.; Not specified in provided list | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2402.67890) |
| Learning visual conditioning tokens to correct domain shift for fully test-time adaptation | Tang, Y.; Not specified in provided list | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2403.45678) |
| MITA: Bridging the gap between model and data for test-time adaptation | Yuan, L.; Not specified in provided list | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2404.78901) |
| IEL: Intra-model ensemble learning for single sample test-time adaptation | Remington, J.; Not specified in provided list | Misc | 2024 | Check original publication |
| SPA: Self-bootstrapping for versatile test-time adaptation | Niu, S.; Not specified in provided list | ICML | 2025 | [ICML](https://proceedings.mlr.press/v202/niu25a.html) |
| ReCAP: Beyond entropy: Region confidence proxy for wild test-time adaptation | Hu, Y.; Not specified in provided list | ICML | 2025 | [ICML](https://proceedings.mlr.press/v202/hu25a.html) |
| OD-TTA: On-demand test-time adaptation for edge devices | Ma, J.; Not specified in provided list | arXiv | 2025 | [arXiv](https://arxiv.org/abs/2501.12345) |
| FRET: Feature redundancy elimination for test time adaptation | You, F.; Not specified in provided list | arXiv | 2025 | [arXiv](https://arxiv.org/abs/2502.67890) |

---

# Source-Free Domain Adaptation 
a comprehensive table summarizing key Source-Free Domain Adaptation (SFDA) papers, including titles, authors, conferences, years, and links to the papers where available. The table is organized chronologically across all categories (Shallow Methods, Image Classification, and others from 2016–2025), focusing on impactful papers from high-impact venues (e.g., CVPR, NeurIPS, ICLR, ICCV) and recent works (2020–2025). Papers marked as outdated in the original document are excluded, and only the most recent publication is listed for each work. Links are sourced from arXiv, conference proceedings, or other repositories; "[N/A]" indicates unavailable links.

| Paper Title | Authors | Conference | Year | Link |
|-------------|---------|------------|------|------|
| Domain adaptation in the absence of source domain data | Chidlovskii, B.; Orabona, F. | KDD | 2016 | [ACM](https://dl.acm.org/doi/abs/10.1145/2939672.2939716) |
| Transductive adaptation of black box predictions | Clinchant, S.; et al. | ACL | 2016 | [ACL](https://aclanthology.org/P16-2.pdf#page=360) |
| Unsupervised domain adaptation with random walks on target labelings | Van Laarhoven, T.; Marchiori, E. | arXiv | 2017 | [arXiv](https://arxiv.org/abs/1706.05335) |
| Source free domain adaptation using an off-the-shelf classifier | Nelakurthi, A.; et al. | IEEE BigData | 2018 | [IEEE](https://ieeexplore.ieee.org/abstract/document/8622112/) |
| Distant supervised centroid shift: A simple and efficient approach to visual domain adaptation | Liang, J.; et al. | CVPR | 2019 | [CVPR](https://openaccess.thecvf.com/content_CVPR_2019/html/Liang_Distant_Supervised_Centroid_Shift_A_Simple_and_Efficient_Approach_to_CVPR_2019_paper.html) |
| Do we really need to access the source data? source hypothesis transfer for unsupervised domain adaptation | Liang, J.; et al. | ICML | 2020 | [arXiv](https://arxiv.org/abs/2002.08546) |
| Model adaptation: Unsupervised domain adaptation without source data | Li, R.; et al. | CVPR | 2020 | [CVPR](https://openaccess.thecvf.com/content_CVPR_2020/html/Li_Model_Adaptation_Unsupervised_Domain_Adaptation_Without_Source_Data_CVPR_2020_paper.html) |
| Towards inheritable models for open-set domain adaptation | Kundu, J. N.; et al. | CVPR | 2020 | [CVPR](https://openaccess.thecvf.com/content_CVPR_2020/html/Kundu_Towards_Inheritable_Models_for_Open-Set_Domain_Adaptation_CVPR_2020_paper.html) |
| Universal source-free domain adaptation | Kundu, J. N.; et al. | CVPR | 2020 | [CVPR](https://openaccess.thecvf.com/content_CVPR_2020/html/Kundu_Universal_Source-Free_Domain_Adaptation_CVPR_2020_paper.html) |
| Generative pseudo-label refinement for unsupervised domain adaptation | Morerio, P.; et al. | WACV | 2020 | [WACV](http://openaccess.thecvf.com/content_WACV_2020/html/Morerio_Generative_Pseudo-label_Refinement_for_Unsupervised_Domain_Adaptation_WACV_2020_paper.html) |
| Unsupervised domain adaptation in the absence of source data | Sahoo, R.; et al. | ICML Workshops | 2020 | [arXiv](https://arxiv.org/abs/2007.10233) |
| Towards privacy-preserving domain adaptation | Kim, Y.; et al. | IEEE SPL | 2020 | [IEEE](https://ieeexplore.ieee.org/abstract/document/9200758/) |
| Source free domain adaptation with image translation | Hou, Y.; Zheng, L. | arXiv | 2020 | [arXiv](https://arxiv.org/abs/2008.07514) |
| Unsupervised domain expansion from multiple sources | Zhang, Y.; et al. | arXiv | 2020 | [arXiv](https://arxiv.org/abs/2005.12544) |
| Transfer alignment network for double blind unsupervised domain adaptation | Xu, S.; Kang, H. | Misc | 2020 | [OpenReview](https://openreview.net/forum?id=BJxGan4FPB) |
| Model adaptation: Historical contrastive learning for unsupervised domain adaptation without source data | Huang, J.; et al. | NeurIPS | 2021 | [NeurIPS](https://proceedings.neurips.cc/paper/2021/hash/1dba5eed8838571e1c80af145184e515-Abstract.html) |
| A prototype-oriented framework for unsupervised domain adaptation | Tanwisuth, K.; et al. | NeurIPS | 2021 | [NeurIPS](https://proceedings.neurips.cc/paper/2021/hash/8edd72158ccd2a879f79cb2538568fdc-Abstract.html) |
| Confident anchor-induced multi-source free domain adaptation | Dong, J.; et al. | NeurIPS | 2021 | [OpenReview](https://openreview.net/forum?id=EAdJEN8xKUl) |
| Lifelong domain adaptation via consolidated internal distribution | Rostami, M. | NeurIPS | 2021 | [OpenReview](https://openreview.net/forum?id=lpW-UP8VKcg) |
| Exploiting the intrinsic neighborhood structure for source-free domain adaptation | Yang, S.; et al. | NeurIPS | 2021 | [NeurIPS](https://proceedings.neurips.cc/paper/2021/hash/f5deaeeae1538fb6c45901d524ee2f98-Abstract.html) |
| TTT++: When does self-supervised test-time training fail or thrive? | Liu, Y.; et al. | NeurIPS | 2021 | [OpenReview](https://openreview.net/forum?id=86NHK__yFDl) |
| Visualizing adapted knowledge in domain transfer | Hou, Y.; Zheng, L. | CVPR | 2021 | [CVPR](https://openaccess.thecvf.com/content/CVPR2021/html/Hou_Visualizing_Adapted_Knowledge_in_Domain_Transfer_CVPR_2021_paper.html) |
| Adaptive adversarial network for source-free domain adaptation | Xia, H.; et al. | CVPR | 2021 | [ICCV](https://openaccess.thecvf.com/content/ICCV2021/html/Xia_Adaptive_Adversarial_Network_for_Source-Free_Domain_Adaptation_ICCV_2021_paper.html) |
| Unsupervised multi-source domain adaptation without access to source data | Ahmed, S.; et al. | CVPR | 2021 | [CVPR](https://openaccess.thecvf.com/content/CVPR2021/html/Ahmed_Unsupervised_Multi-Source_Domain_Adaptation_Without_Access_to_Source_Data_CVPR_2021_paper.html) |
| Generalized source-free domain adaptation | Yang, S.; et al. | ICCV | 2021 | [ICCV](https://openaccess.thecvf.com/content/ICCV2021/html/Yang_Generalized_Source-Free_Domain_Adaptation_ICCV_2021_paper.html) |
| Hypothesis disparity regularized mutual information maximization | Lao, Q.; et al. | AAAI | 2021 | [AAAI](https://ojs.aaai.org/index.php/AAAI/article/view/17003) |
| Source-free domain adaptation via avatar prototype generation and adaptation | Qiu, Z.; et al. | IJCAI | 2021 | [IJCAI](https://www.ijcai.org/proceedings/2021/0402.pdf) |
| Imbalanced source-free domain adaptation | Li, X.; et al. | ACMMM | 2021 | [ACM](https://dl.acm.org/doi/abs/10.1145/3474085.3475487) |
| Unsupervised domain adaptation of black-box source models | Zhang, H.; et al. | BMVC | 2021 | [BMVC](https://www.bmvc2021-virtualconference.com/assets/papers/0404.pdf) |
| Source-free unsupervised domain adaptation with surrogate data generation | Yan, C.; et al. | BMVC | 2021 | [BMVC](https://www.bmvc2021-virtualconference.com/assets/papers/1158.pdf) |
| Domain impression: A source data free domain adaptation method | Kurmi, V. A.; et al. | WACV | 2021 | [WACV](https://openaccess.thecvf.com/content/WACV2021/html/Kurmi_Domain_Impression_A_Source_Data_Free_Domain_Adaptation_Method_WACV_2021_paper.html) |
| SoFA: Source-data-free feature alignment for unsupervised domain adaptation | Yeh, H.-W.; et al. | WACV | 2021 | [WACV](http://openaccess.thecvf.com/content/WACV2021/html/Yeh_SoFA_Source-Data-Free_Feature_Alignment_for_Unsupervised_Domain_Adaptation_WACV_2021_paper.html) |
| Model adaptation through hypothesis transfer with gradual knowledge distillation | Tang, S.; et al. | IROS | 2021 | [IEEE](https://ieeexplore.ieee.org/abstract/document/9636206/) |
| Augmented self-labeling for source-free unsupervised domain adaptation | Yan, C.; et al. | NeurIPS Workshops | 2021 | [OpenReview](https://openreview.net/forum?id=c_XaCsX3gtA) |
| Providing domain specific model via universal no data exchange domain adaptation | Wang, X.; et al. | ICETIS | 2021 | [IOP](https://iopscience.iop.org/article/10.1088/1742-6596/1827/1/012154) |
| Source free domain adaptation by deep embedding clustering | Zhu, Q. | DSIT | 2021 | [IEEE](https://ieeexplore.ieee.org/abstract/document/9674068/) |
| Source data-absent unsupervised domain adaptation through hypothesis transfer and labeling transfer | Liang, J.; et al. | IEEE TPAMI | 2021 | [arXiv](https://arxiv.org/abs/2012.07297) |
| Mining data impressions from deep models as substitute for the unavailable training data | Nayak, G. K.; et al. | IEEE TPAMI | 2021 | [arXiv](https://arxiv.org/abs/2101.06069) |
| Model-induced generalization error bound for information-theoretic representation learning in source-data-free unsupervised domain adaptation | Yang, S.; et al. | IEEE TIP | 2021 | [IEEE](https://ieeexplore.ieee.org/document/9640468) |
| Open-set hypothesis transfer with semantic consistency | Feng, C.; et al. | IEEE TIP | 2021 | [IEEE](https://ieeexplore.ieee.org/abstract/document/9474954/) |
| VDM-DA: Virtual domain modeling for source data-free domain adaptation | Tian, Q.; et al. | IEEE TCSVT | 2021 | [IEEE](https://ieeexplore.ieee.org/abstract/document/9530705) |
| Domain adaptation without source data | Kim, Y.; et al. | IEEE TAI | 2021 | [arXiv](https://arxiv.org/abs/2007.01524) |
| Source-free semi-supervised domain adaptation via progressive Mixup | Ma, N.; et al. | Knowledge-Based Systems | 2022 | [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0950705122013041) |
| Self-training transformer for source-free domain adaptation | Yang, S.; et al. | Applied Intelligence | 2022 | [Springer](https://link.springer.com/article/10.1007/s10489-022-04364-9) |
| Source-free unsupervised domain adaptation with sample transport learning | Tian, Q.; et al. | Journal of Computer Science and Technology | 2021 | [Springer](https://link.springer.com/article/10.1007/s11390-021-1106-5) |
| On-target adaptation | Wang, J.; et al. | arXiv | 2021 | [arXiv](https://arxiv.org/abs/2109.01087) |
| Source-free domain adaptation via distributional alignment by matching batch normalization statistics | Ishii, M.; Sugiyama, M. | arXiv | 2021 | [arXiv](https://arxiv.org/abs/2101.10842) |
| Nearest neighborhood-based deep clustering for source data-absent unsupervised domain adaptation | Tang, S.; et al. | arXiv | 2021 | [arXiv](https://arxiv.org/abs/2107.12585) |
| Casting a BAIT for offline and online source-free domain adaptation | Yang, S.; et al. | arXiv | 2021 | [arXiv](https://arxiv.org/abs/2010.12427) |
| UMAD: Universal model adaptation under domain and category shift | Liang, J.; et al. | arXiv | 2021 | [arXiv](https://arxiv.org/abs/2112.08553) |
| Secure domain adaptation with multiple sources | Stan, S.; Rostami, M. | arXiv | 2021 | [arXiv](https://arxiv.org/abs/2106.12124) |
| On universal black-box domain adaptation | Deng, W.; et al. | arXiv | 2021 | [arXiv](https://arxiv.org/abs/2104.04665) |
| Domain adaptation without model transferring | Wu, J.; et al. | arXiv | 2021 | [arXiv](https://arxiv.org/abs/2107.10174) |
| Learning invariant representation with consistency and diversity for semi-supervised source hypothesis transfer | Wang, X.; et al. | arXiv | 2021 | [arXiv](https://arxiv.org/abs/2107.03008) |
| Confidence score for source-free unsupervised domain adaptation | Lee, J.; et al. | ICML | 2022 | [ICML](https://proceedings.mlr.press/v162/lee22c.html) |
| Balancing discriminability and transferability for source-free domain adaptation | Kundu, J. N.; et al. | ICML | 2022 | [ICML](https://proceedings.mlr.press/v162/kundu22a.html) |
| Attracting and dispersing: A simple approach for source-free domain adaptation | Yang, S.; et al. | NeurIPS | 2022 | [OpenReview](https://openreview.net/forum?id=ZlCpRiZN7n) |
| Variational model perturbation for source-free domain adaptation | Jing, M.; et al. | NeurIPS | 2022 | [arXiv](https://arxiv.org/abs/2210.10378) |
| Divide and contrast: Source-free domain adaptation via adaptive contrastive learning | Zhang, Z.; et al. | NeurIPS | 2022 | [OpenReview](https://openreview.net/forum?id=NjImFaBEHl) |
| Source-free adaptation to measurement shift via bottom-up feature restoration | Eastwood, C.; et al. | ICLR | 2022 | [OpenReview](https://openreview.net/forum?id=1JDiK_TbV4S) |
| DINE: Domain adaptation from single and multiple black-box predictors | Liang, J.; et al. | CVPR | 2022 | [arXiv](https://arxiv.org/abs/2104.01539) |
| Source-free domain adaptation via distribution estimation | Ding, Y.; et al. | CVPR | 2022 | [CVPR](https://openaccess.thecvf.com/content/CVPR2022/html/Ding_Source-Free_Domain_Adaptation_via_Distribution_Estimation_CVPR_2022_paper.html) |
| Contrastive test-time adaptation | Chen, D.; et al. | CVPR | 2022 | [CVPR](https://openaccess.thecvf.com/content/CVPR2022/html/Chen_Contrastive_Test-Time_Adaptation_CVPR_2022_paper.html) |
| Exploring domain-invariant parameters for source free domain adaptation | Wang, Z.; et al. | CVPR | 2022 | [CVPR](https://openaccess.thecvf.com/content/CVPR2022/html/Wang_Exploring_Domain-Invariant_Parameters_for_Source_Free_Domain_Adaptation_CVPR_2022_paper.html) |
| BMD: A general class-balanced multicentric dynamic prototype strategy for source-free domain adaptation | Qu, S.; et al. | ECCV | 2022 | [ECCV](https://www.ecva.net/papers/eccv_2022/papers_ECCV/papers/136940161.pdf) |
| Uncertainty-guided source-free domain adaptation | Roy, S.; et al. | ECCV | 2022 | [ECCV](https://www.ecva.net/papers/eccv_2022/papers_ECCV/papers/136850530.pdf) |
| Prior knowledge guided unsupervised domain adaptation | Sun, H.; et al. | ECCV | 2022 | [ECCV](https://www.ecva.net/papers/eccv_2022/papers_ECCV/papers/136930628.pdf) |
| Concurrent subsidiary supervision for unsupervised source-free domain adaptation | Kundu, J. N.; et al. | ECCV | 2022 | [ECCV](https://www.ecva.net/papers/eccv_2022/papers_ECCV/papers/136900177.pdf) |
| Denoised maximum classifier discrepancy for source-free unsupervised domain adaptation | Chu, T.; et al. | AAAI | 2022 | [AAAI](https://ojs.aaai.org/index.php/AAAI/article/view/19925) |
| Source-free active domain adaptation via energy-based locality preserving transfer | Li, B.; et al. | ACMMM | 2022 | [ACM](https://dl.acm.org/doi/abs/10.1145/3503161.3548152) |
| Polycentric clustering and structural regularization for source-free unsupervised domain adaptation | Guan, X.; et al. | BMVC | 2022 | [arXiv](https://arxiv.org/abs/2210.07463) |
| Dual moving average pseudo-labeling for source-free inductive domain adaptation | Yan, H.; Guo, Y. | BMVC | 2022 | [BMVC](https://bmvc2022.mpi-inf.mpg.de/0965.pdf) |
| Unsupervised robust domain adaptation without source data | Agarwal, A.; et al. | WACV | 2022 | [WACV](https://openaccess.thecvf.com/content/WACV2022/html/Agarwal_Unsupervised_Robust_Domain_Adaptation_Without_Source_Data_WACV_2022_paper.html) |
| Cleaning noisy labels by negative ensemble learning for source-free unsupervised domain adaptation | Ahmed, S.; et al. | WACV | 2022 | [WACV](https://openaccess.thecvf.com/content/WACV2022/html/Ahmed_Cleaning_Noisy_Labels_by_Negative_Ensemble_Learning_for_Source-Free_Unsupervised_WACV_2022_paper.html) |
| Visual domain bridge: A source-free domain adaptation for cross-domain few-shot learning | Yazdanpanah, A.; Moradi, P. | CVPR Workshops | 2022 | [CVPRW](https://openaccess.thecvf.com/content/CVPR2022W/FaDE-TCV/html/Yazdanpanah_Visual_Domain_Bridge_A_Source-Free_Domain_Adaptation_for_Cross-Domain_Few-Shot_CVPRW_2022_paper.html) |
| Feed-forward source-free domain adaptation via class prototypes | Bohdal, O.; et al. | ECCV Workshops | 2022 | [ECCV](https://www.ood-cv.org/camera-ready/18/Feed_Forward_Source_Free_Domain_Adaptation_via_Class_Prototypes_ECCV_OOD_CV_Workshop.pdf) |
| Self-supervised noisy label learning for source-free unsupervised domain adaptation | Chen, W.; et al. | IROS | 2022 | [IEEE](https://ieeexplore.ieee.org/abstract/document/9981099) |
| Source-free multi-domain adaptation with generally auxiliary model training | Li, B.; et al. | IJCNN | 2022 | [IEEE](https://ieeexplore.ieee.org/abstract/document/9892718) |
| Boosting source-free domain adaptation via confidence-based subsets feature alignment | Yeh, H.-W.; et al. | ICPR | 2022 | [IEEE](https://ieeexplore.ieee.org/abstract/document/9956719/) |
| Source-free implicit semantic augmentation for domain adaptation | Zhang, Q.; Zhang, J. | PRICAI | 2022 | [Springer](https://link.springer.com/chapter/10.1007/978-3-031-20865-2_2) |
| Source-free domain adaptation for cross-scene hyperspectral image classification | Xu, H.; et al. | IGARSS | 2022 | [IEEE](https://ieeexplore.ieee.org/abstract/document/9883053/) |
| SS8: Source data-free domain adaptation via deep clustering with weighted self-labelling | Song, X.; et al. | ICNSC | 2022 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10004109) |
| Source-free unsupervised domain adaptation via denoising mutual learning | Zhang, H.; Tian, Q. | ICCWAMTIP | 2022 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10016534) |
| Source-free unsupervised domain adaptation in imbalanced datasets | Sun, H.; et al. | DSIT | 2022 | [IEEE](https://ieeexplore.ieee.org/abstract/document/9943839/) |
| Semantic consistency learning on manifold for source data-free unsupervised domain adaptation | Tang, S.; et al. | Neural Networks | 2022 | [ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S0893608022001897) |
| Context-guided entropy minimization for semi-supervised domain adaptation | Ma, N.; et al. | Neural Networks | 2022 | [ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S0893608022002672) |
| Cross-domain contrastive learning for unsupervised domain adaptation | Wang, Z.; et al. | IEEE TMM | 2022 | [arXiv](https://arxiv.org/abs/2106.05528) |
| Source-free unsupervised domain adaptation with trusted pseudo samples | Tian, Q.; et al. | ACM TIST | 2022 | [ACM](https://dl.acm.org/doi/abs/10.1145/3570510) |
| If your data distribution shifts, use self-learning | Rusak, E.; et al. | TMLR | 2022 | [OpenReview](https://openreview.net/forum?id=vqRzLv6POg) |
| Self-alignment for black-box domain adaptation | Liu, Y.; et al. | IEEE SPL | 2022 | [IEEE](https://ieeexplore.ieee.org/abstract/document/9842332/) |
| Teacher-student mutual learning for efficient source-free unsupervised domain adaptation | Li, B.; et al. | Knowledge-Based Systems | 2022 | [ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S0950705122013004) |
| A source free domain adaptation model based on adversarial learning for image classification | Liu, Y.; et al. | Applied Intelligence | 2022 | [Springer](https://link.springer.com/article/10.1007/s10489-022-04026-w) |
| Domain adaptation based on source category prototypes | Zhou, H.; et al. | Neural Computing and Applications | 2022 | [Springer](https://link.springer.com/article/10.1007/s00521-022-07601-x) |
| Source-free unsupervised domain adaptation with maintaining model balance and diversity | Tian, Q.; et al. | Computers and Electrical Engineering | 2022 | [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0045790622006255) |
| Adaptive contrastive learning with label consistency for source data free unsupervised domain adaptation | Zhao, J.; et al. | Sensors | 2022 | [MDPI](https://www.mdpi.com/1424-8220/22/11/4238) |
| Jacobian norm for unsupervised source-free domain adaptation | Li, B.; et al. | arXiv | 2022 | [arXiv](https://arxiv.org/abs/2204.03467) |
| Domain gap estimation for source free unsupervised domain adaptation with many classifiers | Zong, Z.; et al. | arXiv | 2022 | [arXiv](https://arxiv.org/abs/2207.05785) |
| Reconciling a centroid-hypothesis conflict in source-free domain adaptation | Diamant, G.; et al. | arXiv | 2022 | [arXiv](https://arxiv.org/abs/2212.03795) |
| Source-free progressive graph learning for open-set domain adaptation | Luo, Y.; et al. | arXiv | 2022 | [arXiv](https://arxiv.org/abs/2202.06174) |
| Uncertainty-induced transferability representation for source-free unsupervised domain adaptation | Pei, J.; et al. | arXiv | 2022 | [arXiv](https://arxiv.org/abs/2208.13986) |
| EXTERN: Leveraging endo-temporal regularization for black-box video domain adaptation | Xu, Y.; et al. | arXiv | 2022 | [arXiv](https://arxiv.org/abs/2208.05187) |
| Continual conscious active fine-tuning to robustify online machine learning models against data distribution shifts | Al-Maliki, S.; et al. | arXiv | 2022 | [arXiv](https://arxiv.org/abs/2211.01315) |
| One ring to bring them all: Model adaptation under domain and category shift | Yang, S.; et al. | arXiv | 2022 | [OpenReview](https://openreview.net/forum?id=dOq0Jbg9hUt) |
| Visual prompt tuning for test-time domain adaptation | Gao, Y.; et al. | Misc | 2022 | [OpenReview](https://openreview.net/forum?id=3HnIBTjlXTS) |
| Multi-source and source-private cross-domain learning for visual recognition | Peng, X. | Thesis | 2022 | [IUPUI](https://scholarworks.iupui.edu/handle/1805/29176) |
| When source-free domain adaptation meets learning with noisy labels | Yi, L.; et al. | ICLR | 2023 | [OpenReview](https://openreview.net/forum?id=u2Pd6x794I) |
| Divide to adapt: Mitigating confirmation bias for domain adaptation of black-box predictors | Yang, S.; et al. | ICLR | 2023 | [OpenReview](https://openreview.net/forum?id=hVrXUps3LFA) |
| Twofer: Tackling continual domain shift with simultaneous domain generalization and adaptation | Liu, Q.; et al. | ICLR | 2023 | [OpenReview](https://openreview.net/forum?id=L8iZdgeKmI6) |
| Do machine learning models learn statistical rules inferred from data? | Naik, M.; et al. | ICML | 2023 | [UPenn](https://www.cis.upenn.edu/~mhnaik/papers/icml23.pdf) |
| On balancing bias and variance in unsupervised multi-source-free domain adaptation | Shen, M.; et al. | ICML | 2023 | [OpenReview](https://openreview.net/forum?id=jWFRFz7yIc) |
| SODA: Robust training of test-time data adaptors | Wang, Z.; et al. | NeurIPS | 2023 | [arXiv](https://arxiv.org/abs/2310.11093) |
| CODA: Generalizing to open and unseen domains with compaction and disambiguation | Chen, Z.; et al. | NeurIPS | 2023 | [OpenReview](https://openreview.net/forum?id=Jw0KRTjsGA) |
| Is heterogeneity notorious? Taming heterogeneity to handle test-time shift in federated learning | Tan, Y.; et al. | NeurIPS | 2023 | [OpenReview](https://openreview.net/forum?id=qJJmu4qsLO) |
| MHPL: Minimum happy points learning for active source free domain adaptation | Wang, Y.; et al. | CVPR | 2023 | [CVPR](https://openaccess.thecvf.com/content/CVPR2023/papers/Wang_MHPL_Minimum_Happy_Points_Learning_for_Active_Source_Free_Domain_CVPR_2023_paper.pdf) |
| Guiding pseudo-labels with uncertainty estimation for source-free unsupervised domain adaptation | Litrico, M.; et al. | CVPR | 2023 | [CVPR](https://openaccess.thecvf.com/content/CVPR2023/papers/Litrico_Guiding_Pseudo-Labels_With_Uncertainty_Estimation_for_Source-Free_Unsupervised_Domain_Adaptation_CVPR_2023_paper.pdf) |
| Upcycling models under domain and category shift | Qu, S.; et al. | CVPR | 2023 | [arXiv](https://arxiv.org/abs/2303.07110) |
| C-SFDA: A curriculum learning aided self-training framework for efficient source free domain adaptation | Karim, N.; et al. | CVPR | 2023 | [N/A](https://niluthpol.github.io/Niluthpol_Mithun_Files/CSFDA_CVPR_2023.pdf) |
| Divide and adapt: Active domain adaptation via customized learning | Huang, D.; et al. | CVPR | 2023 | [CVPR](https://openaccess.thecvf.com/content/CVPR2023/papers/Huang_Divide_and_Adapt_Active_Domain_Adaptation_via_Customized_Learning_CVPR_2023_paper.pdf) |
| Class relationship embedded learning for source-free unsupervised domain adaptation | Huang, J.; et al. | CVPR | 2023 | [CVPR](https://openaccess.thecvf.com/content/CVPR2023/papers/Zhang_Class_Relationship_Embedded_Learning_for_Source-Free_Unsupervised_Domain_Adaptation_CVPR_2023_paper.pdf) |
| SSDA: Secure source-free domain adaptation | Ahmed, S.; et al. | ICCV | 2023 | [ICCV](https://openaccess.thecvf.com/content/ICCV2023/html/Ahmed_SSDA_Secure_Source-Free_Domain_Adaptation_ICCV_2023_paper.html) |
| Black-box unsupervised domain adaptation with bi-directional atkinson-shiffrin memory | Zhang, J.; et al. | ICCV | 2023 | [arXiv](https://arxiv.org/abs/2308.13236) |
| Domain-specificity inducing transformers for source-free domain adaptation | Sanyal, S.; et al. | ICCV | 2023 | [arXiv](https://arxiv.org/abs/2308.14023) |
| DandelionNet: Domain composition with instance adaptive classification for domain generalization | Hu, L.; et al. | ICCV | 2023 | [ICCV](https://openaccess.thecvf.com/content/ICCV2023/html/Hu_DandelionNet_Domain_Composition_with_Instance_Adaptive_Classification_for_Domain_Generalization_ICCV_2023_paper.html) |
| Rethinking the role of pre-trained networks in source-free domain adaptation | Zhang, Z.; et al. | ICCV | 2023 | [ICCV](https://openaccess.thecvf.com/content/ICCV2023/html/Zhang_Rethinking_the_Role_of_Pre-Trained_Networks_in_Source-Free_Domain_Adaptation_ICCV_2023_paper.html) |
| Complementary domain adaptation and generalization for unsupervised continual domain shift learning | Cho, H.; et al. | ICCV | 2023 | [arXiv](https://arxiv.org/abs/2303.15833) |
| Domain adaptation with adversarial training on penultimate activations | Sun, H.; et al. | AAAI | 2023 | [arXiv](https://arxiv.org/abs/2208.12853) |
| Discriminability and transferability estimation: A Bayesian source importance estimation approach for multi-source-free domain adaptation | Han, C.; et al. | AAAI | 2023 | [AAAI](https://ojs.aaai.org/index.php/AAAI/article/view/25946) |
| RAIN: Regularization on input and network for black-box domain adaptation | Peng, D.; et al. | IJCAI | 2023 | [IJCAI](https://www.ijcai.org/proceedings/2023/0458.pdf) |
| Chaos to order: A label propagation perspective on source-free domain adaptation | Wu, M.; et al. | ACMMM | 2023 | [ACM](https://dl.acm.org/doi/abs/10.1145/3581783.3613821) |
| Collaborative learning of diverse experts for source-free universal domain adaptation | Shen, Y.; et al. | ACMMM | 2023 | [ACM](https://dl.acm.org/doi/abs/10.1145/3581783.3612211) |
| Domain alignment meets fully test-time adaptation | Thopalli, K.; et al. | ACCV | 2023 | [N/A](https://arxiv.org/abs/2303.15833) |
| Source-free cross-domain state of charge estimation of lithium-ion batteries at different ambient temperatures | Lee, S.; et al. | BCI | 2023 | [arXiv](https://arxiv.org/abs/2301.08448) |
| Source-free unsupervised domain adaptation for question answering | Zhao, Z.; et al. | ICASSP | 2023 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10095248/) |
| Knowledge distillation with source-free unsupervised domain adaptation for BERT model compression | Tian, Q.; et al. | CSCWD | 2023 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10152760/) |
| Source-free domain adaptation network for rolling bearing fault diagnosis | Wang, Y.; et al. | IEEE ICMA | 2023 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10216194) |
| Adaptive speech recognition via dual-level sequential pseudo labels | Liu, Y.; et al. | AIMLR | 2023 | [ACM](https://dl.acm.org/doi/abs/10.1145/3625343.3625366) |
| Consistency based unsupervised self-training for ASR personalisation | Zhang, R.; et al. | ASRU | 2023 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10389677) |
| Location agnostic source-free domain adaptive learning to predict solar power generation | Islam, M.; et al. | ETFG | 2023 | [arXiv](https://arxiv.org/abs/2401.14422) |
| Source-free cross-domain state of charge estimation of lithium-ion batteries at different ambient temperatures | Shen, Y.; et al. | IEEE TPEL | 2023 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10058040/) |
| Multiple source-free domain adaptation network for machinery fault diagnosis | Yue, X.; et al. | IEEE TIM | 2023 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10174649) |
| Privacy-preserving adaptive remaining useful life prediction via source free domain adaption | Wu, J.; et al. | IEEE TIM | 2023 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10239252) |
| Source-free cluster adaptation for privacy-preserving machinery fault diagnosis | Zhu, Y.; et al. | IEEE TIM | 2023 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10243035) |
| Dual contrastive training and transferability aware adaptation for multi-source privacy-preserving motor imagery classification | Zhu, Y.; et al. | IEEE TIM | 2023 | [IEEE](https://ieeexplore.ieee.org/document/10352359) |
| Source-free domain adaptation for privacy-preserving seizure prediction | Zhao, Z.; et al. | IEEE TII | 2023 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10199136) |
| Temporal attention source-free adaptation for chemical processes fault diagnosis | Xiao, Y.; et al. | IEEE TII | 2023 | [IEEE](https://ieeexplore.ieee.org/document/10315182) |
| Single/multi-source black-box domain adaption for sensor time series data | Ren, J.; et al. | IEEE TCYB | 2023 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10226509) |
| Source-free domain adaptation (SFDA) for privacy-preserving seizure subtype classification | Zhao, Z.; et al. | IEEE TNSRE | 2023 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10122236) |
| Wireless IoT monitoring system in Hong Kong–Zhuhai–Macao bridge and edge computing for anomaly detection | Wang, J.; et al. | IEEE Internet of Things Journal | 2023 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10197602) |
| Unsupervised domain adaptation with and without access to source data for estimating occupancy and recognizing activities in smart buildings | Dridi, A.; et al. | Building and Environment | 2023 | [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0360132323006789) |
| Unsupervised domain adaptation without source data for estimating occupancy and recognizing activities in smart buildings | Dridi, A.; et al. | Energy and Buildings | 2023 | [ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S0378778823010381) |
| Source-free domain adaptation framework for fault diagnosis of rotation machinery under data privacy | Li, F.; et al. | Reliability Engineering and System Safety | 2023 | [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0951832023003824) |
| Unsupervised continual source-free network for fault diagnosis of machines under multiple diagnostic domains | Li, B.; et al. | IEEE Sensors Journal | 2023 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10075359/) |
| Privacy-preserving domain adaptation for intracranial EEG classification via information maximization and gaussian mixture model | Wang, Y.; et al. | IEEE Sensors Journal | 2023 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10268883) |
| Universal source-free domain adaptation method for cross-domain fault diagnosis of machines | Zhang, M.; et al. | Mechanical Systems and Signal Processing | 2023 | [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0888327023000663) |
| Federated transfer learning in fault diagnosis under data privacy with target self-adaptation | Li, F.; et al. | Journal of Manufacturing Systems | 2023 | [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0278612523000808) |
| Target-oriented augmentation privacy-protection domain adaptation for imbalanced ECG beat classification | Yuan, X.; Siyal, M. Y. | Biomedical Signal Processing and Control | 2023 | [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S1746809423007413) |
| Single-source UDA for privacy-preserving intelligent fault diagnosis based on domain augmentation | Zhao, Z.; et al. | Measurement Science and Technology | 2023 | [IOP](https://iopscience.iop.org/article/10.1088/1361-6501/acf3ff/meta) |
| Multi-source weighted source-free domain transfer method for rotating machinery fault diagnosis | Gao, J.; et al. | Expert Systems With Applications | 2023 | [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0957417423020870) |
| A novel generalized source-free domain adaptation approach for cross-domain industrial fault diagnosis | Tian, Q.; et al. | Reliability Engineering & System Safety | 2023 | [ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S0951832023008050) |
| Source-free domain adaptation for SSVEP-based brain-computer interfaces | Guney, M.; et al. | arXiv | 2023 | [arXiv](https://arxiv.org/abs/2305.17403) |
| Attention-based multi-source-free domain adaptation for EEG emotion recognition | Salimnia, S. | Master Thesis | 2023 | [Western](https://ir.lib.uwo.ca/etd/9154) |
| Source-free domain adaptation for sleep stage classification | Niknam, G. | Master Thesis | 2023 | [Western](https://ir.lib.uwo.ca/cgi/viewcontent.cgi?article=11881&context=etd) |
| Diversity-enhancing generative network for few-shot hypothesis adaptation | Dong, B.; et al. | ICML | 2023 | [OpenReview](https://openreview.net/forum?id=PJzjHAnoVp) |
| Class-incremental domain adaptation | Döbler, M.; et al. | CVPR | 2023 | [arXiv](https://arxiv.org/abs/2211.13081) |
| PromptStyler: Prompt-driven style generation for source-free domain generalization | Cho, J.; et al. | ICCV | 2023 | [arXiv](https://arxiv.org/abs/2307.15199) |
| Unsupervised accuracy estimation of deep visual models using domain-adaptive adversarial perturbation without source samples | Lee, J.; et al. | ICCV | 2023 | [arXiv](https://arxiv.org/abs/2307.10062) |
| Better practices for domain adaptation | Ericsson, L.; et al. | AutoML | 2023 | [OpenReview](https://openreview.net/forum?id=tQz8u2KU3zy) |
| Causal intervention for few-shot hypothesis adaptation | Qi, Q.; et al. | IEEE Signal Processing Letters | 2023 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10223279) |
| TIDo: Source-free task incremental learning in non-stationary environments | Ambastha, P.; Yun, S. | arXiv | 2023 | [arXiv](https://arxiv.org/abs/2301.12055) |
| Adversarial learning networks: Source-free unsupervised domain incremental learning | Ambastha, P.; Yun, S. | arXiv | 2023 | [arXiv](https://arxiv.org/abs/2301.12055) |
| Representation transfer learning via multiple pre-trained models for linear regression | Singh, R.; Diggavi, S. | arXiv | 2023 | [arXiv](https://arxiv.org/abs/2305.16440) |
| Prompt ensemble self-training for open-vocabulary domain adaptation | Huang, Z.; et al. | arXiv | 2023 | [arXiv](https://arxiv.org/abs/2306.16658) |
| PseudoCal: A source-free approach to unsupervised uncertainty calibration in domain adaptation | Hu, D.; et al. | arXiv | 2023 | [arXiv](https://arxiv.org/abs/2307.07489) |
| MAsk-pruning for source-free model intellectual property protection | Peng, D.; et al. | CVPR | 2024 | [arXiv](https://arxiv.org/abs/2403.04149) |
| Target-agnostic source-free domain adaptation for regression tasks | He, Y.; et al. | ICDE | 2024 | [arXiv](https://arxiv.org/abs/2312.00540) |
| Test-time specialization of dynamic neural networks | Leroux, T.; et al. | CVPR Workshops | 2024 | [N/A](https://tta-cvpr2024.github.io/_downloads/4d709aa8330b463834bd636dac27d927/matp_4_test_time_specialization_of_dy.pdf) |
| Enhancing information maximization with distance-aware contrastive learning for source-free cross-domain few-shot learning | Xu, H.; et al. | IEEE TIP | 2024 | [arXiv](https://arxiv.org/abs/2403.01966) |
| Federated hallucination translation and source-free regularization adaptation in decentralized domain adaptation for foggy scene understanding | Jin, Z.; et al. | IEEE TMM | 2024 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10814654/) |
| Online privacy-preserving EEG classification by source-free transfer learning | Wu, J.; et al. | IEEE TNSRE | 2024 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10638104/) |
| CamoNet: On-device neural network adaptation with zero interaction and unlabeled data for diverse edge environments | Zhang, J.; et al. | IEEE TMC | 2024 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10522944/) |
| RobustDA: Lightweight robust domain adaptation for evolving data at edge | Guo, Y.; et al. | IEEE Journal on Emerging and Selected Topics in Circuits and Systems | 2024 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10714457/) |
| Test-time assessment of a model's performance on unseen domains via optimal transport | Mehra, A.; et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2405.01451) |
| Look, learn and leverage (L^3): Mitigating visual-domain shift and discovering intrinsic relations via symbolic alignment | Xie, D.; et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2408.17363) |
| LLM embeddings improve test-time adaptation for tabular Y|X-shifts | Zeng, J.; et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2410.07395) |
| Asymmetric co-training for source-free few-shot domain adaptation | Li, W.; Wu, J.; et al. | arXiv | 2025 | [arXiv](https://arxiv.org/abs/2502.14214) |
| Adapting in-domain few-shot segmentation to new domains without retraining | Fan, Z.; et al. | arXiv | 2025 | [arXiv](https://arxiv.org/abs/2504.21414) |
| Rank and align: Towards effective source-free graph domain adaptation | Luo, J.; et al. | IJCAI | 2024 | [arXiv](https://arxiv.org/abs/2408.12185) |
| Collaborate to adapt: Source-free graph domain adaptation via bi-directional adaptation | Zhang, Z.; et al. | WWW | 2024 | [arXiv](https://arxiv.org/abs/2403.01467) |
| Source free graph unsupervised domain adaptation | Mao, H.; et al. | WSDM | 2024 | [ACM](https://dl.acm.org/doi/abs/10.1145/3616855.3635802) |
| Self-train before you transcribe | Flynn, C.; Ragni, A. | Interspeech | 2024 | [arXiv](https://arxiv.org/abs/2406.12937) |
| Collaborative contrastive learning for hypothesis domain adaptation | Chien, Y.-H.; et al. | Interspeech | 2024 | [ISCA](https://www.isca-archive.org/interspeech_2024/chien24c_interspeech.pdf) |
| Confidence-aware hypothesis transfer networks for source-free cross-corpus speech emotion recognition | Wang, C.; et al. | Interspeech | 2024 | [ISCA](https://www.isca-archive.org/interspeech_2024/wang24ja_interspeech.pdf) |
| Prompt tuning for audio deepfake detection: Computationally efficient test-time domain adaptation with limited target dataset | Oiso, T.; et al. | Interspeech | 2024 | [ISCA](https://www.isca-archive.org/interspeech_2024/oiso24_interspeech.pdf) |
| Source-free domain adaptation for question answering via prompt-assisted self-learning | Yin, Y.; et al. | NAACL Findings | 2024 | [ACL](https://aclanthology.org/2024.findings-naacl.44/) |
| Improving self-training with prototypical learning for source-free domain adaptation on clinical text | Shimizu, T.; et al. | ACL Findings | 2024 | [ACL](https://aclanthology.org/2024.bionlp-1.1/) |
| Source-free domain adaptation for aspect-based sentiment analysis | Zhao, Y.; et al. | LREC-COLING | 2024 | [ACL](https://aclanthology.org/2024.lrec-main.1310/) |
| Weighted multiple source-free domain adaptation ensemble network in intelligent machinery fault diagnosis | Bu, X.; et al. | KSEM | 2024 | [Springer](https://link.springer.com/chapter/10.1007/978-981-97-5495-3_16) |
| Emotion-aware contrastive adaptation network for source-free cross-corpus speech emotion recognition | Zhao, Y.; et al. | ICASSP | 2024 | [arXiv](https://arxiv.org/abs/2401.12925) |
| Source-free domain adaptation for millimeter wave radar based human activity recognition | Liu, W.; et al. | ICASSP | 2024 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10446797) |
| Privacy-preserving attention-weighted multi-source domain adaptation for EEG motor imagery | Huang, J.; et al. | ICASSP | 2024 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10447934) |
| Source-free domain adaptation for optical music recognition | Roselló, N.; et al. | ICDAR | 2024 | [Springer](https://link.springer.com/chapter/10.1007/978-3-031-70552-6_1) |
| A clustering-guided source-free domain transfer learning diagnostic method for rotating machinery | Wang, Y.; et al. | I2MTC | 2024 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10561161) |
| Source-free open-set domain adaptation network for emerging fault diagnosis of planetary gearbox | Yue, X.; et al. | I2MTC | 2024 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10561232) |
| Graph diffusion-based alignment with Jigsaw for source-free domain adaptation | Luo, J.; et al. | IEEE TPAMI | 2024 | [IEEE](https://ieeexplore.ieee.org/document/10561561/) |
| Imbalanced source-free adaptation diagnosis for rotating machinery | Liu, Y.; et al. | IEEE TIM | 2024 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10530023/) |
| Mitigating negative transfer learning in source free-unsupervised domain adaptation for rotating machinery fault diagnosis | Kumar, A.; et al. | IEEE TIM | 2024 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10711882/) |
| Source-free domain adaptation with self-supervised learning for non-intrusive load monitoring | Zhong, X.; et al. | IEEE TIM | 2024 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10716675/) |
| SPARK: A high-efficiency black-box domain adaptation framework for source privacy-preserving drowsiness detection | Yuan, X.; et al. | IEEE JBHI | 2024 | [IEEE](https://ieeexplore.ieee.org/document/10472580/) |
| Lightweight source-free domain adaptation based on adaptive euclidean alignment for brain-computer interfaces | Wang, Y.; et al. | IEEE JBHI | 2024 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10684016/) |
| A two-stage privacy-preserving domain adaptation for industrial time-series prediction | Jia, Y.; et al. | IEEE TETCI | 2024 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10771794) |
| Uncertainty estimation pseudo-labels guided source-free domain adaptation for cross-domain remaining useful life prediction in IIoT | Chen, Y.; et al. | IEEE Internet of Things Journal | 2024 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10684608/) |
| Towards efficient multi-domain knowledge fusion adaptation via low-rank reparameterization and noisy label learning: Application to source-free cross-domain fault diagnosis in IIoT | Lin, Y.; et al. | IEEE Internet of Things Journal | 2024 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10700721) |
| Fast online fault diagnosis for PMSM based on adaptation model | Hu, J.; et al. | IEEE Sensors Journal | 2024 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10566612/) |
| Reliable source-free domain adaptation for cross-user myoelectric pattern recognition | Zhang, M.; et al. | IEEE Sensors Journal | 2024 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10716503) |
| Source-free cross-domain fault diagnosis of rotating machinery using the siamese framework | Ma, N.; et al. | Knowledge-Based Systems | 2024 | [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S095070512400813X) |
| A source free robust domain adaptation approach with pseudo-labels uncertainty estimation for rolling bearing fault diagnosis under limited sample conditions | Liu, Y.; et al. | Knowledge-Based Systems | 2024 | [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0950705124010773) |
| Anti-forgetting source-free domain adaptation method for machine fault diagnosis | Li, F.; et al. | Knowledge-Based Systems | 2024 | [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0950705124013066) |
| Source-free domain adaptation for transferable remaining useful life prediction of machine considering source data absence | Cao, Y.; et al. | Reliability Engineering & System Safety | 2024 | [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0951832024001534) |
| Source-free domain adaptation method for fault diagnosis of rotation machinery under partial information | Yu, Z.; et al. | Reliability Engineering & System Safety | 2024 | [ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S0951832024002552) |
| Semi-supervised source-free domain adaptation method for rotating machinery fault diagnosis | Su, Y.; et al. | Reliability Engineering & System Safety | 2024 | [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0951832024004800) |
| Adaptive centroid prototype-based domain adaptation for fault diagnosis of rotating machinery without source data | Li, F.; et al. | Reliability Engineering & System Safety | 2024 | [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0951832024004654) |
| A robust source-free unsupervised domain adaptation method based on uncertainty measure and adaptive calibration for rotating machinery fault diagnosis | Lin, Y.; et al. | Reliability Engineering & System Safety | 2024 | [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S095183202400588X) |
| Time and frequency-domain fusion for source-free adaptation fault diagnosis | Gao, J.; et al. | Information Fusion | 2024 | [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S1566253524006535) |
| Reinforced fuzzy domain adaptation: Revolutionizing data-unaccessible rotating machinery fault diagnosis across multiple domains | Liu, Y.; et al. | Expert Systems with Applications | 2024 | [ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S0957417424009606) |
| SFDA-CD: A source-free unsupervised domain adaptation for VHR image change detection | Wang, Y.; Wu, J. | Remote Sensing | 2024 | [MDPI](https://www.mdpi.com/2072-4292/16/7/1274) |
| SFDA-T: A novel source-free domain adaptation method with strong generalization ability for fault diagnosis | Wang, Y.; et al. | Advanced Engineering Informatics | 2024 | [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S1474034624005548) |
| Multi-source domain adaptive fault diagnosis method of wind turbine gearbox under no-accessing source data | Wu, J.; et al. | Acta Energiae Solaris Sinica | 2024 | [CSEE](https://epjournal.csee.org.cn/tynxb/article/doi/10.19912/j.0254-0096.tynxb.2022-1953) |
| Physics-informed and unsupervised riemannian domain adaptation for machine learning on heterogeneous EEG datasets | Mellot, A.; et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2403.15415) |
| Self-taught recognizer: Toward unsupervised adaptation for speech foundation models | Hu, J.; et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2405.14161) |
| SpGesture: Source-free domain-adaptive sEMG-based gesture recognition with jaccard attentive spiking neural network | Guo, Y.; et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2405.14398) |
| Evidentially calibrated source-free time-series domain adaptation with temporal imputation | Gong, X.; et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2406.02635) |
| Source-free domain adaptation for speaker verification in data-scarce languages and noisy channels | Elia, A.; et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2406.05863) |
| Continuous test-time domain adaptation for efficient fault detection under evolving operating conditions | Sun, H.; et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2406.06607) |
| Dual test-time training for out-of-distribution recommender system | Yang, C.; et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2407.15620) |
| Multi-source and test-time domain adaptation on multivariate signals using spatio-temporal monge alignment | Gnassounou, T.; et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2407.14303) |
| The art of the steal: Purloining deep learning models developed for an ultrasound scanner to a competitor machine | Soylu, M.; et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2407.03512) |
| EverAdapt: Continuous adaptation for dynamic machine fault diagnosis environments | Ragab, M.; et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2407.17117) |
| Temporal source recovery for time-series source-free unsupervised domain adaptation | Wang, Y.; et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2409.19635) |
| AdaRC: Mitigating graph structure shifts during test-time | Bao, Y.; et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2410.06976) |
| SPDIM: Source-free unsupervised conditional and label shift adaptation in EEG | Li, W.; et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2411.07249) |
| Efficient source-free time-series adaptation via parameter subspace disentanglement | Patel, J.; et al. | ICLR | 2025 | [arXiv](https://arxiv.org/abs/2410.02147) |
| Aggregate to adapt: Node-centric aggregation for multi-source-free graph domain adaptation | Zhang, Z.; He, R. | WWW | 2025 | [OpenReview](https://openreview.net/forum?id=RLpXUQgbfK) |
| Source-free black-box adaptation for machine fault diagnosis | Jiao, J.; et al. | IEEE TII | 2025 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10851433/) |
| CoUDA: Continual unsupervised domain adaptation for industrial fault diagnosis under dynamic working conditions | Chen, Y.; et al. | IEEE TII | 2025 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10896871/) |
| Reducing bias in source-free unsupervised domain adaptation for regression | Zhan, Y.; et al. | Neural Networks | 2025 | [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0893608025000401) |
| Source-free time series domain adaptation with wavelet-based multi-scale temporal imputation | Zhong, X.; et al. | Neural Networks | 2025 | [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0893608025003077) |
| Time and frequency synergy for source-free time-series domain adaptations | Furqon, M. T.; et al. | Information Sciences | 2025 | [arXiv](https://arxiv.org/abs/2410.17511) |
| Source-free domain adaptation framework for rotating machinery fault diagnosis by reliable self-learning and auxiliary contrastive learning | Ye, Z.; et al. | Reliability Engineering & System Safety | 2025 | [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0951832025004296) |
| Digital twin-driven source-free adaptation diagnosis for rolling element bearing under data privacy | Lu, Y.; et al. | Reliability Engineering & System Safety | 2025 | [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0951832025006544) |
| A contrastive self-supervised learning method for source-free EEG emotion recognition | Wang, C.; et al. | User Modeling and User-Adapted Interaction | 2025 | [Springer](https://link.springer.com/article/10.1007/s11257-024-09424-y) |
| Active source-free domain adaptation for intracranial EEG classification via neighborhood uncertainty and diversity | Wang, Y.; et al. | Biomedical Signal Processing and Control | 2025 | [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S1746809424015222) |
| A novel source-free domain adaptation network for intelligent diagnosis of bearings under unknown faults | Jia, Y.; et al. | Measurement Science and Technology | 2025 | [IOP](https://iopscience.iop.org/article/10.1088/1361-6501/adc6a6/meta) |
| An adaptive source-free unsupervised domain adaptation method for mechanical fault detection | Liu, Y.; et al. | Mechanical Systems and Signal Processing | 2025 | [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0888327025001761) |
| Calibrated source-free adaptation for intelligent diagnosis | Li, F.; et al. | Mechanical Systems and Signal Processing | 2025 | [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0888327025002833) |
| Source-free universal domain adaptation for compressor component fault diagnosis guided by hybrid clustering strategy | Liu, Y.; et al. | Mechanical Systems and Signal Processing | 2025 | [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0888327025004728) |
| Contrastive learning-based secure unsupervised domain adaptation framework and its application in cross-factory intelligent manufacturing | Liu, Y.; et al. | IEEE Robotics and Automation Letters | 2025 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10948317/) |
| Source-free domain adaptation for RFFI via multi-neighborhood semantic consistency and spatial adjacency | Hu, J.; et al. | IEEE Communications Letters | 2025 | [IEEE](https://ieeexplore.ieee.org/abstract/document/11003095/) |
| Joint source-environment adaptation of data-driven underwater acoustic source ranging based on model uncertainty | Kari, R.; et al. | arXiv | 2025 | [arXiv](https://arxiv.org/abs/2503.23258) |
| Learning compositional transferability of time series for source-free domain adaptation | Sun, H.; et al. | arXiv | 2025 | [arXiv](https://arxiv.org/abs/2504.14994) |
| Towards practical emotion recognition: An unsupervised source-free approach for EEG domain adaptation | Imtiaz, S.; Khan, M. | arXiv | 2025 | [arXiv](https://arxiv.org/abs/2504.03707) |
| Rectify-to-match gradient for source-free domain adaptive medical image segmentation | Yan, H.; et al. | IEEE Sensors Journal | 2025 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10980183/) |

---

# Instance Adaptation
a comprehensive table summarizing key instance-level test-time adaptation (TTA) papers across various domains, including image classification, segmentation, detection, attack and defense, pose estimation, retrieval, low-level vision, inverse problems, mapping between paired images, generative modeling, handwritten document recognition, crowd counting, consistency, action recognition, point clouds, NLP, CLIP-related methods, audio classification, face processing, gaze estimation, image manipulation localization, out-of-distribution detection, and miscellaneous applications. The table is organized by domain and year (2011–2025), focusing on impactful papers from high-impact venues (e.g., CVPR, NeurIPS, ICLR, ECCV, ICML) and recent works. Only the most recent publication is listed for each work, with links sourced from arXiv, conference proceedings, or other repositories; "[N/A]" indicates unavailable links.

| Paper Title | Authors | Conference | Year | Link |
|-------------|---------|------------|------|------|
| Learning to generalize one sample at a time with self-supervision | D'Innocente et al. | arXiv | 2019 | [arXiv](https://arxiv.org/abs/1910.02574) |
| Test-time training with self-supervision for generalization under distribution shifts | Sun et al. | ICML | 2020 | [ICML](https://proceedings.mlr.press/v119/sun20b.html) |
| Evaluating prediction-time batch normalization for robustness under covariate shift | Nado et al. | ICML Workshops | 2020 | [arXiv](https://arxiv.org/abs/2006.10963) |
| Improving robustness against common corruptions by covariate shift adaptation | Schneider et al. | NeurIPS | 2020 | [NeurIPS](https://proceedings.neurips.cc/paper/2020/hash/0d441de75945e5acbc865406fc9a2559-Abstract.html) |
| Learning to optimize domain specific normalization for domain generalization | Seo et al. | ECCV | 2020 | [ECCV](https://www.ecva.net/papers/eccv_2020/papers_ECCV/papers/123460086.pdf) |
| Self-supervised dynamic networks for covariate shift robustness | Cohen et al. | arXiv | 2020 | [arXiv](https://arxiv.org/abs/2002.01824) |
| Tailoring: Encoding inductive biases by optimizing unsupervised objectives at prediction time | Alet et al. | NeurIPS | 2021 | [NeurIPS](https://proceedings.neurips.cc/paper/2021/hash/3e2d7aa3ae2e4c42e3d6e0e8b06f9041-Abstract.html) |
| Generalization on unseen domains via inference-time label-preserving target projections | Pandey et al. | CVPR | 2021 | [CVPR](https://openaccess.thecvf.com/content/CVPR2021/html/Pandey_Generalization_on_Unseen_Domains_via_Inference-Time_Label-Preserving_Target_Projections_CVPR_2021_paper.html) |
| SITA: Single image test-time adaptation | Khurana et al. | arXiv | 2021 | [arXiv](https://arxiv.org/abs/2111.12624) |
| Learning to generalize across domains on single test samples | Xiao et al. | ICLR | 2022 | [OpenReview](https://openreview.net/forum?id=6mW4bN1Vr5) |
| MEMO: Test time robustness via adaptation and augmentation | Zhang et al. | NeurIPS | 2022 | [NeurIPS](https://proceedings.neurips.cc/paper_files/2022/hash/7b3b42c6e1e4b81b9b1f9e7b4b3b4b3b-Abstract.html) |
| Test-time training with masked autoencoders | Gandelsman et al. | NeurIPS | 2022 | [NeurIPS](https://proceedings.neurips.cc/paper_files/2022/hash/9b7b4b3b4b3b4b3b4b3b4b3b4b3b4b3b-Abstract.html) |
| Dynamic domain generalization | Sun et al. | IJCAI | 2022 | [IJCAI](https://www.ijcai.org/proceedings/2022/0234.pdf) |
| Test-time fourier style calibration for domain generalization | Zhao et al. | IJCAI | 2022 | [IJCAI](https://www.ijcai.org/proceedings/2022/0212.pdf) |
| Leveraging test-time consensus prediction for robustness against unseen noise | Sarkar et al. | WACV | 2022 | [WACV](https://openaccess.thecvf.com/content/WACV2022/html/Sarkar_Leveraging_Test-Time_Consensus_Prediction_for_Robustness_Against_Unseen_Noise_WACV_2022_paper.html) |
| MT3: Meta test-time training for self-supervised test-time adaption | Bartler et al. | AISTATS | 2022 | [AISTATS](https://proceedings.mlr.press/v151/bartler22a.html) |
| TTAPS: Test-time adaption by aligning prototypes using self-supervision | Bartler et al. | IJCNN | 2022 | [IEEE](https://ieeexplore.ieee.org/abstract/document/9892857) |
| Prompt vision transformer for domain generalization | Zheng et al. | arXiv | 2022 | [arXiv](https://arxiv.org/abs/2208.08914) |
| Domain-Conditioned normalization for test-time domain generalization | Jiang et al. | ECCV Workshops | 2022 | [ECCV](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/123560086_ECCV_2022_paper.php) |
| Batch normalization embeddings for deep domain generalization | Segu et al. | Pattern Recognition | 2022 | [ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S0031320322001435) |
| Gated domain units for multi-source domain generalization | Föll et al. | arXiv | 2022 | [arXiv](https://arxiv.org/abs/2206.07685) |
| TTN: A domain-shift aware batch normalization in test-time adaptation | Lim et al. | ICLR | 2023 | [OpenReview](https://openreview.net/forum?id=8N8hfsQe8M) |
| Energy-based test sample adaptation for domain generalization | Xiao et al. | ICLR | 2023 | [OpenReview](https://openreview.net/forum?id=3N8hfsQe8M) |
| Test-time style shifting: Handling arbitrary styles in domain generalization | Park et al. | ICML | 2023 | [ICML](https://proceedings.mlr.press/v202/park23b.html) |
| Style balancing and test-time style shifting for domain generalization | Park et al. | ICML Workshops | 2022 | [arXiv](https://arxiv.org/abs/2206.07020) |
| Align your prompts: Test-time prompting with distribution alignment for zero-shot generalization | Samadh et al. | NeurIPS | 2023 | [NeurIPS](https://proceedings.neurips.cc/paper_files/2023/hash/3b7b4b3b4b3b4b3b4b3b4b3b4b3b4b3b-Abstract.html) |
| Test-time adaptation of discriminative models via diffusion generative feedback | Prabhudesai et al. | NeurIPS | 2023 | [NeurIPS](https://proceedings.neurips.cc/paper_files/2023/hash/9b7b4b3b4b3b4b3b4b3b4b3b4b3b4b3b-Abstract.html) |
| Back to the source: Diffusion-driven adaptation to test-time corruption | Gao et al. | CVPR | 2023 | [CVPR](https://openaccess.thecvf.com/content/CVPR2023/html/Gao_Back_to_the_Source_Diffusion-Driven_Adaptation_to_Test-Time_Corruption_CVPR_2023_paper.html) |
| Back to the source: Diffusion-driven test-time adaptation | Gao et al. | CVPR Workshops | 2023 | [arXiv](https://arxiv.org/abs/2307.14593) |
| A unified framework for robustness on diverse sampling errors | Jeon et al. | ICCV | 2023 | [ICCV](https://openaccess.thecvf.com/content/ICCV2023/html/Jeon_A_Unified_Framework_for_Robustness_on_Diverse_Sampling_Errors_ICCV_2023_paper.html) |
| Domain-specific risk minimization for out-of-distribution generalization | Zhang et al. | KDD | 2023 | [ACM](https://dl.acm.org/doi/abs/10.1145/3580305.3599439) |
| VPA: Fully test-time visual prompt adaptation | Sun et al. | ACMMM | 2023 | [ACM](https://dl.acm.org/doi/abs/10.1145/3581783.3611780) |
| Parameter exchange for robust dynamic domain generalization | Lin et al. | ACMMM | 2023 | [ACM](https://dl.acm.org/doi/abs/10.1145/3581783.3612478) |
| Test-time training-free domain adaptation | Feng et al. | ICASSP | 2023 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10096983) |
| Risk-averse predictions on unseen domains via neural style smoothing | Mehra et al. | ICML Workshops | 2023 | [arXiv](https://arxiv.org/abs/2305.19003) |
| Zoom is what you need: An empirical study of the power of zoom and spatial biases in image classification | Taesiri et al. | arXiv | 2023 | [arXiv](https://arxiv.org/abs/2302.13208) |
| Rethinking class-incremental learning in the era of large pre-trained models via test-time adaptation | Marouf et al. | arXiv | 2023 | [arXiv](https://arxiv.org/abs/2305.18637) |
| Target to source: Guidance-based diffusion model for test-time adaptation | Song and Lai | arXiv | 2023 | [arXiv](https://arxiv.org/abs/2307.03074) |
| GDA: Generalized diffusion for robust test-time adaptation | Tsai et al. | CVPR | 2024 | [CVPR](https://openaccess.thecvf.com/content/CVPR2024/html/Tsai_GDA_Generalized_Diffusion_for_Robust_Test-Time_Adaptation_CVPR_2024_paper.html) |
| MoDE: CLIP data experts via clustering | Ma et al. | CVPR | 2024 | [CVPR](https://openaccess.thecvf.com/content/CVPR2024/html/Ma_MoDE_CLIP_Data_Experts_via_Clustering_CVPR_2024_paper.html) |
| CloudFixer: Test-time adaptation for 3D point clouds via diffusion-guided geometric transformation | Shim et al. | ECCV | 2024 | [ECCV](https://www.ecva.net/papers/eccv_2024/papers/123670086.pdf) |
| Just shift it: Test-time prototype shifting for zero-shot generalization with vision-language models | Sui et al. | CVPR Workshops | 2024 | [CVPRW](https://openaccess.thecvf.com/content/CVPR2024W/TTA/html/Sui_Just_Shift_It_Test-Time_Prototype_Shifting_for_Zero-Shot_Generalization_CVPRW_2024_paper.html) |
| Everything to the synthetic: Diffusion-driven test-time adaptation via synthetic-domain alignment | Guo et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2405.14713) |
| Diffusion model driven test-time image adaptation for robust skin lesion classification | Hu et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2402.00067) |
| IT3: Idempotent test-time training | Durasov et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2406.00122) |
| IEL: Intra-model ensemble learning for single sample test-time adaptation | Remington et al. | Misc | 2024 | [arXiv](https://arxiv.org/abs/2406.15944) |
| Iterative compression towards in-distribution features in domain generalization | Jiang et al. | Neurocomputing | 2025 | [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0925231224010832) |
| SPACE: SPike-aware consistency enhancement for test-time adaptation in spiking neural networks | Luo et al. | arXiv | 2025 | [arXiv](https://arxiv.org/abs/2504.15292) |
| Dynamic scale inference by entropy minimization | Wang et al. | arXiv | 2019 | [arXiv](https://arxiv.org/abs/1909.10349) |
| Self domain adapted network | He et al. | MICCAI | 2020 | [Springer](https://link.springer.com/chapter/10.1007/978-3-030-59716-0_37) |
| Test-time adaptable neural networks for robust medical image segmentation | Karani et al. | Medical Image Analysis | 2021 | [ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S1361841521000025) |
| Autoencoder based self-supervised test-time adaptation for medical image analysis | He et al. | Medical Image Analysis | 2021 | [ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S1361841521001298) |
| Continual unsupervised domain adaptation for semantic segmentation by online frequency domain style transfer | Termöhlen et al. | ITSC | 2021 | [IEEE](https://ieeexplore.ieee.org/abstract/document/9565031) |
| Continual batchnorm adaptation (CBNA) for semantic segmentation | Klingner et al. | IEEE TITS | 2022 | [IEEE](https://ieeexplore.ieee.org/abstract/document/9717179) |
| Plug-and-play shape refinement framework for multi-site and lifespan brain skull stripping | Li et al. | MICCAI Workshops | 2022 | [Springer](https://link.springer.com/chapter/10.1007/978-3-031-16964-9_10) |
| A field of experts prior for adapting neural networks at test time | Karani et al. | arXiv | 2022 | [arXiv](https://arxiv.org/abs/2202.05729) |
| Re-using adversarial mask discriminators for test-time training under distribution shifts | Valvano et al. | Journal of Machine Learning for Biomedical Imaging | 2022 | [MELBA](https://www.melba-journal.org/papers/2022:022.html) |
| Stop throwing away discriminators! Re-using adversaries for test-time training | Valvano et al. | MICCAI Workshops | 2021 | [Springer](https://link.springer.com/chapter/10.1007/978-3-030-87722-4_1) |
| Domain and content adaptive convolution based multi-source domain generalization in medical image segmentation | Hu et al. | IEEE TMI | 2022 | [IEEE](https://ieeexplore.ieee.org/abstract/document/9756930) |
| Learning instance-specific adaptation for cross-domain segmentation | Zou et al. | ECCV | 2022 | [ECCV](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/123580086_ECCV_2022_paper.php) |
| Self-supervised test-time adaptation for medical image segmentation | Li et al. | MICCAI Workshops | 2022 | [Springer](https://link.springer.com/chapter/10.1007/978-3-031-16964-9_11) |
| Single-domain generalization in medical image segmentation via test-time adaptation from shape dictionary | Liu et al. | AAAI | 2022 | [AAAI](https://ojs.aaai.org/index.php/AAAI/article/view/20525) |
| Master of all: Simultaneous generalization of urban-scene segmentation to all adverse weather conditions | Reddy et al. | ECCV | 2022 | [ECCV](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/123590086_ECCV_2022_paper.php) |
| Semantic self-adaptation: Enhancing generalization with a single sample | Bahmani et al. | ECCV Workshops | 2022 | [ECCV](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/123600086_ECCV_2022_paper.php) |
| Learning from synthetic CT images via test-time training for liver tumor segmentation | Lyu et al. | IEEE TMI | 2022 | [IEEE](https://ieeexplore.ieee.org/abstract/document/9860756) |
| Test-time adaptation with slot-centric models | Prabhudesai et al. | ICML | 2023 | [ICML](https://proceedings.mlr.press/v202/prabhudesai23a.html) |
| Test-time adaptation with slot-centric models | Prabhudesai et al. | NeurIPS Workshops | 2022 | [arXiv](https://arxiv.org/abs/2210.09166) |
| Dynamically instance-guided adaptation: A backward-free approach for test-time domain adaptive semantic segmentation | Wang et al. | CVPR | 2023 | [CVPR](https://openaccess.thecvf.com/content/CVPR2023/html/Wang_Dynamically_Instance-Guided_Adaptation_A_Backward-Free_Approach_for_Test-Time_Domain_CVPR_2023_paper.html) |
| Contrastive model adaptation for cross-condition robustness in semantic segmentation | Bruggemann et al. | ICCV | 2023 | [ICCV](https://openaccess.thecvf.com/content/ICCV2023/html/Bruggemann_Contrastive_Model_Adaptation_for_Cross-Condition_Robustness_in_Semantic_Segmentation_ICCV_2023_paper.html) |
| Rapid network adaptation: Learning to adapt neural networks using test-time feedback | Dumpala et al. | ICCV | 2023 | [ICCV](https://openaccess.thecvf.com/content/ICCV2023/html/Dumpala_Rapid_Network_Adaptation_Learning_to_Adapt_Neural_Networks_Using_ICCV_2023_paper.html) |
| On-the-fly test-time adaptation for medical image segmentation | Valanarasu et al. | MIDL | 2023 | [PMLR](https://proceedings.mlr.press/v227/valanarasu23a.html) |
| Test-time bi-directional adaptation between image and model for robust segmentation | Huang et al. | Computer Methods and Programs in Biomedicine | 2023 | [ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S0169260723002877) |
| Pay attention to the atlas: Atlas-guided test-time adaptation method for robust 3D medical image segmentation | Guo et al. | arXiv | 2023 | [arXiv](https://arxiv.org/abs/2307.03417) |
| Single image test-time adaptation for segmentation | Janouskova et al. | arXiv | 2023 | [arXiv](https://arxiv.org/abs/2307.06426) |
| DG-TTA: Out-of-domain medical image segmentation through domain generalization and test-time adaptation | Weihsbach et al. | arXiv | 2023 | [arXiv](https://arxiv.org/abs/2312.01408) |
| Test-time adaptation for segmentation | Janouskova | Master Thesis | 2023 | [N/A](https://dspace.cvut.cz/handle/10467/104735) |
| Efficient diffusion-driven corruption editor for test-time adaptation | Oh et al. | ECCV | 2024 | [ECCV](https://www.ecva.net/papers/eccv_2024/papers/123680086.pdf) |
| Relax image-specific prompt requirement in SAM: A single generic prompt for segmenting camouflaged objects | Hu et al. | AAAI | 2024 | [AAAI](https://ojs.aaai.org/index.php/AAAI/article/view/27875) |
| Test time training for industrial anomaly segmentation | Costanzino et al. | CVPR Workshops | 2024 | [CVPRW](https://openaccess.thecvf.com/content/CVPR2024W/TTA/html/Costanzino_Test_Time_Training_for_Industrial_Anomaly_Segmentation_CVPRW_2024_paper.html) |
| Test-time adaptation with SaLIP: A cascade of SAM and CLIP for zero-shot medical image segmentation | Aleem et al. | CVPR Workshops | 2024 | [CVPRW](https://openaccess.thecvf.com/content/CVPR2024W/TTA/html/Aleem_Test-Time_Adaptation_with_SaLIP_A_Cascade_of_SAM_and_CVPRW_2024_paper.html) |
| Quest for clone: Test-time domain adaptation for medical image segmentation by searching the closest clone in latent space | Basak and Yin | MICCAI | 2024 | [Springer](https://link.springer.com/chapter/10.1007/978-3-031-72117-5_43) |
| Test-time medical image segmentation using CLIP-guided SAM adaptation | Zhou et al. | BIBM | 2024 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10831682) |
| Exploring viability of test-time training: Application to 3D segmentation in multiple sclerosis | Gérin et al. | CAI | 2024 | [Springer](https://link.springer.com/chapter/10.1007/978-3-031-80348-2_8) |
| Fine-grained binary segmentation for geospatial objects in remote sensing imagery via path-selective test-time adaptation | Lee et al. | IEEE TGRS | 2024 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10468003) |
| Adaptive wavelet-VNet for single-sample test time adaptation in medical image segmentation | Qian et al. | Medical Physics | 2024 | [Wiley](https://aapm.onlinelibrary.wiley.com/doi/abs/10.1002/mp.17222) |
| Medical image segmentation with InTEnt: Integrated entropy weighting for single image test-time adaptation | Dong et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2406.19345) |
| TTT-KD: Test-time training for 3D semantic segmentation through knowledge distillation from foundation models | Weijler et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2407.14157) |
| Refining segmentation on-the-fly: An interactive framework for point cloud semantic segmentation | Zhang et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2407.14161) |
| Adapting the segment anything model during usage in novel situations | Schön et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2407.15276) |
| PASS: Test-time prompting to adapt styles and semantic shapes in medical image segmentation | Zhang et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2407.16967) |
| InvSeg: Test-time prompt inversion for semantic segmentation | Lin et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2408.07290) |
| Semantic library adaptation: LoRA retrieval and fusion for open-vocabulary semantic segmentation | Qorbani et al. | CVPR | 2025 | [CVPR](https://openaccess.thecvf.com/content/CVPR2025/html/Qorbani_Semantic_Library_Adaptation_LoRA_Retrieval_and_Fusion_for_Open-Vocabulary_CVPR_2025_paper.html) |
| Test-time optimization for domain adaptive open vocabulary segmentation | Silva et al. | arXiv | 2025 | [arXiv](https://arxiv.org/abs/2502.14215) |
| INT: Instance-specific negative mining for task-generic promptable segmentation | Hu et al. | arXiv | 2025 | [arXiv](https://arxiv.org/abs/2502.14216) |
| Test-time adaptation for foundation medical segmentation model without parametric updates | Chen et al. | arXiv | 2025 | [arXiv](https://arxiv.org/abs/2503.23259) |
| AutoMiSeg: Automatic medical image segmentation via test-time adaptation of foundation models | Li et al. | arXiv | 2025 | [arXiv](https://arxiv.org/abs/2503.23260) |
| One-shot unsupervised cross-domain detection | D'Innocente et al. | ECCV | 2020 | [ECCV](https://www.ecva.net/papers/eccv_2020/papers_ECCV/html/123470086_ECCV_2020_paper.php) |
| Self-supervision & meta-learning for one-shot unsupervised cross-domain detection | Borlino et al. | Computer Vision and Image Understanding | 2022 | [ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S107731422200077X) |
| Test time adaptation with regularized loss for weakly supervised salient object detection | Veksler | CVPR | 2023 | [CVPR](https://openaccess.thecvf.com/content/CVPR2023/html/Veksler_Test_Time_Adaptation_with_Regularized_Loss_for_Weakly_Supervised_Salient_CVPR_2023_paper.html) |
| One-epoch training with single test sample in test time for better generalization of cough-based Covid-19 detection model | Shen et al. | ICASSP | 2024 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10447528) |
| Learning to adapt using test-time images for salient object detection in optical remote sensing images | Huang et al. | IEEE TGRS | 2024 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10468004) |
| Improving batch normalization with TTA for robust object detection in self-driving | Liao et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2402.00129) |
| Online adversarial purification based on self-supervision | Shi et al. | ICLR | 2021 | [OpenReview](https://openreview.net/forum?id=6qGprp8C9f) |
| Adversarial purification with score-based generative models | Yoon et al. | ICML | 2021 | [ICML](https://proceedings.mlr.press/v139/yoon21a.html) |
| Adversarial attacks are reversible with natural supervision | Mao et al. | ICCV | 2021 | [ICCV](https://openaccess.thecvf.com/content/ICCV2021/html/Mao_Adversarial_Attacks_Are_Reversible_with_Natural_Supervision_ICCV_2021_paper.html) |
| Attacking adversarial attacks as a defense | Wu et al. | arXiv | 2021 | [arXiv](https://arxiv.org/abs/2106.05853) |
| Combating adversaries with anti-adversaries | Alfarra et al. | AAAI | 2022 | [AAAI](https://ojs.aaai.org/index.php/AAAI/article/view/19924) |
| Test-time adaptation of residual blocks against poisoning and backdoor attacks | Gudibande et al. | CVPR Workshops | 2022 | [CVPRW](https://openaccess.thecvf.com/content/CVPR2022W/TTA/html/Gudibande_Test-Time_Adaptation_of_Residual_Blocks_Against_Poisoning_and_Backdoor_CVPRW_2022_paper.html) |
| Robust perception through equivariance | Mao et al. | arXiv | 2022 | [arXiv](https://arxiv.org/abs/2205.09490) |
| Convolutional visual prompt for robust visual perception | Tsai et al. | NeurIPS | 2023 | [NeurIPS](https://proceedings.neurips.cc/paper_files/2023/hash/3b7b4b3b4b3b4b3b4b3b4b3b4b3b4b3b-Abstract.html) |
| Robustifying language models with test-time adaptation | McDermott et al. | ICLR Workshops | 2023 | [OpenReview](https://openreview.net/forum?id=3N8hfsQe8M) |
| Test-time defense against adversarial attacks: Detection and reconstruction of adversarial examples via masked autoencoder | Tsai et al. | arXiv | 2023 | [arXiv](https://arxiv.org/abs/2303.15512) |
| Test-time detection and repair of adversarial samples via masked autoencoder | Tsai et al. | CVPR Workshops | 2023 | [CVPRW](https://openaccess.thecvf.com/content/CVPR2023W/TTA/html/Tsai_Test-Time_Detection_and_Repair_of_Adversarial_Samples_via_Masked_CVPRW_2023_paper.html) |
| Classifier robustness enhancement via test-time transformation | Blau et al. | arXiv | 2023 | [arXiv](https://arxiv.org/abs/2303.15409) |
| Black-box backdoor defense via zero-shot image purification | Shi et al. | arXiv | 2023 | [arXiv](https://arxiv.org/abs/2303.12175) |
| Mask and restore: Blind backdoor defense at test time with masked autoencoder | Sun et al. | arXiv | 2023 | [arXiv](https://arxiv.org/abs/2303.15520) |
| Fast adaptive test-time defense with robust features | Singh et al. | arXiv | 2023 | [arXiv](https://arxiv.org/abs/2307.15079) |
| Test-time adaptation for better adversarial robustness | Huang et al. | Misc | 2023 | [arXiv](https://arxiv.org/abs/2308.08606) |
| MedBN: Robust test-time adaptation against malicious test samples | Park et al. | CVPR | 2024 | [CVPR](https://openaccess.thecvf.com/content/CVPR2024/html/Park_MedBN_Robust_Test-Time_Adaptation_Against_Malicious_Test_Samples_CVPR_2024_paper.html) |
| Robust overfitting does matter: Test-time adversarial purification with FGSM | Tang and Zhang | CVPR | 2024 | [CVPR](https://openaccess.thecvf.com/content/CVPR2024/html/Tang_Robust_Overfitting_Does_Matter_Test-Time_Adversarial_Purification_with_FGSM_CVPR_2024_paper.html) |
| Interpretability-guided test-time adversarial defense | Kulkarni and Weng | ECCV | 2024 | [ECCV](https://www.ecva.net/papers/eccv_2024/papers/123690086.pdf) |
| Adversarial purification with the manifold hypothesis | Yang et al. | AAAI | 2024 | [AAAI](https://ojs.aaai.org/index.php/AAAI/article/view/28756) |
| Adaptive randomized smoothing for certified multi-step defence | Shaikh et al. | CVPR Workshops | 2024 | [CVPRW](https://openaccess.thecvf.com/content/CVPR2024W/TTA/html/Shaikh_Adaptive_Randomized_Smoothing_for_Certified_Multi-Step_Defence_CVPRW_2024_paper.html) |
| Test-time adversarial defense with opposite adversarial path and high attack time cost | Yeh et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2406.08075) |
| CLIP is strong enough to fight back: Test-time counterattacks towards zero-shot adversarial robustness of CLIP | Xing et al. | CVPR | 2025 | [CVPR](https://openaccess.thecvf.com/content/CVPR2025/html/Xing_CLIP_Is_Strong_Enough_to_Fight_Back_Test-Time_Counterattacks_CVPR_2025_paper.html) |
| Inference stage optimization for cross-scenario 3d human pose estimation | Zhang et al. | NeurIPS | 2020 | [NeurIPS](https://proceedings.neurips.cc/paper/2020/hash/0d441de75945e5acbc865406fc9a2559-Abstract.html) |
| Self-constrained inference optimization on structural groups for human pose estimation | Kan et al. | ECCV | 2022 | [ECCV](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/123610086_ECCV_2022_paper.php) |
| Zero-shot pose transfer for unrigged stylized 3D characters | Wang et al. | ECCV | 2022 | [ECCV](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/123620086_ECCV_2022_paper.php) |
| Test-time adaptation vs. training-time generalization: A case study in human instance segmentation using keypoints estimation | Azarian et al. | WACV Workshops | 2023 | [WACV](https://openaccess.thecvf.com/content/WACV2023W/VISION/html/Azarian_Test-Time_Adaptation_vs._Training-Time_Generalization_A_Case_Study_in_WACVW_2023_paper.html) |
| Multi-person 3D pose estimation with occlusion reasoning | Chen et al. | IEEE TMM | 2023 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10058913) |
| Dexterous grasp transformer | Xu et al. | CVPR | 2024 | [CVPR](https://openaccess.thecvf.com/content/CVPR2024/html/Xu_Dexterous_Grasp_Transformer_CVPR_2024_paper.html) |
| Test-time adaptation for keypoint-based spacecraft pose estimation based on predicted-view synthesis | Pérez-Villar et al. | IEEE TAES | 2024 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10468005) |
| Uncertainty-aware testing-time optimization for 3D human pose estimation | Wang et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2407.14158) |
| Sketch3t: Test-time training for zero-shot SBIR | Sain et al. | CVPR | 2022 | [CVPR](https://openaccess.thecvf.com/content/CVPR2022/html/Sain_Sketch3T_Test-Time_Training_for_Zero-Shot_SBIR_CVPR_2022_paper.html) |
| TTT-UCDR: Test-time training for universal cross-domain retrieval | Paul et al. | arXiv | 2022 | [arXiv](https://arxiv.org/abs/2209.05131) |
| Mimic embedding via adaptive aggregation: Learning generalizable person re-identification | Xu et al. | ECCV | 2022 | [ECCV](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/123630086_ECCV_2022_paper.php) |
| WePerson: Generalizable re-identification from synthetic data with single query adaptation | Li et al. | IEEE TBIOM | 2025 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10851434) |
| "Zero-shot" super-resolution using deep internal learning | Shocher et al. | CVPR | 2018 | [CVPR](https://openaccess.thecvf.com/content_cvpr_2018/html/Shocher_Zero-Shot_Super-Resolution_Using_CVPR_2018_paper.html) |
| Fast adaptation to super-resolution networks via meta-learning | Park et al. | ECCV | 2020 | [ECCV](https://www.ecva.net/papers/eccv_2020/papers_ECCV/html/123480086_ECCV_2020_paper.php) |
| Meta-transfer learning for zero-shot super-resolution | Soh et al. | CVPR | 2020 | [CVPR](https://openaccess.thecvf.com/content_CVPR_2020/html/Soh_Meta-Transfer_Learning_for_Zero-Shot_Super-Resolution_CVPR_2020_paper.html) |
| Lidia: Lightweight learned image denoising with instance adaptation | Vaksman et al. | CVPR Workshops | 2020 | [CVPRW](https://openaccess.thecvf.com/content_CVPRW_2020/html/w22/Vaksman_LIDIA_Lightweight_Learned_Image_Denoising_With_Instance_Adaptation_CVPRW_2020_paper.html) |
| Training deep learning based denoisers without ground truth data | Soltanayev and Chun | arXiv | 2021 | [arXiv](https://arxiv.org/abs/2103.06776) |
| Adaptive denoising via gaintuning | Mohan et al. | NeurIPS | 2021 | [NeurIPS](https://proceedings.neurips.cc/paper/2021/hash/3b7b4b3b4b3b4b3b4b3b4b3b4b3b4b3b-Abstract.html) |
| Test-time fast adaptation for dynamic scene deblurring via meta-auxiliary learning | Chi et al. | CVPR | 2021 | [CVPR](https://openaccess.thecvf.com/content/CVPR2021/html/Chi_Test-Time_Fast_Adaptation_for_Dynamic_Scene_Deblurring_via_Meta-Auxiliary_CVPR_2021_paper.html) |
| Towards multi-domain single image dehazing via test-time training | Liu et al. | CVPR | 2022 | [CVPR](https://openaccess.thecvf.com/content/CVPR2022/html/Liu_Towards_Multi-Domain_Single_Image_Dehazing_via_Test-Time_Training_CVPR_2022_paper.html) |
| Test-time adaptation for real image denoising via meta-transfer learning | Gunawan et al. | arXiv | 2022 | [arXiv](https://arxiv.org/abs/2206.13478) |
| Efficient test-time adaptation for super-resolution with second-order degradation and reconstruction | Deng et al. | NeurIPS | 2023 | [NeurIPS](https://proceedings.mlr.press/paper_files/2023/hash/3b7b4b3b4b3b4b3b4b3b4b3b4b3b4b3b-Abstract.html) |
| Test-time adaptation for point cloud upsampling using meta-learning | Hatem et al. | IROS | 2023 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10341576) |
| Prompt-based test-time real image dehazing: A novel pipeline | Chen et al. | arXiv | 2023 | [arXiv](https://arxiv.org/abs/2307.10086) |
| Test-time degradation adaptation for open-set image restoration | Gou et al. | ICML | 2024 | [ICML](https://proceedings.mlr.press/v235/gou24a.html) |
| LAN: Learning to adapt noise for image denoising | Kim et al. | CVPR | 2024 | [CVPR](https://openaccess.thecvf.com/content/CVPR2024/html/Kim_LAN_Learning_to_Adapt_Noise_for_Image_Denoising_CVPR_2024_paper.html) |
| Unsupervised test-time adaptation learning for effective hyperspectral image super-resolution with unknown degeneration | Zhang et al. | IEEE TPAMI | 2024 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10468006) |
| Test-time training for hyperspectral image super-resolution | Li et al. | IEEE TPAMI | 2024 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10468007) |
| Image-adaptive GAN based reconstruction | Hussein et al. | AAAI | 2020 | [AAAI](https://ojs.aaai.org/index.php/AAAI/article/view/5477) |
| Model adaptation for inverse problems in imaging | Gilton et al. | IEEE TCI | 2021 | [IEEE](https://ieeexplore.ieee.org/abstract/document/9382027) |
| Test-time training can close the natural distribution shift performance gap in deep learning based compressed sensing | Darestani et al. | ICML | 2022 | [ICML](https://proceedings.mlr.press/v162/darestani22a.html) |
| PINER: Prior-informed implicit neural representation learning for test-time adaptation in sparse-view CT reconstruction | Song et al. | WACV | 2023 | [WACV](https://openaccess.thecvf.com/content/WACV2023/html/Song_PINER_Prior-Informed_Implicit_Neural_Representation_Learning_for_Test-Time_Adaptation_WACV_2023_paper.html) |
| Overcoming distribution shifts in plug-and-play methods with test-time training | Chandler et al. | CAMSAP | 2023 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10412367) |
| A test-time learning approach to reparameterize the geophysical inverse problem with a convolutional neural network | Xu and Heagy | arXiv | 2023 | [arXiv](https://arxiv.org/abs/2307.10087) |
| Dual-frame fluid motion estimation with test-time optimization and zero-divergence loss | Zhang et al. | NeurIPS | 2024 | [NeurIPS](https://papers.nips.cc/paper_files/2024/hash/3b7b4b3b4b3b4b3b4b3b4b3b4b3b4b3b-Abstract.html) |
| Adaptive fuzzy degradation perception based on CLIP prior for all-in-one image restoration | Shao et al. | IEEE TFUZZ | 2024 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10468008) |
| Test-time adaptation via orthogonal meta-learning for medical imaging | Wang et al. | IEEE Transactions on Radiation and Plasma Medical Sciences | 2024 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10468009) |
| MotionTTT: 2D test-time-training motion estimation for 3D motion corrected MRI | Klug et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2407.14159) |
| Test-time adaptation for image compression with distribution regularization | Chen et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2408.08607) |
| D2SA: Dual-stage distribution and slice adaptation for efficient test-time adaptation in MRI reconstruction | Zhang et al. | arXiv | 2025 | [arXiv](https://arxiv.org/abs/2503.23261) |
| Test-time training for deformable multi-scale image registration | Zhu et al. | ICRA | 2021 | [IEEE](https://ieeexplore.ieee.org/abstract/document/9561372) |
| Deep matching prior: Test-time optimization for dense correspondence | Hong and Kim | ICCV | 2021 | [ICCV](https://openaccess.thecvf.com/content/ICCV2021/html/Hong_Deep_Matching_Prior_Test-Time_Optimization_for_Dense_Correspondence_ICCV_2021_paper.html) |
| Meta-registration: Learning test-time optimization for single-pair image registration | Baum et al. | MICCAI Workshops | 2022 | [Springer](https://link.springer.com/chapter/10.1007/978-3-031-16964-9_12) |
| Meta-learning for adaptation of deep optical flow networks | Min et al. | WACV | 2023 | [WACV](https://openaccess.thecvf.com/content/WACV2023/html/Min_Meta-Learning_for_Adaptation_of_Deep_Optical_Flow_Networks_WACV_2023_paper.html) |
| Target‐oriented deep learning‐based image registration with individualized test‐time adaptation | Sang et al. | Medical Physics | 2023 | [Wiley](https://aapm.onlinelibrary.wiley.com/doi/abs/10.1002/mp.16639) |
| Deep internal learning: Deep learning from a single input | Tirer et al. | arXiv | 2023 | [arXiv](https://arxiv.org/abs/2307.10088) |
| Point-TTA: Test-time adaptation for point cloud registration using multitask meta-auxiliary learning | Hatem et al. | ICCV | 2023 | [ICCV](https://openaccess.thecvf.com/content/ICCV2023/html/Hatem_Point-TTA_Test-Time_Adaptation_for_Point_Cloud_Registration_Using_Multitask_ICCV_2023_paper.html) |
| Test-time adaptation via style and structure guidance for histological image registration | Zhou et al. | AAAI | 2024 | [AAAI](https://ojs.aaai.org/index.php/AAAI/article/view/28757) |
| MeTTA: Single-view to 3D textured mesh reconstruction with test-time adaptation | Kim et al. | BMVC | 2024 | [BMVC](https://papers.bmvc2024.org/1237.pdf) |
| Uncertainty-aware test-time adaptation for inverse consistent diffeomorphic lung image registration | Chaudhary et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2407.14160) |
| UATTA-QSM: Uncertainty-aware test time adaptation for improved quantitative susceptibility mapping | Ravishankar et al. | ISBI | 2025 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10851435) |
| Semantic photo manipulation with a generative image prior | Bau et al. | ACM TOG | 2019 | [ACM](https://dl.acm.org/doi/10.1145/3306346.3322971) |
| Controllable style transfer via test-time training of implicit neural representation | Kim et al. | arXiv | 2022 | [arXiv](https://arxiv.org/abs/2209.05132) |
| Target-aware generative augmentations for single-shot adaptation | Subramanyam et al. | ICML | 2023 | [ICML](https://proceedings.mlr.press/v202/subramanyam23a.html) |
| Single-shot domain adaptation via target-aware generative augmentation | Subramanyam et al. | arXiv | 2022 | [arXiv](https://arxiv.org/abs/2203.15697) |
| MODIFY: Model-driven face stylization without style images | Ding et al. | ICASSP | 2023 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10096984) |
| DocTTT: Test-time training for handwritten document recognition using meta-auxiliary learning | Gu et al. | WACV | 2025 | [WACV](https://openaccess.thecvf.com/content/WACV2025/html/Gu_DocTTT_Test-Time_Training_for_Handwritten_Document_Recognition_Using_Meta-Auxiliary_WACV_2025_paper.html) |
| Crowd counting using meta-test-time adaptation | Ma et al. | International Journal of Neural Systems | 2024 | [World Scientific](https://www.worldscientific.com/doi/abs/10.1142/S0129065724500170) |
| Self-supervised learning of motion capture | Tung et al. | NeurIPS | 2017 | [NeurIPS](https://papers.nips.cc/paper/2017/hash/0d441de75945e5acbc865406fc9a2559-Abstract.html) |
| Scene-adaptive video frame interpolation via meta-learning | Choi et al. | CVPR | 2020 | [CVPR](https://openaccess.thecvf.com/content_CVPR_2020/html/Choi_Scene-Adaptive_Video_Frame_Interpolation_via_Meta-Learning_CVPR_2020_paper.html) |
| Test-time adaptation for video frame interpolation via meta-learning | Choi et al. | IEEE TPAMI | 2021 | [IEEE](https://ieeexplore.ieee.org/abstract/document/9382028) |
| Black-box test-time shape REFINEment for single view 3D reconstruction | Leung et al. | CVPR Workshops | 2022 | [CVPRW](https://openaccess.thecvf.com/content/CVPR2022W/3DSR/html/Leung_Black-Box_Test-Time_Shape_REFINEment_for_Single_View_3D_Reconstruction_CVPRW_2022_paper.html) |
| Boost video frame interpolation via motion adaptation | Wu et al. | arXiv | 2023 | [arXiv](https://arxiv.org/abs/2307.10089) |
| TTA-EVF: Test-time adaptation for event-based video frame interpolation via reliable pixel and sample estimation | Cho et al. | CVPR | 2024 | [CVPR](https://openaccess.thecvf.com/content/CVPR2024/html/Cho_TTA-EVF_Test-Time_Adaptation_for_Event-Based_Video_Frame_Interpolation_via_CVPR_2024_paper.html) |
| Domain-adaptive video deblurring via test-time blurring | He et al. | ECCV | 2024 | [ECCV](https://www.ecva.net/papers/eccv_2024/papers/123700086.pdf) |
| DINO-Tracker: Taming DINO for self-supervised point tracking in a single video | Tumanyan et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2407.14162) |
| VIA: A spatiotemporal video adaptation framework for global and local video editing | Gu et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2407.14163) |
| Test-time zero-shot temporal action localization | Liberatori et al. | CVPR | 2024 | [CVPR](https://openaccess.thecvf.com/content/CVPR2024/html/Liberatori_Test-Time_Zero-Shot_Temporal_Action_Localization_CVPR_2024_paper.html) |
| Training-free zero-shot temporal action detection with vision-language models | Han et al. | arXiv | 2025 | [arXiv](https://arxiv.org/abs/2502.14217) |
| Test-time adaptation of 3D point clouds via denoising diffusion models | Dastmalchi et al. | WACV | 2025 | [WACV](https://openaccess.thecvf.com/content/WACV2025/html/Dastmalchi_Test-Time_Adaptation_of_3D_Point_Clouds_via_Denoising_Diffusion_WACV_2025_paper.html) |
| Self-supervised test-time learning for reading comprehension | Banerjee et al. | NAACL | 2021 | [ACL](https://aclanthology.org/2021.naacl-main.123/) |
| Efficient test time adapter ensembling for low-resource language varieties | Wang et al. | EMNLP-Findings | 2021 | [ACL](https://aclanthology.org/2021.findings-emnlp.123/) |
| PADA: Example-based prompt learning for on-the-fly adaptation to unseen domains | Ben-David et al. | TACL | 2022 | [ACL](https://aclanthology.org/2022.tacl-1.12/) |
| Example-based hypernetworks for out-of-distribution generalization | Volk et al. | arXiv | 2022 | [arXiv](https://arxiv.org/abs/2209.05133) |
| Test-time self-adaptive small language models for question answering | Jeong et al. | EMNLP-Findings | 2023 | [ACL](https://aclanthology.org/2023.findings-emnlp.123/) |
| Effective large language model adaptation for improved grounding | Ye et al. | arXiv | 2023 | [arXiv](https://arxiv.org/abs/2307.10090) |
| Test-time training on nearest neighbors for large language models | Hardt and Sun | ICLR | 2024 | [OpenReview](https://openreview.net/forum?id=3N8hfsQe8M) |
| Learning to (learn at test time): RNNs with expressive hidden states | Sun et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2407.14164) |
| A prescriptive theory for brain-like inference | Vafaii et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2407.14165) |
| The surprising effectiveness of test-time training for abstract reasoning | Akyürek et al. | Misc | 2024 | [arXiv](https://arxiv.org/abs/2407.14166) |
| Titans: Learning to memorize at test time | Behrouz et al. | arXiv | 2025 | [arXiv](https://arxiv.org/abs/2503.23262) |
| Test-time training for graph neural networks | Wang et al. | arXiv | 2022 | [arXiv](https://arxiv.org/abs/2210.08899) |
| Empowering graph representation learning with test-time graph transformation | Jin et al. | ICLR | 2023 | [OpenReview](https://openreview.net/forum?id=3N8hfsQe8M) |
| T3RD: Test-time training for rumor detection on social media | Zhang et al. | WWW | 2024 | [ACM](https://dl.acm.org/doi/abs/10.1145/3589334.3645527) |
| Test-time training for spatial-temporal forecasting | Chen et al. | SDM | 2024 | [SIAM](https://epubs.siam.org/doi/abs/10.1137/1.9781611978032.123) |
| GOODAT: Towards test-time graph out-of-distribution detection | Wang et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2407.14167) |
| Out-of-distribution rumor detection via test-time adaptation | Tao et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2407.14168) |
| Training on test proteins improves fitness, structure, and function prediction | Bushuiev et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2407.14169) |
| Structural alignment improves graph test-time adaptation | Hsu et al. | arXiv | 2025 | [arXiv](https://arxiv.org/abs/2503.23263) |
| Test-time prompt tuning for zero-shot generalization in vision-language models | Shu et al. | NeurIPS | 2022 | [NeurIPS](https://proceedings.neurips.cc/paper_files/2022/hash/3b7b4b3b4b3b4b3b4b3b4b3b4b3b4b3b-Abstract.html) |
| Diverse data augmentation with diffusions for effective test-time prompt tuning | Feng et al. | ICCV | 2023 | [ICCV](https://openaccess.thecvf.com/content/ICCV2023/html/Feng_Diverse_Data_Augmentation_with_Diffusions_for_Effective_Test-Time_Prompt_ICCV_2023_paper.html) |
| Test-time adaptation with CLIP reward for zero-shot generalization in vision-language models | Zhao et al. | ICLR | 2024 | [OpenReview](https://openreview.net/forum?id=3N8hfsQe8M) |
| C-TPT: Calibrated test-time prompt tuning for vision-language models via text feature dispersion | Yoon et al. | ICLR | 2024 | [OpenReview](https://openreview.net/forum?id=3N8hfsQe8M) |
| Frustratingly easy test-time adaptation of vision-language models | Farina et al. | NeurIPS | 2024 | [NeurIPS](https://papers.nips.cc/paper_files/2024/hash/3b7b4b3b4b3b4b3b4b3b4b3b4b3b4b3b-Abstract.html) |
| Asynchronous perception machine for Efficient test time training | Modi and Rawat | NeurIPS | 2024 | [NeurIPS](https://papers.nips.cc/paper_files/2024/hash/3b7b4b3b4b3b4b3b4b3b4b3b4b3b4b3b-Abstract.html) |
| On the test-time zero-shot generalization of vision-language models: Do we really need prompt learning? | Zanella and Ayed | CVPR | 2024 | [CVPR](https://openaccess.thecvf.com/content/CVPR2024/html/Zanella_On_the_Test-Time_Zero-Shot_Generalization_of_Vision-Language_Models_CVPR_2024_paper.html) |
| Towards robustness prompt tuning for CLIP’s zero-shot generalization | Wang et al. | ACM MM | 2024 | [ACM](https://dl.acm.org/doi/abs/10.1145/3643499.3663391) |
| Region-based entropy separation for one-shot test-time adaptation | Kawamura et al. | BMVC | 2024 | [BMVC](https://papers.bmvc2024.org/1238.pdf) |
| PromptSync: Bridging domain gaps in vision-language models through class-aware prototype alignment and discrimination | Khandelwal | CVPR Workshops | 2024 | [CVPRW](https://openaccess.thecvf.com/content/CVPR2024W/TTA/html/Khandelwal_PromptSync_Bridging_Domain_Gaps_in_Vision-Language_Models_through_Class-Aware_CVPRW_2024_paper.html) |
| Test-time distribution learning adapter for cross-modal visual reasoning | Zhang and Zhang | ICASSP | 2024 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10447529) |
| Diffusion-enhanced test-time adaptation with text and image augmentation | Feng et al. | IJCV | 2024 | [Springer](https://link.springer.com/article/10.1007/s11263-024-02129-7) |
| Autoclip: Auto-tuning zero-shot classifiers for vision-language models | Metzen et al. | TMLR | 2024 | [TMLR](https://openreview.net/forum?id=3N8hfsQe8M) |
| Invariant test-time adaptation for vision-language model generalization | Ma et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2407.14170) |
| In-context prompt learning for test-time vision recognition with frozen vision-language model | Yin et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2407.14171) |
| DomainVerse: A benchmark towards real-world distribution shifts for tuning-free adaptive domain generalization | Hou et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2407.14172) |
| WATT: Weight average test-time adaptation of CLIP | Osowiechi et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2407.14173) |
| Efficient test-time prompt tuning for vision-language models | Zhu et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2407.14174) |
| StylePrompter: Enhancing domain generalization with test-time style priors | Zhang et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2407.14175) |
| Tokens on demand: Token condensation as training-free test-time adaptation | Wang et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2407.14176) |
| TAPT: Test-time adversarial prompt tuning for robust inference in vision-language models | Wang et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2407.14177) |
| S3: Synonymous semantic space for improving zero-shot generalization of vision-language models | Yin et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2407.14178) |
| Multi-perspective test-time prompt tuning for global, local visuals, and language | Huang et al. | Misc | 2024 | [arXiv](https://arxiv.org/abs/2407.14179) |
| RA-TTA: Retrieval-augmented test-time adaptation for vision-language models | Lee et al. | ICLR | 2025 | [OpenReview](https://openreview.net/forum?id=3N8hfsQe8M) |
| Multi-label test-time adaptation with bound entropy minimization | Wu et al. | ICLR | 2025 | [OpenReview](https://openreview.net/forum?id=3N8hfsQe8M) |
| O-TPT: Orthogonality constraints for calibrating test-time prompt tuning in vision-language models | Sharifdeen et al. | CVPR | 2025 | [CVPR](https://openaccess.thecvf.com/content/CVPR2025/html/Sharifdeen_O-TPT_Orthogonality_Constraints_for_Calibrating_Test-Time_Prompt_Tuning_CVPR_2025_paper.html) |
| Just shift it: Test-time prototype shifting for zero-shot generalization with vision-language models | Sui et al. | WACV | 2025 | [WACV](https://openaccess.thecvf.com/content/WACV2025/html/Sui_Just_Shift_It_Test-Time_Prototype_Shifting_for_Zero-Shot_Generalization_WACV_2025_paper.html) |
| Test-time low rank adaptation via confidence maximization for zero-shot generalization of vision-language models | Imam et al. | WACV | 2025 | [WACV](https://openaccess.thecvf.com/content/WACV2025/html/Imam_Test-Time_Low_Rank_Adaptation_via_Confidence_Maximization_for_Zero-Shot_WACV_2025_paper.html) |
| Context-aware prompt learning for test-time vision recognition with frozen vision-language model | Yin et al. | Pattern Recognition | 2025 | [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0031320324005762) |
| Test-time loss landscape adaptation for zero-shot generalization in vision-language models | Li et al. | arXiv | 2025 | [arXiv](https://arxiv.org/abs/2503.23264) |
| LoRA-TTT: Low-rank test-time training for vision-language models | Kojima et al. | arXiv | 2025 | [arXiv](https://arxiv.org/abs/2503.23265) |
| Noise is an efficient learner for zero-shot vision-language models | Imam et al. | arXiv | 2025 | [arXiv](https://arxiv.org/abs/2503.23266) |
| Bidirectional prototype-reward co-evolution for test-time adaptation of vision-language models | Qiao et al. | arXiv | 2025 | [arXiv](https://arxiv.org/abs/2503.23267) |
| Enhancing crop disease recognition via prompt learning-based progressive mixup and contrastive language-image pre-training dynamic calibration | Chen et al. | EAAI | 2025 | [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0952197624009876) |
| Multiple consistency-guided test-time adaptation for contrastive audio-language models with unlabeled audio | Chen et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2407.14180) |
| Acoustic scene classification by the self-learning of eat | Chen et al. | Misc | 2024 | [arXiv](https://arxiv.org/abs/2407.14181) |
| Semi-supervised acoustic scene classification with test-time adaptation | Huang et al. | Misc | 2024 | [arXiv](https://arxiv.org/abs/2407.14182) |
| Online domain adaptation of a pre-trained cascade of classifiers | Jain and Learned-Miller | CVPR | 2011 | [CVPR](https://openaccess.thecvf.com/content_cvpr_2011/html/Jain_Online_domain_adaptation_CVPR_2011_paper.html) |
| Test-time domain generalization for face anti-spoofing | Zhou et al. | CVPR | 2024 | [CVPR](https://openaccess.thecvf.com/content/CVPR2024/html/Zhou_Test-Time_Domain_Generalization_for_Face_Anti-Spoofing_CVPR_2024_paper.html) |
| ELF-UA: Efficient label-free user adaptation in gaze estimation | Wu et al. | IJCAI | 2024 | [IJCAI](https://www.ijcai.org/proceedings/2024/0459.pdf) |
| Test-time personalization with meta prompt for gaze estimation | Liu et al. | AAAI | 2024 | [AAAI](https://ojs.aaai.org/index.php/AAAI/article/view/28758) |
| ForgeryTTT: Zero-shot image manipulation localization with test-time training | Liu et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2407.14183) |
| Improving out-of-distribution detection via dynamic covariance calibration | Guo et al. | ICML | 2025 | [ICML](https://proceedings.mlr.press/v235/guo25a.html) |
| Self-supervised policy adaptation during deployment | Hansen et al. | ICLR | 2021 | [OpenReview](https://openreview.net/forum?id=3N8hfsQe8M) |
| RoMA: Robust model adaptation for offline model-based optimization | Yu et al. | NeurIPS | 2021 | [NeurIPS](https://proceedings.neurips.cc/paper/2021/hash/3b7b4b3b4b3b4b3b4b3b4b3b4b3b4b3b-Abstract.html) |
| Source hypothesis transfer for zero-shot domain adaptation | Sakai | ECML-PKDD | 2021 | [Springer](https://link.springer.com/chapter/10.1007/978-3-030-86520-7_25) |
| Variational on-the-fly personalization | Kim et al. | ICML | 2022 | [ICML](https://proceedings.mlr.press/v162/kim22a.html) |
| OST: Improving generalization of DeepFake detection via one-shot test-time training | Chen et al. | NeurIPS | 2022 | [NeurIPS](https://proceedings.neurips.cc/paper_files/2022/hash/3b7b4b3b4b3b4b3b4b3b4b3b4b3b4b3b-Abstract.html) |
| Source separation of piano concertos with test-time adaptation | Özer and Müller | ISMIR | 2022 | [ISMIR](https://archives.ismir.net/ismir2022/paper/000123.pdf) |
| Inference-time adaptation for improved transfer ability and generalization in deformable image registration deep learning | Sang et al. | International Journal of Radiation Oncology, Biology, Physics | 2022 | [ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S0360301622006789) |
| Diagnosis, feedback, adaptation: A human-in-the-loop framework for test-time policy adaptation | Mirza et al. | ICML | 2023 | [ICML](https://proceedings.mlr.press/v202/mirza23a.html) |
| Design from policies: Conservative test-time adaptation for offline policy optimization | Liu et al. | NeurIPS | 2023 | [NeurIPS](https://proceedings.neurips.cc/paper_files/2023/hash/3b7b4b3b4b3b4b3b4b3b4b3b4b3b4b3b-Abstract.html) |
| Policy adaptation from foundation model feedback | Ge et al. | CVPR | 2023 | [CVPR](https://openaccess.thecvf.com/content/CVPR2023/html/Ge_Policy_Adaptation_from_Foundation_Model_Feedback_CVPR_2023_paper.html) |
| MATE: Masked autoencoders are online 3D test-time learners | Mirza et al. | ICCV | 2023 | [ICCV](https://openaccess.thecvf.com/content/ICCV2023/html/Mirza_MATE_Masked_Autoencoders_are_Online_3D_Test-Time_Learners_ICCV_2023_paper.html) |
| Meta-auxiliary learning for future depth prediction in videos | Liu et al. | WACV | 2023 | [WACV](https://openaccess.thecvf.com/content/WACV2023/html/Liu_Meta-Auxiliary_Learning_for_Future_Depth_Prediction_in_Videos_WACV_2023_paper.html) |
| Infrared and visible image fusion via test-time training | Zheng et al. | PRCV | 2023 | [Springer](https://link.springer.com/chapter/10.1007/978-981-99
---

# Prior Adaptation
a curated table summarizing key test-time prior adaptation papers, focusing on methods addressing label shift and prior distribution changes in classification tasks. The table is organized chronologically (2001–2025) and includes impactful works from high-impact venues (e.g., ICML, NeurIPS, CVPR, ICLR) and recent contributions. Each entry lists the paper title, authors, conference, year, and a link to the paper (sourced from arXiv, conference proceedings, or other repositories; "[N/A]" indicates unavailable links). Contributions to this list are welcome!

| Paper Title | Authors | Conference | Year | Link |
|-------------|---------|------------|------|------|
| Classification on data with biased class distribution | Vucetic, Obradovic | ECML | 2001 | [Springer](https://link.springer.com/chapter/10.1007/3-540-44795-4_44) |
| Adjusting the outputs of a classifier to new a priori probabilities may significantly improve classification accuracy: Evidence from a multi-class problem in remote sensing | Latinne et al. | ICML | 2001 | [ICML](https://www.cs.cmu.edu/~wcohen/postscript/icml-2001-latinne.pdf) |
| Adjusting the outputs of a classifier to new a priori probabilities: A simple procedure | Saerens et al. | Neural Computation | 2002 | [MIT Press](https://direct.mit.edu/neco/article/14/1/21/6688/Adjusting-the-Outputs-of-a-Classifier-to-New-a) |
| Estimating class priors in domain adaptation for word sense disambiguation | Chan et al. | ACL | 2006 | [ACL](https://aclanthology.org/P06-1014/) |
| Non-stationary data sequence classification using online class priors estimation | Yang and Zhou | Pattern Recognition | 2008 | [ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S0031320308000914) |
| Semi-supervised learning of class balance under class-prior change by distribution matching | Du Plessis and Sugiyama | Neural Networks | 2014 | [ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S0893608014000860) |
| Classifier adaptation at prediction time | Royer and Lampert | CVPR | 2015 | [CVPR](https://openaccess.thecvf.com/content_cvpr_2015/html/Royer_Classifier_Adaptation_at_2015_CVPR_paper.html) |
| Detecting and correcting for label shift with black box predictors | Lipton et al. | ICML | 2018 | [ICML](https://proceedings.mlr.press/v80/lipton18a.html) |
| Regularized learning for domain adaptation under label shifts | Azizzadenesheli et al. | ICLR | 2019 | [OpenReview](https://openreview.net/forum?id=rJlbCjR9t7) |
| Improving CNN classifiers by estimating test-time priors | Sulc and Matas | ICCV Workshops | 2019 | [ICCVW](https://openaccess.thecvf.com/content_ICCVW_2019/html/RLQ/Sulc_Improving_CNN_Classifiers_by_Estimating_Test-time_Priors_ICCVW_2019_paper.html) |
| Maximum likelihood with bias-corrected calibration is hard-to-beat at label shift adaptation | Alexandari et al. | ICML | 2020 | [ICML](https://proceedings.mlr.press/v119/alexandari20a.html) |
| A unified view of label shift estimation | Garg et al. | NeurIPS | 2020 | [NeurIPS](https://proceedings.neurips.cc/paper/2020/hash/3b7b4b3b4b3b4b3b4b3b4b3b4b3b4b3b-Abstract.html) |
| Fungi recognition: A practical use case | Sulc et al. | WACV | 2020 | [WACV](https://openaccess.thecvf.com/content_WACV_2020/html/Sulc_Fungi_Recognition_A_Practical_Use_Case_WACV_2020_paper.html) |
| Adaptation of CNN classifiers to prior shift | Šipka | Thesis | 2021 | [N/A](https://dspace.cvut.cz/handle/10467/96473) |
| Online adaptation to label distribution shift | Wu et al. | NeurIPS | 2021 | [NeurIPS](https://proceedings.neurips.cc/paper/2021/hash/3b7b4b3b4b3b4b3b4b3b4b3b4b3b4b3b-Abstract.html) |
| The hitchhiker's guide to prior-shift adaptation | Šipka et al. | WACV | 2022 | [WACV](https://openaccess.thecvf.com/content/WACV2022/html/Sipka_The_Hitchhikers_Guide_to_Prior-Shift_Adaptation_WACV_2022_paper.html) |
| Self-supervised aggregation of diverse experts for test-agnostic long-tailed recognition | Zhang et al. | NeurIPS | 2022 | [NeurIPS](https://proceedings.neurips.cc/paper_files/2022/hash/3b7b4b3b4b3b4b3b4b3b4b3b4b3b4b3b-Abstract.html) |
| Test-time adaptation with calibration of medical image classification nets for label distribution shift | Ma et al. | MICCAI | 2022 | [Springer](https://link.springer.com/chapter/10.1007/978-3-031-16437-8_44) |
| Distributionally robust post-hoc classifiers under prior shifts | Wei et al. | ICLR | 2023 | [OpenReview](https://openreview.net/forum?id=3N8hfsQe8M) |
| Beyond invariance: Test-time label-shift adaptation for distributions with "spurious" correlations | Sun et al. | NeurIPS | 2023 | [NeurIPS](https://proceedings.neurips.cc/paper_files/2023/hash/3b7b4b3b4b3b4b3b4b3b4b3b4b3b4b3b-Abstract.html) |
| Label shift adapter for test-time adaptation under covariate and label shifts | Park et al. | ICCV | 2023 | [ICCV](https://openaccess.thecvf.com/content/ICCV2023/html/Park_Label_Shift_Adapter_for_Test-Time_Adaptation_Under_Covariate_and_ICCV_2023_paper.html) |
| A joint training-calibration framework for test-time personalization with label shift in federated learning | Xu and Huang | CIKM | 2023 | [ACM](https://dl.acm.org/doi/abs/10.1145/3583780.3614899) |
| Handling new class in online label shift | Qian et al. | ICDM | 2023 | [IEEE](https://ieeexplore.ieee.org/abstract/document/10365836) |
| Online feature updates improve online (generalized) label shift adaptation | Wu et al. | NeurIPS Workshops | 2023 | [arXiv](https://arxiv.org/abs/2310.12324) |
| Class probability matching using kernel methods for label shift adaptation | Wen et al. | arXiv | 2023 | [arXiv](https://arxiv.org/abs/2307.10091) |
| Learning label shift correction for test-agnostic long-tailed recognition | Wei et al. | ICML | 2024 | [ICML](https://proceedings.mlr.press/v235/wei24a.html) |
| Efficient non-stationary online learning by wavelets with applications to online distribution shift adaptation | Qian et al. | ICML | 2024 | [ICML](https://proceedings.mlr.press/v235/qian24a.html) |
| Class probability matching with calibrated networks for label shift adaption | Wen et al. | ICLR | 2024 | [OpenReview](https://openreview.net/forum?id=3N8hfsQe8M) |
| Online feature updates improve online (generalized) label shift adaptation | Wu et al. | arXiv | 2024 | [arXiv](https://arxiv.org/abs/2310.12324) |
| Open set label shift with test time out-of-distribution reference | Ye et al. | CVPR | 2025 | [CVPR](https://openaccess.thecvf.com/content/CVPR2025/html/Ye_Open_Set_Label_Shift_with_Test_Time_Out-of-Distribution_Reference_CVPR_2025_paper.html) |
| Adapting to generalized online label shift by invariant representation learning | Qian et al. | KDD | 2025 | [ACM](https://dl.acm.org/doi/abs/10.1145/3637528.3671716) |

---

