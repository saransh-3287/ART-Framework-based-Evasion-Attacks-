# Evasion Attacks on Image Classification Models using ART

## Project Overview

This project implements and evaluates multiple adversarial evasion attacks on image classification models trained on:

- MNIST (grayscale digit classification)
- CIFAR-10 (natural object classification)

The attacks are implemented using the **Adversarial Robustness Toolbox (ART)**.

The objective is to study the vulnerability of different neural network architectures under adversarial perturbations.

---

## Models Evaluated

The following models were trained and attacked:

1. **2-Layer Fully Connected Network (MLP)**
2. **6-Layer Convolutional Neural Network (ConvNet)**
3. **Pretrained VGG-19 (fine-tuned on CIFAR-10)**

All models were implemented using PyTorch and wrapped using ART’s `PyTorchClassifier`.

---

## Evasion Attacks Implemented

The following attack methods were evaluated:

### 1. Random Noise Attack
- Uniform random perturbation added
- 5 random values of epsilon in range [0.001, 0.1]

### 2. FGSM (Fast Gradient Sign Method)
- ℓ∞ bounded attack
- Single-step gradient-based perturbation

### 3. PGD (Projected Gradient Descent) – ℓ∞
- Iterative gradient attack
- 5 random values of epsilon and alpha in [0.001, 0.1]

### 4. Targeted PGD (ℓ∞)
- Forces prediction toward a chosen incorrect class

### 5. PGD (ℓ2)
- ℓ2 norm bounded iterative attack

---

## Experimental Setup

- Dataset size for evaluation: 500 test samples per experiment
- Epsilon range: [0.001, 0.1]
- Alpha range: [0.001, 0.1]
- Number of PGD iterations: 40

