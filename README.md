 INTRODUCTION 
This project applied fundamental machine learning techniques to a restaurant dataset in order to predict
restaurant ratings using regression and classification models to predict restaurant ratings and classify restaurants
into high and low rated categories. This is to better understand the factors driving operational performance and 
customer satisfaction. 
The objective was to explore data preparation techniques, model evaluation, and performance comparison while providing
meaningful business insights.
DATA PREPARATION
Using the two regression models, the dataset was first inspected to understand its structure, data types, and 
missing values. Key preprocessing steps included:
•	Handled missing values and ensuring consistency across features.
•	Encoded categorical variables (city, cuisines, currency) using Label Encoding.
•	Converted binary columns (‘Has Table Booking, ‘Has Online Delivery’, ‘Is Delivering Now’) 
into numerical format of 1, 0 = Yes/ No. 
The evaluation metrics used include Mean Absolute Error (MAE), Mean Squared Error (MSE), Root Mean Squared Error (RMSE) 
and the coefficient of determination (R2) Score and the summary of the result is as shown below.  
Model	                   MAE 	      MSE	      RMSE	      R2
Linear Regression 	     1.015	    1.52	    1.232	      0.33
Random Forest Regressor	 0.193	    0.08	    0.296     	0.96
Interpretation
•	Linear Regression showed moderate performance, explaining only 33% of the variance in ratings. The relatively high MAE 
and RMSE indicate noticeable prediction error.
•	In contrast, Random Forest Regressor significantly outperformed Linear Regression, achieving an R2 of 0.96 and much l
lower error values. This suggests that restaurant ratings exhibit complex, non-linear relationships as these ratings 
are driven by customer behaviour, pricing patterns, geographical environment and engagements. 
Business Insights
•	It must be noted that convenience play a significant role in customer satisfaction. When a restaurant is efficient in 
their service delivery and as well quick to order from, customers sense a high service value, and this leads to more visits and satisfaction. 
Economically, this aligns with utility maximisation. 
•	Online delivery and pricing strategy also strongly influence ratings as digital restaurant platforms can now use AI 
algorithms to shape how customers compare options and evaluate value for their money.
CLASSIFICATION MODEL
Two classification models were evaluated using Logistic Regression and Random Forest Classifier to identify high rated 
and low rated restaurants. The Logistic Regression model was analysed and there was a class imbalance in the rating 
category (88% versus 12%) . Then SMOTE technique was used to rebalance the low rated restaurants in the training data. 
Below is the result 
Model                    	SMOTE used	Accuracy 	Precision	    Recall	       F1 
Logistic Regression	         Yes 	    86.49%	    44.67%	    81.48%	     57.70%
Random Forest Classifier 	   No	      92.67%	    73.46%	    55.09%	     62.96%
Interpretation
•	Logistic Regression with SMOTE significantly improved recall, this means that it identified high-rated restaurants more
effectively. However, its precision was relatively low, indicating more false positives.
•	Random Forest Classifier achieved higher overall accuracy and precision, as well as a stronger F1-score, demonstrating 
better balance between identifying high-rated restaurants and avoiding incorrect classifications.
When I tested SMOTE for Random Forest Classifier too, it improved the recall score but the gain was not substantial enough
to justify replacing the original model without SMOTE above. Therefore, Random Forest without SMOTE was retained for 
final comparison.
FOOT NOTE
Linear models assume linear relationships between features and targets. However, restaurant ratings are influenced by 
complex interactions such as pricing, engagement, and service features. Random Forest Regressor models capture 
non-linear relationships and interactions automatically, explaining their superior performance.
Additionally, Logistic Regression was more sensitive to class imbalance, requiring SMOTE for improved detection of 
high-rated restaurants. Random Forest Classifier handled imbalance perfectly. 
OBSERVATION
•	If a more advanced imbalance techniques was used such as SMOTE combined with Tomek links or balanced random forest,
then there would have been a better balance of recall and precision to generate to identify more from the low rated
restaurants. 
CONCLUSION
Overall, this project demonstrates a practical application of machine learning fundamentals, model evaluation, and 
analytical reasoning in a real-world restaurant context. 

CONCLUSION
Overall, this project demonstrates a practical application of machine learning fundamentals, model evaluation, and analytical reasoning in a real-world restaurant context. 
