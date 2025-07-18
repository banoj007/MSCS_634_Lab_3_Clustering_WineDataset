MSCS 634 Lab 3: Clustering Analysis Using K-Means and K-Medoids
Author: Banoj Kumar Jena
Course: MSCS 634 – Data Mining
Assignment: Lab 3
Overview
This lab explores clustering techniques using the Wine Dataset from sklearn. The project implements and compares K-Means and K-Medoids algorithms, evaluating their performance through visualization and quantitative metrics.
Dataset
The Wine Dataset contains 178 samples with 13 features representing chemical properties of wines from three different cultivars. The dataset is well-suited for clustering analysis as it has:

3 distinct classes (wine cultivars)
13 numerical features
Good class separation in the feature space

Methodology
1. Data Preparation

Loaded the Wine Dataset from sklearn
Performed exploratory data analysis
Standardized features using z-score normalization
Applied PCA for visualization purposes

2. K-Means Clustering

Implemented K-Means with k=3 clusters
Used random_state=42 for reproducibility
Calculated cluster centroids as mean of assigned points

3. K-Medoids Clustering

Implemented custom K-Medoids algorithm (due to sklearn_extra compatibility issues)
Used k=3 clusters with same random seed
Selected actual data points as cluster centers (medoids)

4. Evaluation Metrics

Silhouette Score: Measures cluster cohesion and separation
Adjusted Rand Index (ARI): Compares clustering results with true labels

Results
Performance Comparison
AlgorithmSilhouette ScoreAdjusted Rand IndexK-Means0.28070.8708K-Medoids0.27430.8708
Key Findings

K-Means achieved a slightly higher Silhouette Score (0.2807 vs 0.2743)
Both algorithms achieved identical ARI scores (0.8708), indicating similar agreement with true labels
Both methods successfully identified the three wine cultivars with high accuracy
The difference in performance is minimal, suggesting both algorithms are suitable for this dataset

Cluster Visualization
The PCA visualization reveals:

Both algorithms produce similar cluster structures
Clear separation between the three wine cultivars
K-Means centroids and K-Medoids medoids are positioned similarly
Some overlap between clusters is expected given the nature of the data

Analysis and Interpretation
When to Use K-Means:

Advantages:

Computationally efficient
Works well with spherical clusters
Faster convergence
Better for large datasets


Disadvantages:

Sensitive to outliers
Assumes spherical cluster shapes
Centroids may not represent actual data points



When to Use K-Medoids:

Advantages:

More robust to outliers
Uses actual data points as centers
Better for non-spherical clusters
More interpretable cluster centers


Disadvantages:

Computationally more expensive
May be less stable
Slower convergence



Technical Implementation
Challenges Faced

sklearn_extra Compatibility Issue:

The sklearn_extra library had version compatibility problems with NumPy
Solution: Implemented a custom K-Medoids algorithm from scratch


Visualization Complexity:

High-dimensional data (13 features) needed dimensionality reduction
Solution: Used PCA to reduce to 2D for visualization while preserving most variance


Algorithm Comparison:

Ensuring fair comparison between algorithms
Solution: Used identical random seeds and preprocessing steps



Code Structure
├── Data Loading and Preprocessing
├── K-Means Implementation
├── K-Medoids Implementation (Custom)
├── Evaluation and Metrics
├── Visualization and Analysis
└── Results Interpretation
Conclusions

Both K-Means and K-Medoids performed well on the Wine Dataset
K-Means showed slightly better cluster cohesion (higher Silhouette Score)
Both algorithms achieved identical performance in matching true labels (ARI = 0.8708)
The choice between algorithms depends on specific requirements:

Use K-Means for efficiency and spherical clusters
Use K-Medoids for robustness to outliers and interpretable centers
