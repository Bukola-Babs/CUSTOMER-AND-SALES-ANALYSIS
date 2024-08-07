# CUSTOMER-AND-SALES-ANALYSIS
This project works on customer and sales analysis


### Project Overview
This report explores Big Data Processing and Analytics using  PySpark on Google Colab. It covers SparkSession initiation, dataset joins, and thorough Exploratory Data Analysis (EDA). The analysis answers key questions on sales patterns and customer analysis. It employs correlation analyses and showcases effective Linear and Logistic Regression models.

### Data Sources
The datasets employed in this analysis are FactInternetSales, DimCustomer, DimProduct and FactSalesTargets which are secondary data.


### Tools

- Pyspak - Data Joining
- Python - Data Cleaning, Exploration  and Analysis
- Microsoft Word - Creating Report

### Import Libraries
``` python
import findspark
findspark.init()
from pyspark.sql import SparkSession
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
from pyspark.sql import SparkSession
from pyspark.sql.functions import col
from pyspark.sql import SparkSession
from pyspark.sql.functions import col, sum as spark_sum
from pyspark.sql.functions import mean
from pyspark.sql.functions import col, year, current_date
from pyspark.sql.functions import year, current_date
from pyspark.ml.feature import VectorAssembler
from pyspark.ml.regression import LinearRegression
```

### Importing Data


### Data Cleaning/Preparation
Data  Inspection
Joining the Datasets for Insights and Analysis
- Joined DimProduct and FactInternetSales datasets using 'ProductKey,' creating a data frame named df_24.
- Joined DimCustomer dataset 'df3' to df_24 using 'Customer key,' creating a new dataframe df_234.
- Joined FactInternetSales and FactSalesTargets datasets on 'SalesTerritoryKey' for additional exploration.
Handling Missing Values
Data Cleaning and Formatting


### Exploratory Data Analysis
Research Questions and Insights
- Are There Observable Patterns or Disparities in Sales Based on Gender?
  
##### Checking the distribution of customer based on Gender
##### Grouping the DataFrame by 'Gender' and calculating the count of each gender
##### Calculate total sales amount based on gender
##### Display the PySpark DataFrame
```python
gender_distribution = df_234.groupBy('Gender').agg(F.count('Gender').alias('count'))
gender_sales_data = df_234.select('Gender', 'SalesAmount')
gender_sales_trends = gender_sales_data.groupBy('Gender').agg(F.sum('SalesAmount').alias('TotalSales'))
gender_distribution.show()
print("Gender Sales Trends:")
gender_sales_trends.show()
```
  ![RQ1](https://github.com/Lapadonic/CUSTOMER-AND-SALES-ANALYSIS/assets/142020905/8d51cd6c-3f8e-45cf-8647-de14f8af53c0)
  
- How Does the Distribution of Customers Based on Marital Status Impact on Sales?
  
- Does The SalesAmount Exhibit Any Seasonality or Trend Over Time?
- How does the 'SalesAmount' vary across different 'SalesTerritories'?

- Do Specific Occupation Demonstrate a Significant Impact on Sales and Are There Notable Variations in Sales Based on Educational Backgrounds?
- Does the Age of Customers Influence Their Purchasing Behavior or Exhibit any Correlation With Sales Trends?

### Data Analysis
This section presents the code used in this project




  

  
