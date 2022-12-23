# Sales Predictions

By: Israel Diaz

The goal of the project is try to predict the sales for food items at various stores, with the purpose to help retailers to undestand the properties of products and sales that play crucial roles in increasing sales. 

## Description of the Data

The data frame register 8523 entries and 12 variable. Each variable represent the following.

### Dictionary

|Variable Name            	| Description |
|---------------------------|-------------|
|Item_Identifier            |	Unique product ID|
|Item_Weight	              | Weight of product|
|Item_Fat_Content           |	Whether the product is low fat or regular|
|Item_Visibility          	|The percentage of total display area of all products in a store allocated to the particular product|
|Item_Type	                |The category to which the product belongs|
|Item_MRP	                  |Maximum Retail Price (list price) of the product|
|Outlet_Identifier          |Unique store ID|
|Outlet_Establishment_Year	|The year in which store was established|
|Outlet_Size	              |The size of the store in terms of ground area covered|
|Outlet_Location_Type	      |The type of area in which the store is located|
|Outlet_Type	              |Whether the outlet is a grocery store or some sort of supermarket|
|Item_Outlet_Sales         	|Sales of the product in the particular store. This is the target variable to be predicted. |

### Source of the Data

[Big Mart Sales Prediction](https://datahack.analyticsvidhya.com/contest/practice-problem-big-mart-sales-iii/)

## Cleaning Data

To prepare the data for exploratory analysis, I performed data cleansing by basically removing duplicate values, correcting inconsistencies in data types, and imputing missing values.

## Exploratory Analysis

I get the following outcomes from the EAD:

#### Item Fat Content Histomgram by Year

![](https://raw.githubusercontent.com/diazid/sales-predictions/main/histogram1.png)

**Insights**
* The low fat items almost doubled the regular items in quantity every year.

#### Item Type Histogram by Year

![](https://raw.githubusercontent.com/diazid/sales-predictions/main/histogram2.png)

**Insight**

* Seafood was the item with less quantity every year. 
* Fruits and Vegetables was the item with more quantity almost every year except 2007, followed by Snack Foods that was the first one in 2007..

#### Outlet Establishment by Year

![](https://raw.githubusercontent.com/diazid/sales-predictions/main/histogram3.png)

**Insights**

* Not every year were established Outlets.
* 1985 was the year of the greater amounts of outlets. 

#### Outlet Size Histograms by Year

![](https://raw.githubusercontent.com/diazid/sales-predictions/main/histogram4.png)

**Insights**

* 1985 were established small and medium sized outlets. And medium sized outlets doubled the small ones.
* 1987 was the only year in which was established high sized outlets. 
* 1998, 2002 and 2007 we don't know the size of the outlet.
* The other years were medium sized oulets. 

#### Fat Content Vs Outlet Sales Boxplots

![](https://github.com/diazid/sales-predictions/raw/main/boxplot1.png)

**Insights**

* In average, the outlets sold near 1800 both in Low Fat and Regulat Items. 
* 75% of the sales in Low Fat items are bellow the 3050, versus Regular Items are bellow 3198.
* We see a long number of dots above both boxes but in this case ther are not to be considered outliers because they are all part of the observations. 
* The item that sold the most in Low Fat made 13086 vs the one in Regular made 12117

#### Outlet Size vs Outlet Sales Box Plot

![](https://github.com/diazid/sales-predictions/raw/main/boxplot2.png)

**Insights**

* Small sized Outlet made sales with an median of 1544. The 75% of the sales located bellow of 3166, and made the maximum of 10256. 
* Medium sized Outlet made the more amount of sales with an median of 2251. The 75% of the sales located bellow of 2824, and made the maximum of 9779. This is correct because Medium sized outlets sales is the greater part in the dataset. 
* High sized Outlet made sales with an median of 2050. The 75% of the sales located bellow of 3166, and made the maximum of 10256. 
* Unknown sized Outlet made sales with an median of 1443. The 75% of the sales located bellow of 2681, and made the maximum of 9664. 

#### Proportion of Sales per Item Type, Outlet Location, and Year

![](https://github.com/diazid/sales-predictions/raw/main/paralelset.png)

**Insights**

This graph is very insightfull because is possible to compare 2 or more  variables. 

In this case I am studying `Item_Type`, `Outlet_Location_Type`, and `Outlet_Establishment_Year`, and the width of every stream correspond to the sales of that particular portion of the stream, so it is possible to compare the total sales per item, location, and year. 

* By hovering over the graph is easy to see that the item most sold was `Fruits and Vegetables` of every year.
* Tier_1 location sold the most in years 1997 and 1999.
* Tier 2 location sold the most in years 2002, 2004, and 2007
* Tier 3 location sold the most in years 1985, 1987, 1998, and 2009
* The proportions of Items in every Tier location seem to be the same.

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

|  | Train | Test  |
RMSE | 1720.306863 | 1664.975814 |
R^2 | 0.0  | -0.004772 | 

### Lirear Regression Scores



* Both linear regression and decision trees obtained similar results with regard to RMSE and R^2 Score values.
* It would be necessary to try another model, such as Random Forest or Neural Networks, to see if the model fits better.


