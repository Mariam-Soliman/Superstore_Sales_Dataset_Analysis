## Project Overview: 
This project aims to analyze data for a super store in USA to gain insights into sales performance, product performance and regional sales trends. By leveraging data analysis techniques, we seek to uncover trends, patterns, and insights that can drive business decisions and improve sales strategies.

## Project Objective:
The primary objective of this project is to perform a comprehensive analysis of the store's sales performance to support data-driven decision-making. Specifically, we aim to:
1.	Assess Sales Performance: Identify top-selling products, high-revenue states, and seasonal sales trends.
2.	Identify Market Trends: Understand consumer purchasing behavior across different product categories and sub-categories.
3.	Regional Sales Analysis: Compare sales performance across states to determine regional demand variations.

## Scope of Work:
1. Data Preprocessing & Modeling:
-	Load and clean the provided dataset, ensuring data integrity and consistency.
-	Represented data in a star schema data model to organize data for reporting and analysis purposes.
2. Analysis Questions:
-	Visualize sales trends over time using line charts and bar charts.
-	Identify relations between product categories, revenue, and geographic locations.
3. Key Performance Metrics & Business Insights:
-	Calculate Total Revenue, Units Sold, and Average Selling Price per Product.
-	Measure monthly sales trends, and seasonal variations.
-	Identify top-performing products, manufacturers, and states.
4. Reporting & Visualization:
-	Create interactive Power BI dashboards for sales tracking.
-	Develop summary reports highlighting key insights and recommendations.
-	Present findings in a structured manner to stakeholders.

## Dataset Overview
-	Total Rows: 9,800
-	Total Columns: 15
-	Dataset Type: Sales transaction data for a superstore.
-	Column Descriptions:
1.	Order ID (String) – A unique identifier for each order.
2.	Order Date (String) – The date when the order was placed.
3.	Ship Date (String) – The date when the order was shipped.
4.	Ship Mode (String) – The shipping method used (e.g., Standard Class, Second Class).
5.	Customer ID (String) – A unique identifier for each customer.
6.	Customer Name (String) – The full name of the customer.
7.	Segment (String) – The type of customer (Consumer, Corporate, Home Office).
8.	City (String) – The city where the order was placed.
9.	State (String) – The state where the order was placed.
10.	Region (String) – The region of the country (West, East, Central, South).
11.	Product ID (String) – A unique identifier for each product.
12.	Category (String) – The broad category of the product (Furniture, Office Supplies, Technology).
13.	Sub-Category (String) – A more specific classification of the product (e.g., Chairs, Labels, Storage).
14.	Product Name (String) – The name of the product.
15.	Sales (Float) – The total revenue generated from the sale.

## Steps
1-Data Preprocessing (Clean and transform the data) & Modeling:
<br>
<br>

1.1 Load Data into Power Query
<br>
<br>

1.2	Data Cleaning Steps
<br>
<br>
 Convert Data Types (Ensure that each column has the correct data type):
 <br>
•	Order Date & Ship Date → Convert to Date format. dates are in mixed formats (e.g., day/month/year vs. month/day/year),  we use "Using Locale" to specify the correct format.
<br>
•	Sales → Convert to Decimal Number.
<br>
•	Other categorical columns (e.g., Customer ID, Product ID, Ship Mode) should be Text.
<br>
<br>

Remove Duplicates and Errors
<br>
•	Select all columns 
<br>
•	Click Remove Duplicates under the Home tab.
<br>
•	Also remove errors
<br>
<br>
1.3 Data Transformation
<br>
<br>
Add Custom Column "Shipping Duration":
-	Click Add Column > Custom Column.
- Use the formula:
Shipping Duration (Days)=Duration.Days([Ship Date] - [Order Date])
<br>
<br>
1.4	Data Modeling
  
- Partitioned superstore sales table into orders, product, customer, address (using power query) and table date  (dax)
- Removed duplicate values from tables
- Populated a new Product ID (
<br>
Problem: several products had the same ID
<br>
Solution :
<br>
1-remove old Product ID column from tables Product,orders
<br>
2- populated a new unique ID for each product name in table Product add index
<br>
3- merged Orders and Products using merge queries on matching Product Name, after that select to keep Product ID only
<br>
4-Remove Product Name from Orders
)






