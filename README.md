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

## Outline

To prepare the data for exploratory analysis, I performed data cleansing by basically removing duplicate values, correcting inconsistencies in data types, and imputing missing values.

## Exploratory Analysis

I get the following outcomes from the EAD:

* The low fat items almost doubled the regular items in quantity every year.
* Seafood was the item with less quantity every year. 
* Fruits and Vegetables was the item with more quantity almost every year except 2007, followed by Snack Foods that was the first one in 2007.
* In average, the outlets sold near 1800 both in Low Fat and Regulat Items. 

The supporting graphs are the following

*Item Fat Content Histomgram by Year*

![](https://raw.githubusercontent.com/diazid/sales-predictions/main/histogram1.png)

*Item Type Histogram by Year*

![](https://raw.githubusercontent.com/diazid/sales-predictions/main/histogram2.png)

*Outlet Establishment by Year*

![](https://raw.githubusercontent.com/diazid/sales-predictions/main/histogram3.png)

For more technical visualizations you may open the [Jupyter Notebook here](https://github.com/diazid/sales-predictions/blob/main/sales_prediction.ipynb)


#### Proportion of Sales per Item Type, Outlet Location, and Year

This graph is very insightfull because we can see the right proportion of sales in three (or more) variables, in this case `Item Type`, `Outlet Location` and `Year`, and the width of every stream correspond to the sales of that particular portion of the stream, so it is possible to compare the total sales per item, location, and year. 

![](https://github.com/diazid/sales-predictions/raw/main/paralelset.png)

We can extract the folling outcome.

* By hovering over the graph is easy to see that the item most sold was `Fruits and Vegetables` of every year.
* Tier_1 location sold the most in years 1997 and 1999.
* Tier 2 location sold the most in years 2002, 2004, and 2007
* Tier 3 location sold the most in years 1985, 1987, 1998, and 2009
* The proportions of Items in every Tier location seem to be the same.

The visualization is interactive, if you can get more insights you may open the [Jupyter Notebook here](https://github.com/diazid/sales-predictions/blob/main/sales_prediction.ipynb)


#### Item Visibility vs Outlet Sales

![](https://github.com/diazid/sales-predictions/raw/main/multihistogram1.png)

**Insights**

* Every year (except 1985 and 1998) it is seen that for a range of visibility between 0 - 0.1 the highest amount of sales between 0 to 5000 was produced.
* In 1985, the range was much higher than in subsequent years, with sales between 0 - 75,000 for a visibility range of between 0 - 0.2.
* In 1998, sales were quite low for any visibility range.

## ML Pipelines

To carry out the prediction, in this first approach I'll use Linear Regressions and Decision Trees in two pipelines, and using the Scikit Learn Library, every pipeline has a preprocessing that is basically a columns transformer, with the purpose of make all the changes in the columns in order to prepare the data.

The Lineal Regression pipeline is as follow:

![](https://github.com/diazid/sales-predictions/raw/main/lreg_pipeline.png)

The Decision Tree pipeline is as follow:

![](https://github.com/diazid/sales-predictions/raw/main/dtree_pipeline.png)

## Results

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

* Both linear regression and decision trees obtained similar results with regard to RMSE and R^2 Score values.
* It would be necessary to try another model, such as Random Forest to see if the resul improves. 
* So fat, the model that perform better is the Decision Tree.

## For Further Information

For any additional questions, please contact:

    Israel Diaz (Data Scientist in Training)
    diaz.israel@aol.com


