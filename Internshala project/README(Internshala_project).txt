Author: Swastik Nandi


Customer Churn Prediction:
A Bank wants to take care of customer retention for its product: savings accounts. The bank wants you to identify customers likely to churn balances below the minimum balance. You have the customers information such as age, gender, demographics along with their transactions with the bank.
Your task as a data scientist would be to predict the propensity to churn for each customer.
Data Dictionary
There are multiple variables in the dataset which can be cleanly divided into 3 categories:
I. Demographic information about customers
•	customer_id - Customer id 
•	vintage - Vintage of the customer with the bank in a number of days 
•	age - Age of customer 
•	gender - Gender of customer 
•	dependents - Number of dependents 
•	occupation - Occupation of the customer 
•	city - City of the customer (anonymized) 
II. Customer Bank Relationship
•	customer_nw_category - Net worth of customer (3: Low 2: Medium 1: High) 
•	branch_code - Branch Code for a customer account 
•	days_since_last_transaction - No of Days Since Last Credit in Last 1 year 
III. Transactional Information
•	current_balance - Balance as of today 
•	previous_month_end_balance - End of Month Balance of previous month 
•	average_monthly_balance_prevQ - Average monthly balances (AMB) in Previous Quarter 
•	average_monthly_balance_prevQ2 - Average monthly balances (AMB) in previous to the previous quarter 
•	current_month_credit - Total Credit Amount current month 
•	previous_month_credit - Total Credit Amount previous month 
•	current_month_debit - Total Debit Amount current month 
•	previous_month_debit - Total Debit Amount previous month 
•	current_month_balance - Average Balance of current month 
•	previous_month_balance - Average Balance of previous month 
•	churn - Average balance of customer falls below minimum balance in the next quarter (1/0) 


Solution:

	First we clean the data by imputing the missing values and removing the outliers.For cleaning I have used the following techniques.They are:
	
	1) For imputing the missing data I have used mode of those particular columns(eg: occupation,city,dependents) and for the other ones I have assigned them to a different category for that
	   particular column(i.e: missing values of gender are assigned to -1 and missing values of days_since_last_transaction are assigned to 999).
	2) For Outlier treatment I have used logarithmic transformation (since those column's data are right skewed) and after that I droped rows which were still outliers.
	3) Used One hot encoding to change occupation to numeric data type.

	After cleaning the data I have fitted my data into 3 models (viz Logistic regression , Random Forest ,KNN).
	To evaluate those models I have used Evaluation metrics like ROC_AUC score and precision since in this problem we have to correctly predict whether a customer is likely to churn balances.
	Now if we falsely predict a customer to churn balances then it would humiliate the customer as well as reduce the reputation of the bank.Thus we need to reduce to the the FPR rate.Thus evaluation metrics 
	like AUC_ROC and precision are more helpful in this case.

	Then I did a comparitive study on all of those 3 models with 5 fold cross validation technique.

	After doing all those I found that Random Forest gave the most convincing outcome. 