---
layout: default
title: "UC6: Schedule Prediction"
parent: ATM Use Cases
nav_order: 6
---

# UC6 - Schedule Prediction

## Overview

Schedule prediction addresses the challenge of inferring missing or incomplete flight schedule information in historical datasets. This use case was not originally part of the SynthAIr project scope, but emerged as a natural extension of UC1 (Turnaround Time), UC2 (Flight Delay), and UC5 (Flight Diversion) due to their shared data sources and strong operational interdependencies. Schedule information — specifically Scheduled In-Block Time (SIBT) and Scheduled Off-Block Time (SOBT) — is essential for computing arrival and departure delays, which are the target variables in several other use cases.

In Europe, flight schedule data is owned by individual airlines and is not publicly accessible. Researchers must typically purchase such data from private agencies, which presents a significant barrier. In this context, generating and providing access to synthetic flight schedules — while not identical to the original data — offers valuable support to the research community by enabling schedule completion without requiring expensive commercial data purchases.

## Operational Context

Arrival and departure delays are defined as the difference between actual and scheduled times:

$$\text{Arrival Delay} = \text{AIBT} - \text{SIBT}$$

$$\text{Departure Delay} = \text{AOBT} - \text{SOBT}$$

The Scheduled In-Block Time (SIBT) and Scheduled Off-Block Time (SOBT) are also important for turnaround duration prediction. When these scheduled times are missing from a historical dataset, any downstream analysis that requires delay or turnaround duration becomes incomplete. The schedule prediction task directly addresses this gap.

## Dataset and Methodology

### Data Source

This use case leverages the same **BTS database** used in UC1, UC2, and UC5, which provides flight schedules for domestic U.S. flights. In parallel, European flight schedules from OAG were acquired and can be integrated with EUROCONTROL R&D Archive flight records to replicate the analysis in a European context. Due to the late acquisition of European schedules and limited project timeline, the experimental analysis presented here was conducted exclusively on U.S. data, but the methodology is directly transferable to European datasets.

### Prediction Approach

Rather than predicting absolute scheduled timestamps directly, the approach predicts **delay durations** (in minutes) — specifically Arrival ΔT and Departure ΔT — and then infers the scheduled times by subtracting the predicted delays from the known actual times:

$$\text{Scheduled Arrival Time} = \text{AIBT} - \widehat{\Delta T}_{\text{arrival}}$$

$$\text{Scheduled Departure Time} = \text{AOBT} - \widehat{\Delta T}_{\text{departure}}$$

This design choice is motivated by the structure of the target variables. Delay durations are simple numerical values expressed in minutes that align well with standard regression modelling. In contrast, scheduled timestamps, when encoded into numeric values (e.g., UNIX minutes), lose their inherent cyclical nature — such as the 24-hour daily cycle — making it more difficult for models to capture meaningful temporal patterns. Predicting delay durations therefore preserves the interpretability and learnability of the target variable while still enabling accurate inference of the corresponding scheduled times.

### Generative Models

Two generative models were evaluated:

- **TVAE (Tabular Variational Autoencoder)**: Applied in Experiment 3, using the full synthetic dataset generated from the BTS training data. TVAE's capacity to handle large synthetic datasets enabled broad representation of real-world patterns.
- **Gaussian Copula (GC)**: Applied in Experiment 5. Due to computational constraints, GC-generated data was limited to approximately 2,000 samples, which led to underrepresentation of certain patterns compared to TVAE.

Both models were evaluated using the **Train on Real, Test on Real (TRTR)** and **Train on Synthetic, Test on Real (TSTR)** methodology, enabling a direct comparison of predictive performance between real and synthetic training data.

## Results and Analysis

### Predictive Performance

The table below shows the predictive performance of machine learning models trained on real vs. synthetic flight data for schedule prediction. TSTR models (trained on synthetic data) are highlighted in green where they outperform the TRTR baseline.

