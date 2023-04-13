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

## Polynomial Regression Preprocessing

-For our regression model based on Weekly sales and week of year, we filtered our cleaned data to pull from 2011 only, as it was our only complete year out of 2010, 2011, and 2012. We further filtered the data to pull instances just from one store for modeling purposes. 

-For our model based on Store size and weekly sales, we 
