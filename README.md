# EDA-Clustering-Classification
This repository is dedicated to conducting a thorough examination of a dataset related to Bank Customers. It involves performing exploratory data analysis, customer segmentation, and churn classification on the dataset, sourced from Kaggle.

## Table of Contents

<!--ts-->
* [Objective](#Objective)
* [Requirements](#Requirements)
* [Dataset](#Dataset)
* [Exploratory Data Analysis](#Exploratory-Data-Analysis)
* [Feature Engineering and Scaling](#Feature-Engineering-and-Scaling)
* [Model Selection and Evaluation](#Model-Selection-and-Evaluation)
* [Inferences](#Inferences)
* [Further Work and Improvements](#Further-Work-and-Improvements)
* [License](#License)
<!--te-->

## Objective

This study has three main objectives:

1) Conducting an in-depth exploratory analysis on the dataset with the goals of gaining a deeper understanding of the domain, unraveling the factors leading to 'Churn,' and honing skills in data visualization.

2) Developing a highly effective classification model involves leveraging the strength of numerous model comparisons and an iterative process of enhancing metrics through adjustments in feature extraction and selection.

3) Conducting customer segmentation from various perspectives.

## Requirements

- Python Version: 3.11.6
- Pandas Version: 2.1.1
- Numpy Version: 1.24.4
- Matplotlib Version: 3.8.0
- Seaborn Version: 0.13.0
- Tensorflow Version: 2.13.0
- Scikit-Learn Version: 1.3.1
- LightGBM Version: XXXXXXXXX

The overview of the codes can be seen on the following link <a href="https://github.com/BerkaySarpkaya/EDA-Clustering-Classification/tree/main/Overviews"> Overview of the code files</a>

## Dataset

The data was downloaded directly from Kaggle (<a href="https://www.kaggle.com/datasets/thedevastator/predicting-credit-card-customer-attrition-with-m/data">Customer Churn</a>).

## Exploratory Data Analysis

- Dataset does not include any missing or duplicated value
- All the feature distributions has been inspected with respect to Churn with the methods of:
  - Barplots and pie charts features
  - Histplots and kde for numerical features
- Deep dive examination of some features with bivariate analysis
- Correlation analysis

## Feature Engineering and Scaling

- One hot encoding has been performed
- Not Scaled, Standardized, and Normalized dataset were compared
- Feature elimination to deal with the multicollinearity problem
- Feature extraction
- Log and Reciprocal Transformations

