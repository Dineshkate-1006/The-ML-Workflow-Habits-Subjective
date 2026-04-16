## The dataset contains the following columns:

### |Column				|Description|

### |-------------------------------|-----------|

### |customer\_id			|Unique customer identifier|

### |order\_count\_last\_90d		|Number of orders placed in the last 90 days|

### |avg\_order\_value		|Average order value in INR|

### |days\_since\_last\_order		|Days elapsed since the customer's most recent order|

### |repeat\_purchase\_flag		|1 if the customer made a repeat purchase within 

### 30 days, 0 otherwise|

### |discount\_used\_on\_repeat\_order	|Discount applied on the repeat purchase order|



## 

## 

## Task 1

#### Identify which column in the dataset is the label, and which column, if included as a feature, would introduce data leakage. For each, write one sentence justifying your choice.

## 

## Task 1 Explain : 

* #### Label: repeat\_purchase\_flag — this is the target variable the model is being trained to predict (1 = repeat purchase, 0 = no repeat purchase). 
* #### Leaky feature: discount\_used\_on\_repeat\_order — this column contains information that only exists because a repeat purchase happened. Including it as a feature gives the model illegitimate access to the outcome it is supposed to predict, which would inflate performance and make the model useless in production where this value would not yet exist.

## 

## 

## Task 2

#### Your manager skips straight to training a gradient boosting model. Suggest two steps from the complete ML workflow that should have been completed first, and briefly explain why each step matters before jumping to a complex model.



## 

## Task 2 Explain :

#### Any two of the following are acceptable: 

1. #### Data auditing — Before modeling, the dataset should be checked for missing values, outliers, ethical concerns, and privacy issues (e.g., customer\_id should not be used as a feature). Skipping this risks building a model on flawed or biased data.
2. #### Establishing a baseline model — A simple baseline (e.g., predicting the most frequent class — whichever of 0 or 1 appears more often) should be set up first. This defines the minimum performance bar the complex model must beat to justify its use.
3. #### Proper data splitting — The dataset must be divided into training, validation, and test sets before any modeling begins. Skipping this means there is no reliable way to know whether the final model actually generalizes to new customers.



