---
layout: home
title: Home
nav_order: 1
---

# Transforming ATM Through AI-Powered Synthetic Data Generation

**SynthAIr** advances Air Traffic Management (ATM) automation through AI methods for synthetic data generation. This EU-funded research initiative (SESAR 3 Joint Undertaking, grant No 101114847) addresses critical challenges of data scarcity, privacy constraints, and operational complexity by delivering **9 generative models** validated across **6 operational use cases** spanning the complete flight lifecycle.

<div align="center">
  <img src="figures/concept_image.png" />
  <br>
  <em><strong>Figure 1: SynthAIr Concept - AI Models for ATM Data Generation</strong></em>
</div>

## Research Challenge & Innovation

The aviation industry faces persistent barriers in developing AI systems due to:
- **Data Scarcity**: Limited access to comprehensive operational datasets
- **Privacy Constraints**: Commercial sensitivity preventing data sharing
- **Operational Complexity**: Diverse stakeholder requirements and safety-critical environments
- **Regulatory Barriers**: Strict compliance requirements limiting data availability

SynthAIr addresses this challenge by creating **synthetic datasets that preserve statistical properties and operational relationships** of real ATM data while enabling unrestricted access for research and development.

## Validated Use Cases

The six use cases demonstrate synthetic data generation capabilities across critical ATM operational scenarios:

<div align="center">
  <img src="figures/use_cases.svg" />
  <br>
  <em><strong>Figure 2: SynthAIr Use Cases Across the Flight Timeline</strong><br>
  Six operational scenarios spanning the complete flight lifecycle from turnaround to turnaround. The diagram illustrates temporal relationships between flight phases (Off-Block Time ✈️, Take-off Time 🛫, Landing Time 🛬, In-Block Time 🏁) and how synthetic data generation addresses specific operational challenges. Each use case connects to critical decision points: UC6 (Scheduling) spans the entire timeline for strategic planning, UC3 (Passenger Flow) occurs during ground operations, UC2 (Delay Prediction) targets departure and arrival phases, UC4 (Trajectory Generation) covers en-route flight, UC5 (Flight Diversion) handles contingency scenarios, and UC1 (Turnaround Time) optimizes ground operations between flights. The interconnected arrows demonstrate data dependencies and operational impact propagation across phases.</em>
</div>

**UC1 - Turnaround Time Optimization**: Generates synthetic ground operations data to optimize aircraft servicing, boarding, and preparation processes between flights.

**UC2 - Flight Delay Prediction**: Creates synthetic flight operational datasets for both departure and arrival delay forecasting.

**UC3 - Passenger Flow Management**: Synthesizes passenger movement and terminal capacity data for airport infrastructure planning. 

**UC4 - Traffic Generation**: Produces realistic synthetic aircraft trajectory datasets for airspace scenario simulation. Generates flight paths that maintain spatial-temporal relationships, and altitude profiles to support air traffic management system testing and validation.

**UC5 - Flight Diversion Prediction**: Creates synthetic datasets for alternative routing and contingency planning scenarios. 

**UC6 - Schedule Optimization**: Generates synthetic scheduling datasets spanning strategic flight planning and resource allocation.

## Model Portfolio

### Tabular Data Models (5 Architectures)
Specialized for flight operational records and mixed-type data:

- **REaLTabFormer**: Transformer-based autoregressive generation
- **TabSyn**: Diffusion models in latent space for efficient mixed-type synthesis
- **CTGAN**: Conditional adversarial training optimized for rare events and imbalanced data
- **TVAE**: Variational autoencoders providing stable training with minimal computational requirements
- **Gaussian Copula**: Statistical approach offering strongest privacy protection

### Time Series Models (4 Architectures)
Specialized architectures for aircraft trajectory generation:

- **TimeVQVAE**: Time-frequency domain processing with transformer priors for global coherence
- **TCVAE with VampPrior**: Temporal convolutional networks with flexible prior distributions  
- **TimeGAN**: Adversarial training preserving temporal relationships and sequential patterns
- **Flow Matching & Diffusion Models**: Continuous normalizing flows and denoising diffusion for spatiotemporal generation


## Applications

SynthAIr enables ATM stakeholders to:

✈️ **Develop AI systems** without accessing sensitive operational data  
🔒 **Preserve competitive advantages** while enabling collaborative research  
🎯 **Test rare scenarios** safely through synthetic event generation  
📊 **Share standardized datasets** across organizations and borders  
🚀 **Accelerate research** through publicly available synthetic datasets  
🌍 **Scale solutions globally** via transfer learning capabilities  

## Consortium

<div align="center">
  <div style="display: inline-block; width: 24%; text-align: center;">
    <img src="figures/sintef_logo.png" alt="SINTEF Logo" style="width: 80%; vertical-align: middle;">
    <br><small><strong>SINTEF</strong><br>AI & Machine Learning</small>
  </div>
  <div style="display: inline-block; width: 24%; text-align: center;">
    <img src="figures/tud_logo.png" alt="TU Delft Logo" style="width: 50%; vertical-align: middle;">
    <br><small><strong>TU Delft</strong><br>Aviation Engineering</small>
  </div>
  <div style="display: inline-block; width: 24%; text-align: center;">
    <img src="figures/eurocontrol_logo.png" alt="EuroControl Logo" style="width: 40%; vertical-align: middle;">
    <br><small><strong>EUROCONTROL</strong><br>ATM Operations</small>
  </div>
  <div style="display: inline-block; width: 24%; text-align: center;">
    <img src="figures/deepblue_logo.jpg" alt="DeepBlue Logo" style="width: 80%; vertical-align: middle;">
    <br><small><strong>Deep Blue</strong><br>Data Science</small>
  </div>
</div>

**Bringing together expertise** in artificial intelligence (SINTEF), aviation systems (TU Delft), operational air traffic management (EUROCONTROL), and data analytics (Deep Blue).

---

<div align="center">
<em>Funded by the SESAR 3 Joint Undertaking under the European Union's Horizon 2020 research and innovation programme (Grant No 101114847)</em>
</div>
