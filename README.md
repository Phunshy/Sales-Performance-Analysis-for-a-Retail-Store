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


### Data Analysis and Quering


![SQL result 1](https://github.com/user-attachments/assets/1ba9a986-caf2-46fa-b8b7-cd684feb0f5a)

![SQL result 2](https://github.com/user-attachments/assets/947a6e4f-0dc0-49aa-b7b6-0a40c97c6a4f)


![SQL result 9](https://github.com/user-attachments/assets/186bf2b6-6a3d-460a-8b4c-e2db5e08bd29)


### Creating Reports with PowerBI


## Inferences
- The highest total sales was observed in the South region, having total sales of 927, 820.
- Of all the products sold, shoes recorded the highest value of 613,380. 
- The highest total sales was recorded in the month of February, 2024.
- The south region also had the highest units of products sold with a value of 24,298 products.
- Highest average sales per region (347.121) was recorded in the south as well.
- Hats were mostly sold of all the products exhibited, with a total sales of 15,929; this is similar to the highest units sold per product.
