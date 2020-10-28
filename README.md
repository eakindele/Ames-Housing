## Introduction

In this project, I will use Ames tax assessment data to build a linear regression model that will predict the value of a home in Ames, Iowa from given inputs. With this model, a person could come to understand what they might expect to pay for their ideal home in Ames.

Without a predictive model, typically, the average or median is used. There are situations where these summary statistics are reasonable estimates, but considering how much of an investment a house seems to be, using them in this situation is insufficient. 


## Cleaning and Understanding Data

I start by importing the libraries I know I’ll need for this task. Pandsas  and Numpy are brought in to read and manipulate data. Matplotlib and Seabron are used to visualize the data. And I’ll also work out of Sklearn’s linear model and model selection packages for actually working to test and fit my model. 

I made the decision to drop columns where a sizable amount of its data was missing, and ended up letting go of columns "Alley", "Fireplace Qu", "Pool QC", "Fence", and "Misc Features". I considered dropping lot frontage, but given that it was a metric that could pertain to size, I wanted to try to preserve it. In the case of its missing values, I wanted to fill it in with a reasonable estimate.

Additionally, there were a few instances in which categorical data was presented as being numeric. In those cases, I chaned them to the string format. I also spent time creating new columns based on certain features - for example, the overal quality ranged from 1 to 10. I made a new column called general quality that called houses with an overall condition of 1-3 as being lower than those with a 4-7, and all of those being lower than those with an 8-10 rating. I also created polynomial columns of features for the numerical columns with correlations whose absolute value are greater than 0.5.



## Modeling and Interpretation 

I decided to use a linear model because of its interpretability, and the simplicity of its underlying math. I also believe that when a dataset is well prepared and well understood, it can be well prepresetned as a simple, linear model. 

Ultimately, my model acheived a coefficient of determination value of 0.99, and an RMSE of around 166. When considering the scale of home prices, the RMSE value is very low, and I would call the model a success.

It is worth mentioning that not all of the features of the model are simply imortant to a user, so further work could include using more common housing metrics, and probably pulling some of the features that were engineered.