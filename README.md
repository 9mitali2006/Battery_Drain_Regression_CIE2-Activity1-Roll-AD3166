# 📱 Smartphone Battery Drain Prediction Using Linear Regression

## 1. Project Overview

Smartphones have become an essential part of our daily lives. However, battery consumption varies depending on several factors, such as application usage, screen time, mobile data consumption, and the number of applications installed.

This project focuses on predicting daily smartphone battery consumption using **Machine Learning – Linear Regression**.

The project implements two regression techniques:

1. **Simple Linear Regression:** Predicts battery drain using Screen On Time as the only independent variable.
2. **Multiple Linear Regression:** Predicts battery drain using four independent variables:
   - App Usage Time
   - Screen On Time
   - Data Usage
   - Number of Apps Installed

The performance of both models is evaluated and compared using different regression evaluation metrics.

## 2. Problem Statement

To develop a Machine Learning model that predicts the daily battery consumption of a smartphone based on user behavior and smartphone usage patterns.

The objective is to understand how different usage-related factors influence battery consumption and determine whether using multiple independent variables improves prediction accuracy.

## 3. Project Objectives

- Analyze smartphone usage patterns.
- Perform Exploratory Data Analysis (EDA).
- Identify relationships between smartphone usage features and battery consumption.
- Implement Simple Linear Regression.
- Implement Multiple Linear Regression.
- Understand the impact of independent variables on battery drain.
- Evaluate model performance using regression metrics.
- Compare Simple and Multiple Linear Regression.
- Predict battery consumption for a new smartphone user.

## 4. Dataset Description

**Dataset Name:** User Behavior Dataset

**Total Records:** 700

**Total Attributes:** 11

The dataset contains information about smartphone users, their device details, application usage, screen time, data consumption, and battery drain.

### Dataset Attributes

| Attribute | Description |
|---|---|
| User ID | Unique identification number of the user |
| Device Model | Smartphone model used by the user |
| Operating System | Operating system of the smartphone |
| App Usage Time (min/day) | Daily application usage time in minutes |
| Screen On Time (hours/day) | Total screen-on time per day |
| Battery Drain (mAh/day) | Daily battery consumption in mAh |
| Number of Apps Installed | Total number of applications installed |
| Data Usage (MB/day) | Daily mobile data consumption in MB |
| Age | Age of the user |
| Gender | Gender of the user |
| User Behavior Class | User behavior category |

### Selected Features

For this project, four independent variables are selected.

**Independent Variables (X):**
- App Usage Time (min/day)
- Screen On Time (hours/day)
- Data Usage (MB/day)
- Number of Apps Installed

**Dependent Variable (Y):**
- Battery Drain (mAh/day)

Battery Drain is the target variable that the model tries to predict.

## 5. Technologies Used

| Technology | Purpose |
|---|---|
| Python | Programming language |
| Pandas | Data loading and manipulation |
| NumPy | Numerical computations |
| Matplotlib | Data visualization |
| Scikit-learn | Machine Learning model development |
| Google Colab / Jupyter Notebook | Development environment |

## 6. Project Workflow

The project follows these steps:

1. Import required Python libraries.
2. Load the smartphone user behavior dataset.
3. Perform initial dataset exploration.
4. Check missing values and duplicate records.
5. Understand dataset structure and data types.
6. Perform Exploratory Data Analysis (EDA).
7. Calculate statistical summaries.
8. Perform correlation analysis.
9. Visualize relationships between independent variables and battery drain.
10. Split the dataset into training and testing datasets.
11. Implement Simple Linear Regression.
12. Evaluate Simple Linear Regression.
13. Implement Multiple Linear Regression.
14. Evaluate Multiple Linear Regression.
15. Compare both models.
16. Analyze residuals and actual vs predicted values.
17. Predict battery consumption for a new user.

## 7. Exploratory Data Analysis (EDA)

Exploratory Data Analysis is performed to understand the dataset before training the Machine Learning models.

The following operations are performed:

### 7.1 Dataset Exploration
- Display the first five records using `head()`.
- Display the last five records using `tail()`.
- Understand the number of rows and columns.

### 7.2 Missing Value Detection

The `isnull().sum()` function is used to identify missing values in each column.

### 7.3 Duplicate Value Detection

The `duplicated().sum()` function is used to identify duplicate records.

### 7.4 Dataset Information

The `info()` function provides information about:
- Number of records.
- Column names.
- Data types.
- Non-null values.
- Memory usage.

### 7.5 Statistical Analysis

The `describe()` function is used to calculate:
- Mean
- Standard Deviation
- Minimum
- Maximum
- 25th Percentile
- 50th Percentile
- 75th Percentile

### 7.6 Correlation Analysis

Correlation is calculated to understand the relationship between independent variables and battery drain.

The correlation values obtained are:

| Feature | Correlation with Battery Drain |
|---|---:|
| Number of Apps Installed | 0.961853 |
| App Usage Time | 0.956385 |
| Screen On Time | 0.948983 |
| Data Usage | 0.932276 |

All four selected features show a strong positive correlation with battery drain in this dataset.

