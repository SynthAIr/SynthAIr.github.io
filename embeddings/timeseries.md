---
layout: page
title: Time Series Embeddings
parent: Embedding Framework
nav_order: 2
---

# Time Series Embeddings for Air Traffic Management

This section presents embedding approaches for transforming flight trajectories into compact vector representations. These embeddings enable trajectory clustering, anomaly detection, core-set extraction, and transfer learning applications.

## Embedding Approaches

### TCVAE Framework

<div align="center">
  <img src="../figures/embedding/tcvae_emb.svg" />
  <br>
  <em><strong>Figure 1: TCVAE Embedding Process</strong>. Flight trajectories are processed into compact latent representations for clustering, anomaly detection, and core-set extraction.</em>
</div>

**TCVAE** transforms flight trajectories into vector embeddings using temporal convolutional encoding and variational latent representations.


### Latent Flow Matching Framework

<div align="center">
  <img src="../figures/embedding/lfm_tl.svg" />
  <br>
  <em><strong>Figure 39: Transfer Learning with Latent Flow Matching</strong>. Two-phase process: pretraining on source airport data, then transferring to target airport with limited data. Enables modeling of airports with sparse datasets.</em>
</div>

**Latent Flow Matching** combines VAE representations with flow matching for transfer learning applications, using a two-phase approach from source to target airports.


## Trajectory Clustering Applications

### Landing Trajectory Analysis

The TCVAE embeddings enable clustering of landing trajectories, revealing approach patterns for different airports.


#### Dublin (EIDW) Landing Trajectories

<div align="center">
  <img src="../figures/embedding/landing/dublin/raw_trajectories.jpg" />
  <br>
  <em><strong>Figure 7: Dublin Raw Landing Trajectories</strong>. Collection of raw landing trajectories for Dublin airport.</em>
</div>

<div align="center">
  <img src="../figures/embedding/landing/dublin/gmm_clusters6.jpg" />
  <br>
  <em><strong>Figure 8: Dublin GMM Clustering</strong>. Gaussian Mixture Model clustering identifying distinct approach patterns for Dublin.</em>
</div>

<div align="center">
  <img src="../figures/embedding/landing/dublin/hdbscan_clusters_with_outliers.jpg" />
  <br>
  <em><strong>Figure 10: Dublin HDBSCAN Clustering (With Outliers)</strong>. Complete clustering including anomalous trajectories.</em>
</div>

<div align="center">
  <img src="../figures/embedding/landing/dublin/hdbscan_clusters_no_outliers.jpg" />
  <br>
  <em><strong>Figure 9: Dublin HDBSCAN Clustering (No Outliers)</strong>. Main approach pattern clusters for Dublin airport.</em>
</div>

<div align="center">
  <img src="../figures/embedding/landing/dublin/hdbscan_clusters_with_reps.jpg" />
  <br>
  <em><strong>Figure 11: Dublin Representative Trajectories</strong>. Core representative trajectories for each identified cluster.</em>
</div>

#### London (EGLL) Landing Trajectories

<div align="center">
  <img src="../figures/embedding/landing/london/raw_trajectories.jpg" />
  <br>
  <em><strong>Figure 12: London Raw Landing Trajectories</strong>. Raw landing trajectories showing London Heathrow's complex approach patterns.</em>
</div>

<div align="center">
  <img src="../figures/embedding/landing/london/gmm_clusters6.jpg" />
  <br>
  <em><strong>Figure 13: London GMM Clustering</strong>. GMM clustering results for London Heathrow approach patterns.</em>
</div>

<div align="center">
  <img src="../figures/embedding/landing/london/hdbscan_clusters_with_outliers.jpg" />
  <br>
  <em><strong>Figure 15: London HDBSCAN Clustering (With Outliers)</strong>. Complete clustering analysis including outlier detection.</em>
</div>

<div align="center">
  <img src="../figures/embedding/landing/london/hdbscan_clusters_no_outliers.jpg" />
  <br>
  <em><strong>Figure 14: London HDBSCAN Clustering (No Outliers)</strong>. Primary approach clusters for London Heathrow.</em>
