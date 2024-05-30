<div align="center">
    <img width="745" alt="MediSchedule.AI" src="https://github.com/MohamedMandour10/AI-Driven-Appointment-Scheduling-System/assets/115044826/f770450b-a3f1-4482-ba13-9da7d1bde90e">
</div>

# AI-Driven Appointment Scheduling System for Fanous Clinic

## Abstract
The primary goal of this research is to develop an intelligent scheduling recommender system for Fanous Clinic, USA, aimed at optimizing the appointment scheduling process based on disease reports generated from the clinic's mobile application. The system recommends the type of visit required, categorizing it as a Primary Care visit alone, with a consultant, with a pharmacist, Urgent, or Pass. The system leverages data from Fanous Clinic to train and evaluate its performance. Our results demonstrate that the model effectively reduces the workload and time required by Primary Care physicians to review patient reports, enabling more efficient and accurate scheduling decisions. 

## System Objectives and flow
The system's goal is to shift clinic operations from fast intuitive thinking to slow analytical mode. Providing instant, data-driven recommendations, minimizes physicians' cognitive load and allows them to deliver evidence-based care to patients. 
<div style="text-align: center;">
    <img src="https://i.ibb.co/k4bQZKt/Project-Flow-for-Scheduling-Recommender-System.png" width="500" alt="Project-Flow">
</div>

## Dataset and Pre-Processing

### Description
The dataset comprises comprehensive medical profiles of patients, capturing various health parameters and conditions. Each record includes:
- Demographic information (age, gender)
- Primary and secondary disease diagnoses
- Cardiovascular metrics (LDL cholesterol levels, heart rate)
- Medication usage (type and dosage of statins)
- Smoking status and COPD assessments (GOLD stage and group classifications)
- Additional respiratory health metrics (COPD medications, asthma control status, exacerbation risk)
- Inhaler usage (SABA, SAMA, ICS dosage)

This dataset provides a holistic view of each patient's health, facilitating a thorough analysis of their medical conditions and treatment regimens, which is critical for research on the interplay between various health conditions and treatment effectiveness.

### Handling Missing Values
1. **Check for Missing Values**: The dataset was meticulously reviewed for any missing entries using Python's pandas library. Functions such as `isnull()` and `sum()` were employed to identify the presence and extent of missing data across various features.
2. **Strategy for Handling Missing Values**:
    - **Dropping Missing Values**: In instances where the proportion of missing data was significant or no logical imputation method was applicable, the corresponding rows were dropped to maintain data integrity.
    - 
<div style="text-align: center;">
    <img src="https://i.ibb.co/SndcCRF/image.png" width="500" alt="Missing Values Heatmap">
</div>

### Encoding Categorical Variables
1. **Identification of Categorical Variables**: Using pandas' `select_dtypes()` function, categorical features were isolated for encoding.
2. **Label Encoding**: For ordinal categorical variables, label encoding was used to assign each category a unique numerical value.
3. **One-Hot Encoding**: For nominal categorical variables with no intrinsic ordering, one-hot encoding was applied using the `get_dummies()` function in pandas, creating binary columns for each category.

### Exploratory Data Analysis
1. **Univariate Analysis**: Understand the distribution of each feature.
2. **Bivariate and Multivariate Analysis**: Explore relationships between features and the target variable.

## Model Development
After extensive experimentation with various models and parameters, we decided to use a decision tree classifier due to its interpretability and performance. The following parameters were chosen for the decision tree:

**Decision Tree - Best Parameters:**
```json
{
  "max_depth": 10,
  "min_samples_split": 5
}
```
The decision tree classifier provided the best performance, balancing accuracy and ease of interpretation, which is crucial for reliable decision-making in the scheduling process. The following is the classification report.

              precision    recall  f1-score   support

           0       0.83      0.83      0.83        35
           1       0.75      0.90      0.82        10
           2       0.97      0.89      0.93        65
           3       0.60      0.67      0.63         9
           4       0.50      1.00      0.67         1
           5       0.96      0.98      0.97        53

    accuracy                           0.90       173
### Plotting and Visualization of tree
![decesion tree](https://i.ibb.co/HG0wCCG/image.png)

### ROC-AUC Curve
![ROC-AUC Curve](https://github.com/MohamedMandour10/AI-Driven-Appointment-Scheduling-System/assets/115044826/97619d34-6429-4330-80b1-092dae839e2e)

## Conclusion
This scheduling recommender system is a promising tool for modernizing clinical operations, offering a blend of machine learning and practical application in healthcare. By enhancing the scheduling process, the system supports healthcare providers in delivering timely and efficient care, ultimately contributing to improved patient outcomes and streamlined clinic workflows.



