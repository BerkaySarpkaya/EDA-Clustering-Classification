# EDA-Clustering-Classification
This repository is dedicated to conducting a thorough examination of a dataset related to Bank Customers. It involves performing exploratory data analysis, customer segmentation, and churn classification on the dataset, sourced from Kaggle.

## Table of Contents

<!--ts-->
* [Objective](#Objective)
* [Requirements](#Requirements)
* [Dataset](#Dataset)
* [Data Preparation](#Data-Preparation)
* [Feature Engineering and Scaling](#Feature-Engineering-and-Scaling)
* [Model Selection and Evaluation](#Model-Selection-and-Evaluation)
* [Inferences](#Inferences)
* [Further Work and Improvements](#Further-Work-and-Improvements)
* [License](#License)
<!--te-->

## Objective

The main aim of this case was to build a model that could accurately predict whether passengers were satisfied with their flight or not.

The side aims were:

- Comparison of the performance of multiple data sets scaled in different ways including: Raw, Normalization, Standardization and Robust Scaling
- Comparison of different user-ready scikit-learn models and an ANN model created with Tensorflow-Keras

## Requirements

- Python Version: 3.11.6
- Pandas Version: 2.1.1
- Numpy Version: 1.24.4
- Matplotlib Version: 3.8.0
- Seaborn Version: 0.13.0
- Tensorflow Version: 2.13.0
- Scikit-Learn Version: 1.3.1
- pmdarima Version: 2.0.4
- statsmodels Version: 0.14.0
- Prophet Version: 1.1.4

The overview of the code can be seen on the following link <a href="https://github.com/BerkaySarpkaya/Classification-Prediction/blob/main/WBS%20of%20the%20Code.txt"> Overview of the code</a>
## Dataset

The data was downloaded directly from Kaggle (<a href="https://www.kaggle.com/datasets/johndddddd/customer-satisfaction/data">Passenger Satisfaction</a>). It is stated that the origin of the data comes from US Airline passenger satisfaction survey

## Data Preparation

- Data was in xlsx format, with ease to read.
- Imputation of missing values were conducted according to features relations
- After handling missing values, a basic reference model was prepared in order to compare the results with the final model

## Feature Engineering and Scaling

- PCA analysis and dimensionality reduction held to overcome multicollinearity problem.
- One feature, did_flight_delay, was generated from the data. The generated feature did not cause any multicollinearity problems.
- 3 different scaling method were applied to the data (Min-Max Scaling, Z-Score Scaling, Robust Scaling).

## Model Selection and Evaluation

### _Model Selection_

- Accuracy Score was choosen as the main metric because the target variable has balanced output values
- A range of user-ready models were selected including logistic regression, KNN, Perceptron, SVC, Bagging and Boosting Decision Tree algorithms.
- On top of that, a basic ANN architecture was modeled with kernel-regularizer(l2=0.01). Linear activation at the and node and (from_logits=True) argument with loss function were also used to prevent computational errors by treating the output as a raw unbounded score rather than probability.
- "Different model X different scaling method" combinations were performed to see the best Accuracy Score.

### _Model Evaluation_

- The refrence model had high bias and low variance with the accuracy score of 0.872 on train and 0.879 on test data.

- Among all the different cases, the normalized and dimensionality reduction applied dataset with catboost algorithm had the best accuracy of 0.9639 with the following confusion matrix

<img src="https://github.com/BerkaySarpkaya/Classification-Prediction/blob/main/Images/Confusion-Matrix-DR-Normalized-Catboost.PNG" alt="Figure 1">

<em>Figure 1. Confusion matrix of the catboost model - 96.39% accuracy on validation set</em>

- After Hyperparameter tuning held on the final model with 3 degree of cross-validation, accuracy had slightly increased to 0.9641 on validation set, while having an accuracy score of 0.9785 on training set. These results indicates that the high bias problem of reference model has been solved with keeping the variance as low, indicating there is no high bias or overfitting problem.

- The final model's accuracy score was 0.9666 on the Test Set with confusion matrix:

<img src="https://github.com/BerkaySarpkaya/Classification-Prediction/blob/main/Images/Best%20Catboost-Test%20Set.PNG" alt="Figure 2">

<em>Figure 2. Confusion matrix of the hyperparameter tuned catboost model - 96.66% accuracy on test set</em>

## Inferences

- In the all cases of different scaling methods X different models: Boosting Decision Tree methods were always the winners with the lead of catboost and lightgbm
- Top 5 models were always the Catboost, LightGBM, XGBoost, Extra Trees and Random Forest. Their performance almost did not change according to the scaling method as expected.
- Among the scaling methods, only no scaled (raw) data changed the performance of NN model dramatically with a possible reason of ineffective gradient descent process caused by oscilating with large moves. 

## Further Work and Improvements

- Dimenasionality reduction applied dataset was only performed with normalization method. It could have been also combined with other methods to improve the performance.
- A more comprehensive hyperparameter tune process can be applied.
- According to the final confusion matrix, misclassified data can be examined to understand which type of feature combination observations lead to misclassification and the training data can be feed with them more to evolve the model.
- Hyperparameter tuning could be applied to multiple models as the default accuracies were too close to each other.

## License

This project is licensed under the MIT License. See the <a href="https://github.com/BerkaySarpkaya/Classification-Prediction/blob/main/LICENSE"> LICENCE</a> file for details.v
