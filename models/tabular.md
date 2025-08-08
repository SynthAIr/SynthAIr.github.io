---
layout: page
title: Tabular Data Models
parent: Generative Models
nav_order: 1
---


# Tabular Data Generation

The SynthAIr project developed specialized synthetic data generators to address critical challenges in Air Traffic Management: data scarcity, privacy constraints, and commercial sensitivity. Our tabular data pipeline processes mixed-type operational data including flight schedules, delays, and turnaround times using five complementary approaches, each optimized for different data characteristics and use cases. To learn more, see our research publications: [Pre-Tactical Flight-Delay and Turnaround Forecasting with Synthetic Aviation Data](https://arxiv.org/abs/2508.02294) and [Synthetic Flight Data Generation Using Generative Models](https://doi.org/10.1109/ICNS65417.2025.10976960). Public deliverables describing the tabular data generators are currently under evaluation by the SESAR Joint Undertaking and will be made publicly available upon approval.

## Overview

Tabular synthetic data generation in aviation requires handling complex mixed-type datasets with categorical features (airlines, airports, aircraft types), continuous variables (delays, durations), and temporal information (schedules, timestamps). Our approach addresses three fundamental challenges:

- **Data Scarcity**: Limited access to comprehensive flight operations data
- **Privacy Protection**: Commercial sensitivity of operational records
- **Operational Diversity**: Wide range of flight scenarios and conditions

We evaluate generators using the **Train on Synthetic, Test on Real (TSTR)** methodology across three critical prediction tasks: departure delays, arrival delays, and aircraft turnaround times.

<div align="center">
  <img src="../figures/tabular_roadmap.svg" />
  <br>
  <em><strong>Figure 1: Tabular Data Generation Pipeline.</strong> From EU flight operations data (OAG), our AI models generate synthetic flight records validated across three dimensions: privacy protection (Distance to Closest Record), statistical fidelity (correlation preservation, distribution similarity), and utility (performance in downstream prediction tasks).</em>
</div>

## Model Architectures

### REaLTabFormer (Transformer-based)

**REaLTabFormer** leverages transformer architectures to generate synthetic tabular data by treating each flight record as a sequence of tokens. This autoregressive approach captures complex dependencies between features through sequential generation.

**Key Features:**
- GPT-2 based architecture with 6 transformer decoder layers
- Row-wise, token-by-token generation preserving feature relationships
- Target masking regularization prevents data memorization
- Overfitting detection using Q_δ statistic and Distance to Closest Record (DCR)
- **Performance**: Achieves 94-97% of real-data predictive performance

<div align="center">
  <img src="../figures/rtf.svg" />
  <br>
  <em><strong>Figure 2: REaLTabFormer Architecture.</strong> Transformer-based autoregressive model treating tabular data as token sequences with specialized regularization and overfitting detection mechanisms.</em>
</div>

### TabSyn (Diffusion-based)

**TabSyn** employs a two-stage pipeline combining Variational Autoencoders with diffusion models in latent space, enabling efficient high-quality synthesis of mixed-type tabular data.

**Key Features:**
- "Encode → Diffuse → Decode" architecture operating in continuous latent space
- VAE encoder transforms mixed-type data into continuous representations
- Score-based diffusion with linear noise schedule (20-50 sampling steps)
- Adaptive β-VAE training with dynamic KL-divergence scheduling
- **Performance**: Strong fidelity with efficient sampling

<div align="center">
  <img src="../figures/tabsyn.svg" />
  <br>
  <em><strong>Figure 3: TabSyn Architecture.</strong> Two-stage pipeline with VAE encoding to continuous latent space followed by efficient diffusion-based generation.</em>
</div>

### CTGAN (Conditional Adversarial)

**Conditional Tabular GAN (CTGAN)** addresses aviation data's mixed-type nature through specialized preprocessing and conditional generation capabilities, particularly effective for handling imbalanced categorical distributions.

**Key Features:**
- Mode-specific normalization using Bayesian Gaussian Mixture Models
- Conditional generation with training-by-sampling for rare categories
- WGAN-GP loss with gradient penalty for stable adversarial training
- PacGAN framework processing 10 samples jointly to prevent mode collapse
- **Performance**: Effective for targeted scenario generation

<div align="center">
  <img src="../figures/ctgan.svg" />
  <br>
  <em><strong>Figure 4: CTGAN Architecture.</strong> Adversarial framework with specialized preprocessing for mixed-type data and conditional generation capabilities.</em>
</div>

### TVAE (Variational Autoencoder)

**Tabular Variational Autoencoder (TVAE)** provides a probabilistic approach to synthetic data generation with lightweight computational requirements and stable training characteristics.

**Key Features:**
- Evidence Lower Bound (ELBO) optimization
- Reparameterization trick for differentiable latent sampling  
- Batch normalization and L2 regularization
- Minimal GPU requirements with fast training
- **Performance**: Good utility-to-compute ratio

### Gaussian Copula (Statistical)

**Gaussian Copula** represents a classical statistical approach that models dependencies by separating marginal distributions from their correlation structure.

**Key Features:**
- Kernel Density Estimation for marginal distribution modeling
- Multivariate Gaussian copula for dependency structure
- No neural network training required
- Strongest privacy protection among all models
- **Performance**: Best for privacy-critical applications

## Evaluation Framework

Our comprehensive evaluation spans five dimensions ensuring synthetic data maintains essential properties for aviation operations:

### Fidelity Assessment
- **Statistical Similarity**: Kolmogorov-Smirnov tests for continuous distributions, Chi-squared for categorical
- **Correlation Preservation**: Pearson, Spearman, Kendall correlations plus mixed-type measures
- **Joint Distribution Fidelity**: KL-divergence for multivariate distributional alignment
- **Likelihood-based Assessment**: Bayesian Network and Gaussian Mixture Model likelihood
- **Detection Difficulty**: Logistic regression classifier performance (synthetic vs. real)

### Utility Evaluation
- **Predictive Performance**: RMSE, MAE, R² metrics across prediction tasks
- **Feature Importance Alignment**: Cosine similarity of feature importance vectors
- **Utility Scores**: Normalized performance ratios quantifying synthetic-to-real substitutability

## Performance Results

### Model Comparison

| Model | Utility Score | Key Strengths | Best Use Case |
|-------|---------------|---------------|---------------|
| **REaLTabFormer** | 94-97% | Highest fidelity, feature preservation | High-stakes predictions |
| **TabSyn** | 64-93% | Complex correlations, fast sampling | Large-scale data augmentation |
| **CTGAN** | 60-74% | Conditional generation, rare events | Targeted scenario modeling |
| **TVAE** | 55-70% | Stable training, lightweight | Rapid prototyping |
| **Gaussian Copula** | 42-56% | Strong privacy, no training needed | External data sharing |

### Prediction Task Results

**Turnaround Time Prediction** (Highest Predictability: R² ≤ 0.44)
- Most deterministic aviation process
- REaLTabFormer achieves 97% utility retention
- Strong feature alignment across all advanced models

**Departure Delay Prediction** (Moderate Predictability: R² ≤ 0.30)
- Temporal patterns dominate (scheduled hour most important)
- REaLTabFormer maintains 96% performance
- Complex interaction modeling crucial

**Arrival Delay Prediction** (Lowest Predictability: R² ≤ 0.30)
- Most challenging due to cumulative uncertainties
- REaLTabFormer achieves 95% utility retention
- Requires sophisticated dependency modeling

## Selection Guidelines


**For High-Fidelity Simulation**: Deploy REaLTabFormer or TabSyn when prediction accuracy and feature relationship preservation are critical.

**For Large-Scale Augmentation**: Choose TVAE for rapid dataset expansion with moderate utility requirements.

**For Conditional Generation**: Apply CTGAN when generating specific flight scenarios or handling rare operational events.

## Technical Implementation

All models are available as open-source implementations:
- **GitHub Repository**: [github.com/SynthAIr/syntabair](https://github.com/SynthAIr/syntabair)
- **Datasets**: EU flight operations (1.7M+ records), BTS domestic flights
- **Evaluation Framework**: Comprehensive fidelity and utility assessment tools
