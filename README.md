# 📊 Data Science & Machine Learning Portfolio

**Amir Javad Khfaji** · Software Engineering Student · ML Enthusiast

Welcome to my central hub for all my Data Science and Machine Learning work. Every project here is built from scratch, documented properly, and focused on real results — not just notebooks.

---

## 📁 What You'll Find Here

| Type | Description |
|------|-------------|
| ✅ **Complete ML projects** | End-to-end: cleaning → EDA → feature engineering → modeling → evaluation |
| 📊 **Classification & Regression** | Supervised learning with cross-validation |
| 🧹 **Data cleaning pipelines** | Real-world messy data handling |
| 📈 **Visualization & reporting** | Clear charts and actionable insights |

---

## 🚀 Projects

<!-- ============================================ -->
<!-- ADD NEW PROJECTS BELOW THIS LINE              -->
<!-- ============================================ -->

### 🚢 Titanic Survival Prediction

**Status:** ✅ Complete  
**Accuracy:** 84.9% | **Cross-validation:** 82.7%  
**Tech:** Python · pandas · scikit-learn · XGBoost · matplotlib · seaborn

A complete classification pipeline predicting passenger survival on the Titanic. This project demonstrates data cleaning, feature engineering, model comparison, and hyperparameter tuning on a small dataset where feature engineering matters more than complex models.

**Key achievements:**
- Cleaned 177 missing Age values (imputed by Pclass median)
- Engineered Title from Name — became strongest predictor (-0.549 correlation), beating Sex
- Tested 9 models with 5-fold cross-validation
- SVC achieved 84.9% test accuracy with stable 82.7% CV mean
- Hyperparameter tuning provided no benefit — learned when to stop

📁 [View project folder](./Titanic/)  
📖 [Detailed README](./Titanic/README.md)

---

### 🛒 Mall Customer Segmentation

**Status:** ✅ Complete  
**Best Silhouette:** 0.465 | **Improvement:** +12% over baseline  
**Tech:** Python · pandas · scikit-learn · K-Means · DBSCAN · matplotlib · seaborn

An unsupervised learning project segmenting mall customers into actionable marketing groups. Systematically tested 16 K-Means configurations and DBSCAN with parameter sweeps to find the optimal clustering approach.

**Key achievements:**
- Removed Gender — proved it added noise, not signal (improved silhouette from 0.415 → 0.443)
- Capped Income at $95k — removed outlier distortion (further improved to 0.465)
- Created 5 customer segments (Premium, Savers, Casuals, Off People, Budget Conscious)
- DBSCAN revealed a 6th segment: "Too Old Rich" — older high-income customers invisible in 2D plots
- Delivered specific marketing strategies for each segment

📁 [View project folder](./SuperMarketClustering/)  
📖 [Detailed README](./SuperMarketClustering/README.md)

<!-- ============================================ -->
<!-- ADD NEW PROJECTS ABOVE THIS LINE              -->
<!-- ============================================ -->

---

## 🛠 Core Skills

| Category | Tools & Technologies |
|----------|---------------------|
| **Languages** | Python (advanced) |
| **ML & Data** | scikit-learn, XGBoost, pandas, numpy, matplotlib, seaborn |
| **Tools** | JupyterLab, Git, VS Code, Linux |
| **Concepts** | Data cleaning, EDA, feature engineering, cross-validation, classification |

---

## 📫 Let's Connect

- [**GitHub**](https://github.com/amirjavad2)
- [**LinkedIn**](https://www.linkedin.com/in/amirjkhafaji/)
- [**Email:**](amirjavad.khafaji@gmail.com)

---

*Last updated: May 2026*  
> *"If it's working don't touch it"*
