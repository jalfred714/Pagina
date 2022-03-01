---
title: SQL basics
author: Juan Pacheco
date: '2022-03-01'
slug: sql
categories:
  - SQL
tags:
  - JOIN
---

# SQL

# **SQL - CONCAT FUNCTION**

```sql
SELECT 
    usertype,
    CONCAT(start_station_name, "to", end_station_name) AS route,
    COUNT(*) AS num_trip,
    ROUND(AVG(CAST(tripduration as int64)/60),2) AS duration, 
FROM 
    `bigquery-public-data.new_york.citibike_trips`

GROUP BY 
    start_station_name, end_station_name, usertype

ORDER BY 
    num_trip DESC 
LIMIT  10
```

| Function | Usage | Example |
| --- | --- | --- |
| CONCAT | A function that adds strings together to create new text strings that can be used as unique keys | CONCAT (‘Google’, ‘.com’); |
| CONCAT_WS | A function that adds two or more strings together with a separator | CONCAT_WS (‘ . ’, ‘www’, ‘google’, ‘com’)
*The separator (being the period) gets input before and after Google when you run the SQL function |
| CONCAT with + | Adds two or more strings together using the + operator | ‘Google’ + ‘.com’ |

## **CONCAT at work**

When adding two strings together such as ‘Data’ and ‘analysis’, it will be input like this:

- SELECT CONCAT (‘Data’, ‘analysis’);

The result will be:

- Dataanalysis

Sometimes, depending on the strings, you will need to add a space character, so your function should actually be:

- SELECT CONCAT (‘Data’, ‘ ‘, ‘analysis’);

And the result will be:

- Data analysis

The same rule applies when combining three strings together. For example,

- SELECT CONCAT (‘Data’,’ ‘, ‘analysis’, ‘ ‘, ‘is’, ‘ ‘, ‘awesome!’);

And the result will be

- Data analysis is awesome!

# **JOIN**

### **INNER JOIN**

INNER is *optional* in this SQL query because it is the default as well as the most commonly used JOIN operation. You may see this as JOIN only. INNER JOIN returns records if the data lives in both tables. For example, if you use INNER JOIN for the 'customers' and 'orders' tables and match the data using the customer_id key, you would combine the data for each customer_id that exists in both tables. If a customer_id exists in the customers table but not the orders table, data for that customer_id isn’t joined or returned by the query.

```sql
SELECT 
    employees.name AS employees_name,
    employees.role AS employees_role
		departments.name AS department_name
FROM  
    employees
INNER JOIN 
    departments ON 
    employees.department_id = departments.department_id
```

### **LEFT JOIN**

You may see this as LEFT OUTER JOIN, but most users prefer LEFT JOIN. Both are correct syntax. LEFT JOIN returns all the records from the left table and only the matching records from the right table. Use LEFT JOIN whenever you need the data from the entire first table and values from the second table, if they exist. 

****RIGHT JOIN****

You may see this as RIGHT OUTER JOIN or RIGHT JOIN. RIGHT JOIN returns all records from the right table and the corresponding records from the left table. Practically speaking, RIGHT JOIN is rarely used. Most people simply switch the tables and stick with LEFT JOIN.

### **FULL OUTER JOIN**

You may sometimes see this as FULL JOIN. FULL OUTER JOIN returns all records from the specified tables. You can combine tables this way, but remember that this can potentially be a large data pull as a result. FULL OUTER JOIN returns all records from *both* tables even if data isn’t populated in one of the tables.