</div>


<div align="center">
  <img src="../figures/embedding/landing/london/hdbscan_clusters_with_reps.jpg" />
  <br>
  <em><strong>Figure 16: London Representative Trajectories</strong>. Representative trajectories for each approach pattern cluster.</em>
</div>

#### Paris (LFPG) Landing Trajectories

<div align="center">
  <img src="../figures/embedding/landing/paris/raw_trajectories.jpg" />
  <br>
  <em><strong>Figure 17: Paris Raw Landing Trajectories</strong>. Raw landing trajectories for Paris Charles de Gaulle airport.</em>
</div>

<div align="center">
  <img src="../figures/embedding/landing/paris/gmm_clusters6.jpg" />
  <br>
  <em><strong>Figure 18: Paris GMM Clustering</strong>. Gaussian Mixture Model clustering for Paris approach patterns.</em>
</div>

<div align="center">
  <img src="../figures/embedding/landing/paris/hdbscan_clusters_with_outliers.jpg" />
  <br>
  <em><strong>Figure 20: Paris HDBSCAN Clustering (With Outliers)</strong>. Complete clustering including anomaly identification.</em>
</div>

<div align="center">
  <img src="../figures/embedding/landing/paris/hdbscan_clusters_no_outliers.jpg" />
  <br>
  <em><strong>Figure 19: Paris HDBSCAN Clustering (No Outliers)</strong>. Main approach pattern identification for Paris CDG.</em>
</div>


<div align="center">
  <img src="../figures/embedding/landing/paris/hdbscan_clusters_with_reps.jpg" />
  <br>
  <em><strong>Figure 21: Paris Representative Trajectories</strong>. Core trajectories representing each cluster's characteristics.</em>
</div>

#### Zurich (LSZH) Landing Trajectories

<div align="center">
  <img src="../figures/embedding/landing/zurich/raw_trajectories.jpg" />
  <br>
  <em><strong>Figure 22: Zurich Raw Landing Trajectories</strong>. Raw landing trajectories showing Zurich's approach patterns.</em>
</div>

<div align="center">
  <img src="../figures/embedding/landing/zurich/gmm_clusters6.jpg" />
  <br>
  <em><strong>Figure 23: Zurich GMM Clustering</strong>. GMM clustering results for Zurich approach patterns.</em>
</div>

<div align="center">
  <img src="../figures/embedding/landing/zurich/hdbscan_clusters_with_outliers.jpg" />
  <br>
  <em><strong>Figure 25: Zurich HDBSCAN Clustering (With Outliers)</strong>. Complete clustering with outlier trajectory identification.</em>
</div>

<div align="center">
  <img src="../figures/embedding/landing/zurich/hdbscan_clusters_no_outliers.jpg" />
  <br>
  <em><strong>Figure 24: Zurich HDBSCAN Clustering (No Outliers)</strong>. Primary approach clusters for Zurich airport.</em>
</div>

<div align="center">
  <img src="../figures/embedding/landing/zurich/hdbscan_clusters_with_reps.jpg" />
  <br>
  <em><strong>Figure 26: Zurich Representative Trajectories</strong>. Representative trajectories for each identified cluster.</em>
</div>

## End-to-End Route Analysis

### Complete Route Trajectories

The embeddings also enable analysis of complete end-to-end flight routes, revealing patterns in full journey trajectories.

#### Amsterdam to Milan Route (EHAM-LIMC)

<div align="center">
  <img src="../figures/embedding/end_to_end/OpenSky_EHAM_LIMC/raw_trajectories.jpg" />
  <br>
  <em><strong>Figure 27: EHAM-LIMC Raw Trajectories</strong>. Raw trajectories for flights between Amsterdam and Milan.</em>
</div>

<div align="center">
  <img src="../figures/embedding/end_to_end/OpenSky_EHAM_LIMC/gmm_clusters6.jpg" />
  <br>
  <em><strong>Figure 28: EHAM-LIMC GMM Clustering</strong>. Route clustering showing different path preferences.</em>
