---
layout: page
title: Generative Models
nav_order: 3
has_children: true
---

# Generative Models for Aviation Data

The SynthAIr project has developed a comprehensive suite of generative models specifically designed for Air Traffic Management (ATM) applications. Our models address two fundamental data types in aviation: **tabular flight records** and **time-series trajectory data**.


## [Tabular Data Models](/models/tabular.html)
Five complementary approaches for generating synthetic flight records:
- **REaLTabFormer**: Transformer-based autoregressive generation achieving 94-97% utility retention
- **TabSyn**: Diffusion models in latent space for efficient mixed-type synthesis  
- **CTGAN**: Conditional adversarial training optimized for rare events and imbalanced data
- **TVAE**: Variational autoencoders providing stable training with minimal computational requirements
- **Gaussian Copula**: Statistical approach offering strongest privacy protection

## [Time Series Models](/models/timeseries.html)
Specialized architectures for aircraft trajectory generation:
- **TimeVQVAE**: Time-frequency domain processing with transformer priors for global coherence
- **TCVAE with VampPrior**: Temporal convolutional networks with flexible prior distributions
- **TimeGAN**: Adversarial training preserving temporal relationships and sequential patterns
- **Flow Matching**: Continuous normalizing flows for deterministic, efficient trajectory sampling
- **Diffusion Models**: Denoising diffusion in latent space for high-fidelity spatiotemporal generation
