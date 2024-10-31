# Metaheuristic Optimization on Clustered Datasets

This repository applies a range of metaheuristic optimization techniques combined with K-means clustering to various datasets, each addressing unique classification tasks. The project explores the potential of different optimization algorithms to improve clustering quality and provides a systematic approach to evaluating results using multiple metrics.

---

## Table of Contents
- [Introduction](#introduction)
- [Optimization Algorithms](#optimization-algorithms)
- [Datasets and Target Classes](#datasets-and-target-classes)
- [Evaluation Metrics](#evaluation-metrics)
- [PCA Visualization](#pca-visualization)
- [Elbow Curve for Optimal Clustering](#elbow-curve-for-optimal-clustering)
- [Setup and Usage](#setup-and-usage)
- [Results](#results)
- [References](#references)
- [License](#license)

---

## Introduction

Clustering is a fundamental task in machine learning, where data points are grouped based on similarity. While K-means is one of the most commonly used clustering algorithms, it can sometimes converge to local optima or yield suboptimal clusters. This project leverages **metaheuristic optimization techniques** to enhance clustering by refining initial centroid positions and minimizing intra-cluster distances.

The project employs the following metaheuristic algorithms alongside K-means clustering, aiming to improve classification performance across different datasets:

1. **Simulated Annealing**
2. **Particle Swarm Optimization**
3. **Aquila Optimization**
4. **Bat Optimization**
5. **Golden Eagle Optimization** (with adaptive step size)
6. **Differential Evolution**
7. **Grey Wolf Optimization**
8. **Human Learning Optimization**

Each of these algorithms has unique strengths that allow for diversity in optimization and potential improvements over traditional K-means.

---

## Optimization Algorithms

### Overview
Metaheuristic algorithms are inspired by natural phenomena, providing heuristic methods to approximate optimal solutions in complex problem spaces. Below is a brief description of each algorithm employed:

- **Simulated Annealing (SA)**: Mimics the annealing process of metals to avoid local optima, gradually "cooling" to achieve a stable, low-energy solution.
- **Particle Swarm Optimization (PSO)**: Models the social behavior of bird flocks or fish schools, adjusting positions based on both personal and collective experiences.
- **Aquila Optimization (AO)**: Simulates the hunting strategy of Aquila eagles, focusing on prey in a search space for efficient convergence.
- **Bat Optimization**: Uses echolocation inspired by bats to balance exploration and exploitation.
- **Golden Eagle Optimization (GEO)**: Inspired by golden eagle hunting patterns, this algorithm adapts step sizes to optimize solution finding.
- **Differential Evolution (DE)**: Applies mutation, crossover, and selection in an evolutionary framework to improve solution quality iteratively.
- **Grey Wolf Optimization (GWO)**: Based on the hierarchical hunting mechanism of grey wolves, adjusting positions in a social hierarchy.
- **Human Learning Optimization (HLO)**: Replicates the process of human learning for efficient search and optimization.

---

## Datasets and Target Classes

The following datasets were used in this study, each with specific classification tasks:

| Dataset       | Target Class                          | Description |
|---------------|--------------------------------------|-------------|
| Blood Count   | Gender                               | Classified male or female based for blood count data. |
| CMC           | Contraceptive Method (Multi-Class)   | Duration of contraceptive method used.      |
| Colon         | Tumor or Normal                      | Classifies tissue samples as tumor or normal.        |
| Dermatology   | Cancer Stage (Multi-Class)           | Classifies skin condition based on cancer stage.     |
| Diabetes      | Diabetic or Non-Diabetic             | Classifies individuals as diabetic or not.           |
| Heart         | Target                               | Determines heart disease presence.                   |
| Leukemia      | Type (ALL or AML)                    | Classifies leukemia types as ALL or AML.             |
| Liver         | Average Alcohol Consumption          | Assesses average drinking behavior.                  |
| Thyroid       | Cancer (Presence or Absence)         | Identifies the presence of thyroid cancer.           |

Each dataset was subjected to clustering with metaheuristic optimization to better define classes through refined clustering.

---

## Evaluation Metrics

To assess clustering effectiveness and optimization, we used the following metrics:

- **Silhouette Score**: Measures the quality of clustering, indicating how similar each point is to its own cluster compared to others.
- **Accuracy**: Evaluates the percentage of correctly classified instances against the ground truth.
- **Precision**: Assesses the exactness of positive predictions.
- **Recall**: Measures the sensitivity or true positive rate.
- **F1 Score**: Harmonizes precision and recall for balanced metric representation.

## Constants Assumed:
#### 1. For K-means and K-means with Simulated Annealing and K-means with other Metaheuristics
- **Iterations**: 20
- **Population Size**: 20
- **Random State**: 42 (to ensure reproducibility)

#### 2. Particle Swarm Optimization (Implemented Using Pyswarm)
- **n clusters**: 3
- **Iterations**: 20

#### 3. Aquila Optimization
- **Cluster Range**: (2,10)

#### 4. Bat Optimization
- **Loudness**: 0.5
- **Pulse Rate**: 0.5
- **Minimum Frequency**: 0
- **Maximum Frequency**: 2

#### 5. Golden Eagle Optimization
- **Random State**: 30
- **Attack Propensity and Cruise Propensity**: [0.4,0.9]

#### 6. Differential Extraction (Implemented using Pyade)
- **Maximum Evaluations**: 200
- **Population Size**: 20

#### 7. Grey Wolf Optimization
- **Pack Size**: 15
- **Cluster Range**: (2,10)


The optimization algorithms were applied first, after which K-means clustering refined the cluster assignments.

---

## PCA Visualization

Principal Component Analysis (PCA) was used to reduce the dimensionality of each dataset, providing visual representations of clustering results. Both **2D and 3D PCA plots** were generated to visualize clustering quality and spatial distribution of classes.

---

## Elbow Curve for Optimal Clustering

To determine the **optimal number of clusters (K)** for each dataset, we used the **Elbow Curve** method. This method helps identify the point at which increasing the number of clusters yields diminishing returns in reducing the total within-cluster variance.

### How It Works
1. **Calculate Inertia**: For each K (number of clusters), the K-means algorithm is applied, and the inertia, or within-cluster sum of squared errors, is recorded.
2. **Plot Results**: The results are plotted on the Elbow Curve, showing inertia values across different K values.
3. **Identify the "Elbow" Point**: The optimal K is indicated by the "elbow" point in the curve, where inertia reduction starts to taper off. This indicates a point beyond which adding more clusters provides minimal clustering improvement.

### Why the Elbow Curve?
The Elbow Curve provides a **data-driven estimate for K**, which helps in the initial selection of clusters before applying metaheuristic optimization. Since metaheuristic techniques often benefit from good starting conditions, choosing an effective K value based on the Elbow Curve enhances the likelihood of meaningful clustering results.

---


## Setup and Usage

### 1. Clone the Repository
   ```bash
   git clone https://github.com/yourusername/Metaheuristics-Optimization.git
   cd Metaheuristics-Optimization
   ```
### 2. Install the Required Dependencies
```bash
   pip install -r requirements.txt
 ```

## Results
### Summary of Findings

The results indicated that:
1. Clustering quality varied based on the optimization technique, with some algorithms providing better-defined clusters than others.
2. Algorithms like Differential Evolution and Particle Swarm Optimization demonstrated superior clustering improvements across multiple datasets.
3. The similarity in cluster shapes observed across algorithms suggests that, while metaheuristics improve K-means, the underlying data structure plays a significant role.
4. Detailed Results: Each dataset's clustering metrics and PCA plots are saved in the notebooks. This includes scores and comparisons across all metaheuristic algorithms.

## License
Distributed under the MIT License. See LICENSE for more information.
