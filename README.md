# Stock-Prediction

# Apple Stock Market Prediction M.L

## Project Overview
This project aims to predict the stock prices of Apple Inc. using machine learning techniques. By leveraging historical stock price data, we implemented Linear Regression and Polynomial Regression models to forecast future prices. The goal is to provide insights into stock trends and assist investors in making informed decisions.

## Table of Contents
- [Technologies Used](#technologies-used)
- [Dataset](#dataset)
- [Data Preprocessing](#data-preprocessing)
- [Feature Engineering](#feature-engineering)
- [Data Visualization](#data-visualization)
- [Model Implementation](#model-implementation)
  - [Linear Regression](#linear-regression)
  - [Polynomial Regression](#polynomial-regression)
- [Results](#results)
- [Conclusion](#conclusion)
- [Installation](#installation)
- [Usage](#usage)
- [License](#license)

## Technologies Used
- Python
- Libraries: Pandas, NumPy, Matplotlib, Scikit-learn

## Dataset
The dataset used for this project consists of 1259 rows and 7 columns with the following attributes:
- **date**
- **open**
- **high**
- **low**
- **close**
- **volume**
- **Name**

The "Name" column was removed, and the "date" column was converted from object to numeric and set as the index, which is useful for time series analysis.

## Data Preprocessing
1. **Data Loading**: Loaded the dataset with 1259 rows and 7 columns.
2. **Target Definition**: Since we're predicting the next day's closing price, we shifted the data to set the target as the next day’s closing price. The last row was dropped due to NaN in the target.
3. **Backward Fill**: Handled NaN values by using backward fill for time series compatibility.

## Feature Engineering
Feature engineering is essential in machine learning for several reasons:
- **Improve Model Performance**: Creating relevant features can lead to better predictions, such as using moving averages to capture trends in stock prices.
- **Enhance Interpretability**: Adding domain-specific features (like price changes) helps understand model predictions better.
- **Utilize Available Data**: Transforming existing data into new features can provide additional insights for better learning.
- **Prepare for Time-Series Analysis**: Lagged features (previous days’ prices) are crucial for context.

### Feature Creation
- **Moving Averages**: Calculated moving averages to smooth out price fluctuations and identify trends.
- **Price Changes**: Created features to capture daily price changes for volatility insights.
- **Lagged Features**: Used previous days' prices as features to predict the next day’s price.
- **Volume Features**: Created features based on volume, such as the average trading volume over the last few days.

After feature engineering, the columns included:
```plaintext
Index(['open', 'high', 'low', 'close', 'volume', 'SMA_5', 'SMA_20', 'SMA_50',
       'SMA_200', 'price_change', 'pct_change', 'Lag1', 'Lag2', 'volume_5',
       'target'], dtype='object').
