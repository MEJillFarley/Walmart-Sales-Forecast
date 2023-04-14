![My Image](Data%20Images/Walmart_logo%202.png?raw=true)

# Walmart-Sales-Forecast
Walmart department sales by week from 2010-2012

Data Source: https://www.kaggle.com/datasets/ujjwalchowdhury/walmartcleaned/discussion?resource=download&group=bookmarked
 | Column Name   | Type    | Description              |
  | ------------- | ------- | ------------------------ |
  | Store | Int     | Store ID number 
  | Date      | Date  | Year-Month-Day            
  | IsHoliday      | Boolean  | Indicates if instance was a holiday week
  | Dept     | Int | Department ID number
  | Weekly_Sales | Int  | Sum of sales over given week in dollars
  | Temperature        | Int  | Temperature in degree Celsius
  | Fuel_Price       | Int  | Cost of fuel in the region in dollars
  | MarkDown(1-5)      | Int  | Markdown event precede the four prominent holidays
  | CPI         | Int  | Prevailing consumer price index
  | Unemployment      | Int     | Prevailing unemployment rate
  | Type | Int  | Store labeled 1-3 based on size of store
  | Size | Int | Size of the store in Sq Ft
  
-Original data set contains 17 columns and 400,000+ rows 

-Our original data set was uploaded as a csv to an .ipynb file for preprocessing.

-Used 'dt.isocalendar' function to parse the number of week in the year for each instance and created a new column labeled 'week_of_year'.

-Created new columns for our 4 main spending holidays: Superbowl, Labor Day, Thanksgiving, and Christmas. We used the '.loc' function to filter the data based on 'week_of_year' to assign each instance a 0 or 1 value for all 4 holidays. Our data set reflects the holiday and its corresponding week instead of a generic holiday value. 

-Used the 'dt.year' function to extract the year from the 'Date' values for usability purposes. 

## Polynomial Regression

-For our model based on Store size and weekly sales, we looked at all 45 stores and grouped by the size of the store.

-We began by creating a scatter plot comparing Size of the store to Weekly sales.

-Based on the initial scatter plot, our data did not appear to be a good fit for a linear regression model, so we built a polynomial regression model.

-We then used the SKlearn 'PolynomialFeatures' function to build the model and find our predicted y values. We found the best model had 3 degrees.

-Our polynomial regression had an RMSE error of 49,269,168(USD) and an r^2 value of 0.65. This information tells us that our average error between our models predicted sales and acutal sales is roughly $50 million.  

<p align="center">
  <img width=400px height=240px src="https://github.com/MEJillFarley/Walmart-Sales-Forecast/blob/4c48dbc3119464636761869eee79eae556a34a7d/Data%20Images/Screenshot%202023-04-13%20at%207.29.20%20PM.png">
</p>

-We concluded that a polynomial regression model was not sufficient for our goal to predict Walmart sales. We decided to build a random forest model to see if we could more accurately predict sales. 

------------------------
# Machine Learning

## RandomForest Regression Model

-Our team chose to build a RandomForest Regression model do to it's ability to produce good predictions with large data sets.

-Built the model to predict Weekly sales by Date (in weeks).

-We manually split our training and testing data

-Used Stand Scaler module to scale our data, and proceeded to build a RandomForest Regression with our training data.
