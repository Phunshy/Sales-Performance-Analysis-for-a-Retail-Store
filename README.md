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
  SELECT * from [dbo].[Salesdatacsv]

---------------TOTAL REVENUE BY PRODUCT---------------

Select sum (Total_Sales) as totalsalesHat from Salesdatacsv where product = 'HAT'

Select sum (Total_Sales) as totalsalesShoes from Salesdatacsv where product = 'SHOES'

Select sum (Total_Sales) as totalsalesShirt from Salesdatacsv where product = 'SHIRT'

Select sum (Total_Sales) as totalsalesGloves from Salesdatacsv where product = 'GLOVES'

Select sum (Total_Sales) as totalsalesSocks from Salesdatacsv where product = 'SOCKS'

Select sum (Total_Sales) as totalsalesJacket from Salesdatacsv where product = 'JACKET'
```

### Results
---
#### Data Visualization

[Adeniyi Olufunso Comprehensive Sales Data.xlsx](https://github.com/user-attachments/files/17637991/Adeniyi.Olufunso.Comprehensive.Sales.Data.xlsx)
