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
