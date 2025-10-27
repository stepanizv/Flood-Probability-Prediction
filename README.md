# Flood Probability Prediction

## Project Structure
- `model.ipynb` — end-to-end notebook covering data exploration, feature engineering, model training, and submission generation.
- `train.csv`, `test.csv`, `sample_submission.csv` — datasets with `FloodProbability` as the regression target in the training set.
- `our_submission.csv` — latest exported predictions generated from the notebook.
- `static/` — photo assets that summarize observations of the model.

## Notebook Highlights
The notebook walks through the following stages:
1. **Exploratory Data Analysis**  
   - Basic dataset profiling, summary statistics, and missing-value checks.  
   - Univariate feature distributions and correlation heatmaps focused on the most predictive features.
2. **Feature Engineering**  
   - Removes identifier columns, scales numerical features, and creates interaction terms to capture non-linear relationships.
3. **Model Benchmarking**  
   - Trains and evaluates several regressors (`RandomForestRegressor`, `GradientBoostingRegressor`, `XGBRegressor` when available) with metrics such as RMSE, MAE, and R² on an internal validation split.
4. **Best Model Selection & Training**  
   - Retrains the top-performing model on the full training dataset and analyzes feature importance when supported.
5. **Submission Generation**  
   - Produces `submission.csv`, pairing each `id` in `test.csv` with the predicted `FloodProbability`.