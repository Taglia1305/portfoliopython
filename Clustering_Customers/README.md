# Customer Segmentation with K-Means Clustering

Unsupervised machine learning project that segments mall customers into distinct behavioral profiles using K-Means clustering — with full statistical validation and actionable marketing insights.

---

## Overview

Retail businesses rarely treat all customers the same, yet without data they often have no choice. This project applies K-Means clustering to a mall customer dataset to automatically discover hidden purchasing segments, validate them mathematically, and translate each cluster into a concrete marketing persona.

The goal isn't just to run an algorithm — it's to answer a real business question: **who are our customers, and how should we talk to each group?**

---

## Dataset

**Mall Customers Dataset** — 200 records, 5 features.

| Feature | Description |
|---|---|
| `CustomerID` | Unique identifier (dropped before modeling) |
| `Gender` | Male / Female |
| `Age` | Customer age in years |
| `Annual Income (k$)` | Yearly income in thousands of USD |
| `Spending Score (1-100)` | Mall-assigned score based on purchasing behaviour |

---

## Methodology

### 1. Exploratory Data Analysis
Univariate distributions (histograms + KDE) for all numerical features and a bivariate scatter plot of Income vs Spending Score to visually confirm the presence of natural groupings before any algorithm is run.

### 2. Feature Scaling
K-Means is a distance-based algorithm — features on different scales bias the Euclidean distance calculation. `StandardScaler` is applied to `Annual Income` and `Spending Score` before fitting, ensuring both features contribute equally to cluster assignment.

### 3. Optimal K Selection — Two Independent Metrics
Rather than guessing K, two complementary methods are used in parallel:

- **Elbow Method (WCSS):** plots Within-Cluster Sum of Squares across K=1..10. The curve bends sharply at K=5.
- **Silhouette Score:** measures intra-cluster cohesion vs. inter-cluster separation (range −1 to +1, higher is better). Peak score is also at K=5.

Both metrics independently confirm **K=5** as the optimal number of clusters.

### 4. Model Training & Centroid Extraction
Final model fitted with `k-means++` initialisation (`random_state=42` for reproducibility). Cluster centroids are extracted from the scaled space and inverse-transformed back into original units (k$ and score) for interpretability.

### 5. Cluster Profiling & Business Personas
Each cluster is profiled across all features (including Age, which was deliberately excluded from training to test its emergent explanatory power). Gender distribution per cluster is computed via cross-tabulation.

### 6. Multivariate Validation
A pairplot matrix and an Age-distribution boxplot confirm that clusters which were defined on Income and Spending Score also separate meaningfully along Age — a sign of genuine structure in the data, not overfitting.

---

## Results — The 5 Customer Segments

| Cluster | Label | Income | Spending | Key Insight |
|---|---|---|---|---|
| 0 | **Careful / Frugal** | High | Low | High capacity, low engagement. Target with exclusive loyalty programmes. |
| 1 | **Standard / Middle Ground** | Average | Average | Consistent visitors. Retain with regular promotions. |
| 2 | **VIP / Target** | High | High | Prime segment for new launches and premium campaigns. |
| 3 | **Impulsive Shoppers** | Low | High | Emotionally driven purchases. Respond well to flash sales and time-limited offers. |
| 4 | **Sensible Spenders** | Low | Low | Conservative. Budget-friendly and value-for-money messaging works best. |

---

## Tech Stack

- **Python 3**
- `pandas` — data manipulation
- `matplotlib` / `seaborn` — visualisation
- `scikit-learn` — `KMeans`, `StandardScaler`, `silhouette_score`

---

## Project Structure

```
├── Mall_Customers.csv        # Source dataset
├── customer_segmentation.ipynb  # Full analysis notebook
└── README.md
```

---

## How to Run

```bash
# 1. Clone the repo
git clone https://github.com/your-username/customer-segmentation.git
cd customer-segmentation

# 2. Install dependencies
pip install pandas matplotlib seaborn scikit-learn jupyter

# 3. Launch the notebook
jupyter notebook customer_segmentation.ipynb
```

---

## Key Takeaways

- Feature scaling is not optional for distance-based algorithms — skipping it produces distorted clusters dominated by the highest-magnitude feature.
- Using two validation metrics (Elbow + Silhouette) removes ambiguity in K selection that a single method can't resolve alone.
- Age was intentionally left out of the clustering features. Its strong variation across clusters in the multivariate analysis confirms the segmentation captured real behavioural structure, not just noise.
