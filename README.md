This project was undertaken as one of my initial mathematics projects at CSUN in 2020. I opted to focus on a credit card model due to the complexity and widespread use of credit scores, which are underpinned by such models. The credit score system intrigued me, as it plays a crucial role in financial decision-making processes worldwide. My curiosity was not only academic; I was also motivated by a personal interest in understanding the mechanics behind credit scores. This knowledge had the potential to offer insights into improving my own credit score, making the project both a learning opportunity and a practical exploration into enhancing personal financial health.

1. Introduction
1.1 What is Curve Fitting
Curve fitting is a highly valuable and widely utilized analysis tool in software such as Matlab, Origin, Excel, among others. It is employed daily across various sectors including banking and scientific research. Curve fitting examines the relationship between one or more predictor variables and a response variable, aiming to define a "best fit" model of this relationship. Through analyzing this model, we can predict outcomes and discern which variables are more or less influential. For instance, consider working for a bank with 10 customers who have taken out loans and possess credit cards. If only 4 of these customers repaid their loans while the remaining 6 did not, the bank would be interested in identifying potential non-payers in the future. This involves analyzing customer data, such as the number of credit cards held, and the frequency of late payments beyond 30 days. These variables contribute to a curve fitting model that patterns trustworthy behaviors, aiding in the decision-making process.

1.2 My Project Scenario
Background
A bank approached me with a request to develop a model that could assist in determining the trustworthiness of loan applicants. The provided data encompassing account details was complex and required extensive cleaning.

Data Cleaning and Variable Selection
To refine the data, I established several key variables:

Outcome: The primary indicator, representing the dichotomy of customers who have fulfilled or failed their loan obligations.
Age of Account: The duration since the account was opened.
Credit Card Balance to Loan Ratio: The proportion of credit card debt relative to the loan amount.
Auto Balance Ratio: The ratio of auto loan balances to the total loan amount.
Number of Accounts: The total accounts held by a customer.
Accounts Past Due: This includes several variables indicating the number of accounts 30, 60, and 90 days past due.
Number of Inquiries: The frequency of credit inquiries within the last 6 and 12 months.
Number of Mortgages: The count of mortgage accounts.
The initial step involved analyzing the outcome data to identify patterns of loan repayment. Subsequently, I sought out credit card model data for reference and generated random numbers to simulate a realistic scenario.

Objective
The aim is to craft a model that enables the bank to reliably predict the likelihood of loan repayment by prospective borrowers, thereby mitigating financial risk and enhancing decision-making processes.