</div>


#### Stockholm to Paris Route (ESSA-LFPG)

<div align="center">
  <img src="../figures/embedding/end_to_end/OpenSky_ESSA_LFPG/raw_trajectories.jpg" />
  <br>
  <em><strong>Figure 31: ESSA-LFPG Raw Trajectories</strong>. Raw trajectories for flights between Stockholm and Paris.</em>
</div>

<div align="center">
  <img src="../figures/embedding/end_to_end/OpenSky_ESSA_LFPG/gmm_clusters6.jpg" />
  <br>
  <em><strong>Figure 32: ESSA-LFPG GMM Clustering</strong>. Route pattern identification for Stockholm-Paris flights.</em>
</div>


#### Vienna to London Route (LOWW-EGLL)

<div align="center">
  <img src="../figures/embedding/end_to_end/OpenSky_LOWW_EGLL/raw_trajectories.jpg" />
  <br>
  <em><strong>Figure 35: LOWW-EGLL Raw Trajectories</strong>. Raw trajectories for flights between Vienna and London.</em>
</div>

<div align="center">
  <img src="../figures/embedding/end_to_end/OpenSky_LOWW_EGLL/gmm_clusters6.jpg" />
  <br>
  <em><strong>Figure 36: LOWW-EGLL GMM Clustering</strong>. Route clustering for Vienna-London flights.</em>
</div>


## Transfer Learning Applications

Transfer learning extends trajectory generation to airports or routes with limited historical data, demonstrating knowledge transfer between different operational contexts.

### Performance Comparison with 5% Target Data

<table>
  <tr>
    <td width="50%">
      <img src="../figures/embedding/transfer_learning/non-pretrained-05.png" alt="Non-pretrained 5%" style="width:100%">
      <center><em>No Pretraining (5% Data)</em></center>
    </td>
    <td width="50%">
      <img src="../figures/embedding/transfer_learning/pretrainened-05.png" alt="Pretrained 5%" style="width:100%">
      <center><em>With Transfer Learning (5% Data)</em></center>
    </td>
  </tr>
</table>

*Comparison showing improved trajectory quality when using transfer learning with only 5% of target airport data*

### Performance Comparison with 20% Target Data

<table>
  <tr>
    <td width="50%">
      <img src="../figures/embedding/transfer_learning/non-pretrained-20.png" alt="Non-pretrained 20%" style="width:100%">
      <center><em>No Pretraining (20% Data)</em></center>
    </td>
    <td width="50%">
      <img src="../figures/embedding/transfer_learning/pretrainened-20.png" alt="Pretrained 20%" style="width:100%">
      <center><em>With Transfer Learning (20% Data)</em></center>
    </td>
  </tr>
</table>

*Trajectory quality comparison showing sustained transfer learning benefits with increased target data availability*

**Key transfer learning findings:**
- Improved trajectory quality with minimal target airport data
- Knowledge preservation of general flight dynamics across different operational contexts
- Data efficiency enabling generation with as little as 5-20% of full datasets
- Applicability for airports or routes with limited historical trajectory data

Transfer learning applications include:
- Regional airports with sparse historical data
- New routes requiring trajectory modeling
- Seasonal operations with limited data periods
- Emergency scenarios with rare operational patterns


## Applications

### Operational Analysis
- Pattern discovery across routes and airports
- Anomaly detection for unusual trajectories
- Trajectory clustering for operational insights

### Simulation and Modeling
- Core-set extraction of representative trajectories
- Transfer learning between airports
- Synthetic data generation

### Performance Benefits
- Reduced computational requirements
- Efficient analysis of large trajectory datasets
- Scalable across multiple airports

## Summary

These embedding frameworks capture the spatial-temporal dynamics of flight trajectories, enabling trajectory clustering, transfer learning between airports, and operational applications. Transfer learning allows models trained on data-rich airports to work effectively with limited target data (as little as 5-20% of full datasets), supporting route optimization across airports with varying data availability.