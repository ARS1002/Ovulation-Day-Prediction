# Ovulation Day Prediction

Predict the estimated day of ovulation from menstrual-cycle data. This is the code behind the paper **"Ovulation Day Prediction Using Machine Learning"** (ICCCNet 2023, Springer), where I'm the first author: [doi.org/10.1007/978-981-97-2671-4_60](https://doi.org/10.1007/978-981-97-2671-4_60).

## What the notebook does

- **Data:** about 3,000 cycle records with `LengthofCycle`, `LengthofLutealPhase` and the target `EstimatedDayofOvulation`
- **Exploration:** distribution of ovulation day, and how it varies with cycle length (histogram, scatter, box plot)
- **Model 1 – Mixed linear model** (statsmodels): cycle length and luteal-phase length as fixed effects, grouped by cycle length
- **Model 2 – Gaussian hidden Markov model** (hmmlearn) with 3 states
- **Evaluation:** 5-fold cross-validation with MSE, RMSE and R²

## Results

Across the 5 folds the notebook prints an RMSE of 2.65–2.78 days. R² stays close to 0, so cycle length and luteal-phase length alone explain little of the variation in ovulation day.

## How to run

1. Open `ovulation day prediction.ipynb` in Google Colab or Jupyter
2. Upload the dataset as `ovulation_dataset.csv` (the path in the first cell is `/content/ovulation_dataset.csv`)
3. `pip install pandas numpy statsmodels scikit-learn hmmlearn matplotlib seaborn`, then run all cells

The dataset is not included in this repo.

## Tech

Python · statsmodels · hmmlearn · scikit-learn · pandas · Matplotlib · Seaborn
