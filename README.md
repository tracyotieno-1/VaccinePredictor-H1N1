# Predicting H1N1 Vaccine Uptake Using Machine Learning Models
Predict whether people got H1N1 using data collected in the National 2009 H1N1 Flu Survey

## Overview
Vaccination is one of the most effective public health interventions, providing individual protection against infectious diseases while contributing to community immunity through "herd immunity." Understanding vaccination behavior is critical for designing strategies to address vaccine hesitancy, improve uptake, and ensure equitable access, especially during pandemics where timely immunization is essential to controlling outbreaks. This project involves analyzing and modeling vaccination patterns for H1N1 using data from the National 2009 H1N1 Flu Survey. 

The primary goal of this project is to support public health efforts by understanding the factors influencing vaccination uptake during the 2009 H1N1 influenza pandemic. By analyzing data from the National 2009 H1N1 Flu Survey, the project aims to identify key demographic, behavioral, and attitudinal predictors of vaccination. This understanding is crucial for informing future vaccination campaigns.

## Problem Statement
During the 2009 H1N1 influenza pandemic, significant challenges arose in achieving widespread vaccine uptake, despite the availability of an effective vaccine. Understanding why some individuals chose to receive the vaccine while others did not is a critical problem for public health, as similar barriers persist in contemporary vaccination efforts, such as those for COVID-19. This project seeks to address the problem of predicting vaccination behavior based on individual characteristics, including demographics, health behaviors, and attitudes toward vaccination. By identifying the factors most strongly associated with vaccine uptake, public health authorities can better tailor communication strategies and interventions to address vaccine hesitancy and improve immunization rates in future health crises.


## Objectives

- Identify key factors influencing vaccination decisions.
- Provide insights for public health vaccination campaigns.
- Evaluate the performance of the predictive model using appropriate metrics.
- Inform strategies for improving vaccine coverage and addressing hesitancy.
  
## Data Sources
The National 2009 H1N1 Flu Survey dataset, which includes:
- Vaccination status for H1N1.
- Demographic, socioeconomic, and behavioral characteristics of respondents.
- Opinions on vaccine effectiveness and risk perception.

## Stakeholders
- Public health organizations (e.g., CDC, WHO) interested in vaccine uptake.
- Policymakers aiming to increase vaccination rates.
- Researchers and epidemiologists studying vaccination behavior.
- Healthcare providers involved in vaccine distribution and outreach.

### Research Questions
1. What demographic, behavioral, and attitudinal factors are most strongly associated with receiving the H1N1 vaccine?
2. Can a predictive model accurately classify individuals based on their likelihood of vaccination?
3. How do perceptions of vaccine safety and efficacy influence vaccination decisions?
4. Are certain population groups more likely to decline vaccination, and why?
5. How can insights from the 2009 H1N1 vaccination data inform future public health campaigns?

### Data Analysis
The data analysis reveals key insights into the factors influencing H1N1 vaccine uptake, with a notable class imbalance in the target variable, where 78.3% of individuals did not take the vaccine. Correlation analysis showed significant relationships between certain variables, such as behavioral_large_gatherings with behavioral_outside_home, and doctor recommendations with vaccine uptake. Additionally, variables like perceived risk and doctor recommendations were found to strongly influence vaccine uptake, as shown by visualizations where higher perceived risk levels and doctor recommendations correlated with increased vaccine uptake. The analysis also highlighted the potential for multicollinearity among some features, though the low-to-moderate correlation between most independent variables ensured minimal multicollinearity, which is beneficial for building reliable predictive models. The class imbalance and correlations found in the data informed the modeling process, where different algorithms were tested, with logistic regression proving to be the best performer.

### Data Visualizations
#### Distribution of H1N1 Vaccine Uptake

