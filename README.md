# BCG Data Science Analytics Virtual Experience Program

![logo](https://github.com/Abdul-Jaweed/BCG-Data-Science-Analytics-Virtual-Experience-Program/blob/main/BCG.png)

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


Once we got all the data then we would perform eda and univariant, bivariate and multivariate analysis and after that we perform feature engineering based on the data insight and then we split data into train and test to effectively evaluate the model's performance. And standardize the data and perform all Binary classification models for model prediction and find which model accuracy is better. Based on that we picked the model and we will be able to understand the direction and magnitude of the import of prices on customer churn rates, as well as the relative importance of affordable price in compared to other factors.


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



### Feature engineering

Feature engineering or feature extraction or feature discovery is the process of using domain knowledge to extract features (characteristics, properties, attributes) from raw data. The motivation is to use these extra features to improve the quality of results from a machine learning process, compared with supplying only the raw data to the machine learning process.

Feature engineering, in simple terms, is the act of converting raw observations into desired features using statistical or machine learning approaches. Few Best tools for feature engineering. Feature engineering is a machine learning technique that leverages data to create new variables that aren’t in the training set.

#### Process

**The feature engineering process is:**

- Brainstorming or testing features
- Deciding what features to create
- Creating features
- Testing the impact of the identified features on the task
- Improving your features if needed
- Repeat

#### Typical engineered features

**The following list provides some typical ways to engineer useful features:**

- Numerical transformations (like taking fractions or scaling)
- Category encoder like one-hot or target encoder (for categorical data)
- Clustering
- Group aggregated values
- Principal component analysis (for numerical data)
- Feature construction : building new "physical", knowledge-based parameters relevant to the problem. For example, in physics, construction of dimensionless numbers such as Reynolds number in fluid dynamics, Nusselt number in heat transfer, Archimedes number in sedimentation, construction of first approximations of the solution such as analytical strength of materials solutions in mechanics, etc

#### Relevance

Features vary in significance. Even relatively insignificant features may contribute to a model. Feature selection can reduce the number of features to prevent a model from becoming too specific to the training data set (overfitting).


### Modelling

We now have a dataset containing features that we have engineered and we are ready to start
training a predictive model. Remember, we only need to focus on training a Random Forest
classifier.

#### Data sampling

The first thing we want to do is split our dataset into training and test samples. The reason why
we do this, is so that we can simulate a real life situation by generating predictions for our test
sample, without showing the predictive model these data points. This gives us the ability to see
how well our model is able to generalise to new data, which is critical.
A typical % to dedicate to testing is between 20-30, for this example we will use a 75-25% split between train and test respectively.


#### Model training

Once again, we are using a Random Forest classifier in this example. A Random Forest sits
within the category of ensemble algorithms because internally the Forest refers to a collection of
Decision Trees which are tree-based learning algorithms. As the data scientist, you can control
how large the forest is (that is, how many decision trees you want to include).
The reason why an ensemble algorithm is powerful is because of the laws of averaging, weak learners
and the central limit theorem. If we take a single decision tree and give it a sample of data and
some parameters, it will learn patterns from the data. It may be overfit or it may be underfit, but
that is now our only hope, that single algorithm.
With ensemble methods, instead of banking on 1 single trained model, we can train 1000’s of
decision trees, all using different splits of the data and learning different patterns. It would be like
asking 1000 people to all learn how to code. You would end up with 1000 people with different
answers, methods and styles! The weak learner notion applies here too, it has been found that if
you train your learners not to overfit, but to learn weak patterns within the data and you have a lot
of these weak learners, together they come together to form a highly predictive pool of knowledge!
This is a real life application of many brains are better than 1.
Now instead of relying on 1 single decision tree for prediction, the random forest puts it to the
overall views of the entire collection of decision trees. Some ensemble algorithms using a voting
approach to decide which prediction is best, others using averaging.

As we increase the number of learners, the idea is that the random forest’s performance should
converge to its best possible solution.

Some additional advantages of the random forest classifier include:

- The random forest uses a rule-based approach instead of a distance calculation and so features do not need to be scaled

- It is able to handle non-linear parameters better than linear based models

On the flip side, some disadvantages of the random forest classifier include:

- The computational power needed to train a random forest on a large dataset is high, since we need to build a whole ensemble of estimators.

- Training time can be longer due to the increased complexity and size of thee ensemble

#### Evaluation

Now let’s evaluate how well this trained model is able to predict the values of the test dataset.

We are going to use 3 metrics to evaluate performance:

- Accuracy = the ratio of correctly predicted observations to the total observations

- Precision = the ability of the classifier to not label a negative sample as positive

- Recall = the ability of the classifier to find all the positive samples

The reason why we are using these three metrics is because a simple accuracy is not always a good
measure to use. To give an example, let’s say you’re predicting heart failures with patients in a
hospital and there were 100 patients out of 1000 that did have a heart failure.
If you predicted 80 out of 100 (80%) of the patients that did have a heart failure correctly, you
might think that you’ve done well! However, this also means that you predicted 20 wrong and
what may the implications of predicting these remaining 20 patients wrong? Maybe they miss out
on getting vital treatment to save their lives.
As well as this, what about the impact of predicting negative cases as positive (people not having
heart failure being predicted that they did), maybe a high number of false positives means that
resources get used up on thee wrong people and a lot of time is wasted when they could have been
helping the real heart failure sufferers.
This is just an example, but it illustrates why other performance metrics are necessary such
Precision and Recall, which are good measures to use in a classification scenario.

Looking at these results there are a few things to point out:

**Note:** If you are running this notebook yourself, you may get slightly different answers!

-  Within the test set about 10% of the rows are churners (churn = 1).

- Looking at the true negatives, we have 3282 out of 3286. This means that out of all the
negative cases (churn = 0), we predicted 3282 as negative (hence the name True negative).
This is great!

- Looking at the false negatives, this is where we have predicted a client to not churn (churn
= 0) when in fact they did churn (churn = 1). This number is quite high at 348, we want to
get the false negatives to as close to 0 as we can, so this would need to be addressed when
improving the model.

- Looking at false positives, this is where we have predicted a client to churn when they actually
didnt churn. For this value we can see there are 4 cases, which is great!

- With the true positives, we can see that in total we have 366 clients that churned in the test
dataset. However, we are only able to correctly identify 18 of those 366, which is very poor.

- Looking at the accuracy score, this is very misleading! Hence the use of precision and recall
is important. The accuracy score is high, but it does not tell us the whole story.

- Looking at the precision score, this shows us a score of 0.82 which is not bad, but could be
improved.

- However, the recall shows us that the classifier has a very poor ability to identify positive
samples. This would be the main concern for improving this model!

So overall, we’re able to very accurately identify clients that do not churn, but we are not able
to predict cases where clients do churn! What we are seeing is that a high % of clients are being
identified as not churning when they should be identified as churning. This in turn tells me that
the current set of features are not discriminative enough to clearly distinguish between churners
and non-churners.

A data scientist at this point would go back to feature engineering to try and create more predictive
features. They may also experiment with optimising the parameters within the model to improve
performance. For now, lets dive into understanding the model a little more.



### Model understanding

A simple way of understanding the results of a model is to look at feature importances. Feature
importances indicate the importance of a feature within the predictive model, there are several
ways to calculate feature importance, but with the Random Forest classifier, we’re able to extract
feature importances using the built-in method on the trained model. In the Random Forest case,
the feature importance represents the number of times each feature is used for splitting across all
trees.



`Check Feature Engineering and Model Building Notebook for more information`


## TASK - 4 | Findings & Recommendations

Presenting your results and giving recommended actions to the client

### Here is the background information on your task

The client wants a quick update on the project progress.

The AD wants you to draft an abstract (executive summary) of your findings so far.

#### Here is your task

Develop an abstract slide synthesizing all the findings from the project so far, keeping in mind that this will be for the key stakeholders meeting which the Head of the SME division, as well as other various stakeholders, will be attending.


### Executive Summary

#### Situation : 

- PowerCo has a problem with customer churn; they believe it is caused by customers’ price sensitivities. One possible solution is to provide 20% off to customers who are most likely to start leaving.


#### Machine Learning Modeling : 

- After Data cleaning, EDA and Feature engineering, I applied Random Forest Classifier. Random Forest Classifier. Random Forest Classifier model has been built to predict customers’ churn probability, achieving an accuracy of 0.90 and Precision score of 0.91 on test set.


#### Insights :

- 9.7% of the customers have churned and 90% of the customers have not churned.

- Net margin on power subscription and consumption over 12 months is a top driver for churn.

- Forecasted bill of meter rental for the next 2 months also is an influential driver.

- Time seems to be an influential factor, especially the number of months they have been active, their tenure and the number of months since they updated their contract.
