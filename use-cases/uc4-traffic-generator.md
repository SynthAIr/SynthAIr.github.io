---
layout: page
title: UC4 - Synthetic Traffic Generator
parent: ATM Use Cases
nav_order: 4
---

# UC4 - Synthetic Traffic Generator

## Overview

Synthetic aircraft trajectory generation addresses challenges in Air Traffic Management (ATM) including data scarcity and the need for simulation datasets. This use case demonstrates how deep learning models can generate synthetic flight trajectories that preserve spatial and temporal characteristics of real air traffic patterns, providing access to flight data for research, training, and analysis.

Synthetic trajectories support aviation research by enabling benchmark datasets for algorithm evaluation and simulation environments with diverse traffic scenarios. 

## Operational Context

Air traffic growth creates a need for tools to model and analyze flight operations. Data-driven ATM research requires historical flight data, but obtaining comprehensive datasets remains challenging due to accessibility restrictions and limited availability of certain flight scenarios.

The primary challenges driving synthetic trajectory generation include:

- **Data scarcity**: Limited access to comprehensive historical flight data for certain scenarios or routes
- **Dataset augmentation**: Need for additional flight data to augment machine learning models and conduct broader airspace analyses
- **Scenario underrepresentation**: Certain operational conditions—such as specific weather patterns, emergency diversions, or rare flight scenarios—may be insufficiently represented in available datasets
- **Research accessibility**: Academic and research institutions often lack access to comprehensive operational flight databases
- **Simulation requirements**: Large-scale airspace studies and capacity analyses require diverse, realistic trajectory datasets

Synthetic trajectory generation addresses these challenges by producing flight data that exhibits spatiotemporal structures found in real trajectories. The approach uses deep learning to extract and reproduce flight patterns from historical data, capturing dependencies and maintaining consistency throughout flight paths.

The challenge is generating trajectories that preserve statistical characteristics of real flight data and physical constraints of aircraft operations, including speed profiles, altitude progressions, and air traffic procedures.

## Dataset

### Trajectory Data Sources
The trajectory datasets used in UC4 come from two sources providing flight trajectory information across European airspace:

**OpenSky Network Data** provides high-resolution aircraft position reports collected through ADS-B receivers, including:
- **Spatial coordinates**: Latitude, longitude, altitude with high precision
- **Temporal information**: Timestamps with second-level precision  
- **Aircraft identifiers**: ICAO24 address, callsign for flight tracking
- **High temporal resolution**: Often 1-5 seconds between consecutive points, capturing flight dynamics and maneuvers
- **Coverage period**: Flights from 2019 to 2023 across European airspace

**EUROCONTROL R&D Archive** complements OpenSky with officially recorded flight plans and actual flight data:
- **Flight identifiers and metadata**: ECTRL ID, aircraft type, operator information
- **Waypoint-based trajectory information**: Latitude, longitude, flight level at key points
- **Origin-destination information**: ADEP and ADES airport codes
- **Broader coverage**: European airspace with lower sampling rates, typically at flight plan waypoints

### Dataset Types and Structure

Two distinct trajectory dataset types were created to support different aspects of synthetic traffic generation:

**End-to-End Flight Trajectories**: Complete paths from departure to arrival airports, capturing entire flight profiles including:
- **Climb phase**: Takeoff through initial cruise altitude
- **Cruise phase**: Level flight at optimal altitude 
- **Descent phase**: Approach and landing procedures
- **Complete spatial-temporal coverage**: Flight envelope representation

**Landing Trajectories**: Focused on approach and landing phases, covering:
- **Final approach segments**: Typically within 40-100 nautical miles of destination
- **Terminal maneuvering area operations**: Including holding patterns, approach procedures
- **High-resolution terminal dynamics**: Capture of flight phases


## Results and Analysis


### Trajectory Visualization and Comparison

#### Amsterdam (EHAM) to Milan (LIMC) Route

