# Patient Early Detection of Stroke
## Exploratory Data Analysis & Prediction of Patient Incurring Stroke

**Author**: Joshua Bradshaw

### Business problem:

I am predicting the likelihood of a person incurring a stroke.


### Data:
According to World Health, stroke is the second leading cause of death worldwide. The data set would like to improve the early detection of stroke in new patients based on the attributes provided.
- By quickly scanning the details, I noticed that hypertension and heart disease features represent the patients with the diseases aforementioned.
- I would need to do some oversampling (SMOTE) to overcome areas where data is lacking. 
- At a glance, I would suggest more medical features to test my model's performance 


## Methods
* Conducted data cleaning and exploratory analysis on the data set to help identify which cohort was most affected by stroke.
* Used supervised machine learning models to test which would be best for production
  * Logistic Regression
  * K-nearest Neighbors (KNN)


## Model Results
Logistics Regression Baseline
* Train Accuracy: 95.59%
* Test Accuracy: 93.82%

Logistics Regression Balanced
* Train Accuracy: 75.02%
* Test Accuracy: 75.35% (-18.47%)

Logistics Regression SMOTE
* Train Accuracy: 75.02%
* Test Accuracy: 75.35% (-18.47%)

KNN Baseline
* Train Accuracy: 95.67%
* Test Accuracy: 93.51%

KNN w/ best K
* Train Accuracy: 95.64%
* Test Accuracy: 93.74% (+0.23)

GridSearchCV on KNN
* Train Accuracy: 95.64%
* Test Accuracy: 93.66% (+0.15)

Principle Component Analysis
* Helped improved performance, but not noticeable compared to no PCA with KNN

#### Percentage of Stroke Patients by Age Cohort
![image](https://user-images.githubusercontent.com/83310016/182333081-715edc72-7e01-4503-a709-c21e079d2675.png)


> Visual 1 displays stroke patients by distinct age groups, providing quick glance at cohorts most affected by stroke.

#### Stroke by Heart Disease and Hypertension Status
![image](https://user-images.githubusercontent.com/83310016/182333419-3bea013a-1562-49a4-9781-e373804fef8a.png)

> Visual 2 displays patient status by heart disease and hypertension in order to show which group are most affected by stroke.

## Model
### Logistics Regression for Deployment:
* Logistic Regression Model, performed best with or without hyperparameter tuning (L1); and used class weight (balancing) and Synthetic Minority Oversampling Technique due to stroke patients underrepresentation.
  * Noticed some overfitting with my Logistic Regression model
  * Identified more false negatives than I would like for this data set, so I attempted to balance my model in order to create predictions that would favor false positives

Logistics Regression L1 Tune
* Train Accuracy: 95.59%
* Test Accuracy: 93.82%

Logistics Regression AUC - ROC Curve:
* Based on AUC, there is an 85% chance that the logistic regression model will be able to distinguish between stroke and no stroke in a new patient.

## Recommendations:

* Patients with hypertension and heart disease need increased monitoring due to higher stroke cases for this group.
* Suggest patients over 40 get checked every 6 months
* If the patient has a BMI over 26 or has high blood pressure, then I suggest implementation of a fitness and nutritional remediation program.

## Limitations & Next Steps

* Implement other models and compare their performance to what is used, examples include: Naives Bayes, Tree Classifier, Random Forest Classifier, SVC, and XGB Classifier.
* Stroke patients (1) are underrepresented, which is a challenge for this data set. 


### For further information


For any additional questions, please contact joshua.j.bradshaw@outlook.com
