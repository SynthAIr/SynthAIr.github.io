---
layout: default
title: "UC6: Schedule Prediction"
parent: ATM Use Cases
nav_order: 6
---

# UC6 - Schedule Prediction

Schedule prediction addresses the critical challenge of inferring missing or incomplete flight schedule information in historical datasets, particularly relevant for European flight data where schedule information is typically proprietary and inaccessible without commercial purchase. This use case emerged as a natural extension of the turnaround time and delay prediction tasks due to their shared data dependencies and operational interconnections.

The approach focuses on predicting delay durations (arrival and departure delays in minutes) rather than absolute scheduled timestamps, which simplifies the learning process and mitigates temporal encoding challenges. Using **Tabular Variational Autoencoder (TVAE)** and **Gaussian Copula** models trained on BTS flight data, we demonstrated that synthetic data can effectively support schedule completion tasks. Models trained on synthetic data achieved comparable performance to real-data baselines when predicting delay durations, subsequently enabling the calculation of scheduled arrival and departure times by subtracting predicted delays from known actual times. This capability proves particularly valuable for researchers working with incomplete historical datasets where schedule information may be missing or corrupted.

While this analysis was conducted exclusively on U.S. domestic flight data due to late acquisition of European schedules, the methodology is readily transferable to European contexts where proprietary schedule data presents access barriers. The results demonstrate that synthetic data generation can provide valuable support to the research community by enabling schedule completion without requiring expensive commercial data purchases. More detailed technical implementation and comprehensive evaluation results will be published in a deliverable currently under review.