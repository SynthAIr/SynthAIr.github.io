---
layout: page
title: Publications & Deliverables
nav_order: 7
---

# Publications & Deliverables

The research and development in the SynthAIr project are disseminated through peer-reviewed publications, public deliverables, and open-access datasets. This page provides a comprehensive list of our contributions to the field of AI-driven air traffic management.


**Note:** *SynthAIr is an ongoing research project. Several deliverables and scientific publications are currently under internal review, including many under evaluation by the SESAR Joint Undertaking. These materials will be made publicly available upon approval and finalization. Please check back regularly for updates.*


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
- **Abstract:** The increasing demand and complexity of air traffic management (ATM) systems necessitate significant advancements in automation to ensure safety and efficiency. Artificial intelligence (AI) and machine learning (ML) are emerging as promising solutions to manage this growing complexity, offering enhanced decision-making and predictive capabilities. However, the effectiveness of ML models in ATM heavily relies on the availability of extensive, high-quality data. In many cases, such data is scarce or incomplete, which presents a major barrier for training robust models. Synthetic data generation (SDG) is a viable solution to address this, enabling the creation of realistic datasets that unlock the ML value proposition. The Terminal Maneuvering Area (TMA) is a crucial segment of airspace characterized by high traffic density and diverse trajectory types, necessitating granular data to model these scenarios accurately. The main research objective of this work was to investigate the applicability of TimeGAN in generating synthetic 4-dimensional aircraft landing trajectories capable of capturing traffic patterns in this airspace, helping to analyze airspace constraints and delay propagation. The resulting synthetic trajectories were evaluated in terms of data diversity, fidelity and usefulness. The main challenge identified during the research was the imbalance in data classes, which affected the models’ ability to accurately capture data patterns, particularly in less frequent scenarios. Generating synthetic data based on separate groupings showed promise in addressing these imbalances, although this approach was sensitive to the designation of groups. This work proves the capability of TimeGAN in generating diverse, realistic trajectories that are difficult to differentiate from real historical data.
- **Keywords:** Air traffic management, Deep generative models, Generative Adversarial Networks, Multivariate time series generation, Synthetic data quality evaluation

## Public Deliverables

### **D1.1 - Concept outline**

- **Authors:** SINTEF
- **Date:** January 23, 2024
- **DOI:** [10.5281/zenodo.13935203](https://doi.org/10.5281/zenodo.13935203)
<!-- - **License:** [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) -->
- **Abstract:**  This deliverable describes the concept outline of the SynthAIr project. The main objective of SynthAIr is to explore and define AI-based methods for synthetic data generation in the domain of ATM systems due to the limitation of AI-based tools development caused by the lack of sufficient data (e.g., safety-related data) and the challenge of generalizing those AI-based models. The project investigates data-driven methods for synthetic data generation because they require 1) less user knowledge expertise (i.e., no need to derive the explicit model of the distribution) and 2) better generalization capabilities. More specifically, inspired by recent advances in computer vision and language technology, SynthAIr proposes the concept of a Universal Time Series Generator (UTG). A UTG is a model trained on several different time series and capable of generating a synthetic dataset representing a new dataset, simply conditioned by a compressed representation of it. In the aviation domain, this generator can be trained on data related to a few airports and then used to generate synthetic data for a new airport. The same principle can be applied to define a Universal Time Series Forecaster (UTF), which is capable of making predictions in a new environment (i.e., data from a new airport) without any additional training.

### **D2.1 - State of the art**

