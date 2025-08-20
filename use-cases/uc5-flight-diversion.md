---
layout: default
title: "UC5: Flight Diversion Prediction"
parent: ATM Use Cases
nav_order: 5
---

# UC5 - Flight Diversion Prediction

Flight diversion prediction addresses the challenge of identifying when aircraft must be rerouted to alternate airports due to severe weather, medical emergencies, or technical malfunctions. These rare events create significant operational disruptions and impose economic burdens on airlines and airports, particularly at capacity-constrained facilities where unexpected diversions can cause cascading delays.

The primary challenge in developing diversion prediction models lies in the extreme class imbalance of historical datasets. In the BTS database analysis, only 127 flights out of approximately 60,000 were recorded as diverted, making it difficult to train effective machine learning models. To address this limitation, we employed synthetic data generation using a **Gaussian Copula** model specifically trained on the small subset of diverted flights. The generated synthetic diversion cases were then combined with real data to create a more balanced training dataset for predictive modeling. Results demonstrated that models trained on the augmented dataset consistently outperformed those using only real data, with improvements across all classification metrics including precision, recall, and F1-score for diversion prediction.

However, the evaluation revealed that synthetic data augmentation alone cannot overcome the absence of critical operational features such as real-time weather conditions and air traffic congestion data, which are likely essential for accurate diversion prediction. While synthetic data generation mitigated class imbalance issues, overall predictive performance remained limited due to the lack of strongly correlated features in the original dataset. More detailed results and comprehensive analysis will be published in a deliverable currently under review.