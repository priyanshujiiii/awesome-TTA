
# Awesome Test-Time Adaptation (TTA)

A curated list of methods, papers, and resources related to **Test-Time Adaptation (TTA)** — techniques that enable models to adapt to distribution shifts during inference without access to source data.

This repository is part of our comprehensive survey submitted to ACM CUSR.

---

## Table of Contents

- [Methods](#methods)
  - [Self-supervision](#self-supervision)
  - [Information Entropy](#information-entropy)
  - [Batch Normalization](#batch-normalization)
  - [Pseudo Labeling](#pseudo-labeling)
  - [Class Prototype](#class-prototype)
  - [Feature Alignment](#feature-alignment)
  - [Generative Modeling](#generative-modeling)
  - [Nearest Neighbors](#nearest-neighbors)
  - [Augmentation Invariance](#augmentation-invariance)
  - [Meta-learning](#meta-learning)
  - [Time-varying TTA](#time-varying-tta)

- [TTA Settings](#tta-settings)
  - [Source-Free Domain Adaptation (SFDA)](#source-free-domain-adaptation-sfda)
  - [Test-Time Batch Adaptation (TTBA)](#test-time-batch-adaptation-ttba)
  - [Test-Time Instance Adaptation (TTIA)](#test-time-instance-adaptation-ttia)
  - [Online Test-Time Adaptation (OTTA)](#online-test-time-adaptation-otta)
  - [Test-Time Prior Adaptation (TTPA)](#test-time-prior-adaptation-ttpa)

- [How to Contribute](#how-to-contribute)
- [License](#license)

---

## Methods

### Self-supervision
Leverages auxiliary tasks (e.g., rotation prediction, contrastive learning) to adapt models during test time.

- [Paper Title](#) - Author(s), Conference, Year

### Information Entropy
Minimizes prediction entropy or maximizes mutual information to increase confidence on test inputs.

- [Paper Title](#)

### Batch Normalization
Adapts batch norm statistics or fine-tunes BN layers on test data.

- [Paper Title](#)

### Pseudo Labeling
Uses confident test predictions as pseudo-labels for further optimization.

- [Paper Title](#)

### Class Prototype
Aligns test features with precomputed class-wise centroids from the source domain.

- [Paper Title](#)

### Feature Alignment
Matches source and target feature distributions using domain alignment strategies.

- [Paper Title](#)

### Generative Modeling
Utilizes generative models to synthesize source-like data or features for adaptation.

- [Paper Title](#)

### Nearest Neighbors
Applies feature-space similarity and nearest neighbor reasoning to guide test-time adaptation.

- [Paper Title](#)

### Augmentation Invariance
Enforces consistency between model predictions for different augmented views of the same test input.

- [Paper Title](#)

### Meta-learning
Trains the model to quickly adapt to test-time distributions using meta-learning principles.

- [Paper Title](#)

### Time-varying TTA
Focuses on non-stationary test-time settings and adapts models over time as data distributions evolve.

- [Paper Title](#)

---

## TTA Settings

### Source-Free Domain Adaptation (SFDA)
Assumes the source data is not available during adaptation; only a pretrained model is used.

- [Paper Title](#)

### Test-Time Batch Adaptation (TTBA)
Adapts the model using batches of test samples; may rely on batch-level statistics or inter-sample consistency.

- [Paper Title](#)

### Test-Time Instance Adaptation (TTIA)
Each test sample is adapted independently without assuming access to other test samples.

- [Paper Title](#)

### Online Test-Time Adaptation (OTTA)
Continuously adapts the model on a stream of incoming test samples.

- [Paper Title](#)

### Test-Time Prior Adaptation (TTPA)
Incorporates prior knowledge such as label distributions, class priors, or structural constraints at test time.

- [Paper Title](#)

---

## How to Contribute

You are welcome to contribute papers, code, or insights:

1. Fork the repository.
2. Add the paper to the relevant section:
   ```markdown
   - [Paper Title](https://arxiv.org/abs/xxxx.xxxxx) - Author(s), Conference, Year
