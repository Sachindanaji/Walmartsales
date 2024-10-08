
# Walmart Sales Data Analysis
This repository contains SQL scripts for analyzing Walmart sales data. The dataset includes various fields related to sales transactions.

## Dataset Fields
- Invoice ID: Unique identifier for each transaction
- Branch: Branch of the store where the sale occurred
- City: City of the branch
- Customer type: Type of customer (e.g., Member, Non-member)
- Gender: Gender of the customer
- Product line: Category of the product sold
- Unit price: Price per unit of the product
- Quantity: Number of units sold
- Tax 5%: Tax applied to the sale
- Total: Total amount of the transaction
- Date: Date of the transaction
- Time: Time of the transaction
- Payment: Payment method (e.g., Cash, Credit card)
- COGS: Cost of Goods Sold
- Gross margin percentage: Percentage of gross margin
- Gross income: Gross income from the sale
- Rating: Customer rating of the product

## Prerequisites
- MySQL server installed
- Access to the Walmart sales dataset
- Basic knowledge of SQL

## Getting Started
1.Clone the repository:

git clone https://github.com/root/walmart-sales-data-analysis.git
cd walmart-sales-data-analysis

2.Set up your database: Create a new database and import the dataset using the following command:

CREATE DATABASE walmart_sales;
USE walmart_sales;
-- Import your dataset here

## Example Queries

Here are some example SQL queries you can run against the dataset:

1.Total Sales by City

SELECT City, SUM(Total) AS Total_Sales
FROM sales_data
GROUP BY City
ORDER BY Total_Sales DESC;

2.Average Rating by Product Line

SELECT `Product line`, AVG(Rating) AS Average_Rating
FROM sales_data
GROUP BY `Product line`
ORDER BY Average_Rating DESC;

3.Sales Summary by Gender

SELECT Gender, SUM(Total) AS Total_Sales, COUNT(Invoice_ID) AS Number_of_Transactions
FROM sales_data
GROUP BY Gender;

4.Top 5 Products by Gross Income

SELECT `Product line`, SUM(`Gross income`) AS Total_Gross_Income
FROM sales_data
GROUP BY `Product line`
ORDER BY Total_Gross_Income DESC
LIMIT 5;

5.Monthly Sales Trend

SELECT DATE_FORMAT(Date, '%Y-%m') AS Month, SUM(Total) AS Monthly_Sales
FROM sales_data
GROUP BY Month
ORDER BY Month;

## License
This project is licensed under the MIT License - see the LICENSE file for details.
 
## Acknowledgments
- Data source: [Walmart Sales Data]
- Inspiration: SQL query tutorials and database management resources

