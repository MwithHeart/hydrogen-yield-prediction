## Green Hydrogen Production Forecasting using Machine Learning 🚀
This repository contains a complete machine learning project that predicts hydrogen gas production from a solar-powered electrolyzer. 
Using real-world sensor data (like temperature, current, and voltage), this project shows how to transition from a simple baseline model to an advanced Gradient Boosting model (XGBoost) to achieve 93.75% prediction accuracy.


## 📊 Project Overview
Predicting green hydrogen yield is critical for scaling up renewable energy systems and balancing power grids. However, electrolyzers are highly dynamic systems influenced by changing weather, solar cycles, and thermal losses.
This project explores three different machine learning approaches to find the best way to handle these complex patterns.

## 🛠️ The Tech Stack
* Language: Python
* Core Libraries: scikit-learn, xgboost, random forest, linear regression, pandas, numpy
* Visualization: matplotlib, seaborn 


## 📈 Model Performance & Progression
Three distinct model architectures were tested to see how well they could map the underlying chemical and electrical patterns of the dataset.

| Machine Learning Model | R² Score (Accuracy) | Mean Absolute Error (MAE) | Engineering Takeaway |
|------------------------|---------------------|---------------------------|----------------------|
| Linear Regression | 79.11% | 7.72 × 10⁻⁵ grams | Captures the core linear trend of Faraday's Law, but unable to bend around non-linear temperature shifts. |
| Random Forest | 83.37% | 7.29 × 10⁻⁵ grams | Uses an ensemble of decision trees to capture curves and smooth out sudden solar spikes. |
| XGBoost | 93.75% | 4.47 × 10⁻⁵ grams | Sequentially corrects its own mistakes to deliver peak accuracy, cutting the baseline error nearly in half. |

------------------------------
## 🧠 Key Data Engineering Insights
   1. The Data Splitting Trap (Data Leakage): Because this dataset tracks a process over time, the training data and testing data were properly isolated.  
   2. Feature Duplication: Correlation analysis showed that current and power had a near-perfect correlation of 0.9996. This aligns with electrical physics (Power = Current × Voltage). Tree models like Random Forest and XGBoost successfully handled this collinearity without losing predictive stability.
  

------------------------------
## 📁 Repository Structure

├── data/
│   └── electrolyzer_sensor_data.csv        # Raw sensor log file
├── notebooks/
│   └── hydrogen_prediction_pipeline.ipynb  # Clean, end-to-end Python notebook
├── outputs/
│   ├── xgboost_predictions_over_time.png   # Performance line chart
│   └── linear_regression_predictions.png   # Predicted vs. Actual scatter plot
└── README.md                               # Project documentation (this file)

------------------------------
## 🚀 How to Run This Project

   1. Clone the repository:
   
   git clone https://github.com
   cd hydrogen-yield-prediction
   
   2. Install requirements:
   
   pip install scikit-learn xgboost pandas numpy matplotlib seaborn
   
   3. Run the notebook: Open notebooks/hydrogen_prediction_pipeline.ipynb in Jupyter Notebook or VS Code and run all cells.




