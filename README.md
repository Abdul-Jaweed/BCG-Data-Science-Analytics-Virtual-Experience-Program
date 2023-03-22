# BCG Data Science Analytics Virtual Experience Program

Boston Consulting Group, Inc. (BCG) is an American global management consulting firm founded in 1963 and headquartered in Boston, Massachusetts. It is one of the Big Three (or MBB, the world’s three largest management consulting firms by revenue) along with Bain & Company and McKinsey & Company. Since 2021, the consultancy has been led by the German executive Christoph Schweizer.

## TASK - 1 | Business Understanding & Hypothesis Framing

Understanding the business context and problem statement.

### Here is the background information on your task

PowerCo is a major gas and electricity utility that supplies to corporate, SME (Small & Medium Enterprise), and residential customers. The power-liberalization of the energy market in Europe has led to significant customer churn, especially in the SME segment. They have partnered with BCG to help diagnose the source of churning SME customers.

A fair hypothesis is that price changes affect customer churn. Therefore, it is helpful to know which customers are more (or less) likely to churn at their current price, for which a good predictive model could be useful.

Moreover, for those customers that are at risk of churning, a discount might incentivize them to stay with our client. The head of the SME division is considering a 20% discount that is considered large enough to dissuade almost anyone from churning (especially those for whom price is the primary concern).

The Associate Director (AD) held an initial team meeting to discuss various hypotheses, including churn due to price sensitivity. After discussion with your team, you have been asked to go deeper on the hypothesis that the churn is driven by the customers’ price sensitivities. 

Your AD wants an email with your thoughts on how the team should go about testing this hypothesis.

The client plans to use the predictive model on the 1st working day of every month to indicate to which customers the 20% discount should be offered.

**Mail to AD**


Hi AD,

In order to perform hypothesis testing on customer churn or not on the bases of price and services, we would also need a model churn probabilities of customers, and we would derive the affordable price on churn rates.

#### Dataset needed:

 - Historical price data
 - Customer Joined and left data in date form
 - Historical electricity consumption data
 - Historical gas consumption data
 - Customer churned or not data


Once we got all the data then we would perform eda and univariat, bivariate and multivariate analysis and after that we perform feature engineering based on the data insight and then we split data into train and test to effectively evaluate the model's performance. And standardise the data and perform all Binary classification models for model prediction and find which model accuracy is better. Based on that we picked the model and we will be able to understand the direction and magnitude of the import of prices on customer churn rates, as well as the relative importance of affordable price in compared to other factors.

Regards,
Abdul Jaweed



## TASK - 2 | Exploratory Data Analysis

Understanding the business through data

### Here is the background information on your task


The BCG project team thinks that building a churn model to understand whether price sensitivity is the largest driver of churn has potential. The client has sent over some data and the AD wants you to perform some exploratory data analysis.

The data that was sent over includes:

   - Historical customer data: Customer data such as usage, sign up date, forecasted usage etc
   - Historical pricing data: variable and fixed pricing data etc
   - Churn indicator: whether each customer has churned or not

#### Sub-Task 1 :

Perform some exploratory data analysis. Look into the data types, data statistics, specific parameters, and variable distributions. This first subtask is for you to gain a holistic understanding of the dataset. You should spend around 1 hour on this.

#### Sub-Task 2 :

Verify the hypothesis of price sensitivity being to some extent correlated with churn. It is up to you to define price sensitivity and calculate it. You should spend around 30 minutes on this.

#### Sub-Task 3 :

Prepare a half-page summary or slide of key findings and add some suggestions for data augmentation – which other sources of data should the client provide you with and which open source datasets might be useful? You should spend 10-15 minutes on this.