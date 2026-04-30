# ElectroHub  Sales Data Analysis

### Dashboard Link :


### Data Model: Star Schema

### Data Source: Excel Workbook 

## Problem Statement:
In this project, I will take on the role of a Data Analyst at ElectroHub, focusing on delivering data-driven insights. Customers at ElectroHub purchase products from multiple categories, including electronics, footwear, clothing, home appliances, bags, accessories, kitchenware, and personal care items.

## Tasks:

1. Top/Bottom 5 products by Sales/Profit/Quantity Sold.
2. How do sales trend over time?
3. Show the relationship between sales and Profit.
4. Compare Sales/Profit/Quantity Sold by any two periods selected by the user.
5. Average discount offered in each discount category.
6. Total number of orders.
7. Show Sales/Profit/Discount/Net sales/All remaining fields for each order that could be filtered using visual filters.(Products/Date/Customer Id/Promotion Categories )
8. Show Sales by different cities.

### Steps followed

- Step 1: Loaded datasets into Power BI and applied Power Query transformations to ensure all column data types were correctly defined across the four datasets, aligning with project requirements.
- Step 2: In the Dim Promotion dataset, a conditional column was added to calculate the price reduction as a percentage.
- Step 3: In the fact table, it was observed that some columns contained null values across entire rows.
- Step 4: Attempted to resolve the issue using a Merge Query by linking the fact table with the Dim Product table, as the Price per Unit column was available there. This allowed the required column to be brought into the fact table.
