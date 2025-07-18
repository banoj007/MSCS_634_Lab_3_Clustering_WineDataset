# MSCS 634 Lab 3: Clustering Analysis Using K-Means and K-Medoids

**Author**: Banoj Kumar Jena  
**Course**: MSCS 634 – Data Mining  
**Assignment**: Lab 3 – Clustering Analysis  

---

## 📘 Overview

This lab explores clustering techniques using the **Wine Dataset** from scikit-learn. The project implements and compares **K-Means** and **K-Medoids** algorithms and evaluates their performance through **visualization** and **quantitative metrics**.

---

## 📊 Dataset

The **Wine Dataset** consists of:
- 178 samples
- 13 numerical features
- 3 distinct classes (wine cultivars)

This dataset is well-suited for clustering due to:
- Good class separation in the feature space
- Rich numerical feature set
- Balanced class distribution

---

## 🔍 Methodology

### 1. Data Preparation
- Loaded Wine Dataset from `scikit-learn`
- Performed exploratory data analysis (EDA)
- Applied **Z-score normalization**
- Reduced dimensionality using **Principal Component Analysis (PCA)** for visualization

### 2. K-Means Clustering
- Implemented K-Means with `k = 3`
- Set `random_state = 42` for reproducibility
- Computed centroids as means of data points in clusters

### 3. K-Medoids Clustering
- Custom K-Medoids implemented (due to `sklearn_extra` incompatibility)
- Used `k = 3` with the same random seed
- Medoids selected from actual data points

### 4. Evaluation Metrics
- **Silhouette Score**: Measures cohesion vs. separation
- **Adjusted Rand Index (ARI)**: Measures alignment with true labels

---

## 📈 Results

### Performance Comparison

| Algorithm   | Silhouette Score | Adjusted Rand Index |
|-------------|------------------|----------------------|
| K-Means     | 0.2807           | 0.8708               |
| K-Medoids   | 0.2743           | 0.8708               |

### Key Findings
- K-Means slightly outperforms K-Medoids in Silhouette Score
- Both algorithms reach the same ARI score (0.8708)
- Strong clustering alignment with true labels
- Minor performance difference indicates both are suitable for this dataset

---

## 🧠 Analysis and Interpretation

### When to Use K-Means
**Pros**:
- High speed and scalability
- Good for spherical, well-separated clusters
- Efficient on large datasets  
**Cons**:
- Sensitive to noise and outliers
- Centroids may not be real data points

### When to Use K-Medoids
**Pros**:
- Robust to outliers
- Medoids are actual data points
- Better for non-spherical or uneven clusters  
**Cons**:
- Slower and more computationally expensive
- Less stable with random initialization

---

## ⚙️ Technical Implementation

### Challenges Faced & Solutions

| Challenge | Solution |
|----------|----------|
| Incompatibility with `sklearn_extra` | Built custom K-Medoids implementation |
| High dimensionality (13 features) | Applied PCA for 2D visualization |
| Fair comparison | Used same preprocessing and `random_state` |


## ✅ Conclusions

- **Both K-Means and K-Medoids perform well** on the Wine Dataset.
- K-Means shows **better cohesion** via higher Silhouette Score.
- **Identical ARI scores** confirm strong clustering accuracy from both models.

### Algorithm Choice Guidelines:
- **Use K-Means** when speed and scalability are priorities.
- **Use K-Medoids** when robustness and interpretability are important.


