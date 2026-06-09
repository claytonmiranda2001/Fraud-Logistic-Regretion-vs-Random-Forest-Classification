#Project Objective

This project focuses on developing a fraud detection model using a dataset obtained from Kaggle.
The goal is to build a robust classification model capable of identifying fraudulent transactions, with special attention to class imbalance.

#Data Preprocessing

* Missing Values:
No missing values were found in the dataset.
* Outlier Treatment:
Outliers were identified using boxplots and histograms.
Most variables had less than 10% of outliers.
Removing outliers led to a significant loss of minority class instances.
Therefore, outliers were kept to preserve important fraud patterns.
* Multicollinearity:
Correlation analysis showed no strong multicollinearity.
No additional treatment was required.

#Data Splitting

The dataset was divided into:

* 70% Training set
* 15% Validation set (for hyperparameter tuning)
* 15% Test set (final evaluation)

#Data Balancing & Scaling

Balancing Techniques Tested:

* SMOTE
* SMOTETomek
* ADASYN

These techniques introduced noise due to high class imbalance, so the dataset was kept imbalanced.

#Standardization

Applied StandardScaler to normalize feature scales.

#Models Used

* Logistic Regression: Used as a baseline model

* Random Forest: Selected as the final model due to better performance on imbalanced data

#Key configurations:

* class_weight enabled
* n_jobs = -1 for parallel processing
* Feature selection applied to reduce noise

#Hyperparameter Tuning

Tuned parameters:

* n_estimators
* min_samples_split
* min_samples_leaf

Goal: reduce overfitting and improve generalization.

#Model Evaluation

Given the class imbalance, the following metrics were prioritized:

* F1-score (macro average)
* Precision-Recall Curve

Metrics such as accuracy and ROC curve were avoided, as they can be misleading in imbalanced datasets.

#Results

* Training Score: 98%
* Test Score: 93%
* Overfitting: Reduced from 7% to 5% after tuning

#Libraries Used

* pandas
* seaborn
* matplotlib
* scikit-learn
* imbalanced-learn

#Conclusion

The Random Forest model demonstrated strong performance in detecting fraud, even with imbalanced data.
The chosen evaluation metrics ensured a more reliable assessment of the model’s ability to identify the minority class.
