# Awesome Test-Time Adaptation (TTA)

A curated list of methods, papers, and resources related to **Test-Time Adaptation (TTA)** — techniques that enable models to adapt to distribution shifts during inference, without requiring access to source data.

This repository is part of the comprehensive survey submitted to ACM Computing Surveys (CUSR).

---

## Table of Contents

- [Adaptation Techniques](#adaptation-techniques)
- [How to Contribute](#how-to-contribute)
- [License](#license)
- [Citation](#citation)

---

## Adaptation Techniques

Below is a list of core adaptation techniques studied in the literature. Many methods fall under multiple overlapping paradigms (e.g., self-supervised + batch-wise + entropy minimization). We've grouped them by the **primary idea or mechanism** for clarity.

---

### Self-supervision
Leverages auxiliary tasks like rotation prediction, jigsaw puzzles, or contrastive learning to adapt the model at test time.

- [Paper Title](#) – Author(s), Conference, Year

---

### Information Entropy Minimization
Reduces prediction uncertainty by minimizing entropy or maximizing mutual information during test-time optimization.

- [Paper Title](#)

---

### Batch Normalization Adaptation
Updates batch norm statistics or affine parameters using test data batches.

- [Paper Title](#)

---

### Pseudo Labeling
Assigns pseudo-labels to confident predictions and uses them for further adaptation.

- [Paper Title](#)

---

### Class Prototypes
Aligns test features to stored or evolving class centroids computed from source or target data.

- [Paper Title](#)

---

### Feature Alignment
Matches test-time feature distributions to source-like representations using domain alignment techniques.

- [Paper Title](#)

---

### Generative Modeling
Uses generative models (e.g., GANs, VAEs, diffusion) to reconstruct or translate test samples for alignment or enhancement.

- [Paper Title](#)

---

### Nearest Neighbors
Employs K-NN-based decision boundaries or neighborhood consistency in feature space for adaptation.

- [Paper Title](#)

---

### Augmentation Invariance
Enforces consistency across augmented views of the same input (feature-level or prediction-level).

- [Paper Title](#)

---

### Meta-learning for TTA
Uses meta-training to prepare models for fast adaptation to distribution shifts at inference.

- [Paper Title](#)

---

### Time-varying / Online Adaptation
Adapts models continuously using streaming or evolving test distributions.

- [Paper Title](#)

---

### Source-Free Domain Adaptation (SFDA)
Performs domain adaptation without access to source data; only the pretrained model is available at test time.

- [Paper Title](#)

---

### Test-Time Batch vs. Instance Adaptation
- **Batch Adaptation (TTBA)**: Uses mini-batches of test samples for collective adaptation.
- **Instance Adaptation (TTIA)**: Performs sample-wise adaptation independently.

- [Paper Title](#)

---

### Prior-based Adaptation
Incorporates priors (e.g., class frequency, marginal label distribution) into test-time objectives.

- [Paper Title](#)

---

## How to Contribute

1. Fork the repository.
2. Add a paper entry under the relevant section:

   ```markdown
   - [Paper Title](https://arxiv.org/abs/xxxx.xxxxx) – Author(s), Conference, Year
