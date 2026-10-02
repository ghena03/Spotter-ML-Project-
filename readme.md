# Freight Rate Prediction Challenge

This repository contains my solution for the Spotter Freight Rate Prediction assessment.

## Assessment Instructions

See `Freight_Rate_ML_Assessment.pdf` for the assessment instructions.

## Solution Overview

The solution includes:

- Exploratory data analysis and data-quality checks
- Time-based validation
- Feature engineering
- Missing-value handling
- Categorical feature encoding
- Model comparison and hyperparameter tuning
- Final predictions for 12,000 validation loads
- December 2025 predictions

### Validation Approach

I used a chronological validation split to better simulate predicting future loads:

- January–August 2025: training
- September–October 2025: development validation

After selecting the final model, it was retrained using all 48,000 labeled records before generating the final predictions.

### Final Model

The final model is a `HistGradientBoostingRegressor` using absolute-error loss.

The selected configuration achieved a development validation MAE of approximately **$110.15**.

### Final Predictions

The final predictions are provided in:

`validation_predictions.csv`

The file contains predictions for all 12,000 validation loads.

### December 2025 Predictions

The required December predictions are provided in:

`data/december_chart_inputs.csv`

The generated prediction chart is:

`scorer_results/candidate_december.png`

## Running the Scorer

Install the required dependencies:

```bash
python -m pip install -r requirements.txt
