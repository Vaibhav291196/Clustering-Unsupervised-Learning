# Candidate Segmentation using Unsupervised Learning

## 📌 Project Overview

This project focuses on customer/candidate segmentation using Unsupervised Machine Learning techniques.

The objective is to identify distinct groups of candidates based on their:

- Work Experience
- Current CTC
- Job Position
- Number of Promotions
- Graduation Year
- Compensation Trends

By clustering similar candidates together, the organization can:

- Personalize learning paths
- Recommend suitable courses
- Improve placement strategies
- Design targeted upskilling programs
- Increase candidate success rates

---

## 🎯 Business Problem

Scaler is an Ed-Tech platform that provides:

- Professional upskilling programs
- Career transition support
- Placement assistance

Since candidates come from diverse educational and professional backgrounds, a one-size-fits-all learning strategy is ineffective.

The goal is to:

> Segment candidates into meaningful groups and provide customized learning recommendations.

---

## 📊 Dataset Description

The dataset contains candidate-level information.

### Features

| Feature | Description |
|----------|------------|
| company_hash | Company Identifier |
| email_hash | Candidate Identifier |
| orgyear | Graduation Year |
| ctc | Current Compensation |
| job_position | Current Job Role |
| ctc_updated_year | Last Compensation Update |
| Experience | Total Experience |
| number_of_promotions | Promotion Count |
| ctc_category | Salary Category |
| com_jobcat_exp_avg_ctc | Average Salary Benchmark |

Dataset Size:

- 200K+ records
- Multiple industries
- Multiple job roles

---

# 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Scikit-Learn
- Matplotlib
- Seaborn
- SciPy
- Jupyter Notebook

---

# 📂 Project Workflow

## 1. Data Collection

Load candidate dataset.

```python
pd.read_csv()
```

---

## 2. Data Cleaning

Performed:

- Missing value handling
- Duplicate removal
- Feature validation
- Salary correction
- Datatype conversion

---

## 3. Feature Engineering

Created additional business features:

### Experience

```python
Experience = ctc_updated_year - orgyear
```

---

### Promotion-based Features

Used:

- Number of Promotions
- Experience-adjusted progression

---

### Salary Categories

Candidates categorized into multiple compensation bands.

---

### Benchmark Salary Feature

Created:

```python
Average Salary per Job Category
```

Used for candidate comparison.

---

## 4. Exploratory Data Analysis

Performed analysis on:

- Salary distribution
- Experience distribution
- Promotion patterns
- Job category trends
- Compensation growth

Visualizations:

- Histograms
- Boxplots
- KDE plots
- Correlation Heatmaps
- Cluster Visualizations

---

# ⚙️ Data Preprocessing

## Encoding

Categorical variables converted into numerical representations.

Methods:

- Label Encoding
- Category Mapping

---

## Feature Scaling

Clustering algorithms are highly sensitive to feature magnitude.

Used:

### StandardScaler

```python
StandardScaler()
```

Benefits:

- Mean = 0
- Standard Deviation = 1

Improves clustering quality.

---

# 🤖 Clustering Algorithms Used

---

## 1. K-Means Clustering

### Objective

Partition data into K clusters by minimizing intra-cluster variance.

Algorithm Steps:

1. Initialize centroids
2. Assign nearest cluster
3. Recompute centroids
4. Repeat until convergence

Implementation:

```python
KMeans()
```

### Initialization

Used:

```python
k-means++
```

for improved centroid selection.

---

## 2. Agglomerative Hierarchical Clustering

### Objective

Build clusters using a bottom-up approach.

Process:

- Start with individual observations
- Merge nearest clusters
- Continue until stopping condition

Implementation:

```python
AgglomerativeClustering()
```

Advantages:

- No centroid assumption
- Hierarchical interpretation

---

## 3. Gaussian Mixture Model (GMM)

### Objective

Model data as a mixture of Gaussian distributions.

Implementation:

```python
GaussianMixture()
```

Characteristics:

- Soft Clustering
- Probabilistic Assignment
- Handles overlapping clusters

Advantages over K-Means:

- Flexible cluster shapes
- Better modeling of real-world distributions

---

## 4. DBSCAN

### Density-Based Spatial Clustering

Implementation:

```python
DBSCAN()
```

Advantages:

- Detects arbitrary-shaped clusters
- Identifies noise points
- No need to specify K

---

# 🔍 Cluster Selection Methods

## Elbow Method

Used to identify optimal number of clusters.

Metric:

```python
WCSS
```

(Within Cluster Sum of Squares)

---

## Silhouette Score

Primary evaluation metric.

Formula:

```text
-1 ≤ Score ≤ 1
```

Interpretation:

| Score | Meaning |
|---------|---------|
| Close to 1 | Well-separated clusters |
| Around 0 | Overlapping clusters |
| Negative | Incorrect clustering |

---

# 📈 Model Evaluation

Models compared using:

### Silhouette Score

| Algorithm | Clusters |
|------------|----------|
| K-Means | 3 |
| Agglomerative Clustering | 3 |
| Gaussian Mixture Model | 3 |
| DBSCAN | Density-Based |

Observations:

- GMM achieved superior clustering quality.
- Agglomerative clustering provided interpretable cluster structures.
- K-Means offered faster training.
- DBSCAN effectively identified outliers.

---

# 📊 Cluster Interpretation

The final clusters represent different candidate groups.

Examples:

### Cluster 1

Early Career Professionals

Characteristics:

- Low experience
- Lower salary
- Fewer promotions

Recommendations:

- Foundation programs
- Career transition courses

---

### Cluster 2

Mid-Level Professionals

Characteristics:

- Moderate experience
- Stable compensation
- Growth potential

Recommendations:

- Specialized upskilling
- Interview preparation

---

### Cluster 3

Senior Professionals

Characteristics:

- High experience
- Higher compensation
- Leadership exposure

Recommendations:

- Advanced programs
- Leadership tracks

---

# 📉 Visualizations Included

- Salary Distribution
- Experience Distribution
- Correlation Matrix
- Elbow Curve
- Silhouette Analysis
- Cluster Scatter Plots
- Hierarchical Dendrograms
- Cluster Comparison Charts

---

# 📁 Project Structure

```text

Candidate-Segmentation/
│
├── Candidate_Clustering.ipynb
├── dataset/
│ └── scaler_clustering.csv
└── README.md

```

---

---

# 📋 Key Methods & Algorithms Used

## Data Processing

- Missing Value Treatment
- Feature Engineering
- Feature Scaling

## Exploratory Data Analysis

- Univariate Analysis
- Bivariate Analysis
- Correlation Analysis

## Clustering

- K-Means Clustering
- Agglomerative Clustering
- Gaussian Mixture Models (GMM)
- DBSCAN

## Cluster Evaluation

- Elbow Method
- Silhouette Score

## Visualization

- Scatter Plots
- Dendrograms
- Cluster Analysis Graphs

---

# 🔑 Business Impact

This solution helps:

- Personalize candidate learning journeys
- Improve recommendation systems
- Identify high-potential candidates
- Optimize placement strategies
- Increase candidate engagement
- Improve course completion rates

---

# 📚 Conclusion

This project demonstrates the application of Unsupervised Machine Learning for large-scale candidate segmentation. By leveraging K-Means, Agglomerative Clustering, GMM, and DBSCAN, meaningful candidate groups were identified, enabling targeted upskilling and personalized learning recommendations.

Among the evaluated approaches, Gaussian Mixture Models provided the most flexible and effective clustering performance, making them suitable for real-world candidate segmentation tasks.