<table>
  <tr>
    <td width="50%">
      <img src="../figures/uc4/training_trajectories_with_class_colors_OpenSky_EHAM_LIMC.jpg" alt="Real Trajectories EHAM-LIMC" style="width:100%">
      <center><em>Real Trajectories</em></center>
    </td>
    <td width="50%">
      <img src="../figures/uc4/synthetic_trajectories_with_class_colors_OpenSky_EHAM_LIMC.jpg" alt="Synthetic Trajectories EHAM-LIMC" style="width:100%">
      <center><em>Synthetic Trajectories</em></center>
    </td>
  </tr>
</table>

*Real flight trajectories (left) showing route variations and operational diversity compared with synthetic trajectories (right) capturing primary route corridors and operational variations*

#### Stockholm (ESSA) to Paris (LFPG) Route

<table>
  <tr>
    <td width="50%">
      <img src="../figures/uc4/training_trajectories_with_class_colors_OpenSky_ESSA_LFPG.jpg" alt="Real Trajectories ESSA-LFPG" style="width:100%">
      <center><em>Real Trajectories</em></center>
    </td>
    <td width="50%">
      <img src="../figures/uc4/synthetic_trajectories_with_class_colors_OpenSky_ESSA_LFPG.jpg" alt="Synthetic Trajectories ESSA-LFPG" style="width:100%">
      <center><em>Synthetic Trajectories</em></center>
    </td>
  </tr>
</table>

*Cross-route validation showing model generalization across different European corridors*

The synthetic trajectories reproduce:
- **Primary route corridors** following established air traffic flows
- **Altitude profile diversity** reflecting different aircraft types and operational procedures
- **Spatial variation patterns** consistent with air traffic control routing practices
- **Class-conditional generation** for targeted trajectory synthesis for specific operational scenarios

### Quantitative Evaluation Results

