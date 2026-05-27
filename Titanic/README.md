# Titanic Survival Prediction

**84.9% Accuracy | 82.7% Cross-Validation**

Python · pandas · scikit-learn · XGBoost · matplotlib · seaborn

---

## Quick Summary

Built a classification model predicting passenger survival on the Titanic. Feature engineering (especially extracting Title from Name) proved more valuable than complex algorithms.

## Key Results

| Metric | Score |
|--------|-------|
| Test Accuracy | 84.9% |
| 5-Fold CV Mean | 82.7% |
| Best Model | SVC (default params) |

## What I Did

- Cleaned 177 missing Age values (median by Pclass)
- Extracted Title from Name → became strongest predictor (-0.549 correlation)
- Tested 9 models with cross-validation
- Learned: hyperparameter tuning doesn't always help

## Files

- `notebooks/titanic_analysis.ipynb` – Full analysis
- `data/` – Raw datasets
- `requirements.txt` – Dependencies

## Run It

```bash
pip install -r requirements.txt
jupyter notebook notebooks/titanic_analysis.ipynb
```
