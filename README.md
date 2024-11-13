# Customer-segmentation-sql
## Overview
This project demonstrates customer segmentation using SQL for a retail dataset. By analyzing customer behaviors, income, spending patterns, and demographic attributes, uncovered actionable insights to support targeted marketing strategies.

## Objectives
- Segment customers based on income, spending frequency, and recency.
- Identify high-value customer segments for targeted marketing.
- Calculate metrics like lifetime value (LTV) to prioritize customer outreach.

## Dataset
The dataset consists of the following attributes:
- **CustomerID**: Unique identifier for each customer.
- **Name**: Customer's name.
- **Age**: Customer's age.
- **Gender**: Customer's gender.
- **Income**: Annual income.
- **Recency**: Days since last purchase.
- **Frequency**: Number of purchases.
- **Monetary**: Total spending.
- **Segment**: Segmentation label based on customer value.

## SQL Analysis & Queries
Below are the SQL queries used in this analysis. Each query is followed by a brief explanation and a screenshot of the result.

### 1. View All Customer Data
This query retrieves all data for initial inspection.

```sql
SELECT * FROM Customers;

### 2 Select Specific Columns

SELECT CustomerID, Name, Income, Segmentation
FROM Customers;

### 3. Filter by Segmentation

SELECT * FROM Customers
WHERE Segmentation = 'High-Value';

###4. Group by Segmentation

SELECT Segmentation, COUNT(*) AS CustomerCount
FROM Customers
GROUP BY Segmentation;

###5. Find Customers with High Income

SELECT * FROM Customers
WHERE Income > 75000;

###6.  Order Customers by Recency

SELECT * FROM Customers
ORDER BY Recency DESC;

###7. Find Average Monetary Value

SELECT AVG(Monetary) AS AverageMonetary
FROM Customers;

###8. Using Case for Income Categories

SELECT CustomerID, Name, Income,
       CASE
           WHEN Income > 70000 THEN 'High Income'
           WHEN Income BETWEEN 40000 AND 70000 THEN 'Medium Income'
           ELSE 'Low Income'
       END AS IncomeCategory
FROM Customers;

###9. Top 3 Customers by Monetary Value

SELECT TOP 3 * FROM Customers
ORDER BY Monetary DESC;

###9. Segment Customers by Age Range

SELECT CustomerID, Name, Age,
       CASE
           WHEN Age < 30 THEN 'Youth'
           WHEN Age BETWEEN 30 AND 50 THEN 'Adult'
           ELSE 'Senior'
       END AS AgeGroup
FROM Customers;

###10. Analyze Spending Trends by Gender
Compare average spending based on gender.

SELECT Gender, AVG(Monetary) AS AvgSpending
FROM Customers
GROUP BY Gender;