The table below reports quality and statistical metrics comparing TimeVQVAE and TCVAE on the EHAM–LIMC (Amsterdam–Milan) route dataset. Results are from the peer-reviewed ICNS 2025 publication ([Synthetic Aircraft Trajectory Generation Using Time-Based VQ-VAE](https://doi.org/10.1109/ICNS65417.2025.10976929)).

| Metric | Description | TCVAE | TimeVQVAE |
|--------|-------------|-------|-----------|
| **FID** (↓) | Fréchet Inception Distance — distribution similarity | 0.7944 | **0.0029** |
| **IS** (↑) | Inception Score — realism and diversity | 2.1514 ± 0.1283 | **3.4049 ± 0.2660** |
| **MDD** (↓) | Marginal Distribution Difference | 0.1789 | **0.0512** |
| **ACD** (↓) | Autocorrelation Difference | 289.3323 | **5.6334** |
| **SD** (↓) | Skewness Difference | 0.2253 | **0.0554** |
| **KD** (↓) | Kurtosis Difference | 0.3164 | **0.1065** |

TimeVQVAE outperforms TCVAE across all six metrics. The improvement in FID (0.7944 → 0.0029) and ACD (289.3323 → 5.6334) is particularly substantial, indicating that the time-frequency processing and vector quantization in TimeVQVAE produce trajectories with significantly better distributional fidelity and temporal correlation structure.

### Flyability Assessment

Generated trajectories were validated using the **BlueSky open-source air traffic simulator**, which provides operational realism testing beyond purely statistical metrics. Trajectory similarity was assessed using multiple distance measures — SSPD, Hausdorff, Fréchet, LCSS, EDR, DTW, and ERP — applied to synthetic trajectories against the real distribution.

Key findings from the flyability assessment of TimeVQVAE-generated trajectories on the EHAM–LIMC route:

- **SSPD**: Approximately 80% of generated trajectories achieve distances below 0.01, indicating very high spatial similarity to real routes
- **Hausdorff and Fréchet distances**: Approximately 60% of trajectories achieve distances below 0.1, confirming strong shape fidelity for the majority of generated samples
- **LCSS and EDR**: Approximately 20% of trajectories score below 0.1; these metrics are sensitive to sequence alignment and temporal ordering, reflecting remaining challenges in reproducing the exact temporal progression of flight phases
- **DTW and ERP**: The majority of trajectories score above 1.0, reflecting the sensitivity of warping-based metrics to the high dimensionality and variable length of trajectory sequences

Overall, the flyability results confirm that TimeVQVAE-generated trajectories are operationally plausible and spatially consistent with real air traffic patterns, while also revealing that temporal alignment in fine-grained flight phases remains an open challenge for future work.


## Trajectory Clustering and Pattern Discovery

### Dublin Airport Landing Trajectories

Dublin Airport (EIDW) demonstrates embedding-based trajectory clustering methodology due to its traffic volume and diverse approach patterns. Using TCVAE embeddings, the approach can discover distinct operational patterns and identify anomalous flight behaviors.

#### Raw Landing Trajectories
![Dublin Raw Trajectories](../figures/uc4/dublin_raw_trajectories.jpg)
*Raw flight trajectories into Dublin Airport showing natural operational diversity across multiple approach corridors*

#### HDBSCAN Clustering Results
![Dublin HDBSCAN Clustering](../figures/uc4/dublin_hdbscan_clusters_no_outliers.jpg)
*Hierarchical density-based clustering showing seven distinct approach patterns corresponding to main arrival corridors at Dublin Airport*

#### Anomaly Detection Results
![Dublin Anomaly Detection](../figures/uc4/dublin_hdbscan_clusters_with_outliers.jpg)
*HDBSCAN's density-based noise detection flags trajectories that deviate from common patterns, indicating potential operational anomalies (shown in grey)*

#### Representative Trajectory Clusters
![Dublin HDBSCAN with Representatives](../figures/uc4/dublin_hdbscan_clusters_with_reps.jpg)
*Clustering results with representative trajectories highlighting the medoid flight path for each identified approach pattern*



### Key Clustering Insights

The embedding-based trajectory clustering pipeline provides several advantages:

**Dimensionality Reduction**: Compresses multivariate trajectories into 64-dimensional vectors while preserving spatiotemporal patterns

**Automated Feature Learning**: Captures flight characteristics without manual engineering of trajectory features

**Noise Robustness**: Filters minor sampling irregularities and measurement noise that could affect traditional clustering approaches

**Flexible Cluster Discovery**: Identifies approach patterns and flags anomalous trajectories

**Operational Pattern Recognition**: Identifies approach corridors, descent procedures, and operational variations that correspond to air traffic management practices



## Operational Implications

### Simulation and Training Applications
The synthetic trajectories enable simulation environments for:
- **Air traffic controller training** using realistic but synthetic traffic scenarios
- **Algorithm development** with diverse trajectory patterns for robust testing  
- **Capacity analysis** through synthetic traffic generation at various density levels
- **Safety assessment** using generated edge-case scenarios for evaluation


### Data Augmentation for Machine Learning  
Generated trajectories provide training data enhancement:
- **Rare scenario augmentation** for events underrepresented in historical data
- **Class balancing** for route-specific or aircraft-type-specific modeling applications
- **Robustness improvement** through synthetic data variety in machine learning pipelines
- **Performance validation** using synthetic test cases for comprehensive model evaluation


## Conclusion

UC4 demonstrates the application of generative models for synthetic aircraft trajectory generation across European flight corridors. The results show that the model can generate trajectories that preserve key characteristics of real flight patterns while maintaining statistical consistency with the original data.


The trajectory visualizations show that synthetic data captures primary route corridors and operational variations present in real flight data. The clustering analysis reveals distinct approach patterns at Dublin Airport, with automatic identification of anomalous trajectories. Transfer learning results indicate potential for extending models to airports with limited historical data.

These capabilities support various ATM research and development activities, providing tools for data augmentation, simulation, and analysis while addressing data scarcity challenges in aviation operations research.