## Why did I choose this topic?
This project was undertaken as one of my initial mathematics projects at CSUN in 2020. I opted to focus on a credit card model due to the complexity and widespread use of credit scores, which are underpinned by such models. The credit score system intrigued me, as it plays a crucial role in financial decision-making processes worldwide. My curiosity was not only academic; I was also motivated by a personal interest in understanding the mechanics behind credit scores. This knowledge had the potential to offer insights into improving my own credit score, making the project both a learning opportunity and a practical exploration into enhancing personal financial health.

## 1. Introduction

### 1.1 What is Curve Fitting

Curve fitting is a highly valuable and widely utilized analysis tool in software such as Matlab, Origin, Excel, among others. It is employed daily across various sectors including banking and scientific research. Curve fitting examines the relationship between one or more predictor variables and a response variable, aiming to define a "best fit" model of this relationship. Through analyzing this model, we can predict outcomes and discern which variables are more or less influential. For instance, consider working for a bank with 10 customers who have taken out loans and possess credit cards. If only 4 of these customers repaid their loans while the remaining 6 did not, the bank would be interested in identifying potential non-payers in the future. This involves analyzing customer data, such as the number of credit cards held, and the frequency of late payments beyond 30 days. These variables contribute to a curve fitting model that patterns trustworthy behaviors, aiding in the decision-making process.

### 1.2 My Project Scenario

#### Background

A bank approached me with a request to develop a model that could assist in determining the trustworthiness of loan applicants. The provided data encompassing account details was complex and required extensive cleaning.

#### Data Cleaning and Variable Selection

To refine the data, I established several key variables:

- **Outcome**: The primary indicator, representing the dichotomy of customers who have fulfilled or failed their loan obligations.
- **Age of Account**: The duration since the account was opened.
- **Credit Card Balance to Loan Ratio**: The proportion of credit card debt relative to the loan amount.
- **Auto Balance Ratio**: The ratio of auto loan balances to the total loan amount.
- **Number of Accounts**: The total accounts held by a customer.
- **Accounts Past Due**: This includes several variables indicating the number of accounts 30, 60, and 90 days past due.
- **Number of Inquiries**: The frequency of credit inquiries within the last 6 and 12 months.
- **Number of Mortgages**: The count of mortgage accounts.

The initial step involved analyzing the outcome data to identify patterns of loan repayment. Subsequently, I sought out credit card model data for reference and generated random numbers to simulate a realistic scenario.

#### Objective

The aim is to craft a model that enables the bank to reliably predict the likelihood of loan repayment by prospective borrowers, thereby mitigating financial risk and enhancing decision-making processes.

## 2. Data

### 2.1 Outcome

The initial dataset received from the bank consisted of 7,500 records concerning loan outcomes. For illustrative purposes, we will discuss only 40 of these outcomes. Due to the extensive and complex nature of the data, I employed a frequency table for simplification. Frequency tables significantly enhance data readability by condensing information. This approach transformed what would have been an overwhelming 7,500-line table into a succinct summary, demonstrating the utility of frequency tables in data analysis.

### 2.1.1 Outcome and Age of Accounts

To further analyze the data, I combined the variables of outcome and the age of accounts, applying frequency coding to aggregate instances with identical values. This method allowed for a concise representation of the data, making it easier to observe patterns. For example, one entry in the dataset showed an account age of 3 months with an outcome of zero, indicating the account did not fulfill the loan repayment.

#### Table 1: Outcome

| Outcome |
|---------|
| 0       |
| 1       |
| 0       |
| 1       |
| 0       |
| 1       |
| 0       |
| 1       |
| 1       |
| 1       |
| 0       |
| 1       |
| 0       |
| 1       |
| 0       |
| 1       |
| 0       |
| 0       |
| 0       |
| 1       |
| 1       |
| 1       |
| 0       |
| 0       |
| 1       |
| 0       |
| 1       |
| 0       |
| 1       |
| 0       |
| 1       |
| 0       |
| 1       |
| 0       |
| 1       |
| 0       |
| 1       |
| 0       |
| 1       |

#### Table 2: Frequency of Outcomes

| Outcome | Amount |
|---------|--------|
| 0       | 2500   |
| 1       | 5000   |

#### Table 3: Outcome and Age of Accounts

| Outcome | Age of Accounts | Group Count |
|---------|-----------------|-------------|
| 0       | 1-3             | 1           |
| 0       | 3-1             | 1           |
| 0       | 4-1             | 1           |
| 0       | 5-3             | 1           |
| 0       | 6-3             | 1           |
| 1       | 0-1             | 1           |
| 1       | 1-4             | 1           |
| 1       | 2-4             | 1           |
| 1       | 3-3             | 1           |
| 1       | 4-2             | 1           |

### 2.1.2 Sample Weight

To manage the large dataset effectively while maintaining accuracy, I applied a technique known as sample weighting. This method allows for data reduction without distorting the underlying numerical relationships. For example, with an initial distribution of 5,000 '1' outcomes and 2,500 '0' outcomes, reducing the dataset to a total of 270 entries required careful balancing to reflect the original proportions. Employing sample weighting ensured that the reduced dataset accurately represented the original data's distribution.

#### Table 4: Without Sample Weight

| Outcome | Amount | Group Count |
|---------|--------|-------------|
| 1       | 0      | 1           |
| 1       | 1      | 4           |
| 1       | 2      | 4           |
| 1       | 3      | 3           |

#### Table 5: With Sample Weight

| Outcome | Amount | Group Count |
|---------|--------|-------------|
| 1       | 0      | 7           |
| 1       | 1      | 28          |
| 1       | 2      | 28          |
| 1       | 3      | 21          |
| 1       | 4      | 14          |


