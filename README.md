# Graduate-Admissions-Model

## Authors: John Lederer, Hye Rim Ahn, Yirong Cai, Richard Nguyen

## Purpose

This model attempts to predict the chance of an international student's admission into graduate school based on 7 parameters: GRE score, TOEFL score, university rating, statement of purpose strength, letter of recommendation strength, undergraduate GPA, research experience, and chance of admission. This model can help international students gauge their likelihood of admission to graduate school, helping them to plan accordingly. It can also give insight to prospective graduate students about what graduate schools look for in successful candidates, allowing them to engage in behaviors that may increase their chance of admission. This is of great importance because graduate school admission criteria is often viewed as a "black box"; it is often difficult to understand why some students are admitted while others are rejected.

## Data

The model is constructed using data obtained from https://www.kaggle.com/mohansacharya/graduate-admissions; it was originally created by Mohan S Acharya, Asfia Armaan, and Aneeta S Antony. The data set contains 500 observations of 9 variables including: serial number, GRE score, TOEFL score, university rating, statement of purpose strength, letter of recommendation strength, undergraduate GPA, research experience, and chance of admission.

## Methods

We began with a full model predicting chance of admission using all available predictors. We then used BIC to preform variable selection and an ANOVA test to ensure that the removed predictors were not statistically significant. We then checked the normality assumption via a normal Q-Q plot and Shapiro-Wilk test; we also checked the constant variance assumption via a residual plot and Breusch-Pagan test. Attempting to meet the assumptions, we preformed a Box-Cox Transformation using the approximate optimal lambda of 2.2, this transformation allowed the model to meet the assumptions of normality and constant variance. We then checked for highly influential points using Cook's distance, and elected to remove some observations with undue influence. We thus arrived at a final model.

## Findings

The final model we selected is as follows:

![equation](https://latex.codecogs.com/png.image?%5Cbg_white%20\dpi{110}\hat{y}_{\text{Chance&space;of&space;Admit}}^{2.2}&space;=&space;-1.627&space;&plus;&space;0.002x_{\text{TOEFL}}&space;&plus;&space;0.001x_{\text{GRE}}&space;&plus;&space;0.085x_{\text{GPA}}&space;&plus;&space;0.016x_{\text{Research}}&space;&plus;&space;0.011x_{\text&space;{LOR}})

The model is statistically significant with a p-value less than 2.2e-16. It explains a considerable amount of variation in chance of admission to graduate school with an R-squared of 0.8941. An interesting finding was that nearly all students with a relatively high GPA also had undergraduate research, this is logical as students conducting research may be more interested and involved in their course work. Our final model indicates that the statistically significant predictors of admission chance are TOEFL score, GRE score, undergraduate GPA, and undergraduate research. Surprisingly, the strength of their undergraduate university, and strength of the statement of purpose did not have a statistically significant affect on their chance of admission.
