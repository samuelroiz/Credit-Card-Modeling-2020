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

## 3. Graphs

After compiling all the data, applying sample weights, and determining the frequency distribution, it's crucial to visualize this information through graphs. This step will help compare the different variables to identify the best fit.

### 3.1 Age of Accounts

**Figure 1: Noisy Age of Account (Months)**

The graph initially appeared somewhat cluttered, displaying numerous spikes beyond the 170-month mark. These spikes, indicative of noise, obscured the clarity of the data presentation. To enhance accuracy and readability, I trimmed the maximum age range of the accounts, effectively reducing the noise.

With the adjustments made, the graph's clarity significantly improved. It revealed that accounts aged around fifty months exhibit a higher likelihood of non-repayment by customers. However, this alone doesn't provide sufficient insight to make a decision on trustworthiness based on account age alone. Subsequent graphs will further aid in determining which customers are more likely to be reliable.

### 3.2 Credit Card Balance to Loan Ratio

**Figure 2: Age of Account (Months)**

#### 3.1.1 Summary of Age of Accounts
The summary of Age of Accounts suggests that the longer an account has been open, the lower the risk it poses to the bank. This is because a longer account history indicates consistent management and payment of dues. Conversely, newer accounts pose a higher risk due to their lack of established history, presenting greater uncertainty and potential loss for the bank.

#### 3.2 Credit Card Balance to Loan Ratio

A credit card consolidation loan consolidates multiple credit card debts into a single loan with a fixed interest rate and term. This strategy not only can reduce the overall interest paid but also streamline the debt repayment process.

**Figure 3: Noisy Credit Card Balance to Loan Ratio**

**Figure 4: Adjusted Credit Card Balance to Loan Ratio**

After applying noise reduction techniques to the data, a clearer trend emerges, particularly around the 50% credit card balance to loan ratio mark. Here, we observe a spike indicating an increased likelihood (by at least 10%) of non-repayment. This insight is crucial for assessing risk and making informed lending decisions.

#### 3.2.1 Summary of Credit Card Balance to Loan Ratio

The analysis reveals that lower credit card balance to loan ratios are associated with decreased risk levels, starting from a baseline risk of 5%. However, as the ratio increases, so does the risk, reaching a notable increase of at least 10% once the ratio exceeds 32%. Beyond a 100% ratio, the risk escalates to 14% or more, highlighting the significant impact of this metric on creditworthiness.

### 3.3 Auto Balance Ratio

The Auto Balance Ratio is crucial for credit scoring as it reflects the proportion of available credit utilized. Best practices suggest keeping this ratio under 30%, as lower utilization rates are viewed more favorably.

**Figure 5: Auto Balance Ratio**

Lower auto balance ratios are typically associated with a higher likelihood of creditworthiness, as they indicate prudent credit management. Conversely, accounts exhibiting negative ratios (indicating no credit usage or maxed-out credit) are flagged as higher risk due to their potential financial instability.

### 3.3 Auto Balance Ratio

#### 3.3.1 Summary of Auto Balance Ratio
The Auto Balance Ratio offers insights into the financial behavior of account holders. A positive auto-balance ratio indicates potential risk, whereas a negative ratio suggests minimal to no risk. Accounts with an auto-balance ratio between one and fifty represent a significant risk, with an estimated ten to twelve percent likelihood of default. However, compared to other variables, the Auto Balance Ratio is less reliable for predicting risk unless the ratio falls within this specific range.

### 3.4 Number of Accounts

**Figure 6: Noisy Number of Accounts**

**Figure 7: Number of Accounts**

#### 3.4.1 Summary of Number of Accounts
The Number of Accounts a client holds can influence their credit risk profile. Generally, the risk associated with a client increases gradually with the number of accounts they have. This is attributed to the potential for increased financial obligations and the uncertainty surrounding the stability of these accounts. A client with fewer accounts is deemed less risky as they have fewer financial commitments. Risk levels start at five percent for clients with one to four accounts but escalate to twenty percent for those holding forty to forty-five accounts. Beyond forty-eight accounts, the risk is considered very high, partly due to the lack of sufficient data on accounts exceeding this number.

### 3.5 Number of Accounts Ever 30 Days Past Due

