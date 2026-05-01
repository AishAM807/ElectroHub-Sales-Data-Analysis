# ElectroHub  Sales Data Analysis

### Dashboard Link :


### Data Model: Star Schema

### Data Source: Excel Workbook 

## Problem Statement:
In this project, I will take on the role of a Data Analyst at ElectroHub, focusing on delivering data-driven insights. Customers at ElectroHub purchase products from multiple categories, including electronics, footwear, clothing, home appliances, bags, accessories, kitchenware, and personal care items. The objective of this project is to analyze ElectroHub’s sales data to uncover meaningful business insights related to sales performance, customer purchasing patterns, and promotion effectiveness. The raw data presents several challenges, including missing values, inconsistent data formats, and fragmented datasets, which must be addressed to enable accurate analysis and build an interactive reporting solution in Power BI.

## Tasks:

1. Top/Bottom 5 products by Sales/Profit/Quantity Sold.
2. How do sales trend over time?
3. Show the relationship between sales and Profit.
4. Compare Sales/Profit/Quantity Sold by any two periods selected by the user.
5. Average discount offered in each discount category.
6. Total number of orders.
7. Show Sales/Profit/Discount/Net sales/All remaining fields for each order that could be filtered using visual filters. (Products/Date/Customer Id/Promotion Categories )
8. Show Sales by different cities.

### Steps followed

- Step 1: Loaded datasets into Power BI and applied Power Query transformations to ensure all column data types were correctly defined across the four datasets, aligning with project requirements.
- Step 2: In the Dim Promotion dataset, a conditional column was added to calculate the price reduction as a percentage.
- Step 3: In the fact table, it was observed that some columns contained null values across entire rows.

  
<img width="822" height="515" alt="Image" src="https://github.com/user-attachments/assets/438a128f-de72-48f6-b870-efa67dfdd696" />



- Step 4: Attempted to resolve the issue using a Merge Query by linking the fact table with the Dim Product table, as the Price per Unit column was available there. This allowed the required column to be brought into the fact table.
  

<img width="681" height="639" alt="Image" src="https://github.com/user-attachments/assets/651fe53e-fc65-456d-8486-9c1f8d166d94" />


- Step 5: To calculate the total sales, a custom column function was implemented, as illustrated below.


<img width="689" height="443" alt="Image" src="https://github.com/user-attachments/assets/6862e130-37d0-4cc5-9d17-739f0a6c9c97" />

  
- Step 6: The Discount Percentage values were sourced from the Promotion table by using a Merge Query, joining on Promotion ID as the primary key to integrate the data into the Fact table.
  
<img width="680" height="634" alt="Image" src="https://github.com/user-attachments/assets/e8e62d77-0588-47ae-bffa-cce615bf090d" />

- Step 7: To calculate the Discount value, a custom column function was applied, as illustrated below.

<img width="688" height="441" alt="Image" src="https://github.com/user-attachments/assets/3de4f166-ec53-4f94-b1ee-627bd618e611" />
  
- Step 8: Similarly, to calculate Net Sales, a custom column function was used to create a new column in the Fact table.

<img width="685" height="434" alt="Image" src="https://github.com/user-attachments/assets/9eddaf32-6db5-4095-9a13-af521eefe9b4" />

- Step 9: To add the Profit column, Profit was assumed to be 10% of Net Sales, and a custom column function was used to successfully incorporate it into the Fact table.

<img width="693" height="445" alt="Image" src="https://github.com/user-attachments/assets/78a77a1c-f0c4-472d-a3fb-b60f943a8847" />
  
- Step 10: To complete the first task, a new report view page was developed, where bar charts were implemented to visualize the top/bottom 5 products by sales, profit, and units sold.

  
- Step 11: The Filter Pane was utilized to filter and display the Top 5 and Bottom 5 products by Sales, Profit, and Units Sold.

 # Report Snapshot (Power BI DESKTOP)

<img width="889" height="500" alt="Image" src="https://github.com/user-attachments/assets/13cb15f2-7459-4b2c-95d5-7cc29a4b773f" />
