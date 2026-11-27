# Bankruptcy Prediction with Classical ML Classifiers

Coursework for **Machine Learning** (Assignment 1), Department of Applied Informatics, University of Macedonia.

Binary classification of companies as **healthy (Y=1)** or **bankrupt (Y=2)** from 8 continuous financial indicators and 3 binary indicators. Eight scikit-learn classifiers are compared under stratified cross-validation, with undersampling to handle the class imbalance.

## Method

- **Exploration:** counts of healthy vs. bankrupt companies per year, plus min/max/mean of each continuous indicator for each class.
- **Preprocessing:** checks for missing values, then Min-Max scaling of the continuous indicators. The binary indicators are kept as they are.
- **Evaluation:** 4-fold `StratifiedKFold`.
- **Imbalance handling:** in each fold, the *training* set is randomly undersampled to at most 3 healthy companies per bankrupt one. The test set is never modified.
- **Classifiers:** k-NN, Gaussian Naive Bayes, SVM, LDA, Logistic Regression, Decision Tree, Random Forest and Passive-Aggressive. Each is tuned with `GridSearchCV` (cv=3).
- **Metrics:** confusion matrix, accuracy, balanced accuracy, precision, recall, F1 and ROC-AUC on both train and test sets. Bankrupt is the positive class.

## Repository structure

```
notebooks/bankruptcy_classification.ipynb   # full pipeline (Google Colab)
requirements.txt
```

## How to run

1. Open the notebook in Google Colab.
2. Put the dataset file `Dataset2Use_Assignment1.xlsx` in your Google Drive. It was provided by the course and is **not included** here.
3. Change `LOCATION` in the data-loading cell to that folder's path.
4. Run all cells. Results for each fold are written to `balancedDataOutcomes_{Train,Test}_Fold_{k}.csv`.

## Authors

- **Stylianos Zapartas** (ics24040)
- **Dimitra Bazouki** (ics24116)

Department of Applied Informatics, University of Macedonia, Thessaloniki, Greece.
