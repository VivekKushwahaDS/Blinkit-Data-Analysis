# Blinkit-Data-Analysis

# Import Data and Clean It
step 1- Creating a database 'Blinkitdb'
step 2- Import a data into database
step 3- Data contain 8523 rows and 12 columns

step 4-To clean the 'item_Fat_Content' column use update command:-
update BlinkIT_Data  set Item_Fat_Content= case WHEN Item_Fat_Content IN ('LF','low fat') THEN 'Low Fat' WHEN Item_Fat_Content='reg' THEN 'Regular' ELSE Item_Fat_Content end
step 5-Calculate Total sales in Millions:-
select concat(cast(sum(Total_Sales)/1000000 as decimal(10,2)),'M') as Total_Sales_Millions from [dbo].[BlinkIT_Data]
Step 6- Calculate Average Sales
select cast(avg(total_sales) as decimal(10,2)) as Avg_Sales From [dbo].[BlinkIT_Data]