### 7.7 Data Visualization

The following visualizations are performed:

- Correlation Heatmap
- Scatter Plot: App Usage Time vs Battery Drain
- Scatter Plot: Screen On Time vs Battery Drain
- Scatter Plot: Data Usage vs Battery Drain
- Scatter Plot: Number of Apps Installed vs Battery Drain

These visualizations help understand how smartphone usage characteristics are related to battery consumption.

## 8. Machine Learning Algorithms

### 8.1 Simple Linear Regression

Simple Linear Regression is a supervised Machine Learning algorithm used to predict a continuous numerical value using one independent variable.

In this project:

- Independent Variable (X): Screen On Time (hours/day)
- Dependent Variable (Y): Battery Drain (mAh/day)

**Mathematical Equation:**

`Y = mX + C`

Where:

- Y = Predicted battery drain
- X = Screen On Time
- m = Slope or coefficient
- C = Intercept

The model learns the relationship between screen-on time and battery consumption.

**Model Implementation:**

The `LinearRegression()` class from Scikit-learn is used to create the model.

The model is trained using the `fit()` function and predictions are generated using the `predict()` function.

### 8.2 Multiple Linear Regression

Multiple Linear Regression is used to predict a continuous numerical value using two or more independent variables.

In this project, four independent variables are used.

**Independent Variables:**
1. App Usage Time
2. Screen On Time
3. Data Usage
4. Number of Apps Installed

**Mathematical Equation:**

`Y = C + m1X1 + m2X2 + m3X3 + m4X4`

Where:

- Y = Predicted battery drain
- C = Intercept
- X1 = App Usage Time
- X2 = Screen On Time
- X3 = Data Usage
- X4 = Number of Apps Installed
- m1, m2, m3, m4 = Regression coefficients

The model considers all four features together to predict battery consumption.

## 9. Model Training and Testing

The dataset is divided into two parts using the `train_test_split()` function.

**Train-Test Split:**

- Training Data: 80%
- Testing Data: 20%
- Random State: 42

### Why Train-Test Split?

The training dataset is used to teach the model the relationship between input features and the target variable.

The testing dataset is used to evaluate how well the trained model predicts values on data that was not used during training.

The same train-test splitting configuration is used for both models.

## 10. Model Evaluation Metrics

Three evaluation metrics are used to measure model performance.

### 10.1 Mean Absolute Error (MAE)

MAE calculates the average absolute difference between actual and predicted values.

**Formula:**

`MAE = (1/n) × Σ |Actual - Predicted|`

A lower MAE indicates better prediction performance.

### 10.2 Mean Squared Error (MSE)

MSE calculates the average squared difference between actual and predicted values.

**Formula:**

`MSE = (1/n) × Σ (Actual - Predicted)²`

A lower MSE indicates better prediction performance. It penalizes larger prediction errors more heavily because the errors are squared.

### 10.3 R² Score (Coefficient of Determination)

R² measures how much of the variation in the target variable is explained by the regression model.

**Formula:**

`R² = 1 - (SS_res / SS_tot)`

Where:

- SS_res = Sum of Squared Residuals
- SS_tot = Total Sum of Squares

An R² score closer to 1 indicates that the model explains a larger proportion of the variation in the target variable.

## 11. Model Results

Both models are evaluated using the same testing dataset.

### Simple Linear Regression Results

| Evaluation Metric | Result |
|---|---:|
| Mean Squared Error (MSE) | 66,751.94 |
| Mean Absolute Error (MAE) | 205.78 |
| R² Score | 0.8924 |
| R² Percentage | 89.24% |

### Multiple Linear Regression Results

| Evaluation Metric | Result |
|---|---:|
| Mean Squared Error (MSE) | 35,191.75 |
| Mean Absolute Error (MAE) | 157.31 |
| R² Score | 0.9433 |
| R² Percentage | 94.33% |

## 12. Model Comparison

The performance of Simple Linear Regression and Multiple Linear Regression is compared below.

| Metric | Simple Linear Regression | Multiple Linear Regression |
|---|---:|---:|
| MSE | 66,751.94 | 35,191.75 |
| MAE | 205.78 | 157.31 |
| R² Score | 0.8924 | 0.9433 |

### Observations

- Multiple Linear Regression has a lower MSE than Simple Linear Regression.
- Multiple Linear Regression has a lower MAE, indicating smaller average prediction errors.
- Multiple Linear Regression achieves a higher R² score.
- Using four independent variables provides better prediction performance than using only Screen On Time on the selected test dataset.

**Conclusion:** Multiple Linear Regression performs better than Simple Linear Regression for this dataset based on the selected evaluation metrics.

## 13. Residual Analysis

Residual analysis is performed to understand the prediction errors made by the regression model.

**Residual = Actual Value - Predicted Value**

Two types of visual analysis are performed:

### 13.1 Residual Plot

The residual plot displays predicted values on the X-axis and residuals on the Y-axis.

A horizontal reference line at zero is added.

It helps identify patterns in prediction errors and assess whether the errors are randomly distributed.

