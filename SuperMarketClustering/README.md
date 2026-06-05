# Mall Customer Segmentation — Unsupervised Clustering

**K-Means · DBSCAN · Customer Segmentation · Marketing Analytics**

A complete unsupervised machine learning project segmenting mall customers into actionable marketing groups using K-Means and DBSCAN clustering. Achieved **12% improvement in silhouette score** through systematic feature engineering.

---

## 📊 Dataset

| Property | Details |
|----------|---------|
| **Source** | SuperMarketClustering.csv |
| **Size** | 200 rows × 5 columns |
| **Features** | CustomerID, Gender, Age, Annual Income (k$), Spending Score (1-100) |
| **Target** | None (unsupervised learning) |
| **Missing Values** | None |

---

## 🛠 Preprocessing

| Step | Action |
|------|--------|
| Dropped | CustomerID (irrelevant identifier) |
| Encoded | Gender → binary (Male=1, Female=0) |
| Capped | Annual Income at $95k to reduce outlier distortion |
| Scaled | StandardScaler for DBSCAN only (K-Means performed better on raw data) |

### Feature Engineering Experiments

| Version | Features | Best Silhouette | Outcome |
|---------|----------|-----------------|---------|
| Original | Gender, Age, Income, Spending | 0.415 (k=6) | Baseline |
| No Gender | Age, Income, Spending | 0.443 (k=7) | Gender was noise |
| Capped Income | All features, Income ≤95k | 0.464 (k=5) | Outliers removed |
| **Capped + No Gender** | **Age, Capped Income, Spending** | **0.465 (k=5)** | **Best — final model** |

**Key finding:** Gender added noise, not signal. Capping income removed distortion from high-income outliers.

---

## 🤖 K-Means Clustering

### Elbow Method
WCSS plotted for k=1-10 — elbow identified at k=4-6.

### Final Model

| Parameter | Value |
|-----------|-------|
| Algorithm | K-Means (k-means++, random_state=42) |
| Clusters | 5 |
| Features | Age, Annual Income (capped $95k), Spending Score |
| **Silhouette Score** | **0.465** (12% improvement over baseline 0.415) |

### Cluster Interpretations

| Cluster | Income | Spending | Name | Marketing Strategy |
|---------|--------|----------|------|---------------------|
| 1 | High | High | **Premium** | Loyalty rewards, VIP treatment |
| 2 | High | Low | **Savers** | Stock necessities, be reliable |
| 3 | Average | Average | **Casuals** | Moderate upselling (largest segment) |
| 4 | Low | High | **Off People** | Discounts, flash sales, aspirational |
| 5 | Low | Low | **Budget Conscious** | Value bundles, no-frills messaging |

---

## 🔍 DBSCAN Comparison

### Unscaled Data
- Best: eps=15, min_samples=7 → 4 clusters, silhouette=0.350
- Underperformed K-Means

### Scaled Data (StandardScaler)
- Best: eps=1.1, min_samples=7 → 6 clusters, 3 noise points, **silhouette=0.465**
- Matched K-Means performance with more clusters

### Unique DBSCAN Discovery
**"Too Old Rich"** — Older high-income customers with high spending
- Separated by Age factor, invisible in 2D Income vs Spending plots
- **Business insight:** Need relationship-based retention (respect, service, assistance), not discounts

### DBSCAN Limitation
Required significant parameter tuning and scaling to match K-Means. For this dataset, K-Means provided more stable, interpretable clusters with less effort.

---

## 🔑 Key Findings

| Finding | Implication |
|---------|-------------|
| Gender is not useful for segmentation | Removing it improved cluster quality |
| Income capping ($95k) removed outlier distortion | Cleaner cluster boundaries |
| K-Means k=5 (capped income, no Gender) | Best balance of validity + interpretability |
| DBSCAN matched but didn't beat K-Means | Revealed age-separated high-wealth segment |
| Silhouette ~0.46 | Customer base is continuous, not sharply divided (typical for consumer data) |

---

## 📈 Models Tested

| Algorithm | Configurations |
|-----------|----------------|
| **K-Means** | k=4,5,6,7 × 4 feature sets = 16 configurations |
| **DBSCAN** | eps sweep (3-20 raw, 0.5-2.0 scaled) × min_samples (3-7) |

---

## 📚 Libraries Used

| Library | Purpose |
|---------|---------|
| **pandas, numpy** | Data manipulation and analysis |
| **matplotlib, seaborn** | Data visualization (2D plots, heatmaps, cluster visuals) |
| **scikit-learn** | KMeans, DBSCAN, StandardScaler, silhouette_score |
| **mpl_toolkits.mplot3d** | 3D plotting (exploratory only — not used in final model) |

---

## 💼 Business Recommendations

| Segment | Strategy |
|---------|----------|
| **Premium** | Loyalty program invitations, personalized offers |
| **Savers** | "Essentials" marketing, reliable stock |
| **Casuals** | Moderate upselling, category expansion |
| **Off People** | Flash sales, discounts, aspirational branding |
| **Budget Conscious** | Value bundles, bulk discounts, family offers |
| **Too Old Rich** (DBSCAN) | Relationship-based service, carry-out assistance, senior respect programs |

---

## 📈 Results Summary

Model	Silhouette	Clusters	Notes\
K-Means (baseline)	0.415	6	Original features\
K-Means (final)	0.465	5	Capped income, no Gender\
DBSCAN (unscaled)	0.350	4	Underperformed\
DBSCAN (scaled)	0.465	6	Matched K-Means, revealed "Too Old Rich"\
Conclusion: K-Means with k=5 on capped income (no Gender) achieved the best balance of statistical validity and business interpretability. DBSCAN validated the structure and suggested age-separated high-wealth customers deserve unique treatment.

## 📬 Connect

- [**GitHub**](github.com/amirjavad2)
- [**LinkedIn**](linkedin.com/in/amirjkhafaji)
- [**Email**](amirjavad.khafaji@gmail.com)

---
Part of [DataScienceML](https://github.com/amirjavad2/DataScienceML) Portfolio
