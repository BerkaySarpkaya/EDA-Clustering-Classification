# EDA-Clustering-Classification
This repository is dedicated to conducting a thorough examination of a dataset related to Bank Customers. It involves performing exploratory data analysis, customer segmentation, and churn classification on the dataset, sourced from Kaggle.

## Table of Contents

<!--ts-->
* [Objective](#Objective)
* [Requirements](#Requirements)
* [Dataset](#Dataset)
* [Exploratory Data Analysis](#Exploratory-Data-Analysis)
* [Feature Engineering and Scaling](#Feature-Engineering-and-Scaling)
* [Model Selection and Evaluation for Classification](#Model-Selection-and-Evaluation-for-Classification)
* [Segmentation](#Segmentation)
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
- Scikit-Learn Version: 1.3.1
- LightGBM Version: 4.1.0

The overview of the codes can be seen on the following link <a href="https://github.com/BerkaySarpkaya/EDA-Clustering-Classification/tree/main/Overviews"> Overview of the code files</a>

## Dataset


The dataset includes demographic and spending indicators of a bank's customers, along with information indicating whether a customer has churned or not. The data was downloaded directly from Kaggle (<a href="https://www.kaggle.com/datasets/thedevastator/predicting-credit-card-customer-attrition-with-m/data">Customer Churn</a>).

## Exploratory Data Analysis

- Dataset does not include any missing or duplicated value
- All the feature distributions has been inspected with respect to Churn with the methods of:
  - Barplots and pie charts features
  - Histplots, violinplot, and kde for numerical features
- Deep dive examination of some features with bivariate analysis
- Correlation analysis with triangle heatmap

## Feature Engineering and Scaling

- One hot encoding has been performed
- Not Scaled, Standardized, and Normalized dataset were compared
- Feature elimination to deal with the multicollinearity problem
- Feature extraction
- Log and Reciprocal Transformations

## Model Selection and Evaluation for Classification

### Strategy

Main strategy to see the potential of increasing the metrics was first creating a reference model, where the unprocessed dataset and a simple model without fine tuning were used. After that point, feature engineering, dataset selection, scaling method altering, feature transformation, feature selection, model selection, and hyperparameter tuning were conducted. On the below list, elaborate strategies and same important outputs can be seen.

- The primary metric selected was the Accuracy Score. However, in the necessary steps, precision and recall values for churn were also assessed due to the dataset's skewness.
- Model selection was performed with 19 different models including logistic regression, KNN, Perceptron, SVC, Bagging and Boosting Decision Tree algorithms.
- Dataset options were combined with different scaling methods and different transformation methods on a feature called 'Credit_Limit' to see the best performance.
- Feature Selection process increased the accuracy of the model by 0.2%.

### Evaluation

- The reference model exhibited high bias and low variance, achieving an accuracy score of 0.894 on the training data and 0.888 on the test data. This reults reached to 1.00 for train, 0.940 for validation, and 0.935 for test sets. The bias problem was solved. However, an overfitting problem has occured.

- Feature Importance graph chaned a lot after the process. 

<img src="https://github.com/BerkaySarpkaya/EDA-Clustering-Classification/blob/main/Images/Ref-Model-Feature-Importance.png" alt="Figure 1">

<em>Figure 1. Feature Importance of Reference Model</em>

<img src="https://github.com/BerkaySarpkaya/EDA-Clustering-Classification/blob/main/Images/Best-Model-Feature-Importance.png" alt="Figure 2">

<em>Figure 2. Feature Importance of the Best Model</em>

- Accuracy scores of different combinations can be seen in the figure 3

<img src="https://github.com/BerkaySarpkaya/EDA-Clustering-Classification/blob/main/Images/Results%20of%20Combinations.PNG" alt="Figure 3">

<em>Figure 3. Different dataset combinations and accuracies</em>

- Both the distribution and skeweness of the train and test sets are the same. Their confusion matrixes can be seen below.

<img src="https://github.com/BerkaySarpkaya/EDA-Clustering-Classification/blob/main/Images/Test%20Set.png" alt="Figure 4">

<em>Figure 4. Confusion matrix of the Test Set </em>

<img src="https://github.com/BerkaySarpkaya/EDA-Clustering-Classification/blob/main/Images/Validation%20Set.png" alt="Figure 5">

<em>Figure 5. Confusion matrix of the Validation Set</em>

## Segmentation

