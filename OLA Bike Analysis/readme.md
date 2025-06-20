# Ola Bike Ride Demand Forecasting 🚴‍♂️📈

This project forecasts ride request demand for the Ola Bike ride-sharing service using machine learning techniques. It analyzes historical ride data along with environmental and temporal features to predict hourly ride requests, helping improve resource allocation and service reliability.

## 📌 Project Overview

Bike-sharing systems have become essential to modern urban transportation. Accurately forecasting demand ensures the right number of bikes are available at the right time. This project uses historical data to develop machine learning models for high-accuracy demand forecasting.

## 📊 Features Used

- datetime (converted to hour, month, weekday, etc.)
- temperature and “feels like” temperature
- humidity
- season
- weather condition
- holiday and working day indicators

## 🛠️ Technologies Used

- Python 3.8
- Jupyter Notebook / Google Colab
- Pandas, NumPy for data handling
- Matplotlib, Seaborn for visualization
- Scikit-learn, XGBoost for machine learning

## 📁 Dataset Description

The dataset contains 10,886 hourly ride request records from 2011 and 2012. The target variable is:
- `count`: the number of bike ride requests per hour.

## 🧹 Data Preprocessing

- Converted datetime into multiple temporal features
- One-hot encoded categorical variables
- Removed features with low correlation
- Applied log transformation to normalize target variable

## 🔍 Exploratory Data Analysis

- Higher demand observed during weekdays and office hours
- Peak demand in summer months (June–August)
- Optimal demand occurs around 30–40°C temperatures
- High correlation between `temp` and `atemp`

## 🤖 Models Implemented

- Linear Regression
- Decision Tree Regressor
- K-Nearest Neighbors (KNN) with GridSearchCV
- Random Forest Regressor (with hyperparameter tuning)
- XGBoost Regressor (with early stopping and tuning)

## 🏆 Best Model Performance

| Model               | R² Score  |
|--------------------|-----------|
| Random Forest      | 0.99995   |
| XGBoost            | 0.9985    |
| KNN (Hypertuned)   | 0.9932    |
| Decision Tree      | 0.9903    |
| Linear Regression  | 0.8655    |

The Random Forest Regressor achieved the best performance with an R² score of 99.995%.

## 🚧 Limitations & Future Work

- Historical data only (2011–2012); no real-time integration
- Dataset limited to one region
- Deep learning models not yet applied

🔮 Future improvements:
- Integrate real-time weather and traffic APIs
- Expand to multiple cities or regions
- Use LSTM or other time series deep learning models

## 📬 Feedback

Feel free to fork, raise issues, or suggest improvements via pull requests. Contributions are welcome!
