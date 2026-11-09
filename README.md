# Wine Quality Prediction System

A classroom prototype (Data Mining laboratory, Section B) that classifies a red-wine sample as **GOOD QUALITY** or **NEEDS IMPROVEMENT** from its physicochemical measurements.

## Problem
A small wine producer needs a consistent, preliminary way to screen wine samples using recorded lab measurements, before deciding which batches need further quality assessment.

## Dataset
UCI Machine Learning Repository, Wine Quality (red wine CSV):
https://archive.ics.uci.edu/dataset/186/wine+quality

## Prediction rule
- `quality >= 6` -> GOOD QUALITY
- `quality < 6` -> NEEDS IMPROVEMENT

The original `quality` score is the target only and is never used as an input feature (this avoids target leakage).

## Technologies
Python 3.10+, pandas, scikit-learn (Random Forest), joblib, Streamlit, GitHub.

## Installation and run steps
```bash
pip install -r requirements.txt
python train_model.py        # downloads data, trains model, creates wine_quality.csv and wine_model.pkl
streamlit run app.py         # opens the app at http://localhost:8501
```

In the app, download the sample input CSV, then upload it to see predictions. Results can be downloaded as a CSV.

## Limitations
- Trained only on one red-wine dataset; it may not generalize to other wine types, producers, regions, or testing conditions.
- The quality score comes from sensory ratings, which are subjective.
- Classes are not perfectly separable, so some GOOD wines will be missed and some weaker wines passed.
- This is a screening aid only. It does not replace laboratory testing, sensory evaluation, food-safety procedures, or professional quality-control decisions.
