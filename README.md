# Walmart Sales Data Analysis \| SQL Project

## Project Overview

This project analyzes Walmart sales transaction data using **MySQL** to
explore revenue performance, product categories, customer ratings,
payment methods, and transaction patterns. The goal is to turn raw sales
records into useful business insights through SQL queries.

## Tools & Technologies

-   **Database:** MySQL
-   **SQL Editor:** MySQL Workbench and Visual Studio Code
-   **Language:** SQL
-   **Dataset:** [Walmart Sales Dataset on
    Kaggle](https://www.kaggle.com/najir0123/walmart-10k-sales-datasets)

## Dataset

The dataset contains sales transaction information such as invoice ID,
branch, category, date, time, payment method, quantity, rating, and
total sales. Confirm the exact column names against your database table.

## Business Questions Explored

1.  What is the total revenue by branch?
2.  Which product categories have the highest average ratings within
    each branch?
3.  Which weekdays have the highest number of transactions in each
    branch?
4.  How can transactions be grouped into morning, afternoon, and
    evening?
5.  How do branch revenues compare between 2022 and 2023?
6.  Which five branches have the highest percentage decrease in revenue?
7.  How do transaction counts and quantities sold vary by payment
    method?

## SQL Concepts Used

-   Aggregate functions: `SUM()`, `AVG()`, and `COUNT()`
-   `GROUP BY`, `WHERE`, and `ORDER BY`
-   `CASE` expressions
-   Date and time functions
-   Common Table Expressions (CTEs)
-   `INNER JOIN`
-   Window functions: `RANK()` and `ROW_NUMBER()`
-   Percentage and year-over-year revenue calculations

## Revenue Decrease Analysis

For the year-over-year comparison, revenue is aggregated by branch for
each year. The two yearly results are joined by branch, and the
percentage decrease is calculated relative to the previous year's
revenue:

``` sql
ROUND(
    (last_year_revenue - current_year_revenue)
    / NULLIF(last_year_revenue, 0) * 100,
    2
)
```

Branches with lower revenue in the current year can then be sorted by
`decrease_percentage` to identify the five largest percentage declines.

## Key Outcomes

-   Compared sales performance across branches.
-   Ranked product categories by average customer rating within each
    branch.
-   Examined transaction volume by weekday and time of day.
-   Compared branch revenue between 2022 and 2023.
-   Identified branches with the largest percentage decline in revenue.

> Add specific numerical findings or screenshots from your actual query
> results here before publishing. Avoid claiming results that have not
> been verified.

## Project Structure

Update this example to match the files and folders in your repository:

``` text
Walmart-Sales-Analysis/
├── sql_queries/
│   └── walmart_analysis.sql
├── data/
│   └── walmart.csv
└── README.md
```

## How to Run

1.  Install MySQL and connect through MySQL Workbench or a SQL extension
    in Visual Studio Code.
2.  Download the dataset from
    [Kaggle](https://www.kaggle.com/najir0123/walmart-10k-sales-datasets).
3.  Import the dataset into your MySQL database.
4.  Open the SQL scripts in your editor.
5.  Select the correct database and run the queries.
6.  Review the result grids and record verified findings.

Do not upload credentials or API tokens. Only include the dataset in the
repository if you have permission to redistribute it.

## What I Learned

Through this project, I practiced writing SQL for business analysis,
using joins and CTEs to compare datasets, applying window functions for
ranking, working with date and time values, and translating business
questions into queries.

## Author

**Rudra Madhaba Dalabehera**

Aspiring Data Analyst \| SQL \| Python \| Excel \| Power BI
