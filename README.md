# Sales-Performance-Analysis-for-a-Retail-Store
The sales performance of a retail store was analyzed using available data to shed more light on top selling products, regional performance, and monthly sales trends.
## Sales Analysis

### Project Overview
This project aims to provide insights into the sales performance of a retail store over the past 20 months. By exploring various aspects of the sales data, I tried to identify trends, make recommendations, and gain a deeper understanding of the store's performance.

### Data Sources
The primary data set used for this analysis is the "LITA Capstone Dataset.xlsx" , which contains detailed information about each sale made by the store.

### Tools
- Microsoft Excel - Data Cleaning and Analysis [Download here](https://microsoft.com)
- SQL Server - Data Analysis [Download here](https://www.microsoft.com/en-us/sql-server/sql-server-downloads)
- PowerBI - Creating reports [Download here](https://www.microsoft./power-bi/downloads)


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

### Data Analysis
SQL

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


