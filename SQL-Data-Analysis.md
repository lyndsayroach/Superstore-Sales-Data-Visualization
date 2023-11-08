# Data Analysis Using SQL

Calculate the total sales as a decimal with 2 decimal places.
```
SELECT SUM(CAST(Sales AS DECIMAL(10, 2))) AS [Total Sales]
FROM [SuperstoreData].[dbo].[Superstore_dataset];
```
Calculate the total profit as a decimal with 2 decimal places.
```
SELECT SUM(CAST(Profit AS DECIMAL(10, 2))) AS [Total Profit]
FROM [SuperstoreData].[dbo].[Superstore_dataset];
```
Calculate the total sales quantity as an integer.
```
SELECT SUM(CAST(Quantity AS INT)) AS [Total Sales Quantity]
FROM [SuperstoreData].[dbo].[Superstore_dataset];
```
Calculate the total sales quantity for each region as an integer.
```
SELECT Region, SUM(CAST(Quantity AS INT)) AS [Total Sales Quantity]
FROM [SuperstoreData].[dbo].[Superstore_dataset]
GROUP BY Region;
```
Calculate the total profit for each state and order the results in descending order of profit.
```
SELECT State, SUM(CAST(Profit AS DECIMAL(10, 2))) AS [Total Profit]
FROM [SuperstoreData].[dbo].[Superstore_dataset]
GROUP BY State
ORDER BY [Total Profit] DESC;
```
Calculate the total profit by state for each year. 
```
SELECT State, YEAR([Order Date]) AS Year, SUM(CAST(Profit AS DECIMAL(10, 2))) AS [Total Profit]
FROM [SuperstoreData].[dbo].[Superstore_dataset]
GROUP BY State, YEAR([Order Date])
ORDER BY State, Year;
```
Calculate the total profit for each year without considering the state.
```
SELECT YEAR([Order Date]) AS Year, SUM(CAST(Profit AS DECIMAL(10, 2))) AS [Total Profit]
FROM [SuperstoreData].[dbo].[Superstore_dataset]
GROUP BY YEAR([Order Date])
ORDER BY Year;
```
Calculate the total profit for each category.
```
SELECT Category, SUM(CAST(Profit AS DECIMAL(10, 2))) AS [Total Profit]
FROM [SuperstoreData].[dbo].[Superstore_dataset]
GROUP BY Category;
```
Calculate the total profit for each sub-category.
```
SELECT [Sub-Category], SUM(CAST(Profit AS DECIMAL(10, 2))) AS [Total Profit]
FROM [SuperstoreData].[dbo].[Superstore_dataset]
GROUP BY [Sub-Category];
```
Calculate the total sales quantity for each type of customer.
```
SELECT Segment, SUM(CAST(Quantity AS INT)) AS [Total Sales Quantity]
FROM [SuperstoreData].[dbo].[Superstore_dataset]
GROUP BY Segment;
```
Calculate the number of sales by year and month.
```
SELECT YEAR([Order Date]) AS Year, MONTH([Order Date]) AS Month, COUNT(*) AS [Number Of Sales]
FROM [SuperstoreData].[dbo].[Superstore_dataset]
GROUP BY YEAR([Order Date]), MONTH([Order Date])
ORDER BY Year, Month;
```
Calculate the total profit by year and month.
```
SELECT YEAR([Order Date]) AS Year, MONTH([Order Date]) AS Month, SUM(CAST(Profit AS DECIMAL(10, 2))) AS [Total Profit]
FROM [SuperstoreData].[dbo].[Superstore_dataset]
GROUP BY YEAR([Order Date]), MONTH([Order Date])
ORDER BY Year, Month;
```
