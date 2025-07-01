---
layout: page
title: Time-Series Models
parent: Generative Models
nav_order: 2
---


# Time Series Generation
For trajectory data, we developed specialized models that capture the complex spatiotemporal dynamics of aircraft movements. Our models handle both terminal area operations and complete end-to-end flights.

<div align="center">
  <img src="../figures/timeseries_roadmap.svg" />
  <br>
  <em><strong>Figure 3: Time Series Generation Pipeline.</strong> Aircraft trajectory data from OpenSky Network and EUROCONTROL, enriched with weather context (ERA5, METAR), feeds into five generative models (TCVAE, TimeVQVAE, TimeGAN, Flow Matching, Diffusion Models) producing synthetic trajectories validated for fidelity, diversity, and domain-specific flyability.</em>
</div>