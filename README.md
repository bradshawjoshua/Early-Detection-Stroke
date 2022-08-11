# Patient Early Detection of Stroke
## Exploratory Data Analysis & Prediction of Patient Incurring Stroke

**Author**: Joshua Bradshaw

### Business problem:

I am predicting the likelihood of a person incurring a stroke.


### Data:
According to World Health, stroke is the second leading cause of death worldwide. My goal is to improve the early detection of stroke in new patients based on the attributes provided.
- By quickly scanning the details, I noticed that hypertension and heart disease features represent the patients with the diseases aforementioned.
- I would need to do some oversampling (SMOTE) to overcome areas where data is lacking. 
- At a glance, I would suggest more medical features to test my model's performance. 


## Methods
* Conducted data cleaning and exploratory analysis on the data set to help identify which cohort was most affected by stroke.
* Used supervised machine learning models to test which model would be best for production.
  * Logistic Regression
  * K-nearest Neighbors (KNN)

## Model Results
Logistic Regression Baseline
* Train Accuracy: 95.59%
* Test Accuracy: 93.82%

Logistic Regression L1
* Train Accuracy: 95.12%
* Test Accuracy: 95.23%

Logistic Regression Balanced with SMOTE
* Train Accuracy: 74.79%
* Test Accuracy: 73.40%

KNN Baseline with SMOTE
* Train Accuracy: 88.88%
* Test Accuracy: 80.05%

KNN w/ best K with SMOTE
* Train Accuracy: 99.97%
* Test Accuracy: 88.50%

XGBoost with SMOTE
* Train Accuracy: 100%
* Test Accuracy: 93.04%

Principle Component Analysis
* Helped improve model performance (speed), but not noticeable compared to no PCA with KNN.

#### Percentage of Stroke Patients by Age Cohort
![image](https://user-images.githubusercontent.com/83310016/182333081-715edc72-7e01-4503-a709-c21e079d2675.png)


> Visual 1 displays stroke patients by distinct age groups, providing quick glance at cohorts most affected by stroke.

#### Stroke by Heart Disease and Hypertension Status
![image](https://user-images.githubusercontent.com/83310016/182333419-3bea013a-1562-49a4-9781-e373804fef8a.png)

> Visual 2 displays patient status by heart disease and hypertension in order to show which groups are most affected by stroke.

## Model
### Logistic Regression Balanced with SMOTE for Deployment:
* Logistic Regression Balanced with SMOTE performed best with or without hyperparameter tuning (L1); and used class weight (balancing) and Synthetic Minority Oversampling Technique due to stroke patients' underrepresentation (minority).
   * Noticed some overfitting with my Logistic Regression models.
   * Identified more false negatives than I would like for this data set, so I attempted to balance my model in order to create predictions that would favor false positives.


Logistic Regression Balanced With SMOTE
* Train Accuracy: 74.8%
* Test Accuracy: 73.4%

Logistic Regression AUC - ROC Curve:
* Based on AUC, there is an 85% chance that the Logistic Regression model will be able to distinguish between stroke and no stroke in a new patient.

## Recommendations:

* Patients with hypertension and heart disease need increased monitoring due to higher stroke cases for this group.
* Suggest patients over 40 get checked every 6 months.
* If the patient has a BMI over 26 or has high blood pressure, then I suggest implementation of a fitness and nutritional remediation program.

## Limitations & Next Steps

* Implement other models and compare their performance to what is used, examples include: Naives Bayes, Tree Classifier, Random Forest Classifier, and SVC.
* Stroke patients (1) are underrepresented, which is a challenge for this data set. 


### For further information


For any additional questions, please contact joshua.j.bradshaw@outlook.com
