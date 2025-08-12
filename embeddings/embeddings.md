---
layout: page
title: Embedding Framework
nav_order: 4
has_children: true
---

# Embedding Framework for Air Traffic Management

This framework presents general-purpose embeddings extracted from Air Traffic Management (ATM) data, leveraging latent representations learned during synthetic data generation. These embeddings transform both flight records and trajectories into compact vector representations that capture operational patterns, temporal dynamics, and statistical relationships. Open-source implementations are available in our [embedding repositories](/repositories/repositories.html#embedding-models). Public deliverables describing the embedding framework are available as part of the SynthAIr project documentation.

## Overview

The embedding framework consists of four specialized models that transform different types of ATM data into meaningful vector representations. These models provide complementary approaches to embedding generation, each optimized for specific data types and analytical requirements.

### Embedding Types

The framework addresses two primary data modalities in Air Traffic Management:

#### [Tabular Data Embeddings](tabular.html)
Specialized embeddings for flight operational data including delays, turnaround times, carrier information, and aircraft specifications:

- **TabSyn**: VAE-based embeddings focusing on global pattern recognition across flight attributes
- **REaLTabFormer**: Transformer-based embeddings capturing sequential dependencies and contextual patterns

#### [Time Series Embeddings](timeseries.html)
Advanced embeddings for flight trajectories and temporal sequences:

- **TCVAE**: Temporal convolutional embeddings using dilated causal convolutions for multi-scale temporal dependencies
- **Latent Flow Matching**: Transfer learning-enabled embeddings for cross-airport model adaptation

## Key Applications

### Operational Analysis
- **Pattern Discovery**: Identify common operational signatures across carriers, routes, and airports
- **Anomaly Detection**: Detect unusual flights and operational conditions through embedding space analysis
- **Clustering**: Group similar flight patterns for operational insights and procedure validation

### Simulation and Modeling
- **Core-Set Extraction**: Select representative trajectories that capture essential patterns for efficient simulation
- **Transfer Learning**: Apply models trained on data-rich airports to airports with limited datasets
- **Synthetic Data Generation**: Use embeddings to guide generation of realistic synthetic flight data

### Performance Optimization
- **Computational Efficiency**: Reduced dimensional representations accelerate downstream analyses
- **Memory Efficiency**: Compact embeddings enable analysis of large-scale flight datasets
- **Scalability**: Framework supports analysis across multiple airports and operational contexts

## Getting Started

Explore the detailed documentation for each embedding type:

1. **[Tabular Data Embeddings](tabular.html)** - Learn about TabSyn and REaLTabFormer embeddings for flight operational data
2. **[Time Series Embeddings](timeseries.html)** - Discover TCVAE and Latent Flow Matching for trajectory analysis

Each section includes comprehensive examples, visualization results, and practical applications demonstrating the effectiveness of these embedding approaches for Air Traffic Management analytics.
