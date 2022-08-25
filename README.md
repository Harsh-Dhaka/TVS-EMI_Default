# TVS-EMI_Default

A Financial institution in India wants to leverage Machine Learning techniques to determine the client’s loan repayment abilities and take proactive steps to reduce the magnitude of exposure to default.

# Goal: 
The goal of the problem is to predict whether a client will default on the vehicle loan payment or not, given the recent data of all the loan transactions. This can help the institution to distinguish the future applicants who might default. For each ID in the Test Dataset, you must predict the “Default” level

# Attribute Information:
After importing necessary libraries, we see the train dataset contains 132440 rows and 33 columns whereas the test dataset contains 56760 rows and 32 columns.

# Data Preprocessing and EDA:
While checking for missing values we see there were around 1% to max 16% missing values present in some of the variables,same in the test dataset.
For dealing with missing values in both train and test dataset, imputed median value in numerical variables and mode value in categorical variables.
After imputing missing values we used some pandas built-in functions like groupby,cross-tab for getting a better overview about the variables or we can say what actually variables are describing with one another.(E.g. Default[0/1] of an individual is shown according to the Default_hist variable. Count of Defaults is shown as per the Job_Type variable.)
Some of the variables are not showing any significance, for getting a better information from them some user defined functions were used for the better modeling.(E.g. Age variable has many unique values, those values were bin in 3 buckets. Experience variable also have many unique values, those values are also bin in buckets[New,Mid,Senior]).

# Statistical Analysis:
After completing the data preprocessing, we performed some statistical tests to see the significance of independent variables for the future modelling.
After performing tests like Anova,Chi-Square on independent variables we see some of the variables are showing dpendency on target variable.(E.g. Region_type,Default_hist,job_type are some of them.)

# Model:
For the modelling part, we separated numerical, Un-encoded categorical and categorical columns.
Performed dummy encoding on the required categorical features.On numerical features we used power transformer and then scaled requisite numerical features.Also used Standard Scalar for scaling the requisite features.
After doing all this we concat all the dummy encoded and scaled data as final_scaled_train and final_scaled_test datasets.
We considered Logistic Regression as our base model, but it doesn't shows any performance here.
After which we used DecisionTree classifier for getting better performance,than we hypertuned DT Classifier and got a better result.Also checked the features importances of tuned decision tree.
After using DT classifier we used feature selection techniques like SFS and then made up another model by considering the features got from DT feature importances and SFS.
Also used some boosting techniques like XGBoost, then stacking classifier,KNN for getting a better result from previous ones.
At the end we see the tuned decision tree shows best result



