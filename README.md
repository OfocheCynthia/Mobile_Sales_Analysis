## Mobile_Sales_Analysis
## Overview:

+ This is a sales report for a Mobile Products Sales company 

___

## Contents

Project Overview >> Data Source >> Tools Used >> Table Outlay  Query Language  VIsualisation

---
## Project Overview

>> This project analyzes a mobile phone sales dataset to uncover key business insights. The dataset contains details such as product model, brand, price, Age, Gender, color, quantity sold, payment method and sales amount. Using data analysis techniques, I explored sales performance across different dimensions, including product category, customer preferences, and regional trends.
The main goal of this project is to identify:.
+ How Age and Gender impacts customer demand.
+ Sales patterns across colors and product categories.
+ Potential business opportunities for increasing sales.
+ The most preferred payment method.
  
In this analysis, I used pivot table to explore metrics like Total Sales by Color, Payment Method, Gender. I also used Excel for data cleaning and exploration, SQL for querying and segmentation, and Power BI for creating an interactive sales dashboard that highlights key business insights.

--- 
### Data Source
www.kaggle.com/dataset

---
## Tools Used
+ Pivot table/ Charts
+ PowerBi
+ SQL

## Table Outlay:
FIrst Four Rows

|TransactionID|	Date|	MobileModel|	Brand|	Price|	UnitsSold|	TotalRevenue|	CustomerAge|	CustomerGender|	Location|	PaymentMethod|
|-----|----|----|----|----|----|----|----|----|----|----|
|79397f68-61ed-4ea8-bcb2-f918d4e6c05b|	1/6/2024|	direction|	Green Inc|	1196.95	85|	28002.8	32|	Female|	Port Erik|	Online|	
|4f87d114-f522-4ead-93e3-f336402df6aa|	4/5/2024|	right|	Thomas-Thompson|	1010.34	64|	2378.82	55|	Female|	East Linda|	Credit Card|	
|6750b7d6-dcc5-48c5-a76a-b6fc9d540fe1|	2/13/2024|	summer|	Sanchez-Williams|	400.8	95|	31322.56	57|	Male|	East Angelicastad|	Online|

## Query Language:(SQL)
Some of the query languages to retrieve records are displayed here

```SQL
---Categorize the data into gold, silver and diamond---
SELECT Price,
CASE
WHEN Price <= 300 THEN 'Silver'
WHEN Price BETWEEN 301 AND 900 THEN 'Gold'
ELSE 'Diamond'
END AS CustomerSegment
FROM mobile_sales;

```

```SQL
---retrieve all female customers that bought goods above 900---
SELECT * FROM mobile_sales
WHERE CustomerGender = 'Female'
AND Price > 900;

```

```SQL
---Retrieve the sales by payment method, arranging from largest to smallest amount---
SELECT PaymentMethod,SUM(TotalRevenue) AS TotalSales
FROM mobile_sales
GROUP BY PaymentMethod
ORDER BY TotalSales DESC;

```

```SQL                                                                            
---Retrieve the most expensive brand---
SELECT Brand, MAX(Price) AS HighestPrice
FROM mobile_sales
GROUP BY Brand
ORDER BY HighestPrice DESC;

```

```SQL
---How many brands are there?---
SELECT COUNT(DISTINCT BRAND) AS TotalBrands
FROM mobile_sales;

```

## Visualisation
### Pivot Tables

<img width="979" height="436" alt="Mobile sales pivot table" src="https://github.com/user-attachments/assets/00c19c81-f2eb-4c47-93d8-c666f691435e" />

### Dashboard

<img width="1033" height="439" alt="Mobile sales Dashboard" src="https://github.com/user-attachments/assets/3c76b0eb-ad50-4c4d-99f0-b26c98c360e9" />

### Link to Charts
[Link to Chart]

[View my Linkedin](https://www.linkedin.com/in/ofochecynthia)




