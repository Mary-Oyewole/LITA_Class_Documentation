# LITA_Class_Documentation
# Sales Performance and Customer Segmentation Analysis

## Project Overview

This repository contains two data analysis projects:

### *Project 1: Sales Performance Analysis for a Retail Store*  
Analyzing sales data to uncover insights like top-selling products, regional performance, and monthly sales trends.

### *Project 2: Customer Segmentation for a Subscription Service*  
Exploring customer data to understand subscription patterns, cancellations, and key customer trends.

Both projects culminate in *interactive Power BI dashboards* showcasing key findings.

---

## Table of Contents
1. [Technologies Used](#technologies-used)
2. [Project Workflow](#project-workflow)
3. [SQL Queries](#sql-queries)
   - [Sales Performance Analysis](#sales-performance-analysis)
   - [Customer Segmentation](#customer-segmentation)
4. [Power BI Dashboards](#power-bi-dashboards)
5. [Sample Outputs](#sample-outputs)
6. [How to Run](#how-to-run)
7. [Acknowledgments](#acknowledgments)

---

## Technologies Used

- *Excel*: Data cleaning, pivot tables, and formula-based analysis  
- *SQL*: Querying datasets for insights  
- *Power BI*: Visualization and interactive dashboards  

---

## Project Workflow

### *Data Cleaning*
1. *Removed duplicates and null values* in both datasets using Excel.
2. *Sales Data*:
   - Added computed columns for *Revenue* (Quantity * Unit Price) and *Total Sales*.
   - Generated pivot tables:
     - Total Sales by Product  
     - Total Sales by Region  
     - Average Sales Per Product  
     - Total Revenue by Region  
3. *Customer Data*:
   - Created pivot tables for analyzing:
     - Total Subscription Count by Region  
     - Subscription Trends

### *Visualizations*
- Created bar charts and graphs to represent:
  - Total sales and revenue breakdowns by product and region.
  - Customer subscription trends.

### *SQL Queries*
- Loaded datasets into *SQL Server*.
- Used SQL to answer key questions (listed below).

---

## SQL Queries

### *Sales Performance Analysis*

sql
-- Q1: Retrieve total sales for each product category
SELECT Product, SUM(Quantity * UnitPrice) AS Total_Sales
FROM [dbo].[Sales Data]
GROUP BY Product;

-- Q2: Number of sales transactions by region
SELECT Region, SUM(Quantity * UnitPrice) AS Total_Sales
FROM [dbo].[Sales Data]
GROUP BY Region;

-- Q3: Highest selling product by total sales
SELECT Product, SUM(Quantity * UnitPrice) AS Total_Sales
FROM [dbo].[Sales Data]
GROUP BY Product;


### *Customer Segmentation*

sql
-- Q1: Total number of customers by region
SELECT Region, COUNT(CustomerID) AS Total_Customers
FROM [dbo].[Customer Data]
GROUP BY Region;

-- Q2: Most popular subscription type
SELECT SubscriptionType, COUNT(CustomerID) AS Number_Of_Customers
FROM [dbo].[Customer Data]
GROUP BY SubscriptionType;

-- Q3: Total revenue by subscription type
SELECT SubscriptionType, SUM(Revenue) AS Total_Revenue
FROM [dbo].[Customer Data]
GROUP BY SubscriptionType;


---

## Power BI Dashboards

### *Project 1: Sales Performance Dashboard*
Key sections:
- Sales Overview  
- Top-performing Products  
- Regional Breakdown  

### *Project 2: Customer Segmentation Dashboard*
Key sections:
- Active vs. Canceled Subscriptions  
- Popular Subscription Types  
- Subscription Duration Trends  

---

## Sample Outputs

*Example from Sales Data*:  

| Product   | Revenue ($) | Total Sales |
|-----------|-------------|-------------|
| Gloves    | 5,000       | 1,200       |
| Hat       | 8,000       | 1,500       |
| Jacket    | 10,000      | 2,000       |

---

## How to Run

1. Clone the repository:  
   bash
   git clone https://github.com/Mary-Oyewole/LITA_Class_Documentation.git
   
2. Load the datasets into your SQL Server environment.
3. Use provided SQL queries to generate insights.
4. Visualize findings in Power BI using provided templates.

---

## Acknowledgments

Special thanks to the resources and tools used:
- [Microsoft Excel](https://www.microsoft.com/excel)
- [SQL Server](https://www.microsoft.com/sql-server)
- [Power BI](https://powerbi.microsoft.com)
