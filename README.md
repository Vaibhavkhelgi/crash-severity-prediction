# Crash Severity Prediction using Machine Learning

## Overview

This project focuses on predicting **crash severity (single-fatal vs multi-fatal crashes)** using the FARS dataset. The objective is to build a machine learning model that can accurately identify high-risk crash scenarios based on environmental and roadway conditions.  
<br>
The project primarily addresses the challenge of **class imbalance**, where multi-fatal crashes are rare but critical to detect.  
<br>
The project involves:
<li><b>Binary Classification</b>: Develop a classification model to predict whether a crash results in '0'(single fatal) or '1'(multiple fatal).</li>

---

## Python Packages Used
<li><b>Data Manipulation</b>: pandas, numpy</li>
<li><b>Data Visualization</b>: matplotlib, seaborn</li>
<li><b>Machine Learning</b>: sklearn, xgboost, lightgbm, imblearn</li>
<li><b>General Purpose</b>: warnings</li>

---

## Dataset

The dataset is derived from the **FARS (Fatality Analysis Reporting System)** and includes features related to crash conditions such as:
- Lighting conditions  
- Road type (rural/urban)  
- Vehicle involvement  
- Number of persons involved  

<br>
The dataset contains **39,000+ records and 200+ features after encoding**.  
<br>
A major challenge is **class imbalance**, with multi-fatal crashes representing approximately **7% of the dataset**.

---

## Preprocessing

### Steps taken:
<li><b>Data Cleaning</b>: Handled missing values, removed duplicates, and dropped irrelevant features.</li>
<li><b>Data Transformation</b>: Standardized categorical variables and prepared dataset for modeling.</li>
<li><b>Exploratory Data Analysis</b>: Visualized distributions and identified patterns using plots.</li>

---

## Feature Engineering

### Steps taken:
<li><b>Feature Creation</b>: Created new features such as <i>night crash</i>, <i>multi-vehicle crash</i>, <i>persons per vehicle</i>, and <i>rural night crash</i>.</li>
<li><b>Encoding</b>: Converted categorical variables into numerical format using encoding techniques.</li>
<li><b>Feature Importance</b>: Identified key features influencing crash severity.</li>

---

## Modelling Approach

<li><b>Model Exploration</b>: Tested Logistic Regression, Decision Tree, Random Forest, XGBoost, and LightGBM.</li>
<li><b>Handling Class Imbalance</b>: Applied SMOTE and class weights to improve minority class detection.</li>
<li><b>Model Selection</b>: Compared models using Recall, F1-score, and ROC-AUC.</li>

---

## Performance Assessment

<b>Evaluation Metrics</b>: Focused on Recall, F1-score, and ROC-AUC due to class imbalance.

<table>
  <tr>
    <th>Model</th>
    <th>Recall</th>
    <th>F1-score</th>
    <th>ROC-AUC</th>
  </tr>
  <tr>
    <td>Random Forest Tuned</td>
    <td>0.89</td>
    <td>0.31</td>
    <td>0.86</td>
  </tr>
  <tr>
    <td>LightGBM</td>
    <td>0.85</td>
    <td>0.31</td>
    <td>0.86</td>
  </tr>
  <tr>
    <td>XGBoost Tuned</td>
    <td>0.75</td>
    <td>0.31</td>
    <td>0.86</td>
  </tr>
  <tr>
    <td>Logistic Regression Tuned</td>
    <td>0.65</td>
    <td>0.30</td>
    <td>0.83</td>
  </tr>
  <tr>
    <td>Decision Tree</td>
    <td>0.23</td>
    <td>0.22</td>
    <td>0.58</td>
  </tr>
  <tr>
    <td>XGBoost</td>
    <td>0.07</td>
    <td>0.12</td>
    <td>0.86</td>
  </tr>
  <tr>
    <td>Logistic Regression</td>
    <td>0.05</td>
    <td>0.09</td>
    <td>0.82</td>
  </tr>
  <tr>
    <td>Random Forest</td>
    <td>0.01</td>
    <td>0.02</td>
    <td>0.86</td>
  </tr>
</table>

<b>Conclusion:</b> Tuned Random Forest achieved the highest recall (0.89), making it the best model for detecting multi-fatal crashes. LightGBM also performed closely with strong overall metrics.

---

## Conclusion

The project successfully improved detection of multi-fatal crashes by addressing class imbalance and optimizing model performance.

- Recall improved from **5% to 89%**  
- Ensemble models outperformed baseline models  
- Tuned Random Forest provided the best balance for deployment  

---

## Key Insights

<li>Night-time crashes are more severe</li>
<li>Multi-vehicle crashes increase fatality risk</li>
<li>Higher number of persons per vehicle increases severity</li>

---

## Limitations

<li>High false positives due to recall optimization</li>
<li>Imbalanced dataset</li>
<li>No real-time or external data (weather, traffic)</li>

---

## TODO in future:
<li>Improve feature engineering with additional data sources</li>
<li>Optimize threshold for better precision-recall balance</li>
<li>Deploy model for real-time crash severity prediction</li>
