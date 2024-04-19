## Why did I choose this topic?
This project was undertaken as one of my initial mathematics projects at CSUN in 2020. I opted to focus on a credit card model due to the complexity and widespread use of credit scores, which are underpinned by such models. The credit score system intrigued me, as it plays a crucial role in financial decision-making processes worldwide. My curiosity was not only academic; I was also motivated by a personal interest in understanding the mechanics behind credit scores. This knowledge had the potential to offer insights into improving my own credit score, making the project both a learning opportunity and a practical exploration into enhancing personal financial health.

# Contents

## Introduction
- **1.1 What is Curve Fitting**
- **1.2 My Project Scenario**

## Data
- **2.1 Outcome**
  - **2.1.1 Outcome and Age of Accounts**
  - **2.1.2 Sample Weight**
- **2.2 Full Table**

## Graphs
- **3.1 Age of Accounts**
  - **3.1.1 Summary of Age of Accounts**
- **3.2 Credit Card Balance to Loan**
  - **3.2.1 Summary of Credit Card Balance to Loan**
- **3.3 Auto Balance Ratio**
  - **3.3.1 Summary of Auto Balance Ratio**
- **3.4 Number of Accounts**
  - **3.4.1 Summary of Number of Accounts**
- **3.5 Number of Accounts Ever 30 Days Past Due**
- **3.6 Number of Accounts Ever 60 Days Past Due**
- **3.7 Number of Accounts Ever 90 Days Past Due**
  - **3.7.1 Summary of Accounts Ever Days Past Due**
- **3.8 Number of Inquiries Last 6 Months**
- **3.9 Number of Inquiries Last 12 Months**
  - **3.9.1 Summary of Inquiries**
- **3.10 Number of Mortgages**
  - **3.10.1 Summary of Number of Mortgages**

## Results
- **4.1 Interesting Observations**
- **4.2 Challenges Encountered**
- **4.3 Lessons Learned**

## Data
Data was obtained from people's accounts using random numbers. You are highly encouraged to visit [this website](http://www.wisc.edu/writing/Handbook/ScienceReport.html) for more information.

## 1. Introduction
### 1.1 What is Curve Fitting
Curve fitting is one of the most widely used analytical tools in applications such as Matlab, Origin, Excel, etc. It examines the relationship between one or more predictors and a response variable with the goal of identifying a "best fit" model. This model helps us predict and determine which variables are more or less effective. For instance, suppose I work for a bank with 10 customers who have taken out loans and own credit cards; only 4 of these customers repaid their loans. The bank needs to identify which customers are less likely to repay their loans. By analyzing variables such as the number of credit cards held and frequency of late payments beyond 30 days, we can develop a curve-fitting model to identify trustworthy customers.

### 1.2 My Project Scenario
A bank asked me to develop a model to help determine the trustworthiness of loan applicants. The data provided was extensive and disorganized, necessitating significant cleanup and the creation of multiple variables. The primary variables I used included the outcome, Age of Account, Credit Card Balance to Loan, Auto Balance Ratio, Number of Accounts, Number of Accounts Ever 30 Days Past Due, Number of Accounts Ever 60 Days Past Due, Number of Accounts Ever 90 Days Past Due, Number of Inquiries Last 6 Months, and Number of Inquiries Last 12 Months. The first step was to analyze the outcome, which represented the number of people who did and did not repay their loans. To model these scenarios, I utilized examples from credit card data models and wrote a code to generate random numbers.

## 2. Data Analysis
### 2.1 Outcome
The initial data set received from the bank included outcomes for 7,500 accounts, but it was presented in a very cluttered format. I employed a frequency table to simplify this data, reducing thousands of lines into a more manageable two-line representation.

#### 2.1.1 Outcome and Age of Accounts
This summary table combines the variables of outcome and age of accounts. Applying a frequency code helped to identify patterns, such as the correlation between younger accounts (3 months old) and non-payment. For example, there was one account that had an outcome of zero (non-payment) and was only three months old.

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

