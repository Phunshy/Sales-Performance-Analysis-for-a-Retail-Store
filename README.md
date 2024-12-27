# Sales-Performance-Analysis-for-a-Retail-Store
The sales performance of a retail store was analyzed using available data to shed more light on top selling products, regional performance, and monthly sales trends.
## Sales Analysis

### Project Overview
---
This project aims to provide insights into the sales performance of a retail store over the past 20 months. By exploring various aspects of the sales data, I tried to identify trends, make recommendations, and gain a deeper understanding of the store's performance. These have enabled me to make resonable decisions and inferences.

### Data Sources
---
The primary data set used for this analysis is the "LITA Capstone Dataset.xlsx" , which contains detailed information about each sale made by the store.

### Tools used
---
- Microsoft Excel - Data Cleaning, Analysis and Visualization [Download here](https://microsoft.com)
- SQL (Structured Query Language) Server - Data Analysis and Quering [Download here](https://www.microsoft.com/en-us/sql-server/sql-server-downloads)
- PowerBI - Creating reports [Download here](https://www.microsoft./power-bi/downloads)
- GitHub - Portfolio building [Log in here](https://github.com/)


### Data Cleaning/Preparation
In the initial data cleaning phase, I carried out the underlisted tasks:
1. Data loading and Inspection
2. Removing duplicate values
3. Handling missing values and narrow columns
4. Data cleaning and formatting.

### Exploratory Data Analysis (EDA)
This involved exploring the sales data to answer questions such as:
- Determine the total sales by product, region and month
- calculate metrics such as average sales per product and total revenue by region
- create other interesting reports such as:
  - Unit sold by region;
  - Average sales per region;
  - Top selling product;
  - Units soldby product.

### Data Analysis and Quering

```SQL
  select * from [dbo].[Salesdatacsv] 

Delete from [dbo].[Salesdatacsv] where Customer_Id is Null and Region is Null


---------------TOTAL REVENUE BY PRODUCT---------------
Select sum (Total_Sales) as totalsalesHat from Salesdatacsv where product = 'HAT'

Select sum (Total_Sales) as totalsalesShoes from Salesdatacsv where product = 'SHOES'

Select sum (Total_Sales) as totalsalesShirt from Salesdatacsv where product = 'SHIRT'

Select sum (Total_Sales) as totalsalesGloves from Salesdatacsv where product = 'GLOVES'

Select sum (Total_Sales) as totalsalesSocks from Salesdatacsv where product = 'SOCKS'

Select sum (Total_Sales) as totalsalesJacket from Salesdatacsv where product = 'JACKET'

----------NUMBER OF SALES TRANSACTION IN EACH REGION---------
Select Region,
count (OrderID) as regionalsales from [dbo].[Salesdatacsv]
Group by Region
Order by regionalsales DESC


----------HIGHEST SELLING PRODUCT BY TOTAL SALES VALUE-------------
Select top 1 (Product),
sum (Total_Sales) as totalsales from [dbo].[Salesdatacsv]
Group by Product

-------------TOTAL REVENUE PER PRODUCT------------
Select Product,
Sum (Total_Sales) As Total_Sales from [dbo].[Salesdatacsv] 
Group by Product
Order by TOTAL_SALES DESC

Select * from [dbo].[Salesdatacsv]

-----------MONTHLY SALES TOTAL FOR THE CURRENT YEAR----------

Select MONTH  (OrderDate) As MONTHS,
Sum (Total_Sales) As MONTHLYSALES
from [dbo].[Salesdatacsv]
where
YEAR (OrderDate) = YEAR (GETDATE())
Group by MONTH (OrderDate)
Order by MONTHS 


--------------TOP 5 CUSTOMERS BY TOTAL PURCHASE AMOUNT-------------
Select Top 5 (Customer_Id) As TOPCUSTOMER,
Sum (Total_Sales) As Total_PurchasePrice from [dbo].[Salesdatacsv] 
Group by Customer_Id 
Order by TOPCUSTOMER DESC

----------PERCENTAGE OF TOTAL SALES CONTRIBUTED BY EACH REGION----------
Select Region,
Sum (Total_Sales) As TOTAL_SALES,
(Sum(Total_Sales)*100.0/(Select Sum (Total_Sales) from [dbo].[Salesdatacsv]))
As Percentage_TOTAL_SALES
from[dbo].[Salesdatacsv]
Group by Region


-----------PRODUCTS WITH NO SALES IN THE LAST QUARTER-----------
Select * from [dbo].[Salesdatacsv]

Select OrderID,
Product
From [dbo].[Salesdatacsv] where OrderID NOT IN (Select OrderID
From [dbo].[Salesdatacsv]
where OrderDate >=
DATEADD (Quarter, -1, GETDATE ()))

```

### Results
---

#### Data Visualization

[Adeniyi Olufunso Comprehensive Sales Data.xlsx](https://github.com/user-attachments/files/17637991/Adeniyi.Olufunso.Comprehensive.Sales.Data.xlsx)


### Data Analysis and Quering


![SQL result 1](https://github.com/user-attachments/assets/1ba9a986-caf2-46fa-b8b7-cd684feb0f5a)

![SQL result 2](https://github.com/user-attachments/assets/947a6e4f-0dc0-49aa-b7b6-0a40c97c6a4f)


![SQL result 9](https://github.com/user-attachments/assets/186bf2b6-6a3d-460a-8b4c-e2db5e08bd29)

### Creating Reports with PowerBI

![Power BI Sales Performance](https://github.com/user-attachments/assets/8fbf56e9-4eea-4129-b68c-7247cb825b4b)

## Sales Overview
- The store's total sales for 2023 and the first eight months of 2024 amount to $2,101,090. 
- The highest total sales was recorded in the month of February, 2024 in the South region, having total sales of 927, 820. The south region also had the highest units of products sold with a value of 24,298 products.
- Highest average sales per region (347.121) was recorded in the south as well.
- Sales in the regions followed the order South > East > North > West.
### Total sales by Products Breakdown:
- Shoes: Top-selling product, accounting for 29% of total sales.
- Shirt: Second-best seller, contributing 23% to total sales.
- Hat: Strong sales, making up 15% of total sales.
- Gloves: Consistent sales, representing 14% of total sales.
- Jacket: Room for growth, accounting for 10% of total sales.
- Socks: Opportunities for improvement, making up 9% of total sales.
- Highest Sales: Shoes (613,380)
- Lowest Sales: Socks (180,785)

## Recommendations
Monthly sales Recommendations:
- Investigate factors behind significant fluctuations.
- Analyze product sales and customer segments.
- Optimize marketing strategies for consistent growth.
- Monitor inventory and supply chain for potential issues.

Regional sales Recommendations:
- South: Maintain and expand market share; Focus on south & Maintain momentum.
- East: Focus on growth strategies; Grow East, Build on strong performance.
- North: Investigate opportunities to bridge the gap with East.
- West: Identify and address sales obstacles; Improve North and West by Identifying and addressing sales obstacles.
- Conduct market research to understand regional customer needs.
- Adjust resource allocation and strategies based on regional performance. Adjust inventory management and marketing strategies.

Product sales recommendation
- Optimize Shoe sales: Maintain momentum, explore upselling/cross-selling.
- Grow Shirt sales: Investigate opportunities to bridge the gap with Shoes.
- Enhance Hat sales: Build on strong performance.
- Improve Jacket and Socks sales: Identify and address sales obstacles.



