CONSUMER BEHAVIOUR AND RESTAURANT RATING PREDICTION 
Machine Learning Project | Python, scikit-learn, imbalanced learn 

Overview
This project applies regression and classification models to a restaurant dataset to predict ratings and classify restaurants as high or low rated. The goal was to understand the factors driving customer satisfaction and operational performance, while comparing model approaches across both tasks. 

Problem 
Restaurant ratings are influenced by complex and non-linear interactions. These are pricing, service convenience, location and customer engagement. This project tests whether linear assumptions hold, and what happens when they don't. 

Dataset
A structured restaurant dataset containing features including country, city, cuisine type, pricing, online delivery availability, table booking, votes and aggregate ratings. 

Target Variable
Regression: Aggregate rating ( continous, 0-5 scale)
Classification: Rating Category (1= High rated >4, 0= low rated <=4)

Data Preparation 
Dropped irrelevant identifiers: Restaurant ID, Name, Address, Rating Text, Rating Colour. 
Dropped rows with missing cuisine values
Encoded binary columns (Has table booking, has online delivery, is delivery now) as 1/0 
Applied Label Encoding to multiclass features: City, Currency, Cuisines
80/20 train-test split with random_state=42 for reproducibility. 

Part 1 Regression: Predicting Restaurant Ratings 
Models Compared 
Metric       Linear Regression       Random Forest Regressor
MAE              1.015                     0.193
MSE              1.517                     0.087
RMSE             1.232                     0.296
R2               0.33                      0.96

Key Findings 
Random Forest Regressor dramatically outperformed Linear Regression, achieving an R2 of 0.96 vs 0.33. Thius confirms that restaurant ratings are driven by complex and non linear relationships. However, it must be noted that linear assumptions are insuffiicient for this type of behavioural data. 

Feature Importance (Linear Regresion Coefficients)
Has Online Delivery (0.724) is the strongest predictor as restaurants offering online delivery tend to rate 0.72 points higher. 
Price Range (0.534) suggest that higher priced restaurants receive better ratings, suggesting that premium quality is being rewarded. 
Is Delivering Now (-0.155) has a slight negative effect. This possibly suggest lower end fast food establishments.

Part 2 Classification High Rated Versus Low Rated Restaurants

Class Imbalance 
The dataset contained significant class imbalance
Low Rated (<= 4), : 8430 restaurants (88%)
High Rated (>4),  : 1112 restaurants (12%)

SMOTE (Synthetic Minority Oversampling Technique) was applied to the training data for Logistic Regression to address this imbalance. 
SMOTE was also tested on Random Forest Classifier but did not justify replacing the model. 

Models Compared 
Model                       SMOTE       Accuracy         Precision             Recall           F1
Logistic Regresssion         Yes         86.49%            44.67%              81.48%           57.70%
Random Forest Classifier     No          92.67%            73.46%              55.09%           62.96%

Key Findings 
Random Forest Classifier without SMOTE achieved the strongest overall performance which are higher accuracy, higher precision and higher F1 score. 
Logistic Regression with SMOTE improved recall significantly but at the cost of precision, producing mare false positives.

Random Forest Classifier eas selected as the final model forits superior balance between identifying high rated restaurants and avoiding incorrect classifications. 

Observations and Future Improvements 
If given more time, more advanced imbalanced techniques would be explored:
SMOTE combined with TOMEK Links
Cost-Sensitive Learning 
Balanced Random Forest 

These approaches could generate a better recall precision balance for minority class detection without sacrificing overall accuracy. 

KEY NOTE 
Linear models underperform on real world behavioural data.
Class imbalance require deliberate handling as accuracy alone can be a misleading metric. 
SMOTE improves recall but reduces precision. The right choice depends on the business cost of false negatives vs false positives. 
Random Forest handles both non-linearity and class imbalance more robustly than linear alternatives. 

Prerequisites 
ip install pandas numpy scikit-learn imbalanced-learn 
matplotlib seaborn plotly joblib





















