- **Authors:** TUD, SINTEF, DEEPBLUE, EUROCONTROL
- **Date:** May 14, 2024
- **DOI:** [10.5281/zenodo.13935162](https://doi.org/10.5281/zenodo.13935162)
<!-- - **License:** [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) -->
- **Abstract:** This deliverable discusses the state-of-the-art related to the use cases considered in the project, as well as relevant synthetic data modelling techniques to be used for elaboration of use cases. Based on multiple data-, modelling-, and stakeholder-related criteria, two promising use cases were selected for further elaboration in the project. The literature review serves as a starting point for the activities in WP3 (Synthetic Data Generation for Multivariate Time Series for ATM-automation) and WP4 (Universal Time Series Model for Prediction and Data Generation for ATM-automation), based on the selected use cases.

### **D2.2 - Definition of Use Cases**

- **Authors:** TUD, SINTEF, DEEPBLUE, EUROCONTROL
- **Date:** 22 January 2025
- **CORDIS Link:** [Download](https://ec.europa.eu/research/participants/documents/downloadPublic?documentIds=080166e51793f649&appId=PPGMS)
- **Abstract:** This deliverable discusses the definition of the different use cases proposed in the SynthAIr project. Starting from the definition of the downstream problems, the existing models in the literature and the relevance of each use case to aviation stakeholders to the evolution of the use cases within the life of the project. Based on feasibility and relevance, the use cases were then sorted into a priority list to formulate a starting point for WP3 (Synthetic Data Generation for Multivariate Time Series for ATM-automation).

### **D3.1 - Initial Synthetic Data Generation ML Models #1**

- **Authors:** SINTEF, TUD, DEEPBLUE, EUROCONTROL
- **Date:** 08 October 2024
- **CORDIS Link:** [Download](https://ec.europa.eu/research/participants/documents/downloadPublic?documentIds=080166e5131831cc&appId=PPGMS)
- **Abstract:** This deliverable presents the initial machine learning models developed for synthetic data generation as part of the SynthAIr project. It introduces four advanced AI methods designed to generate synthetic multivariate time series data in the context of Air Traffic Management (ATM). The document outlines the methodology, model architectures, and a comprehensive evaluation framework. Preliminary results showcase the models' potential to generate realistic ATM data, particularly aircraft trajectories, while also identifying key challenges and limitations. A guide to the open-source code is included to promote reproducibility and support further development within the ATM research community.

### **D3.2 - Synthetic ATM Dataset**

- **Authors:** SINTEF, TUD, DEEPBLUE, EUROCONTROL
- **Date:** 08 October 2024
- **CORDIS Link:** [Download](https://ec.europa.eu/research/participants/documents/downloadPublic?documentIds=080166e513184d8c&appId=PPGMS)
- **Abstract:** This deliverable presents the synthetic Air Traffic Management (ATM) datasets generated as part of the SynthAIr project. It focuses on datasets created using the initial machine learning models outlined in deliverable D3.1. These datasets offer a high-fidelity representation of aircraft trajectory characteristics, realistic variability, and class-conditional generation. The document provides detailed information on the datasets' characteristics, including key variables, distributions, and spatial-temporal coverage. It also includes a user guide for accessing and utilizing the open-source data, along with a summary of known limitations. By providing diverse, high-fidelity synthetic data that is easily accessible, this deliverable supports ongoing ATM research and development, in alignment with SynthAIr's objectives to advance ATM automation and simulation capabilities.

### **D4.1- Initial General Time Series Embeddings ML Model**

- **Authors:** SINTEF, TUD, DEEPBLUE, EUROCONTROL
- **Date:** 22 November 2024
- **CORDIS Link:** [Download](https://ec.europa.eu/research/participants/documents/downloadPublic?documentIds=080166e5151fe59c&appId=PPGMS)
- **Abstract:** This deliverable presents the initial development of general time series embeddings for ATM data. It demonstrates how the rich latent representations learned by variational autoencoder models can serve as general-purpose time series embeddings without requiring additional model development. The document outlines an evaluation framework for assessing embedding quality and presents initial
results focusing on trajectory clustering and visualization. While these results are promising, we also identify areas for future enhancement. This work lays the groundwork for developing more refined embedding models in subsequent deliverables, ultimately contributing to enhanced ATM automation and simulation capabilities through improved data representations.


### **D5.1: Exploratory Research Plan (ERP) – Initial**

- **Authors:** DEEPBLUE, TUD, SINTEF, EUROCONTROL
- **Date:** 30 October 2024
- **CORDIS Link:** [Download](https://ec.europa.eu/research/participants/documents/downloadPublic?documentIds=080166e514083263&appId=PPGMS)
- **Abstract:** This document is the initial version of the SynthAIr Exploratory Research Plan (ERP). It describes the Exploratory research plan which will guide the preparation and execution of the validation exercises of the SynthAIr solution for TRL1 (Basic Technology Research / Research to Prove Feasibility).

### **D6.1 - Communication, Dissemination and Exploitation Plan**

- **Authors:** DEEPBLUE
- **Date:** July 04, 2024
- **DOI:** [10.5281/zenodo.13935230](https://doi.org/10.5281/zenodo.13935230)
<!-- - **License:** [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) -->
- **Abstract:** This document is the Communication, Dissemination and Exploitation Initial Plan for SynthAIr. It contains detailed information about the Communication and Dissemination strategy, and the preliminary Exploitation strategy. Targets, key messages, information about branding, channels, social media, publications, events and overall KPIs both for communication and dissemination actions are detailed in this document.