![Frequency of Outcomes](https://github.com/samuelroiz/Credit-Card-Modeling-2020/blob/main/images/table-2-credit-card-modeling.jpg?raw=true)


![Outcome and Age of Accounts](https://github.com/samuelroiz/Credit-Card-Modeling-2020/blob/main/images/table-3-credit-card-modeling.jpg?raw=true)

#### 2.1.2 Sample Weight
Since my dataset is large, I need to reduce it. However, reducing the data can skew the results. To maintain accuracy, I use a sample weight, which helps preserve the original ratio of the data. For instance, in the original dataset, there are 5,000 'ones' and 2,500 'zeros', indicating more 'ones' than 'zeros'. If I reduce the dataset to a total of 270 entries, I would adjust it to have an equal number of 'ones' and 'zeros', both at 85, with a sample weight of 7 applied only to the 'ones'. This means that when generating a table of outcomes for 'ones', I multiply the variables by 7 to reflect their true proportion in the original data.

![Without Sample Weight](https://github.com/samuelroiz/Credit-Card-Modeling-2020/blob/main/images/table-4-credit-card-modeling.jpg?raw=true)

![With Sample Weight](https://github.com/samuelroiz/Credit-Card-Modeling-2020/blob/main/images/table-5-credit-card-modeling.jpg?raw=true)

#### 2.2 Full Table
We have data on over twenty-eight variables. Below is a summary of the full table that we compiled from the bank data.

![Full Table](https://github.com/samuelroiz/Credit-Card-Modeling-2020/blob/main/images/table-6-credit-card-modeling.jpg?raw=true)

![Full Table](https://github.com/samuelroiz/Credit-Card-Modeling-2020/blob/main/images/table-7-credit-card-modeling.jpg?raw=true)

## 3. Graphs
Since I have gathered all of my data, applied sample weights, and executed frequency distribution analyses, I now need to create graphs to compare the variables and identify the best fit.

### 3.1 Age of Accounts
![Noisy Age of Account in month](https://github.com/samuelroiz/Credit-Card-Modeling-2020/blob/main/images/figure-1-credit-card-modeling.jpg?raw=true)

The graph, as you can see above, is somewhat messy. It displays numerous spikes after 170 months, which are typically considered noise. To improve clarity and accuracy, I need to trim down the maximum range of the age of accounts.

After reducing the spikes, the graph becomes clearer. This graph indicates that accounts at fifty months have a higher probability of defaulting. However, this information alone is insufficient to determine trustworthiness based solely on the age of accounts. The subsequent graphs will provide further insights to help determine whom we can trust.

![Age of Accounts](https://github.com/samuelroiz/Credit-Card-Modeling-2020/blob/main/images/figure-2-credit-card-modeling.jpg?raw=true)
### 3.1.1 Summary of Age of Accounts
The age of an account significantly impacts the risk profile presented to the bank. Older accounts demonstrate reliability and present less risk as they have a history of being in good standing and making payments on time. Conversely, younger accounts pose a higher risk as they have less history and the account holders have less to lose, making the potential for default higher.

### 3.2 Credit Card Balance to Loan
Credit card consolidation loans allow individuals to combine several credit card debts into a single loan with a fixed interest rate and term, potentially saving money and simplifying debt repayment.

**Figure 3:** Shows a trend where accounts with at least a fifty percent credit card balance to loan ratio exhibit a higher likelihood of non-payment, increasing by at least ten percent. Noise reduction is necessary for clearer analysis.

**Figure 4:** After noise reduction, the data becomes more accurate and provides a reliable indication of which accounts are at risk.
![Noisy Credit Card Balance to Loan](https://github.com/samuelroiz/Credit-Card-Modeling-2020/blob/main/images/figure-3-credit-card-modeling.jpg?raw=true)
![Credit Card Balance to Loan](https://github.com/samuelroiz/Credit-Card-Modeling-2020/blob/main/images/figure-4-credit-card-modeling.jpg?raw=true)
#### 3.2.1 Summary of Credit Card Balance to Loan
The risk associated with the credit card balance to loan ratio starts at five percent and increases progressively. As the ratio rises, so does the risk, peaking at fourteen percent once it exceeds a hundred percent. This incremental rise underscores the need for careful monitoring of this ratio.

### 3.3 Auto Balance Ratio
This metric is crucial as it informs credit scoring agencies about the percentage of available credit utilized by an individual. Best practices recommend using no more than 30 percent of your credit limits to maintain good credit health.

**Figure 5:** Illustrates that accounts with lower auto balance ratios are considered riskier. Accounts with negative ratios indicate no credit usage and maximum credit availability, which is viewed as a lower risk.

![Auto Balance Ratio](https://github.com/samuelroiz/Credit-Card-Modeling-2020/blob/main/images/figure-5-credit-card-modeling.jpg?raw=true)
#### 3.3.1 Summary of Auto Balance Ratio
The auto balance ratio is a significant risk indicator. Accounts with a positive ratio are considered risky, particularly those with ratios between one to fifty, which are deemed to have a risk of ten to twelve percent. However, compared to other variables, the auto balance ratio is not the most reliable risk predictor unless the ratio falls within this specific range.

#### 3.4 Number Accounts
The number of accounts represents how many accounts the client has with banks. We will examine if the number of accounts influences the likelihood of the client repaying the loan. The first graph (Figure 6) is quite noisy towards the end, indicating that the noise needs to be suppressed for clearer analysis. The second graph is much clearer. Accounts ranging from forty to forty-five exhibit a higher risk compared to others. Although all have at least a five percent probability of default, the risk significantly increases by three percent for every ten additional accounts.

![Number of Accounts](https://github.com/samuelroiz/Credit-Card-Modeling-2020/blob/main/images/figure-6-credit-card-modeling.jpg?raw=true)

![Number Accounts](https://github.com/samuelroiz/Credit-Card-Modeling-2020/blob/main/images/figure-7-credit-card-modeling.jpg?raw=true)
#### 3.4.1 Summary of Number of Accounts
The summary of the Number of Accounts indicates that the more accounts a client holds, the slower the risk increases. This gradual increase is due to the added responsibilities associated with managing multiple accounts, and the uncertainty regarding their stability. Conversely, the fewer accounts a client has, the more risk the bank can assume, as the client has fewer financial obligations that could impact their financial stability. The risk starts at five percent for one to four accounts, climbs to twenty percent for forty to forty-five accounts, and reaches an even higher risk level of twenty to forty-eight percent. Beyond fifty accounts, the risk becomes very high due to insufficient data on such accounts.

### 3.5 Number of Accounts Ever 30 Days Past Due
The Number of Accounts Ever 30 Days Past Due metric reflects how often accounts have been late with payments by more than 30 days. Accounts with zero late payments post a low default risk of only four percent. However, as the frequency of late payments increases, so does the probability of default. For example, an account that has been late nine times shows a dramatically higher default probability of thirty-six percent, underscoring the significant impact that payment history has on credit risk.

![Number of Acc. 30 Days Past Due](https://github.com/samuelroiz/Credit-Card-Modeling-2020/blob/main/images/figure-8-credit-card-modeling.jpg?raw=true)

### 3.6 Number of Accounts Ever 60 Days Past Due
The graph for the Number of Accounts Ever 60 Days Past Due is similar to that for 30 days but shows a significantly higher risk as the frequency of late payments increases. Notably, the risk drops to zero because no account has been late thirteen times. However, it's crucial to also consider the data for 90 days past due for a complete assessment.

![Number of Acc. 60 Days Past Due](https://github.com/samuelroiz/Credit-Card-Modeling-2020/blob/main/images/figure-9-credit-card-modeling.jpg?raw=true)

### 3.7 Number of Accounts Ever 90 Days Past Due
Similarly, for accounts that have been past due for ninety days, if an account has nine past due incidences, the risk of non-payment is at least twenty-five percent. For those that have been late fourteen times or more, the probability of default escalates dramatically, reaching up to one hundred percent. These metrics are crucial for determining financial stability.
![Number of Acc. 90 Days Past Due](https://github.com/samuelroiz/Credit-Card-Modeling-2020/blob/main/images/figure-10-credit-card-modeling.jpg?raw=true)
#### 3.7.1 Summary of Accounts Ever Days Past Due
Analyzing the Days Past Due (DPD) data, the risk assessment for 30 DPD advises against trusting any clients with more than five late payments; the risk jumps significantly after fifteen late payments, reaching an eighty percent increase in risk. For 60 days, the principle remains, but with fewer occurrences: no trust should be extended beyond zero late payments, as even one instance raises the risk by five percent, escalating to seventeen percent at three late payments.

### 3.8 Number of Inquiries Last 6 Months
Credit inquiries can significantly impact those with few accounts or a short credit history. Statistically, individuals with six or more inquiries on their credit reports are much more likely to declare bankruptcy than those with no inquiries. The risk associated with inquiries is substantial: starting at seven percent with one inquiry and skyrocketing to thirty percent with just six additional inquiries.

![Number Inquiries Last 6 months](https://github.com/samuelroiz/Credit-Card-Modeling-2020/blob/main/images/figure-11-credit-card-modeling.jpg?raw=true)

### 3.9 Number of Inquiries Last 12 Months
The pattern for the last 12 months of inquiries mirrors that of the last six months. The graph should be refined to focus only on the first twelve accounts to minimize noise and enhance clarity. However, once an account has been late twelve times, the associated risk soars to a staggering sixty percent.

![Figure 12](https://github.com/samuelroiz/Credit-Card-Modeling-2020/blob/main/images/figure-12-credit-card-modeling.jpg?raw=true)

#### 3.9.1 Summary of Inquiries
The summary of these two inquiry variables shows it is highly accurate in identifying clients who pose a significant risk. It is evident that we must exercise caution with even a single inquiry, where the risk starts at five percent. The risk then increases drastically by three percent every six months. Over twelve months, the risk rises by ten percent for every six inquiries, reaching a forty percent increase when there are ten inquiries.

### 3.10 Number of Mortgages

![Number of Mortgages](https://github.com/samuelroiz/Credit-Card-Modeling-2020/blob/main/images/figure-13-credit-card-modeling.jpg?raw=true)

#### 3.10.1 Summary of Number of Mortgages
The risk associated with the number of mortgages starts at five percent and increases gradually up to twenty-six percent. It is clear that the more mortgages an account holds, the higher the financial risk to the bank. This is because with each additional mortgage, the account holder has more loans to repay, increasing their financial burden. Conversely, fewer mortgages mean less risk.

## 4 Results
In this section, I will discuss my thoughts on the project, including the challenges, the fun aspects, and the mistakes encountered.

### 4.1 Interesting
What is fascinating about curve fitting is the variety of ways it can be applied. As long as the data and tables are correctly managed, you can adapt the method to fit different scenarios. Curve fitting is a compelling method; it appears simple yet can be quite complex to execute. The process is lengthy, and I found it particularly interesting because I am accustomed to producing graphs quickly. It is also versatile, allowing applications in diverse scenarios, such as estimating the number of people who consume eggs. This flexibility makes it an enjoyable and exploratory method.

### 4.2 Challenges
I faced numerous challenges. The first was knowing where to start, as graphing is impossible without data. Organizing the data was the most challenging part because with 7,500 accounts and 28 variables (totaling 210,000 data points), it was overwhelming initially. Applying the frequency table code also proved difficult as I couldn't figure out how to use the `tabulate()` function properly and had to find an alternative method. Time was another significant challenge; I often chose less efficient methods when quicker options were available. Additionally, learning to use LaTeX was tricky, especially in managing the order of figures, which tended to move around in the document. I had to use the `\float barrier` to prevent this.

### 4.3 Learned
I am proud of what I've learned from this project. While I enhanced my curve fitting skills, I also acquired many valuable techniques applicable beyond using MATLAB. If asked to apply curve fitting in another software, I am confident in starting immediately due to my solid understanding of the basics. Knowing the method is crucial before learning the software; understanding the theoretical foundation helps make the practical application more intuitive. This project reinforced my appreciation for MATLAB's straightforward, understandable approach.

