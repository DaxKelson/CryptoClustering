# Cryptocurrency Market Data Clustering and PCA Analysis

## Overview

This project performs clustering and dimensionality reduction on cryptocurrency market data using K-Means clustering and Principal Component Analysis (PCA). The goal is to group cryptocurrencies based on their price change behaviors over various time periods and to identify the most significant patterns driving these groupings.

## Dataset

The dataset (`crypto_market_data.csv`) contains price change percentage data for various cryptocurrencies over multiple time intervals, including 24 hours, 7 days, 14 days, 30 days, 60 days, 200 days, and 1 year. The `coin_id` column uniquely identifies each cryptocurrency and is used as the DataFrame index.

## Methodology

### Data Preparation and Scaling

- The raw data is loaded into a Pandas DataFrame.
- The data is scaled using `StandardScaler` from scikit-learn to normalize feature values before clustering.

### K-Means Clustering

- The elbow method is applied by calculating inertia for K values from 1 to 10 to determine the optimal number of clusters.
- A K-Means model is initialized with the selected best K value and fitted to the scaled data.
- The predicted cluster labels are added as a new column to the DataFrame.

### Principal Component Analysis (PCA)

- PCA is performed to reduce dimensionality while retaining significant variance.
- The analysis retains three principal components.
- Explained variance ratios are calculated to understand how much information each component captures.
- K-Means clustering is repeated on the PCA-transformed data, and clusters are assigned accordingly.

### Interpretation

- The total explained variance of the three principal components is interpreted to evaluate the effectiveness of dimensionality reduction.
- Feature loadings (PCA components) are examined to identify which original features have the strongest positive or negative influence on each principal component.

## Results

- Clustering results group cryptocurrencies into distinct clusters based on their market behavior.
- PCA reduces the complexity of the dataset while maintaining most of the variance.
- The elbow curve visualization helps in selecting the optimal number of clusters.
- Feature loadings provide insight into which time-period price changes most strongly influence each principal component.

## Usage

1. Ensure the `crypto_market_data.csv` file is located in the `Resources` directory.
2. Run the Jupyter notebook step-by-step to perform scaling, clustering, PCA, and visualization.
3. Adjust the `bestValue` variable after reviewing the elbow plot to set the optimal number of clusters.
4. Interpret the PCA loadings to understand feature influences.

## Dependencies

- Python 3.x
- pandas
- scikit-learn
- matplotlib (for visualization)

## Author

Dax Kelson

## Date

5/16/2025
