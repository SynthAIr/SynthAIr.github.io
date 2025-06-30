---
layout: page
title: Publications & Deliverables
nav_order: 7
---

# Publications & Deliverables

The research and development in the SynthAIr project are disseminated through peer-reviewed publications, public deliverables, and open-access datasets. This page provides a comprehensive list of our contributions to the field of AI-driven air traffic management.

## Conference Papers


### **Synthetic Aircraft Trajectory Generation Using Time-Based VQ-VAE**

- **Authors:** Abdulmajid Murad (SINTEF), Massimiliano Ruocco (SINTEF, NTNU) 
- **Conference:** Integrated Communications, Navigation and Surveillance Conference (ICNS)
- **Location:** Brussels, Belgium
- **Date:** April 8-10, 2025
- **Publisher:** IEEE
- **DOI:** [10.1109/ICNS65417.2025.10976929](https://doi.org/10.1109/ICNS65417.2025.10976929)
- **Abstract:** In modern air traffic management, generating synthetic flight trajectories has emerged as a promising solution for addressing data scarcity, protecting sensitive information, and supporting large-scale analyses. In this paper, we propose a novel method for trajectory synthesis by adapting the Time-Based Vector Quantized Variational Autoencoder (TimeVQVAE). Our approach leverages time-frequency domain processing, vector quantization, and transformer-based priors to capture both global and local dynamics in flight data. By discretizing the latent space and integrating transformer priors, the model learns long-range spatiotemporal dependencies and preserves coherence across entire flight paths. We evaluate the adapted TimeVQVAE using an extensive suite of quality, statistical, and distributional metrics, as well as a flyability assessment conducted in an open-source air traffic simulator. Results indicate that TimeVQVAE outperforms a temporal convolutional VAE baseline, generating synthetic trajectories that mirror real flight data in terms of spatial accuracy, temporal consistency, and statistical properties. Furthermore, the simulator-based assessment shows that most generated trajectories maintain operational feasibility, although occasional outliers underscore the potential need for additional domain-specific constraints. Overall, our findings underscore the importance of multi-scale representation learning for capturing complex flight behaviors and demonstrate the promise of TimeVQVAE in producing representative synthetic trajectories for downstream tasks such as model training, airspace design, and air traffic forecasting.
- **Keywords:** Aircraft trajectory, synthetic data generation, multivariate time series, machine learning in ATM


### **Synthetic Flight Data Generation Using Generative Models**

- **Authors:** Karim Aly (TUD), Alexei Sharpanskykh (TUD)
- **Conference:** Integrated Communications, Navigation and Surveillance Conference (ICNS)
- **Location:** Brussels, Belgium
- **Date:** April 8-10, 2025
- **Publisher:** IEEE
- **DOI:** [10.1109/ICNS65417.2025.10976960](https://doi.org/10.1109/ICNS65417.2025.10976960)
- **Abstract:** The increasing adoption of synthetic data in aviation research offers a promising solution to data scarcity and confidentiality challenges. This study investigates the potential of generative models to produce realistic synthetic flight data and evaluates their quality through a comprehensive four-stage assessment framework. The need for synthetic flight data arises from their potential to serve as an alternative to confidential real-world records and to augment rare events in historical datasets. These enhanced datasets can then be used to train machine learning models that predict critical events, such as flight delays, cancellations, diversions, and turnaround times. Two generative models, Tabular Variational Autoencoder (TVAE) and Gaussian Copula (GC), are adapted to generate synthetic flight information and compared based on their ability to preserve statistical similarity, fidelity, diversity, and predictive utility. Results indicate that while GC achieves higher statistical similarity and fidelity, its computational cost hinders its applicability to large datasets. In contrast, TVAE efficiently handles large datasets and enables scalable synthetic data generation. The findings demonstrate that synthetic data can support flight delay prediction models with accuracy comparable to those trained on real data. These results pave the way for leveraging synthetic flight data to enhance predictive modeling in air transportation.
- **Keywords:** Generative Artificial Intelligence, Variational Autoencoders, Gaussian Copula, Synthetic Flight Information, Synthetic Data Quality Assessment, Flight Delay Prediction, Air Traffic Management, Air Transportation Deep Learning, Statistical Modeling



