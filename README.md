# Taxi Fare Prediction using Linear Regression

A machine learning project that predicts taxi fares based on trip-related features, using the Chicago Taxi Trips dataset from Google's Machine Learning Crash Course.

## Overview

This project explores how well a simple linear regression model can predict taxi fares using trip data. The main goal was to understand the relationship between trip distance, trip duration, and fare amount, and to see how adding more features affects model performance.

## Dataset

The dataset used is the **Chicago Taxi Trips** dataset, provided as part of Google's Machine Learning Crash Course. It contains records of taxi trips including distance traveled, time taken, and the fare charged.

## Features

Key columns used from the dataset:

- `TRIP_MILES` – distance of the trip in miles
- `TRIP_SECONDS` – duration of the trip in seconds (used to derive `TRIP_MINUTES`)
- `TRIP_MINUTES` – engineered feature, duration in minutes
- `FARE` – target variable, the fare amount for the trip

## Approach

1. Loaded and explored the dataset to understand its structure.
2. Checked for missing values to ensure data quality.
3. Selected relevant features for predicting fare.
4. Analyzed relationships between features using correlation values and scatter plots.
5. Engineered a new feature, `TRIP_MINUTES`, from `TRIP_SECONDS`.
6. Built and trained linear regression models using Keras.
7. Compared model performance using RMSE.
8. Visualized predicted fares against actual observed fares.

## Models

Two experiments were run to compare feature combinations:

| Experiment | Features Used | Description |
|---|---|---|
| Model 1 (Baseline) | `TRIP_MILES` | Single-feature linear regression |
| Model 2 | `TRIP_MILES`, `TRIP_MINUTES` | Two-feature linear regression |

Both models were built using **Keras**, trained with the **RMSprop** optimizer, and used **Mean Squared Error (MSE)** as the loss function. Model performance was evaluated using **RMSE**.

## Results

- `TRIP_MILES` on its own is a strong predictor of taxi fare.
- Adding `TRIP_MINUTES` as a second feature gave a small improvement over the baseline model.
- The two-feature model achieved a slightly lower RMSE compared to the single-feature model.

These results are based on a fairly simple dataset and model, so they should be seen as a learning exercise rather than a benchmark for real-world fare prediction.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Plotly
- TensorFlow / Keras
- Google ML Education (`ml_edu`) utilities

## Project Structure

```
taxi-fare-prediction/
│
├── taxi_fare_prediction.ipynb   # Main notebook with all analysis and models
└── README.md                    # Project documentation
```

## How to Run

1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/taxi-fare-prediction.git
   cd taxi-fare-prediction
   ```

2. Install the required dependencies:
   ```bash
   pip install pandas numpy matplotlib plotly tensorflow
   ```

3. Open the notebook:
   ```bash
   jupyter notebook taxi_fare_prediction.ipynb
   ```

4. Run the cells in order to reproduce the analysis and model training.

## Future Improvements

- Experiment with additional features such as pickup/drop-off location or time of day.
- Try non-linear models (e.g., decision trees or gradient boosting) to see if they capture patterns better than linear regression.
- Perform more thorough feature engineering and outlier handling.
- Use cross-validation for a more reliable performance estimate.

---

This project was built as a hands-on exercise to practice linear regression and feature engineering concepts from Google's Machine Learning Crash Course.
