# Arkmind AI Engineer Technical Assessment 1
This repository is a Technical Assessment for Arkmind AI Engineer

## Overview
1. assessment.ipynb
    - The technical assesment contents are completed here
2. models
    - Multiple Fine-tuned models 
3. data.csv
    - The dataset provided.
4. requirements.txt

## Approach
1. Data Understanding
    - Load data 
    - Visualize data 
        - 0 Duplicated IDs
        - 61 rows of null on ela and financeAmount
        - 230 rows of 0 values in ela and financeAmount
        - 2 Outliers within netSalary and ela
        <img src="images/outlier.png" alt="outlier" width="80" height="80">

2. Data Preprocessing
   - Drop data rows with NaN and 0 values.
   - Remove outliers
   - Drop unnecessary columns.
   - Only 707 rows left
   - Feature Engineering (Create new column based off the difference between ela & loanApplied).

3. Feature Understanding
    - Created graphs to better understand the data.
    - Scatter Plot of Approved and Rejected Applicants based off netSalary & ela
    <img src="images/scatterplot.png" alt="outlier" width="80" height="80">


3. Model Training
    - A XGBoost Classifier is used due to its regularization feature to prevent overfitting, especially when trained on a small dataset like this. Besides, it is also well-known for its great performance and accuracy on most tasks.
    - Fine-tune the model by using grid search cross validation method.
        - Learning rate: 0.1 to 0.4, step=0.1
        - Number of estimators: 500 to 900, step=100
        - Max depth: 2 to 5, step=1
        - Cross validation fold: 5

4. Model Evaluation and Results:
    - Accuracy: 82.98%
    - Precision: 57.14%
    - Recall: 63.16%
    - F1-score: 60%
    - Confusion Matrix (as shown in script)

5. Extra comment:
    - The precision and recall scores obtained are quite low when we have an accuracy of more than 80%. This should be because of the small dataset size. Thus, the first action to further improve the model is to collect more data. 