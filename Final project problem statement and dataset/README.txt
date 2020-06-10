@Author: Suranjan Daw

Project: Customer Churn Prediction for a bank. The detailed problem statement is in the Final Project Problem Statement.docx file. 

Points and Effort for this project:

1. Most of the data points had outliers
2. The data was skewd thus Log transformation was required
3. There were missing values in gender of the customer, occupation of the customer , city of the customer , dependents of each 
customer and days since last transaction. All of them were dealt with using techniques mnetuoned in the notebook
4. There are two files Data_Explore_Manipulate.ipynb and Final_Project_model.ipynb As there names suggest Data_Explore_Manipulate.ipynb 
explores the dataset and manipulates the data as required for better performance if our models. The Final_Project_model.ipynb 
runs our data througn different ML algorithms and evaluate their performance .
5. The evaluation criteria we will be using is f1_score , precision and AUC ROC scores. 
Here Precision is quite important since it depends of True Positives and a higher value of Precision indiocates a low False Positive.
A less False Positive is important since in Bank Customer Churning problem. Wrongfully labeling a person to False Positive 
will impact the bank's reputation and can harass the customer. 


Fist run the Data_Explore_Manipulate.ipynb file and then run Final_Project_model.ipynb file to get results. 

It can be seen that the Random Forest model and Logistic Regression model works best provided the given dataset.
The Mean scores for all the model suggests that Random Forest performed the best for this datase with a precision of 74.26 %

Thank You. 


