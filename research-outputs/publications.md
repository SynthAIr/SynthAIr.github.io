---
layout: page
title: Publications
parent: Research Outputs
nav_order: 1
---

# Publications

Scientific publications from the SynthAIr project, including peer-reviewed conference papers and preprints.

## Preprints

### **Pre-Tactical Flight-Delay and Turnaround Forecasting with Synthetic Aviation Data**

- **Authors:** Abdulmajid Murad (SINTEF), Massimiliano Ruocco (SINTEF, NTNU)
- **Preprint:** [arXiv:2508.02294](https://arxiv.org/abs/2508.02294)
- **Date:** August 4, 2025
- **Abstract:** Access to comprehensive flight operations data remains severely restricted in aviation due to commercial sensitivity and competitive considerations, hindering the development of predictive models for operational planning. This paper investigates whether synthetic data can effectively replace real operational data for training machine learning models in pre-tactical aviation scenarios-predictions made hours to days before operations using only scheduled flight information. We evaluate four state-of-the-art synthetic data generators on three prediction tasks: aircraft turnaround time, departure delays, and arrival delays. Using a Train on Synthetic, Test on Real (TSTR) methodology on over 1.7 million European flight records, we first validate synthetic data quality through fidelity assessments, then assess both predictive performance and the preservation of operational relationships. Our results show that advanced neural network architectures, specifically transformer-based generators, can retain 94-97% of real-data predictive performance while maintaining feature importance patterns informative for operational decision-making. Our analysis reveals that even with real data, prediction accuracy is inherently limited when only scheduled information is available-establishing realistic baselines for pre-tactical forecasting. These findings suggest that high-quality synthetic data can enable broader access to aviation analytics capabilities while preserving commercial confidentiality, though stakeholders must maintain realistic expectations about pre-tactical prediction accuracy given the stochastic nature of flight operations. 
- **Keywords:** Synthetic Data, Air Traffic Management (ATM), Flight Delay Prediction, Turnaround Time, Machine Learning, Data Utility, Generative Models, Aviation Operations

## Conference Papers


### **Synthetic Aircraft Trajectory Generation Using Time-Based VQ-VAE**

- **Authors:** Abdulmajid Murad (SINTEF), Massimiliano Ruocco (SINTEF, NTNU) 
- **Conference:** [Integrated Communications, Navigation and Surveillance Conference (ICNS)](https://i-cns.org/)
- **Location:** Brussels, Belgium
- **Date:** April 8-10, 2025
- **Publisher:** IEEE
- **DOI:** [10.1109/ICNS65417.2025.10976929](https://doi.org/10.1109/ICNS65417.2025.10976929)
- **Abstract:** In modern air traffic management, generating synthetic flight trajectories has emerged as a promising solution for addressing data scarcity, protecting sensitive information, and supporting large-scale analyses. In this paper, we propose a novel method for trajectory synthesis by adapting the Time-Based Vector Quantized Variational Autoencoder (TimeVQVAE). Our approach leverages time-frequency domain processing, vector quantization, and transformer-based priors to capture both global and local dynamics in flight data. By discretizing the latent space and integrating transformer priors, the model learns long-range spatiotemporal dependencies and preserves coherence across entire flight paths. We evaluate the adapted TimeVQVAE using an extensive suite of quality, statistical, and distributional metrics, as well as a flyability assessment conducted in an open-source air traffic simulator. Results indicate that TimeVQVAE outperforms a temporal convolutional VAE baseline, generating synthetic trajectories that mirror real flight data in terms of spatial accuracy, temporal consistency, and statistical properties. Furthermore, the simulator-based assessment shows that most generated trajectories maintain operational feasibility, although occasional outliers underscore the potential need for additional domain-specific constraints. Overall, our findings underscore the importance of multi-scale representation learning for capturing complex flight behaviors and demonstrate the promise of TimeVQVAE in producing representative synthetic trajectories for downstream tasks such as model training, airspace design, and air traffic forecasting.
- **Keywords:** Aircraft trajectory, synthetic data generation, multivariate time series, machine learning in ATM


### **Synthetic Flight Data Generation Using Generative Models**

- **Authors:** Karim Aly (TUD), Alexei Sharpanskykh (TUD)
- **Conference:** [Integrated Communications, Navigation and Surveillance Conference (ICNS)](https://i-cns.org/)
- **Location:** Brussels, Belgium
- **Date:** April 8-10, 2025
- **Publisher:** IEEE
- **DOI:** [10.1109/ICNS65417.2025.10976960](https://doi.org/10.1109/ICNS65417.2025.10976960)
- **Abstract:** The increasing adoption of synthetic data in aviation research offers a promising solution to data scarcity and confidentiality challenges. This study investigates the potential of generative models to produce realistic synthetic flight data and evaluates their quality through a comprehensive four-stage assessment framework. The need for synthetic flight data arises from their potential to serve as an alternative to confidential real-world records and to augment rare events in historical datasets. These enhanced datasets can then be used to train machine learning models that predict critical events, such as flight delays, cancellations, diversions, and turnaround times. Two generative models, Tabular Variational Autoencoder (TVAE) and Gaussian Copula (GC), are adapted to generate synthetic flight information and compared based on their ability to preserve statistical similarity, fidelity, diversity, and predictive utility. Results indicate that while GC achieves higher statistical similarity and fidelity, its computational cost hinders its applicability to large datasets. In contrast, TVAE efficiently handles large datasets and enables scalable synthetic data generation. The findings demonstrate that synthetic data can support flight delay prediction models with accuracy comparable to those trained on real data. These results pave the way for leveraging synthetic flight data to enhance predictive modeling in air transportation.
- **Keywords:** Generative Artificial Intelligence, Variational Autoencoders, Gaussian Copula, Synthetic Flight Information, Synthetic Data Quality Assessment, Flight Delay Prediction, Air Traffic Management, Air Transportation Deep Learning, Statistical Modeling


### **Generation of Synthetic Aircraft Landing Trajectories Using Generative Adversarial Networks**

- **Authors:** Sebastiaan Wijnands (TUD), Alexei Sharpanskykh (TUD), Karim Aly (TUD)
- **Conference:** [SESAR Innovation Days](https://www.sesarju.eu/SIDS2024)
- **Location:** Rome, Italy
- **Date:** November 11-15, 2024
- **URL:** [2024-054](https://www.sesarju.eu/sites/default/files/documents/sid/2024/papers/SIDs_2024_paper_054%20final.pdf)
- **Abstract:** The increasing demand and complexity of air traffic management (ATM) systems necessitate significant advancements in automation to ensure safety and efficiency. Artificial intelligence (AI) and machine learning (ML) are emerging as promising solutions to manage this growing complexity, offering enhanced decision-making and predictive capabilities. However, the effectiveness of ML models in ATM heavily relies on the availability of extensive, high-quality data. In many cases, such data is scarce or incomplete, which presents a major barrier for training robust models. Synthetic data generation (SDG) is a viable solution to address this, enabling the creation of realistic datasets that unlock the ML value proposition. The Terminal Maneuvering Area (TMA) is a crucial segment of airspace characterized by high traffic density and diverse trajectory types, necessitating granular data to model these scenarios accurately. The main research objective of this work was to investigate the applicability of TimeGAN in generating synthetic 4-dimensional aircraft landing trajectories capable of capturing traffic patterns in this airspace, helping to analyze airspace constraints and delay propagation. The resulting synthetic trajectories were evaluated in terms of data diversity, fidelity and usefulness. The main challenge identified during the research was the imbalance in data classes, which affected the models' ability to accurately capture data patterns, particularly in less frequent scenarios. Generating synthetic data based on separate groupings showed promise in addressing these imbalances, although this approach was sensitive to the designation of groups. This work proves the capability of TimeGAN in generating diverse, realistic trajectories that are difficult to differentiate from real historical data.
- **Keywords:** Air traffic management, Deep generative models, Generative Adversarial Networks, Multivariate time series generation, Synthetic data quality evaluation