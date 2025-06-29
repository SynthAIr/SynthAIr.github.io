---
layout: home
title: Home
nav_order: 1
---

# Transforming ATM Through AI-Powered Synthetic Data Generation

SynthAIr advances Air Traffic Management (ATM) automation by developing  AI methods for synthetic data generation. Addressing critical challenges of data scarcity, privacy constraints, and operational complexity, this project delivers **9 generative models** validated across **6 operational use cases**.

## Project Overview

The aviation industry faces persistent challenges in accessing data for developing and validating AI systems. SynthAIr bridges this gap by creating synthetic datasets that preserve the statistical properties and operational relationships of real ATM data.

<div align="center">
  <img src="figures/u1.svg" />
  <br>
  <em><strong>Figure 1: SynthAIr Use Cases Across the Flight Timeline.</strong> Six operational use cases span the complete flight lifecycle, from passenger flow prediction (UC3) through scheduling (UC6), departure delays (UC2), trajectory generation (UC4), diversion prediction (UC5), arrival delays (UC2), and turnaround time optimization (UC1).</em>
</div>

## Technical Innovation

### Tabular Data Generation
Our tabular data pipeline addresses mixed-type operational data including flight schedules, delays, and turnaround times. We implemented five complementary approaches each optimized for different data characteristics.

<div align="center">
  <img src="figures/tabular_roadmap.svg" />
  <br>
  <em><strong>Figure 2: Tabular Data Generation Pipeline.</strong> From EU flight operations data (OAG), our AI models generate synthetic flight records validated across three dimensions: privacy protection (Distance to Closest Record), statistical fidelity (correlation preservation, distribution similarity), and utility (performance in downstream prediction tasks).</em>
</div>

### Time Series Generation
For trajectory data, we developed specialized models that capture the complex spatiotemporal dynamics of aircraft movements. Our models handle both terminal area operations and complete end-to-end flights.

<div align="center">
  <img src="figures/timeseries_roadmap.svg" />
  <br>
  <em><strong>Figure 3: Time Series Generation Pipeline.</strong> Aircraft trajectory data from OpenSky Network and EUROCONTROL, enriched with weather context (ERA5, METAR), feeds into five generative models (TCVAE, TimeVQVAE, TimeGAN, Flow Matching, Diffusion Models) producing synthetic trajectories validated for fidelity, diversity, and domain-specific flyability.</em>
</div>

## Key Achievements

- **Embedding Framework:** Beyond synthetic data generation, our models provide powerful embeddings for operational pattern discovery, anomaly detection, and transfer learning between airports
- **Validated Performance:** Synthetic data matches real data performance across critical metrics, with R² scores within 2-5% for prediction tasks
- **Open Science:** **6 public repositories** containing implementation code, pre-trained models, and comprehensive documentation

## Impact & Applications

SynthAIr enables ATM stakeholders to:
- **Develop AI systems** without accessing sensitive operational data
- **Test scenarios** that are rare or dangerous in real operations
- **Share data** across organizations while preserving competitive advantages
- **Accelerate research** through publicly available synthetic datasets

## Consortium

This project brings together expertise in AI (SINTEF), aviation (TUD and EuroControl), and data science (DeepBlue), funded by SESAR Joint Undertaking under the European Union's Horizon 2020 research and innovation programme.

<div align="center">
  <div style="display: inline-block; width: 24%; text-align: center;">
    <img src="figures/sintef_logo.png" alt="SINTEF Logo" style="width: 80%; vertical-align: middle;">
  </div>
  <div style="display: inline-block; width: 24%; text-align: center;">
    <img src="figures/tud_logo.png" alt="TU Delft Logo" style="width: 50%; vertical-align: middle;">
  </div>
  <div style="display: inline-block; width: 24%; text-align: center;">
    <img src="figures/eurocontrol_logo.png" alt="EuroControl Logo" style="width: 40%; vertical-align: middle;">
  </div>
  <div style="display: inline-block; width: 24%; text-align: center;">
    <img src="figures/deepblue_logo.jpg" alt="DeepBlue Logo" style="width: 80%; vertical-align: middle;">
  </div>
</div>