[SQL Joins - The Ultimate Guide](https://www.essentialsql.com/sql-joins/)

- **INNER JOIN:** Returns only the rows where the target appears in both tables.
- **LEFT JOIN:** Returns every row from the left table, as well as any rows from the right table with matching keys found in the left table.

```sql
-- Let's say table_1 has 100 rows and table_2 has 10 rows.
-- They share 10 keys in common.

-- Using INNER JOIN --> We get 10 rows in our results.
SELECT
    COUNT(*)
FROM
    table_1
INNER JOIN
    table_2
ON table_1.key = table_2.key;

-- Using LEFT JOIN --> We get 100 rows in our results.
SELECT
    COUNT(*)
FROM
    table_1
LEFT JOIN
    table_2
ON table_1.key = table_2.key;
```

# Example- World bank intl education

```sql
SELECT 
    `bigquery-public-data.world_bank_intl_education.international_education`.country_name, 
    `bigquery-public-data.world_bank_intl_education.country_summary`.country_code, 
    `bigquery-public-data.world_bank_intl_education.international_education`.value
FROM 
    `bigquery-public-data.world_bank_intl_education.international_education`
INNER JOIN 
    `bigquery-public-data.world_bank_intl_education.country_summary` 
ON `bigquery-public-data.world_bank_intl_education.country_summary`.country_code = `bigquery-public-data.world_bank_intl_education.international_education`.country_codeSELECT 
    `bigquery-public-data.world_bank_intl_education.international_education`.country_name, 
    `bigquery-public-data.world_bank_intl_education.country_summary`.country_code, 
    `bigquery-public-data.world_bank_intl_education.international_education`.value
FROM 
    `bigquery-public-data.world_bank_intl_education.international_education`
INNER JOIN 
    `bigquery-public-data.world_bank_intl_education.country_summary` 
ON `bigquery-public-data.world_bank_intl_education.country_summary`.country_code = `bigquery-public-data.world_bank_intl_education.international_education`.country_code
```

This basic query joins the tables on the country_code foreign key, and returns the country name, country code, and value column. This is quite a long, unwieldy query for such a basic result! The length of each table name (which must include the full address for each table for BigQuery to know where to pull the data from) makes this hard to read and work with.

However, you can solve this by setting an **alias** for each table.

**Use descriptive aliases**

```sql
SELECT 
    edu.country_name,
    summary.country_code,
    edu.value
FROM 
    `bigquery-public-data.world_bank_intl_education.international_education` AS edu
INNER JOIN 
    `bigquery-public-data.world_bank_intl_education.country_summary` AS summary
ON edu.country_code = summary.country_code
```

This query is much easier to read and understand. Recall that you can set aliases for tables by specifying the alias for the table after the table’s name in FROM and/or JOIN statements.

For this example, the international_education table was renamed as **edu**, and the country_summary table as **summary**. Using descriptive aliases is a best practice and will help you keep your queries clean, readable, and easy to work with.

# **Example**

What is the average amount of money spent per region on education?

```sql
SELECT 
    AVG(edu.value) average_value, summary.region
FROM 
    `bigquery-public-data.world_bank_intl_education.international_education` AS edu
INNER JOIN 
    `bigquery-public-data.world_bank_intl_education.country_summary` AS summary
ON edu.country_code = summary.country_code
WHERE summary.region IS NOT null
GROUP BY summary.region
ORDER BY average_value DESC
```

# **INNER JOINs versus OUTER JOINs**

Example

You have been tasked to provide data for a feature sports article on Michael Jordan’s basketball career. The writer wants to include a funny twist and asks you to find out if Michael Jordan played better at schools with animal mascots.

To analyze his early career, you start with the years he played basketball in college. You need to examine National Collegiate Athletic Association (NCAA) college basketball stats from 1984.

You’ll need a list of all NCAA Division I colleges and universities; their mascots, if applicable; and their number of wins and losses. You can find this information in the public dataset **ncaa_basketball** on BigQuery.

Next, you will write a query. Your query should join the season statistics from one table with the mascot information from another. You need to use a LEFT JOIN instead of an INNER JOIN because not all teams have mascots. If you use an INNER JOIN, you would exclude teams with no mascot.

```sql
SELECT
 seasons.market AS university,
 seasons.name AS team_name,
 seasons.wins,
 seasons.losses,
 seasons.ties,
 mascots.mascot AS team_mascot
FROM
 `bigquery-public-data.ncaa_basketball.mbb_historical_teams_seasons` AS seasons
INNER JOIN
 `bigquery-public-data.ncaa_basketball.mascots` AS mascots
ON
 seasons.team_id = mascots.id
WHERE
 seasons.season = 1984
 AND seasons.division = 1
ORDER BY
 seasons.market
```

# **Using subqueries to aggregate data**

```sql
SELECT 
    warehouse.warehouse_id,
    CONCAT(warehouse.state,':', Warehouse.warehouse_alias) AS warehouse_name,
    COUNT(Orders.order_id) AS number_of_orders,
      (SELECT 
        COUNT(*)
        FROM warehouse_orders.Orders Orders) AS total_orders,
    CASE 
    WHEN COUNT(Orders.order_id)/(SELECT COUNT(*) FROM warehouse_orders.Orders) <=0.20
    THEN "Fulfilled 0-20% of orders"
    WHEN COUNT(Orders.order_id)/(SELECT COUNT(*) FROM warehouse_orders.Orders) > 0.20
    AND COUNT(Orders.order_id)/(SELECT COUNT(*) FROM warehouse_orders.Orders) <= 0.60
    THEN "Fulfilled 21-60% of orders"
   ELSE "Fulfilled more than 60% of orders"
   END AS fulfillment_summary

FROM  warehouse_orders.Warehouse warehouse 
LEFT JOIN warehouse_orders.Orders Orders
    ON Orders.warehouse_id = warehouse.warehouse_id
GROUP BY 
    warehouse.warehouse_id,
    warehouse.warehouse_name
HAVING 
COUNT(Orders.Orders_id)>0
```

# **SQL functions and subqueries: A functional friendship**

SQL functions are what help make data aggregation possible. (As a reminder, data aggregation is the process of gathering data from multiple sources in order to combine it into a single, summarized collection.) So, how do SQL functions work? Going back to W3Schools, let’s review some of these functions to get a better understanding of how to run these queries:

- **[SQL HAVING](http://www-db.deis.unibo.it/courses/TW/DOCS/w3schools/sql/sql_having.asp.html):** This is an overview of the HAVING clause, including what it is and a tutorial on how and when it works.
- **[SQL CASE](https://www.w3schools.com/sql/sql_case.asp):** Explore the usage of the CASE statement and examples of how it works.
- **[SQL IF](https://www.w3schools.com/sql/func_mysql_if.asp):** This is a tutorial of the IF function and offers examples that you can practice with.
- **[SQL COUNT](http://www-db.deis.unibo.it/courses/TW/DOCS/w3schools/sql/sql_func_count.asp.html):** The COUNT function is just as important as all the rest, and this tutorial offers multiple examples to review.

## **Subqueries - the cherry on top**

Think of a query as a cake. A cake can have multiple layers contained within it and even layers within those layers. Each of these layers are our subqueries, and when you put all of the layers together, you get a cake (query). Usually, you will find subqueries nested in the SELECT, FROM, and/or WHERE clauses.

There are a few rules that subqueries must follow:

- Subqueries must be enclosed within parentheses
- A subquery can have only one column specified in the SELECT clause. But if you want a subquery to compare multiple columns, those columns must be selected in the main query.
- Subqueries that return more than one row can only be used with multiple value operators, such as the IN operator which allows you to specify multiple values in a WHERE clause.
- A subquery can’t be nested in a SET command. The SET command is used with UPDATE to specify which columns (and values) are to be updated in a table.

[Writing Subqueries in SQL | Advanced SQL - Mode](https://mode.com/sql-tutorial/sql-sub-queries/)