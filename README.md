# Economic Factors and S&P 500 Analysis
DATA 201 Final Project, Fall 2025  
Ezenwanyi Duru & Erika Holbrook

## Overview
This project analyzes how key macroeconomic indicators relate to movements in the S&P 500 between 2006 and 2010, including the 2008 financial crisis. Using Python, we merged time-series data from FRED and Yahoo Finance, engineered trend-based trading signals, and applied regression, classification, and clustering methods to understand how economic environments shape market behavior.

Completed as part of DATA 201: Data Analytics & Machine Learning at Tufts University.

## Research Questions
- How do inflation, unemployment, interest rates, crude oil, corporate profits, GDP, retail sales, gold prices, and real estate index relate to S&P 500 changes?
- Can daily Buy/Sell signals be predicted using logistic regression and random forest models?
- How do economic regimes cluster using PCA and k-means?
- Which indicators are most predictive of market direction?

## Data Sources
- Federal Reserve Economic Data (FRED): 11 macroeconomic indicators  
- Yahoo Finance: Daily S&P 500 (^GSPC) historical prices  
- Indicators include daily, monthly, and quarterly frequencies merged and forward-filled.

## Methods

### Data Cleaning and Preparation
- Imported FRED CSVs and Yahoo Finance data
- Standardized and merged datasets on date
- Forward-filled low-frequency indicators
- Filtered observations to 2006–2010
- Created engineered features:
  - Daily percent change  
  - 200-day moving average  
  - Binary Buy/Sell signal  
  - Shifted target for next-day prediction  

### Modeling

#### Logistic Regression
- Binary classification (Buy = 1, Sell = 0)
- Achieved ~87% accuracy and AUC ~0.91
- Most accurate and interpretable model

#### Random Forest
- Captured nonlinear relationships
- Cross-validation accuracy ~75%
- Identified important predictors:
  - Crude oil prices  
  - Corporate profits  
  - Housing index  
  - Inflation and unemployment  

#### PCA and K-Means Clustering
- PCA captured ~80% variance in PC1 + PC2
- K-means (k = 4) identified macroeconomic regimes:
  - Bullish / Healthy  
  - Post-crisis stabilization  
  - High-inflation commodity-driven  
  - Bearish / Stressed  

## Key Findings
- S&P 500 correlates positively with retail sales, interest rates, and tech investment.
- S&P 500 correlates negatively with unemployment and gold prices.
- Logistic regression outperformed random forest on accuracy and AUC.
- Clustering reveals distinct macroeconomic regimes with different Buy/Sell tendencies.
- Economic indicators help classify market direction during turbulent periods.

## Limitations
- Dataset limited to 2006–2010 (heavily influenced by 2008 crisis)
- Forward-filling may reduce temporal precision
- Trading strategy simplified; does not model returns or transaction costs
- Results may not generalize to other market environments

## Future Work
- Extend analysis to additional years and indices
- Add hyperparameter tuning for random forest
- Explore LSTM and time-series forecasting models
- Incorporate financial sentiment and volatility indicators
- Evaluate strategy based on actual returns and risk metrics

## How to Run
1. Clone the repository, open jupyter notebook
2. Run all cells to reproduce analysis. (After final master data set is created, will see section read_csv("stock_macro_shifted_df") )
*Raw FRED downloads excluded; the cleaned, merged csv dataset is provided.*
