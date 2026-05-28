---
layout: page
title: Public Deliverables
parent: Research Outputs
nav_order: 2
---

# Public Deliverables

Official project deliverables made publicly available through the European Commission's CORDIS platform and other repositories.

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

### **D3.3 - Final Synthetic Data Generation Report**

- **Authors:** SINTEF, TUD
- **Date:** 19 May 2025
- **Abstract:** This deliverable presents the comprehensive evaluation of the nine synthetic data generation models developed under the SynthAIr project. It details the experimental protocols, quantitative and qualitative metrics, comparative analyses, and downstream task performance across six representative Air Traffic Management (ATM) use cases. Its goal is to demonstrate the fidelity, utility, diversity, and privacy properties of the generated datasets, providing researchers and operational teams with actionable insights into when — and how — these synthetic generators can replace or augment real-world ATM data. Results show that advanced neural network architectures, in particular transformer-based generators, retain 94–97% of real-data predictive performance while maintaining feature importance patterns informative for operational decision-making.

### **D3.4 - Final Synthetic Data Generation ML Models**

- **Authors:** SINTEF, TUD
- **Date:** 19 May 2025
- **Abstract:** This deliverable presents the final synthetic data generation machine learning models developed in the SynthAIr project. It documents eight AI models designed for generating synthetic data in Air Traffic Management: five tabular data generators (CTGAN, TabSyn, REaLTabFormer, TVAE, and Gaussian Copula) and three time-series generators (TCVAE with VampPrior, TimeVQVAE, and TimeGAN). For each model, theoretical foundations, architectural components, training methodologies, and implementation details are provided through well-structured open-source repositories. This work represents a significant contribution in synthetic data generation for aviation, enabling privacy-preserving data sharing and enhanced predictive modelling in the ATM domain.

### **D4.1 - Initial General Time Series Embeddings ML Model**

- **Authors:** SINTEF, TUD, DEEPBLUE, EUROCONTROL
- **Date:** 22 November 2024
- **CORDIS Link:** [Download](https://ec.europa.eu/research/participants/documents/downloadPublic?documentIds=080166e5151fe59c&appId=PPGMS)
- **Abstract:** This deliverable presents the initial development of general time series embeddings for ATM data. It demonstrates how the rich latent representations learned by variational autoencoder models can serve as general-purpose time series embeddings without requiring additional model development. The document outlines an evaluation framework for assessing embedding quality and presents initial results focusing on trajectory clustering and visualization. While these results are promising, it also identifies areas for future enhancement. This work lays the groundwork for developing more refined embedding models in subsequent deliverables, ultimately contributing to enhanced ATM automation and simulation capabilities through improved data representations.

### **D4.2 - General Time Series Embeddings ML Model (Implementation)**

- **Authors:** SINTEF
- **Date:** 31 May 2025
- **Abstract:** This deliverable provides the technical documentation for two code repositories from the SynthAIr project that implement machine learning embedding models. The first repository focuses on tabular embeddings for analysing flight operational data to enable pattern discovery and anomaly detection. The second repository implements time series models for trajectory generation and transfer learning, featuring multiple generative architectures including diffusion models, flow matching, and VAEs specifically designed for aircraft trajectory modelling. Both repositories are structured with clear documentation, installation procedures, and practical examples, following open-source best practices to ensure researchers and practitioners can readily adopt and extend these tools.

### **D4.3 - General Embeddings ML Model**

- **Authors:** SINTEF
- **Date:** 20 May 2025
- **Abstract:** This deliverable presents a framework for general-purpose embeddings in Air Traffic Management (ATM), demonstrating how latent representations from synthetic data generation can be leveraged for downstream tasks. Building upon previous deliverables (D3.1, D4.1, D3.3), it presents tabular embeddings from variational and transformer-based architectures, and time series embeddings from temporal convolutional networks and flow matching models. These embeddings transform flight records and trajectories into compact vectors capturing operational patterns and temporal dynamics. The deliverable demonstrates their application in operational pattern discovery, anomaly detection, trajectory clustering, core-set extraction, and transfer learning between airports with limited data. Results suggest these approaches provide analytical value beyond synthetic data generation, offering ATM stakeholders tools for data exploration and operational optimisation with reduced computational requirements.

### **D5.1 - Exploratory Research Plan (ERP) – Initial**

- **Authors:** DEEPBLUE, TUD, SINTEF, EUROCONTROL
- **Date:** 30 October 2024
- **CORDIS Link:** [Download](https://ec.europa.eu/research/participants/documents/downloadPublic?documentIds=080166e514083263&appId=PPGMS)
- **Abstract:** This document is the initial version of the SynthAIr Exploratory Research Plan (ERP). It describes the exploratory research plan which will guide the preparation and execution of the validation exercises of the SynthAIr solution for TRL1 (Basic Technology Research / Research to Prove Feasibility).

### **D5.2 - Exploratory Research Report (ERR)**

- **Authors:** DEEPBLUE, SINTEF, TUD, EUROCONTROL
- **Date:** 9 September 2025
- **Abstract:** This document presents the consolidated results of the SynthAIr project aiming to reach a maturity level of TRL 1. SynthAIr explored the potential of synthetic dataset generation in ATM and aviation by developing AI/ML models for different operational applications. The project aim was two-fold: (1) to assess the feasibility and value of synthetic datasets as standalone solutions for specific use cases; and (2) to evaluate augmented datasets — combining real and synthetic data — to enhance the capabilities of predictive AI/ML models in aviation. The report details three validation exercises covering the project's validation objectives, presents confidence assessments of the results, and concludes with recommendations for future research directions toward higher TRL levels.

### **D6.1 - Communication, Dissemination and Exploitation Plan**

- **Authors:** DEEPBLUE
- **Date:** July 04, 2024
- **DOI:** [10.5281/zenodo.13935230](https://doi.org/10.5281/zenodo.13935230)
<!-- - **License:** [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) -->
- **Abstract:** This document is the Communication, Dissemination and Exploitation Initial Plan for SynthAIr. It contains detailed information about the Communication and Dissemination strategy, and the preliminary Exploitation strategy. Targets, key messages, information about branding, channels, social media, publications, events and overall KPIs both for communication and dissemination actions are detailed in this document.

### **D6.4 - Final Communication, Dissemination and Exploitation Plan**

- **Authors:** DEEPBLUE, SINTEF, TUD, EUROCONTROL
- **Date:** 29 January 2026
- **Abstract:** This document is the final Communication, Dissemination and Exploitation Plan for SynthAIr. It contains detailed information about the Communication, Dissemination and Exploitation strategy and its results at project end. It reports on the outcomes of all communication channels (website, social media, press and media, graphic materials, videos), dissemination activities (open-access publications, conference presentations, stakeholder events), and the exploitation strategy for the project's exploitable results, including the open-source repositories and synthetic datasets produced during the project lifetime.