![image](https://github.com/user-attachments/assets/0c43ebd2-f3f0-48b9-9ca4-3949a9a007e5)

The target variable H1N1 Vaccine has a class imbalance with with class No being the highest at 78.3%

#### H1N1 Vaccine Uptake vs. Perceived Risk

![image](https://github.com/user-attachments/assets/4aace8d4-283b-4833-a899-f5a4b0e0ffac)

The bar chart illustrates the relationship between the perceived risk of H1N1 (on a scale of 1 to 5) and vaccine uptake. It shows that higher perceived risk (levels 4 and 5) correlates with increased vaccine uptake, whereas lower perceived risk (levels 1 and 2) is associated with significantly fewer people choosing to vaccinate.

#### H1N1 Vaccine Uptake vs. Doctor Recommendation

![image](https://github.com/user-attachments/assets/fc0f0f04-0760-493e-9880-a0d76023a5fe)

The bar chart highlights the influence of doctor recommendations on H1N1 vaccine uptake. Individuals who received a doctor’s recommendation (value 1) showed a significantly higher proportion of vaccine uptake than those who did not (value 0), where most chose not to vaccinate.

#### Model Performance 
Four models were evaluated: a baseline model, logistic regression, decision tree, and random forest. The key results are as follows:

##### Logistic Regression:
- Test Accuracy: 0.8722
- Precision (Class 1): 0.89, Recall: 0.86, F1-Score: 0.87
- Precision (Class 0): 0.86, Recall: 0.89, F1-Score: 0.87
- Confusion Matrix: 3055 True Negatives, 382 False Positives, 497 False Negatives, 2942 True Positives
- Best performing model in terms of accuracy and balanced metrics.

##### Random Forest:
- Training Accuracy: 0.9712
- Test Accuracy: 0.8266
- Precision (Class 1): 0.77, Recall: 0.94, F1-Score: 0.84
- Precision (Class 0): 0.92, Recall: 0.71, F1-Score: 0.80
- Confusion Matrix: 2444 True Negatives, 993 False Positives, 199 False Negatives, 3240 True Positives
- Potential overfitting indicated by the large gap between training and test accuracy.

##### Decision Tree:
- Test Accuracy: 0.8040
- Precision (Class 1): 0.81, Recall: 0.80, F1-Score: 0.80
- Precision (Class 0): 0.80, Recall: 0.81, F1-Score: 0.81
- Confusion Matrix: 2789 True Negatives, 648 False Positives, 700 False Negatives, 2739 True Positives


Overall, logistic regression achieved the best balance of accuracy, precision, recall, and F1-score across both classes.



#### Logistic Model

![image](https://github.com/user-attachments/assets/dfcb3e84-d84b-4bec-88ec-a02a313d95e3)

The confusion matrix evaluates the performance of the logistic regression model on test data. It shows that the model correctly classified 3055 true negatives (class 0) and 2942 true positives (class 1), achieving high accuracy for both classes. However, there are 382 false positives and 497 false negatives, indicating some misclassifications that could be improved with further model optimization or additional features.

![image](https://github.com/user-attachments/assets/d917e411-a6d5-416f-a24e-aacd85674a59)

The logistic Model is the best-performing model since it has the highest area under the curve of 0.94

### Conclusion
The H1N1 vaccine uptake dataset analysis revealed critical factors influencing vaccine adoption, such as perceived risk, doctor recommendations, and behavioral factors. Despite the class imbalance in the data, careful preprocessing and model selection, including the use of logistic regression, produced a highly accurate and balanced model. The findings suggest that increasing perceived risk and encouraging doctor recommendations could be effective strategies to boost vaccine uptake.

### Recommendations
1. Target education campaigns to raise awareness about the perceived risk of H1N1, especially for those with lower risk perception.
2. Encourage doctor recommendations for H1N1 vaccination to increase uptake, as individuals who received a doctor's recommendation showed significantly higher vaccine adoption.
3. Monitor and manage behavioral factors, such as participation in large gatherings or time spent outside the home, as these were correlated with vaccine uptake.


