# Blinkit-Data-Analysis

## Import a Data
step 1- Creating a database 'Blinkitdb'
step 2- Import a data into database and Table name 'BlinkIT_Data'
step 3- Table Data contain 8523 rows and 12 columns
## Cleaning A Data 
step 4-To clean the 'item_Fat_Content' column use update command:-
update BlinkIT_Data  set Item_Fat_Content= case WHEN Item_Fat_Content IN ('LF','low fat') THEN 'Low Fat' WHEN Item_Fat_Content='reg' THEN 'Regular' ELSE Item_Fat_Content end
## Calculate KPI
step 5-Calculate Total sales in Millions:-
select concat(cast(sum(Total_Sales)/1000000 as decimal(10,2)),'M') as Total_Sales_Millions from [dbo].[BlinkIT_Data]
Step 6- Calculate Average Sales
select cast(avg(total_sales) as decimal(10,2)) as Avg_Sales From [dbo].[BlinkIT_Data]
Step 7- Calculate Average Rating
select round(Avg(rating),2)as Aver_Rating from blinkit_data
step 8-Calculate [Total Sales,Average Sales,No Of Items,Average Rating] Categories by Fat Content
select `Item Fat Content`,round(SUM(Sales),2) as `Total Sales`,
round(avg(Sales),2)as `Average Sales`,count(*)as `No of Items FROM`,round(avg(rating),2)as `Average rating` FROM blinkit_Data GROUP BY `Item Fat Content` Order by `Total Sales` DESC
Step 9-Calculate [Total Sales,Average Sales,No Of Items,Average Rating] Categories by Item Type
select `Item Type`,round(SUM(Sales),2) as `Total Sales`,
round(avg(Sales),2)as `Average Sales`,count(*)as `No of Items`,round(avg(rating),2)as `Average rating` FROM blinkit_Data GROUP BY `Item Type` Order by `Total Sales`DESC 
Step 10- Calculate [Total Sales,Average Sales,No Of Items,Average Rating] Categories by Outlet Establishment Year
select `Outlet Establishment Year`,round(SUM(Sales),2) as `Total Sales`,
round(avg(Sales),2)as `Average Sales`,count(*)as `No of Items`,round(avg(rating),2)as `Average rating` FROM blinkit_Data GROUP BY `Outlet Establishment Year` Order by `Total Sales`DESC 
