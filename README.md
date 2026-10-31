# Spatio-Temporal Traffic Prediction Using Graph-Based Representation Learning

**Research Project | Data Science Research Center, Faculty of Science, Chiang Mai University**

## Overview

Traffic speed prediction is an important component of intelligent transportation systems, supporting traffic management and transportation planning.

This project investigates the use of spatial and temporal information from traffic sensor networks to predict traffic speed. Using the METR-LA dataset, the study compares baseline and deep learning models to evaluate the contribution of temporal patterns and spatial relationships to prediction performance.

## Objectives

- Develop a traffic speed prediction model using GRU and Graph Convolutional Networks (GCN).
- Compare Naive, GRU, GCN, and hybrid GRU-GCN models.
- Analyze the effects of temporal and spatial information on prediction performance.

## Dataset

**METR-LA**

The dataset contains traffic speed measurements collected from **207 traffic sensors**.

Key characteristics:
- **Nodes:** Traffic sensors
- **Edges:** Spatial relationships between sensors represented by an adjacency matrix
- **Temporal data:** Sequential traffic speed observations
- **Prediction task:** Predict the next time step using the preceding 12 time steps

The dataset is not included in this repository.

## Methodology

The workflow consists of seven stages:

1. **Data Preprocessing** — Handle missing measurements and normalize the data using statistics calculated from the training set.
2. **Time-Based Split** — Divide the data chronologically into training (70%), validation (10%), and testing (20%) sets.
3. **Sliding Window** — Use 12 historical time steps to predict traffic speed at the next time step.
4. **Graph Construction** — Represent traffic sensors as graph nodes and incorporate their spatial relationships through an adjacency matrix.
5. **Model Training** — Train and compare Naive, GRU, GCN, and hybrid GRU-GCN approaches.
6. **Traffic Speed Prediction** — Generate predictions for the next time step.
7. **Model Evaluation** — Evaluate prediction performance using Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE).

## Models

- **Naive Baseline:** Uses the most recent available traffic speed as the prediction.
- **GRU:** Captures temporal dependencies in traffic speed observations.
- **GCN:** Learns spatial relationships between connected traffic sensors.
- **GRU-GCN Hybrid:** Combines temporal modeling with graph-based spatial representation learning.

## Experimental Results

The following results are reported in the research poster.

| Model | MAE (mph) | RMSE (mph) |
|---|---:|---:|
| Naive | 2.81 | 4.63 |
| GRU | 2.70 | 4.41 |
| GCN | 2.34 | 4.06 |
| GRU-GCN | 2.31 | 4.01 |

### Key Findings

- All three learned models outperformed the Naive baseline in the reported experiment.
- GCN reduced MAE by approximately **17.0%** relative to the Naive baseline, highlighting the contribution of spatial information.
- The hybrid GRU-GCN model achieved the lowest reported MAE and RMSE.
- GRU-GCN reduced MAE by approximately **18.0%** and RMSE by approximately **13.3%** relative to the Naive baseline.
- The improvement of GRU-GCN over GCN was small, suggesting that the additional benefit of combining temporal and spatial modeling requires further investigation.

*Results reflect the reported experiment. Further evaluation across multiple random seeds and prediction horizons would help assess the robustness and generalizability of the findings.*

## Technologies

- Python
- PyTorch
- NumPy
- Pandas
- Deep Learning
- Graph Convolutional Networks
- Gated Recurrent Units
- Time-Series Analysis

## Repository Structure

```text
graph-based-traffic-prediction/
├── README.md
├── notebooks/
│   └── Spatio_graph.ipynb
└── poster/
    └── research_poster.png
```

## Research Poster

The research poster presents the motivation, methodology, model architectures, experimental results, and conclusions of this project.

## Limitations and Future Work

- Evaluate model performance across multiple random seeds.
- Investigate longer prediction horizons, including 15, 30, and 60 minutes.
- Examine the effects of different graph construction strategies.
- Further investigate the contribution of temporal modeling to the hybrid architecture.

## Acknowledgment

**Data Science Research Center, Faculty of Science, Chiang Mai University.**

## Disclaimer

This repository presents a summary of the research project and its reported experimental findings. Please refer to the research poster and notebook for additional methodological details.
