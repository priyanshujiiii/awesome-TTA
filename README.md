# Awesome Test-Time Adaptation (TTA)

A curated list of **Test-Time Adaptation (TTA)** methods, papers, and resources.  
This repository accompanies our ACM Computing Surveys (CUSR) submission titled *"Awesome TTA: A Comprehensive Survey on Test-Time Adaptation Techniques"*.

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
| Test-Time Batch Adaptation     | Adapts using batches of test samples                                    |
| Test-Time Instance Adaptation  | Adapts to each test sample independently                                |
| Test-Time Prior Adaptation     | Leverages priors (e.g., class frequency) at test time                   |

---

## Detailed Descriptions and Papers

### Self-supervision
Leverages auxiliary tasks (e.g., rotation prediction, jigsaw puzzles, contrastive learning) to help the model adapt at test time.

- [Paper Title](#) – Author(s), Conference, Year

---



### Information Entropy
Reduces uncertainty in predictions by minimizing entropy or maximizing confidence.

- [Paper Title](#)

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

## How to Contribute

if you Like our work please cite our paper

```
@article{sharma2025awesome,
  title={Awesome TTA: A Comprehensive Survey on Test-Time Adaptation Techniques},
  author={Priyanshu Sharma},
  journal={ACM Computing Surveys (CUSR)},
  year={2025}
}
