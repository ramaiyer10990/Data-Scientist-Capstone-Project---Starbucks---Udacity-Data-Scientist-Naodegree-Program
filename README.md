# Data Scientist Capstone Project - Starbucks - Udacity Data Scientist Naodegree Program

## Starbucks Capstone project
Udacity Data Scientist Nanodegree Capstone Challenge

### Table of Contents

1. [Installation](#installation)
2. [Project Motivation](#motivation)
3. [File Descriptions](#files)
4. [Results](#results)
5. [Licensing, Authors, and Acknowledgements](#licensing)

## Installation <a name="installation"></a>

There should be no necessary libraries to run the model code here beyond the Anaconda distribution of Python.  The code should run with no issues using Python versions 3.*.

## Project Motivation<a name="motivation"></a>

The dataset for this project is provided from the Data Scientist Nanodegree program through Udacity that creates the data simulating how people arrive on a decision to make purchases and by what factors these decisions are influenced by promotional offers. Our goal here is to provide a recommendation engine that would recommend Starbucks with an offer sent to a particular customer of a certain category.

We are interested to answer the following two questions:
1. Which offer should be sent to a particular customer to let the customer buy more?
2. Which demographic groups would respond best to a certain offer type?


## File Descriptions <a name="files"></a>

The notebook available here showcases work related to the above questions.  

This dataset is a simplified version of the real Starbucks app because the underlying simulator only has one product whereas Starbucks actually sells dozens of products.

The data is contained in three files:
- `portfolio.json` - containing offer ids and meta data about each offer (duration, type, etc.)
- `profile.json` - demographic data for each customer
- `transcript.json` - records for transactions, offers received, offers viewed, and offers completed

Here is the schema and explanation of each variable in the files:

`portfolio.json`
- id (string) - offer id
- offer_type (string) - the type of offer ie BOGO, discount, informational
- difficulty (int) - the minimum required to spend to complete an offer
- reward (int) - the reward is given for completing an offer
- duration (int) - time for the offer to be open, in days
- channels (list of strings)

`profile.json`
- age (int) - age of the customer
- became_member_on (int) - the date when customer created an app account
- gender (str) - gender of the customer (note some entries contain 'O' for other rather than M or F)
- id (str) - customer id
- income (float) - customer's income

`transcript.json`
- event (str) - record description (ie transaction, offer received, offer viewed, etc.)
- person (str) - customer id
- time (int) - time in hours since the start of the test. The data begins at time t=0
- value - (dict of strings) - either an offer id or transaction amount depending on the record


## Results<a name="results"></a>

The main findings of the code can be found at the post available [here]().

After performing exploratory data analysis, we found out which demographic group shows significance in the data.
2017 is the year with the highest number of memberships in all three gender categories and 2013 have had the lowest number of memberships. Males have highest memberships in the month of January and August, Females have highest memberships in December and Other gender have highest memberships in October. Males have lowest memberships in February and June, Females have lowest memberships in February and Other genders have lowest memberships in January, March, July and November. As for days, Males have had the highest number of memberships on Saturdays and lowest on Fridays, Females had the highest number of memberships on Sunday and Tuesdays, lowest on Saturdays and Wednesdays, Other gender category had the highest memberships on Thursdays and lowest on Saturdays.
Considering Males and Females, we don't see much difference with memberships as per day but with Other gender, we can observe a significant difference with membership on certain days.

Based on the data visualizations, we built a Random Forest Classifier model that predicts whether a member of a certain demographic completes a transaction using all three event types i.e. offer received, offer viewed and offer completed.
The feature importances of the applied Random Forest Classifier model depicts the significance of every feature depicted: When a member completes a 'Bogo' transaction. In this particular case, Income has the highest importance where as web has the lowest importance and mobile and e-mail do not have importance.
We achieved a model that predicts the accuracy in predicting the completion of a ‘Bogo’ deal to be 67.52 % where as for non-completion to be 62.04%. The model incorrectly predicted completed transactions to be 37.96% and for not completed transactions to be 32.48%. Furthermore, the model also predicted the accuracy in completion of a ‘Discount’ deal which is 73.84 % where as for non-completion, it is 67.23%. The model incorrectly predicted completed transactions to be 26.16% and for not completed transactions to be 32.77%
Using the Machine learning model, we build and evaluated our recommendation engine that recommends Starbucks which offers are being used by a particular customer/user.



## Licensing, Authors, Acknowledgements<a name="licensing"></a>

Must give credit to Starbucks for the dataset.
Udacity for the highly intense, innovative and curative project.