Accounts that have never been late on payments beyond thirty days exhibit only a four percent probability of default. However, as the frequency of late payments increases, so does the risk of default. The probability jumps dramatically from a four percent chance of default for accounts never late to a thirty-six percent chance for accounts that have been late nine times. This stark contrast underscores the significant impact of payment timeliness on credit risk assessment.

### 3.6 Number of Accounts Ever 60 Days Past Due

The graph illustrating the number of accounts ever sixty days past due shows a pattern similar to the thirty-day metric, albeit with significantly higher risk levels for each occurrence of late payment. The risk drops to zero for accounts late thirteen times, simply because there are no accounts with this number of late payments. It's crucial, however, to analyze the data for accounts 90 days past due before drawing definitive conclusions.

**Figure 9: Number of Accounts 60 Days Past Due**

### 3.7 Number of Accounts Ever 90 Days Past Due

Accounts with nine instances of being 90 days past due exhibit a minimum risk of 25% for not repaying. For both sixty and ninety days past due, accounts with at least fourteen instances of late payments show a high probability, up to 100%, of default. This data underscores the significant role these variables play in assessing financial stability.

**Figure 10: Number of Accounts 90 Days Past Due**

#### 3.7.1 Summary of Accounts Ever Days Past Due

This analysis reveals the predictive accuracy of Days Past Due (DPD) metrics. For 30 DPD, accounts with five or more instances of late payments are considered unreliable. Risk acceptance should not extend beyond 15 instances, as this represents an eighty percent increase in risk. For 60-day metrics, the risk begins at 5% with any late payment, advising against trust beyond zero occurrences. For those willing to accept risk, it is advisable not to exceed three instances, as this corresponds to a significant risk increase.

### 3.8 Number of Inquiries Last 6 Months

Credit inquiries significantly impact individuals with few accounts or a short credit history. Statistically, individuals with six or more inquiries on their credit reports are much more likely to declare bankruptcy than those with none. The associated graph demonstrates a steep increase in risk with the number of inquiries; a single inquiry starts with a seven percent risk, escalating dramatically with each additional inquiry.

**Figure 11: Number of Inquiries Last 6 Months**

### 3.9 Number of Inquiries Last 12 Months

The trend for inquiries over the last twelve months mirrors that of the last six months, suggesting a high risk associated with multiple inquiries. The graph should ideally be limited to twelve accounts to reduce noise. Beyond twelve inquiries, the risk skyrockets to sixty percent.

**Figure 12: Number of Inquiries Last 12 Months**

#### 3.9.1 Summary of Inquiries

The inquiry data provides a clear indication of high risk associated with multiple inquiries. A single inquiry poses at least a five percent risk, which significantly increases with each additional inquiry over six months. Over twelve months, the risk increases by ten percent for every six inquiries, with a dramatic forty percent increase observed beyond ten inquiries.

### 3.10 Number of Mortgages

**Figure 13: Number of Mortgages**

#### 3.10.1 Summary of Number of Mortgages

The risk associated with the number of mortgages starts at five percent and increases gradually with each additional mortgage, peaking at twenty-six percent. This trend indicates that individuals with multiple mortgages pose a higher risk to lenders, as they must manage multiple loan repayments concurrently. Fewer mortgages correlate with lower risk levels.

## 4 Results

This section reflects on the project's outcomes, challenges, and learning experiences.

### 4.1 Interesting Findings

Curve fitting is fascinating for its versatility in application and methodology. Despite its simplicity, mastering curve fitting can be challenging. This project highlighted the intriguing aspect of applying curve fitting to various scenarios, beyond conventional applications, making it an engaging and versatile tool.

### 4.2 Challenges

The project presented numerous challenges, starting with data collection. Managing a dataset with 7,500 accounts and 28 variables (totalling 210,000 data points) was daunting. Additionally, the application of frequency table codes and the integration of LaTeX formatting posed significant hurdles. Time management and efficient data processing were among the primary challenges faced during this project.

### 4.3 Learnings

The project was a valuable learning experience, offering insights into curve fitting and broader data analysis techniques. Understanding the methodology behind curve fitting has equipped me with skills applicable across various software and analytical tasks, emphasizing the importance of methodological knowledge over programming proficiency alone.

