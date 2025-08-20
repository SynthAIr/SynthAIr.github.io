---
layout: page
title: Open Source Repositories
parent: Research Outputs
nav_order: 3
---

# Open Source Repositories

The SynthAIr project provides a comprehensive suite of open-source tools for synthetic data generation and embedding-based analytics in Air Traffic Management. Our repositories are organized by functionality and data type, offering researchers and practitioners flexible solutions for various ATM applications.

**🔗 Main GitHub Organization:** [https://github.com/SynthAIr](https://github.com/SynthAIr)


## Tabular Data Generators

### SynTabAIr
[https://github.com/SynthAIr/syntabair](https://github.com/SynthAIr/syntabair)

Generates synthetic tabular flight data from European datasets, implementing:
- CTGAN (Conditional Tabular GAN)
- TabSyn (Diffusion-based synthesis)
- REaLTabFormer (Transformer-based generation)
- Gaussian Copula methods
- Comprehensive evaluation metrics for fidelity, privacy, and utility

**License:** CC BY-SA 4.0

### SynFlyInf
[https://github.com/SynthAIr/SynFlyInf](https://github.com/SynthAIr/SynFlyInf)

Focuses on generating synthetic flight information using U.S. Bureau of Transportation Statistics data:
- TVAE (Tabular Variational Autoencoder) implementation
- Gaussian Copula approaches
- Jupyter notebook-based workflow for different use cases
- Support for flight delay, turnaround time, and diversion prediction

**License:** CC BY-SA 4.0

### Passenger Flow
[https://github.com/SynthAIr/passenger_flow](https://github.com/SynthAIr/passenger_flow)

Specialized for airport security checkpoint data generation:
- TVAE model adapted for passenger flow patterns
- Notebook-driven analysis and generation pipeline
- Pre-trained models available for immediate use
- Downstream task evaluation capabilities

**License:** MIT

## Time Series Generators

### DM_FM_Trajectories
[https://github.com/SynthAIr/DM_FM_Trajectories](https://github.com/SynthAIr/DM_FM_Trajectories)

Implements state-of-the-art generative models for aircraft trajectory synthesis, featuring:
- Multiple architectures: Diffusion models, Flow matching, and VAEs
- Transfer learning capabilities for data-scarce scenarios
- Weather integration for conditional generation
- Comprehensive evaluation framework

**License:** CC BY-SA 4.0

### TimeVQVAE_Trajectories
[https://github.com/SynthAIr/TimeVQVAE_Trajectories](https://github.com/SynthAIr/TimeVQVAE_Trajectories)

Advanced trajectory generation using vector quantization:
- Time-frequency domain processing
- Hierarchical generation for global and local patterns
- Three-stage training process
- Transformer-based priors for temporal modeling

**License:** CC BY-SA 4.0


### TimeGAN_Trajectories
[https://github.com/SynthAIr/TimeGAN_Trajectories](https://github.com/SynthAIr/TimeGAN_Trajectories)

Specialized for landing trajectory generation at terminal maneuvering areas:
- Time-series GAN architecture capturing both static and temporal features
- Optimized for approach patterns and runway-specific sequences
- K-means clustering with Dynamic Time Warping for trajectory categorization
- Three-module structure: preprocessing, model training, and evaluation

**License:** CC0-1.0

## Embedding Models

### AeroEmbed
[https://github.com/SynthAIr/AeroEmbed](https://github.com/SynthAIr/AeroEmbed)

A framework for extracting and analyzing embeddings from flight operational data using TabSyn. This repository enables:
- Extraction of meaningful representations from mixed-type flight records
- Operational pattern discovery and anomaly detection
- Clustering analysis and carrier profiling
- Comprehensive visualization tools for embedding space exploration

**License:** CC BY-SA 4.0



## Getting Started

Each repository includes:
- Detailed installation instructions using Poetry or pip
- Comprehensive documentation and usage examples
- Pre-processed datasets or data preparation scripts
- Evaluation frameworks and visualization tools
- Example notebooks demonstrating key functionalities



## Citation

When using these tools in your research, please cite the relevant SynthAIr publications/deliverables and acknowledge the specific repository used. Detailed citation information is available in each repository's README file.

## Support

For questions, issues, or collaboration opportunities:
- Open an issue in the relevant GitHub repository
- Consult the documentation within each repository
- Visit our project website at [https://synthair.github.io/](https://synthair.github.io/)

These repositories represent ongoing research in synthetic data generation for ATM. We encourage the community to explore, use, and extend these tools to advance the field of AI-driven air traffic management.