### 13.2 Actual vs Predicted Plot

This plot compares actual battery drain values with predicted battery drain values.

A diagonal reference line represents perfect predictions.

Points closer to the reference line indicate more accurate predictions.

## 14. Regression Coefficients

The coefficients obtained from Multiple Linear Regression are:

| Feature | Regression Coefficient |
|---|---:|
| App Usage Time (min/day) | 1.400023 |
| Screen On Time (hours/day) | 54.253409 |
| Data Usage (MB/day) | 0.072643 |
| Number of Apps Installed | 12.832561 |

**Intercept:** 138.090335

### Interpretation

Each coefficient represents the estimated change in predicted battery drain for a one-unit increase in that feature, while keeping the other features constant.

For example:

- A one-minute increase in app usage time is associated with an estimated increase of 1.40 mAh/day in battery drain.
- A one-hour increase in screen-on time is associated with an estimated increase of 54.25 mAh/day in battery drain.
- A one-MB increase in data usage is associated with an estimated increase of 0.073 mAh/day in battery drain.
- One additional installed app is associated with an estimated increase of 12.83 mAh/day in battery drain.

These are model-estimated relationships, not proof of direct causation.

## 15. Prediction for a New User

After training the Multiple Linear Regression model, a prediction is performed for a new smartphone user.

**Input Details:**

| Feature | Value |
|---|---:|
| App Usage Time | 300 min/day |
| Screen On Time | 5.5 hours/day |
| Data Usage | 1200 MB/day |
| Number of Apps Installed | 50 |

**Predicted Battery Drain:**

`1585.29 mAh/day`

The trained model uses the four input features to estimate the user's daily battery consumption.

## 16. How to Run the Project

### Prerequisites

Make sure Python is installed on your system.

Install the required libraries using:

```bash
pip install pandas numpy matplotlib scikit-learn jupyter
```

### Step 1: Clone the Repository

```bash
git clone <your-repository-url>
```

### Step 2: Navigate to the Project Directory

```bash
cd smartphone-battery-drain-prediction
```

### Step 3: Add the Dataset

Place the `user_behavior_dataset.csv` file in the project directory.

### Step 4: Open the Jupyter Notebook

```bash
jupyter notebook
```

Alternatively, upload the notebook to Google Colab.

### Step 5: Update the Dataset Path

Update the CSV file path in the dataset loading cell:

```python
df = pd.read_csv("user_behavior_dataset.csv")
```

### Step 6: Execute the Notebook

Run all notebook cells sequentially to perform:

- Data exploration
- Data visualization
- Model training
- Model evaluation
- Model comparison
- Battery drain prediction

## 17. Project Structure

```text
Smartphone-Battery-Drain-Prediction/
│
├── RCA_CIE2_1(2).ipynb
│
├── user_behavior_dataset.csv
│
└── README.md
```

## 18. Conclusion

This project successfully demonstrates the implementation of Simple Linear Regression and Multiple Linear Regression for predicting smartphone battery consumption.

The dataset contains 700 records and 11 attributes. Four independent variables are selected to predict Battery Drain (mAh/day).

Simple Linear Regression, using Screen On Time as the predictor, achieves an R² score of 89.24%.

Multiple Linear Regression, using App Usage Time, Screen On Time, Data Usage, and Number of Apps Installed, achieves an R² score of 94.33%.

The comparison shows that Multiple Linear Regression performs better on the selected test dataset, with lower MSE and MAE and a higher R² score.

The project demonstrates important Machine Learning concepts, including:

- Supervised Learning
- Regression
- Simple Linear Regression
- Multiple Linear Regression
- Exploratory Data Analysis
- Correlation Analysis
- Train-Test Split
- Regression Coefficients
- Intercept and Slope
- Model Prediction
- Residual Analysis
- Model Evaluation

The project provides practical understanding of how regression algorithms can be used to analyze user behavior and estimate smartphone battery consumption.

**Note:** The reported performance is based on the selected dataset and train-test split. Further validation on unseen data and checking regression assumptions would be necessary before using this model in a real-world application.

## 19. Future Scope

The project can be further improved by:

- Including additional smartphone usage parameters.
- Testing other regression algorithms.
- Performing cross-validation.
- Applying feature selection techniques.
- Analyzing outliers and regression assumptions.
- Developing a user-friendly interface for real-time battery drain prediction.
- Deploying the trained model as a web application.

---

**Project Title:** Smartphone Battery Drain Prediction Using Linear Regression

**Domain:** Machine Learning

**Algorithm:** Simple Linear Regression and Multiple Linear Regression

**Target Variable:** Battery Drain (mAh/day)
Submission GitHub ID: https://github.com/9mitali2006

Student Repository URL: https://github.com/9mitali2006/Battery_Drain_Regression_AD3166

Project Name: Smartphone Battery Drain Prediction Using Linear Regression

Repository Visibility: Public

This repository contains the completed machine learning project, including the Jupyter Notebook, dataset (where redistribution is permitted), project documentation, and supporting files required for academic evaluation.

The repository is maintained by the student for submission and review as part of the academic activity.
