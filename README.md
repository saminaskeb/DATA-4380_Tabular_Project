![](UTA-DataScience-Logo.png)

# Pima Indians Diabetes Classification

* This repository contains an end-to-end data science pipeline applying classification algorithms to the Pima Indians Diabetes dataset from Kaggle to predict diabetes diagnosis.

# Overview
The goal of this project is to predict whether a patient is likely to be diagnosed with diabetes based on several health metrics. We formulated this as a supervised binary classification task using the Pima Indians Diabetes dataset. Our approach included exploratory data analysis, preprocessing, model training using logistic regression and random forest classifiers, as well as performance optimization through hyperparameter tuning and SMOTE oversampling. The final tuned Random Forest model achieved an F1 score of approximately 70% on the validation set and generalized well on the test set.

* **Data**:
  * Type: Tabular data in CSV format, where each row represents a female patient of Pima Indian heritage and columns represent medical attributes (e.g., Glucose, BMI, Age).
  * Size: 768 records, 8 features + 1 binary target
  * Instances (Train, Test, Validation Split): 60% training, 20% validation, 20% test

#### Preprocessing / Clean up

* Replaced biologically implausible zeroes (e.g., BMI=0) with NaN, then imputed using the median
* Scaled features using StandardScaler where appropriate (e.g., logistic regression)
* Applied SMOTE on training data to handle class imbalance

#### Data Visualization
<img width="1483" height="2042" alt="image" src="https://github.com/user-attachments/assets/50757e62-db63-4a42-8434-0d2cd48a2a0d" />

![image](https://github.com/user-attachments/assets/ae5fe93c-2cc2-40b5-8f6d-230ab7aea99f)

### Problem Formulation

* Input: 8 numerical health-related features
* Output: Binary label indicating diabetes (1) or not (0)
* Models Tried:

  * Logistic Regression (scaled)
  * Random Forest (unscaled, scaled, with and without SMOTE)
  * Random Forest with GridSearchCV for hyperparameter tuning

### Performance Comparison

* Metric: Recall (False negatives are more costly in healthcare)

Best Performance:

 * F1 Score ~70% using Random Forest with SMOTE + GridSearch
 * Recall improved significantly with SMOTE + GridSearch(from 59% to 75%)
 * Visualizations: Bar plots comparing Accuracy, Precision, Recall, and F1 Score across models
   
![image](https://github.com/user-attachments/assets/757c2382-481f-4c6a-8e64-cacd374caac2)

### Conclusions

* SMOTE significantly improved recall and F1 Score
* Hyperparameter tuning yielded marginal improvements beyond SMOTE alone
* Random Forest was more effective than Logistic Regression on this dataset
  
### Future Work

* Experiment with other classifiers (e.g., XGBoost, SVM)
* Incorporate feature engineering and domain knowledge
* Try cross-validation and ensemble methods

## How to reproduce results

* Clone this repository and open the final notebook in Google Colab
* Run the notebook cell by cell
* Ensure all dependencies are installed

### Overview of files in repository

* Final_Tabular_Kebebe.ipynb: full project notebook

* README.md: this file

### Training

* Training is performed within the notebook using scikit-learn APIs
* Hyperparameter tuning performed using GridSearchCV
  
#### Performance Evaluation

* Evaluation metrics include Accuracy, Precision, Recall, F1 Score

* Comparison plots and classification reports are generated automatically


## Citations

* Kaggle: Pima Indians Diabetes Database (https://www.kaggle.com/datasets/uciml/pima-indians-diabet







