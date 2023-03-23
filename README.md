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

In order to test the hypothesis of whether churn is driven by the customers’ price sensitivity, we 
would need to model churn probabilities of customers, and derive the effect of prices on churn 
rates. We would need the following data to be able to build the models. 

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

Perform some exploratory data analysis. Look into the data types, data statistics, specific parameters, and variable distributions. This first subtask is for you to gain a holistic understanding of the dataset.

**Client Dataset**
#### client_data.csv


 - id = client company identifier
 - activity_new = category of the company’s activity
- channel_sales = code of the sales channel
- cons_12m = electricity consumption of the past 12 months
- cons_gas_12m = gas consumption of the past 12 months
- cons_last_month = electricity consumption of the last month
- date_activ = date of activation of the contract
- date_end = registered date of the end of the contract
- date_modif_prod = date of the last modification of the product
- date_renewal = date of the next contract renewal
- forecast_cons_12m = forecasted electricity consumption for next 12 months
- forecast_cons_year = forecasted electricity consumption for the next calendar year
- forecast_discount_energy = forecasted value of current discount
- forecast_meter_rent_12m = forecasted bill of meter rental for the next 2 months
- forecast_price_energy_off_peak = forecasted energy price for 1st period (off peak)
- forecast_price_energy_peak = forecasted energy price for 2nd period (peak)
- forecast_price_pow_off_peak = forecasted power price for 1st period (off peak)
- has_gas = indicated if client is also a gas client
- imp_cons = current paid consumption
- margin_gross_pow_ele = gross margin on power subscription
- margin_net_pow_ele = net margin on power subscription
- nb_prod_act = number of active products and services
- net_margin = total net margin
- num_years_antig = antiquity of the client (in number of years)
- origin_up = code of the electricity campaign the customer first subscribed to
- pow_max = subscribed power
- churn = has the client churned over the next 3 months


**Price Dataset**
#### price_data.csv


- id = client company identifier
- price_date = reference date
- price_off_peak_var = price of energy for the 1st period (off peak)
- price_peak_var = price of energy for the 2nd period (peak)
- price_mid_peak_var = price of energy for the 3rd period (mid peak)
- price_off_peak_fix = price of power for the 1st period (off peak)
- price_peak_fix = price of power for the 2nd period (peak)
- price_mid_peak_fix = price of power for the 3rd period (mid peak)

Note: some fields are hashed text strings. This preserves the privacy of the original data but the commercial meaning is retained and so they may have predictive power



#### Sub-Task 2 :

Verify the hypothesis of price sensitivity being to some extent correlated with churn. It is up to you to define price sensitivity and calculate it.

#### Sub-Task 3 :

Prepare a half-page summary or slide of key findings and add some suggestions for data augmentation – which other sources of data should the client provide you with and which open source datasets might be useful?

`Check EDA Notebook for more information`

### EDA Summary 

#### Findings

- Approximately 10% of customers have churned
- Consumption data is highly skewed and must be treated before modelling
- There are outliers present in the data and these must be treated before modelling
- Price sensitivity has a low correlation with churn
- Feature engineering will be vital, especially if we are to increase the predictive power of price sensitivity

#### Suggestions

- Competitor price data - perhaps a client is more likely to churn if a competitor has a good offer available ?
- Average Utilities prices across the country - if PowerCo’s prices are way above or below the country average, will a client be likely to churn ?
- Client feedback - a track record of any complaints, calls or feedback provided by the client to PowerCo might reveal if a client is likely to churn.



## TASK - 3 | Feature Engineering & Modelling

Uncovering signals within the data, predicting churn probability and evaluating model performance

### Here is the background information on your task

The team now has a good understanding of the data and feels confident to use the data to further understand the business problem. The team now needs to brainstorm and build out features to uncover signals in the data that could inform the churn model.

Feature engineering is one of the keys to unlocking predictive insight through mathematical modeling. Based on the data that is available and was cleaned, identify what you think could be drivers of churn for our client and build those features to later use in your model.

First focus on building on top of the feature that your colleague has already investigated: “the difference between off-peak prices in December and January the preceding year”. After this, if you have time, feel free to get creative with making any other features that you feel are worthwhile.

Once you have a set of features, you must train a Random Forest classifier to predict customer churn and evaluate the performance of the model with suitable evaluation metrics. Be rigorous with your approach and give full justification for any decisions made by yourself as the intern data scientist. 

Recall that the hypotheses under consideration is that churn is driven by the customers’ price sensitivities and that it would be possible to predict customers likely to churn using a predictive model.

If you’re eager to go the extra mile for the client, when you have a trained predictive model, remember to investigate the client’s proposed discounting strategy, with the head of the SME division suggesting that offering customers at high propensity to churn a 20% discount might be effective.

Build your models and test them while keeping in mind you would need data to prove/disprove the hypotheses, as well as to test the effect of a 20% discount on customers at high propensity to churn.

#### Sub-Task 1 :

Your colleague has done some work on engineering the features within the cleaned dataset and has calculated a feature which seems to have predictive power. 

This feature is “the difference between off-peak prices in December and January the preceding year”. 

Run the cells in the notebook provided (named feature_engineering.ipynb) to re-create this feature. then try to think of ways to improve the feature’s predictive power and elaborate why you made those choices. 


#### Sub-Task 2 :

Now that you have a dataset of cleaned and engineered features, it is time to build a predictive model to see how well these features are able to predict a customer churning. It is your task to train a Random Forest classifier and to evaluate the results in an appropriate manner. We would also like you to document the advantages and disadvantages of using a Random Forest for this use case. It is up to you how to fulfill this task, but you may want to use the below points to guide your work:

- Ensure you’re able to explain the performance of your model, where did the model underperform ?
- Why did you choose the evaluation metrics that you used? Please elaborate on your choices.
- Document the advantages and disadvantages of using the Random Forest for this use case.
- Do you think that the model performance is satisfactory? Give justification for your answer.
- (Bonus) - Relate the model performance to the client's financial performance with the introduction of the discount proposition. How much money could a client save with the use of the model? What assumptions did you make to come to this conclusion ?