<table>
  <thead>
    <tr>
      <th rowspan="2">Predictive Score</th>
      <th colspan="2">Experiment 3 (TVAE)</th>
      <th colspan="2">Experiment 5 (GC)</th>
    </tr>
    <tr>
      <th>TRTR</th>
      <th>TSTR</th>
      <th>TRTR</th>
      <th>TSTR</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td colspan="5" style="background:#f0f0f0; font-weight:bold;">Predicted: Arrival ΔT (min)</td>
    </tr>
    <tr>
      <td>Average RMSE</td>
      <td>33.97</td>
      <td style="background:#d4edda;">25.29</td>
      <td>36.21</td>
      <td style="background:#d4edda;">30.44</td>
    </tr>
    <tr>
      <td>Average MAE</td>
      <td>27.22</td>
      <td style="background:#d4edda;"><strong>18.31</strong></td>
      <td>28.56</td>
      <td style="background:#d4edda;"><strong>22.18</strong></td>
    </tr>
    <tr>
      <td>Average R²</td>
      <td>-0.80</td>
      <td>0.12</td>
      <td>-0.61</td>
      <td>-0.11</td>
    </tr>
    <tr>
      <td colspan="5" style="background:#f0f0f0; font-weight:bold;">Calculated: Scheduled Arrival Time (UNIX minutes)</td>
    </tr>
    <tr>
      <td>Average RMSE</td>
      <td>40.80</td>
      <td style="background:#d4edda;">35.06</td>
      <td>41.04</td>
      <td style="background:#d4edda;">34.68</td>
    </tr>
    <tr>
      <td>Average MAE</td>
      <td>31.16</td>
      <td style="background:#d4edda;"><strong>26.88</strong></td>
      <td>30.36</td>
      <td style="background:#d4edda;"><strong>26.77</strong></td>
    </tr>
    <tr>
      <td>Average R²</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
    </tr>
    <tr>
      <td colspan="5" style="background:#f0f0f0; font-weight:bold;">Predicted: Departure ΔT (min)</td>
    </tr>
    <tr>
      <td>Average RMSE</td>
      <td>34.51</td>
      <td style="background:#d4edda;">22.82</td>
      <td>33.14</td>
      <td style="background:#d4edda;">26.32</td>
    </tr>
    <tr>
      <td>Average MAE</td>
      <td>27.53</td>
      <td style="background:#d4edda;"><strong>15.27</strong></td>
      <td>26.65</td>
      <td style="background:#d4edda;"><strong>18.91</strong></td>
    </tr>
    <tr>
      <td>Average R²</td>
      <td>-1.95</td>
      <td>-0.13</td>
      <td>-0.90</td>
      <td>-0.15</td>
    </tr>
    <tr>
      <td colspan="5" style="background:#f0f0f0; font-weight:bold;">Calculated: Scheduled Departure Time (UNIX minutes)</td>
    </tr>
    <tr>
      <td>Average RMSE</td>
      <td>38.19</td>
      <td style="background:#d4edda;">24.97</td>
      <td>44.97</td>
      <td style="background:#d4edda;">33.27</td>
    </tr>
    <tr>
      <td>Average MAE</td>
      <td>28.15</td>
      <td style="background:#d4edda;"><strong>14.75</strong></td>
      <td>32.36</td>
      <td style="background:#d4edda;"><strong>20.91</strong></td>
    </tr>
    <tr>
      <td>Average R²</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
    </tr>
  </tbody>
</table>

*Table 1: Predictive performance of machine learning models trained on real vs. synthetic flight data for schedule prediction. Green cells highlight cases where synthetic data (TSTR) outperforms the real-data baseline (TRTR). Lower RMSE/MAE is better.*

### Key Findings

**TSTR consistently outperforms TRTR** across all experiments and both generative models. Models trained on synthetic data achieve lower RMSE and MAE than models trained on real data for both arrival and departure delay prediction. This is a notable result: synthetic data not only matches but exceeds the predictive utility of real data for schedule completion.

**TVAE outperforms GC** in this use case, primarily due to the larger synthetic dataset it produces. The GC-generated data was limited to approximately 2,000 samples due to computational constraints, leading to underrepresentation of certain operational patterns. TVAE's capacity to generate larger datasets provided broader coverage of the real-world distribution.

**Scheduled times are accurately recovered**: The R² values for the calculated scheduled times (both arrival and departure) are 1.00 in all cases. This reflects the deterministic nature of the calculation — once a delay duration is predicted and subtracted from the known actual time, the scheduled time is exactly determined. The key quality metric is therefore the MAE on the delay prediction, where TVAE TSTR achieves **18.31 minutes** for arrival delays and **15.27 minutes** for departure delays.

**Negative R² on delay prediction**: The negative R² values on the raw delay prediction task (TRTR and TSTR) indicate that predicting delay durations from scheduled features alone is inherently difficult at the pre-tactical horizon — consistent with findings from UC2. The positive value achieved by TVAE TSTR (R² = 0.12 for arrival delays) is a meaningful improvement and reflects the benefit of the richer synthetic training set.

## Operational Implications

### Addressing data availability challenges

Despite being conducted exclusively on U.S. data, the approach is readily transferable to European contexts where schedule data is proprietary and typically inaccessible without purchase. The results demonstrate that models trained on synthetic data can effectively infer and complete missing flight schedule information in historical datasets — a particularly valuable capability for European researchers working with EUROCONTROL data where SIBT and SOBT fields are absent.

### Significance of target feature design

The choice to predict delay durations (in minutes) rather than scheduled timestamps proved crucial. Duration-based targets simplify the learning process and mitigate challenges related to temporal encoding — such as the loss of cyclical patterns — resulting in more accurate and generalisable models. This design principle is applicable to other use cases involving temporal targets in aviation analytics.

### Enabling downstream use cases

UC6 is an enabler for the other use cases. Complete schedule information unlocks the full predictive potential of UC1 (turnaround time includes scheduled turnaround duration), UC2 (delay prediction requires scheduled departure/arrival times), and UC5 (tactical diversion prediction uses scheduled times). By providing a practical mechanism for schedule imputation, UC6 directly expands the applicability of the entire SynthAIr framework.

## Conclusion

UC6 demonstrates that **synthetic data can effectively support schedule completion tasks in aviation**, outperforming real-data baselines in all TSTR experiments. TVAE-generated synthetic data achieves the best results, reducing departure delay MAE from 27.53 (real data) to 15.27 minutes (synthetic) and arrival delay MAE from 27.22 to 18.31 minutes, while recovering scheduled times with consistent accuracy.

Although the analysis was conducted on U.S. domestic data, the methodology is directly applicable to European contexts where flight schedule information is commercially restricted. The results provide a practical foundation for researchers working with incomplete historical datasets, enabling schedule imputation without requiring access to proprietary schedule data.
