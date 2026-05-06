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


- Step 12: To complete Task 2, a line chart was created from the visualization pane to represent sales across different time periods (day, month, quarter, and year). The drill-down and drill-up functionalities were utilized to effectively analyze sales trends over time.

- Step 13: For Task 3, a scatter chart was utilized to analyze and represent the relationship between sales and profit.
  
- Step 14: To complete Task 4, a bar chart was selected to display the average discount across different promotion categories.
  
- Step 15: In Task 8, a map visual was implemented to analyze the geographical distribution of sales across different cities.
  
- Step 16: To complete Task 6, a card visual was used to display the total number of orders. An index column was created in the fact table using Power Query to calculate the total orders, assuming each order is unique.

 # Report Snapshot (Power BI DESKTOP)

<img width="1036" height="498" alt="Image" src="https://github.com/user-attachments/assets/2428371a-d4e4-4543-a1b3-a70cc6aed6e7" />

- Step 17: To fulfill the requirements of Task 4, two separate date tables, namely Date Table 1 and Date Table 2, were generated using the CALENDARAUTO() function.

- Step 18: An active relationship was developed for Date Table 1, whereas Date Table 2 was maintained with an inactive relationship.

- Step 19: To visualize Sales, Profit, and Quantity Sold over the selected period, a clustered column chart was utilized.

- Step 20: A DAX measure was developed using CALCULATE, ALL, and USERELATIONSHIP functions to activate and leverage the inactive relationship associated with Date Table 2.


		Sum of Net Sales = CALCULATE(SUM('Fact Table'[Net Sales ]), ALL('Date Table 1'[Date]), USERELATIONSHIP('Date Table 2'[Date], 'Fact Table'[Date (dd/mm/yyyy)]))

- Step 21: Similarly, to analyze total profit by Date Filter 1, I used a column chart and created a DAX measure with CALCULATE, ALL, and USERELATIONSHIP functions to enable the inactive relationship with Date Filter 2.


		Sum Of Profit = CALCULATE(SUM('Fact Table'[Profit]), ALL('Date Table 1'[Date]), USERELATIONSHIP('Date Table 2'[Date],'Fact Table'[Date (dd/mm/yyyy)]))


- Step 22: Similar steps were followed to calculate total units sold for Date Table 1, along with creating a measure to utilize Date Filter 2.

		Total Unit sold = CALCULATE(SUM('Fact Table'[Units Sold]), ALL('Date Table 1'[Date]), USERELATIONSHIP('Date Table 2'[Date], 'Fact Table'[Date (dd/mm/yyyy)]))

 # Report Snapshot (Power BI DESKTOP)

<img width="1067" height="494" alt="Image" src="https://github.com/user-attachments/assets/4b108aae-b02e-413a-9ff3-eab23b7bdae9" />

<img width="913" height="505" alt="Image" src="https://github.com/user-attachments/assets/86d3f12d-e9a8-4ed2-a8ce-2d15088ad30b" />


- Step 23: To meet the requirements of Task 4 using the second approach, two date filters were implemented to allow selection of different date ranges, without increasing the overall model size.

- Step 24: Bar charts were utilized to present total sales, profit, and quantity sold. The Edit Interactions functionality was used to remove cross-interactions between visuals for different date selections, enabling independent date filtering.

<img width="980" height="665" alt="Image" src="https://github.com/user-attachments/assets/11bc7efb-18b3-485a-9b3f-344b45b97e36" />

<img width="976" height="672" alt="Image" src="https://github.com/user-attachments/assets/501c6e7b-4e78-4828-bc88-255266997834" />

Step 25: To complete Requirement 7, a table visual was used to display detailed data for each order, along with visual-level filters. Additionally, slicers were implemented to enable filtering by Date, Customer Name, Product Name, and Promotion Name.

Step 26: In the Model view, since the cross-filter direction was set to single, measures were implemented to simulate dynamic interaction between slicers and ensure consistent filtering across all visuals.
    		
		Dim Sum = SUM('Fact Table'[Net Sales ])


Step 27: The above measure was applied in the filter pane of all four slicers, ensuring that they interact dynamically and respond consistently to each other’s selections.

<img width="963" height="461" alt="Image" src="https://github.com/user-attachments/assets/432ecfbf-74d4-4df3-9baa-d793f086629c" />

 # Report Snapshot (Power BI DESKTOP)
 
<img width="918" height="500" alt="Image" src="https://github.com/user-attachments/assets/6d41cf2d-c2d5-4119-b304-631efd90377b" />


# Insights:

🔹 1. Sales, Profit & Quantity Comparison (Date Filter Analysis)
- The comparison between the two selected date ranges shows higher performance in the second period:
- Total Sales increased from 103M → 113M
- Total Profit increased from 10.3M → 11.3M
- Units Sold increased from 6.1K → 6.6K
- This indicates overall business growth and improved demand in the later period.

🔹 2. Top & Bottom Product Performance
✅ Top Performing Products
Apple iPhone 14 is the best-performing product across:
- Sales (~21.4M)
- Profit (~2.1M)
- Quantity sold (281 units)
- Other strong performers:
- Apple MacBook Air
- Sony Bravia 55” TV
- Samsung Galaxy S21
Insight:
👉 Electronics (especially premium Apple products) dominate revenue and profitability.

🔹 3. Quantity vs Profit Observation
Some products (e.g., Nivea Body Lotion) show high quantity but low profit
Indicates:
👉 High sales volume does not always translate into high profitability
👉 Margins are lower for certain categories

🔹 4. Sales Distribution by City
Major sales are concentrated in metro cities:
- Mumbai
- Delhi
- Bangalore
- Hyderabad
Insight:
👉 Urban regions drive the majority of revenue
👉 Opportunity to expand in tier-2 and tier-3 cities

🔹 5. Promotion Effectiveness
Weekend Flash Sale generates the highest discount impact (~23K)
Followed by:
- Clearance Sale (~18K)
- Summer Sale (~7K)
- Least effective:
- Festive Diwali (~1K)
Insight:
👉 Short-term aggressive promotions perform better than seasonal campaigns


🔹 6. Orders Overview
Total number of orders: 3510
Insight:
👉 Strong order volume indicates consistent customer demand

🔹 7. Profit vs Net Sales Relationship
Strong positive linear relationship between profit and net sales
Insight:
👉 Profit grows proportionally with sales
👉 Indicates stable pricing and margin strategy

🔹 8. Sales Trend Over Time
- Sales trend shows:
- Stable performance from 2020 to 2023
- Peak around 2023 (~32M)
- Sharp drop in 2024
Insight:
👉 Possible reasons for decline:
- Incomplete data for 2024
- Seasonal slowdown
- Business or market changes

🔹 9. Data & Filtering Capability
Interactive slicers allow filtering by:
- Date
- Customer
- Product
- Promotion
Insight:
👉 Enables dynamic analysis and better decision-making
