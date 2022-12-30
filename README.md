# Sales Predictions

By: Israel Diaz

    The goal of the project is try to predict the sales for food items at various stores, with the purpose to help retailers to undestand the properties of products and sales that play crucial roles in increasing sales. 

## Description of the Data

The data frame register 8523 entries and 12 variable. Each variable represent the following.

### Dictionary

|Variable Name            	| Description                                                                                       |
|---------------------------|---------------------------------------------------------------------------------------------------|
|Item_Identifier            |	Unique product ID                                                                               |
|Item_Weight	            | Weight of product                                                                                 |
|Item_Fat_Content           |	Whether the product is low fat or regular                                                       |
|Item_Visibility          	|The percentage of total display area of all products in a store allocated to the particular product|
|Item_Type	                |The category to which the product belongs                                                          |
|Item_MRP	                |Maximum Retail Price (list price) of the product                                                   |
|Outlet_Identifier          |Unique store ID                                                                                    |
|Outlet_Establishment_Year	|The year in which store was established                                                            |
|Outlet_Size	            |The size of the store in terms of ground area covered                                              |
|Outlet_Location_Type	    |The type of area in which the store is located                                                     |
|Outlet_Type	            |Whether the outlet is a grocery store or some sort of supermarket                                  |
|Item_Outlet_Sales         	|Sales of the product in the particular store. This is the target variable to be predicted.         |

### Source of the Data

[Big Mart Sales Prediction](https://datahack.analyticsvidhya.com/contest/practice-problem-big-mart-sales-iii/)

To prepare the data for exploratory analysis, I performed data cleansing by basically removing duplicate values, correcting inconsistencies in data types, and imputing missing values.

## Exploratory Analysis

I have found two major insights from the analysis:

* Despite how little intuitive, the wider range of sales occured in items with low visibility.
* I found a moderate positive correlation between the MRP value and the Sales, so the more MRP, the wider range of sales. 

**Item_Visualization vs Outlet Sales**
![](https://github.com/diazid/sales-predictions/raw/main/multihistogram1.png)


**Item MRP vs Outlet Sales**
![](https://github.com/diazid/sales-predictions/raw/main/multihistogram2.png)


## Model Evaluation

To make the Sales predictions I have built 2 models, Linear Regression and Decision Tree, the models were made as follows:

* Both linear regression and decision trees obtained similar results on RMSE and R^2 Score values.
* It would be necessary to try another model, such as Random Forest, to see if the result improves.
* So far, the model that works best is the Decision Tree.

### Base Line Model

|     | Train       | Test        |
|-----|-------------|-------------|
|RMSE | 1720.306863 | 1664.975814 |
|R^2  | 0.0         | -0.004772   | 

### Linear Regression Scores

|     | Train       | Test        |
|-----|-------------|-------------|
|RMSE | 1140.324208 | 1094.756967 |
|R^2  | 0.560615    | 0.565603    | 

### Desicion Tree

|     | Train       | Test        |
|-----|-------------|-------------|
|RMSE | 1082.64619  | 1057.44313  |
|R^2  | 0.60394     | 0.59471     | 


## Recommendations

To continue with this theme, I recommend:

* To build models based on Random Forrest, Support Vector Machines and XGBoost to find better performance in predicting target values.
* To do feature engineering, because we have the `Item_Identifier` and it would be interesting to see what each part of the ID means.

## For Further Information

For any additional questions, please contact:

    Israel Diaz (Data Scientist in Training)
    diaz.israel@aol.com


