---
status: newBorn
related-links: 
created: 2025-07-05T12:14
updated: 2025-07-05T12:14
---
---

- Table of Contents
    - Deal with NULL values
    - Create DATE functions
        - Create aggregations in your SQL Queries including
            - COUNT
            - SUM
            - MIN & MAX
            - AVG
            - GROUP BY
            - DISTINCT
            - HAVING
    - Implement CASE statements

# Nulls

> **NULLs** are a datatype that specifies where no data exists in SQL. It is a property of data and not a value. That’s why we use ‘is’ instead of ‘=’ in NULL because equal is used in values not properties.

```sql
SELECT *
FROM accounts
WHERE primary_poc is NULL;
```

### Reasons for NULL to happen.

- **NULL**s frequently occur when performing a **LEFT** or **RIGHT JOIN**. You saw in the last lesson - when some rows in the left table of a left join are not matched with rows in the right table, those rows will contain some **NULL** values in the result set.
- **NULL**s can also occur from simply missing data in our database.

## COUNT

> It helps in finding number of rows according to a particular condition. It doesn’t count NULL. COUNT can be done on both numeric and non-numeric values.

```sql
SELECT COUNT(*) AS order_count
FROM orders
WHERE occurred_at BETWEEN '12-01-2016' AND '01-01-2017'
```

<aside> 💡 Remember the format of date here is ‘mm-dd-yyyy’

</aside>

```sql
SELECT COUNT(primary_poc) AS account_primary_poc_count
FROM accounts
```

We can notice that the above syntax gives 9 values less than the original value. This is because COUNT doesn’t include NULL values. This property of COUNT can be used to find the number of NULL rows in a particular column.

> Followed by this code, we can check if the result is true.

```sql
SELECT *
FROM accounts
WHERE primary_poc IS NULL
```

## SUM

> SUM is used to find the total sum of any column. Unlike COUNT, SUM can be only used on numeric values. SUM count NULLs as 0.

<aside> 💡 A thing to remember is Aggregators only work on verticals[columns].

</aside>

```sql
SELECT SUM(standard_qty) AS standard,
       SUM(gloss_qty) AS gloss,
       SUM(poster_qty) AS poster
FROM orders
```

MAX and MIN

Syntax:

```sql
SELECT MIN(standard_qty) AS standard_min,
       MIN(gloss_qty) AS gloss_min,
       MIN(poster_qty) AS poster_min,
       MAX(standard_qty) AS standard_max,
       MAX(gloss_qty) AS gloss_max,
       MAX(poster_qty) AS poster_max
FROM   orders
```

AVG

> **AVG** returns the mean of the data - that is the sum of all of the values in the column divided by the number of values in a column. This aggregate function again ignores the **NULL** values in both the numerator and the denominator. If we wanted to include NULLs as well[which will significantly effect the result], we can use combination of SUM(column we need average of)/ COUNT(column we need average of). As COUNT includes rows which have NULL values.

Syntax:

```sql
SELECT AVG(standard_qty) AS standard_avg,
       AVG(gloss_qty) AS gloss_avg,
       AVG(poster_qty) AS poster_avg
FROM orders
```

GROUP BY:

<aside> 💡 This clause comes between WHERE and ORDER BY clause. This is used tp aggregate data accourding to groups of a particular column. Whenever there is column_name is the SELECT statement with other aggregators, it is supposed by the QUERY that user wants the aggregations done in accordance to that column. Therefore the column must be in GROUP BY to support the idea, otherwise will return an error.

In the code below, we have aggregated the quantities of different product in accordance with the account column using GROUP BY.

</aside>

```sql
SELECT account_id,
       SUM(standard_qty) AS standard,
       SUM(gloss_qty) AS gloss,
       SUM(poster_qty) AS poster
FROM orders
GROUP BY account_id
ORDER BY account_id
```

> We can use ALIAS name in GROUP BY

```sql
SELECT a.name as name, MIN(total_amt_usd) smallest_order
FROM accounts a
JOIN orders o
ON a.id = o.account_id
GROUP BY name
ORDER BY smallest_order;
```

<aside> 💡 We can use ORDER BY in multiple columns. The order of columns listed in the **ORDER BY** clause does make a difference. You are ordering the columns from left to right. The order of column names in your **GROUP BY** clause doesn’t matter—the results will be the same regardless. Any column that is not within an aggregation must show up in your GROUP BY statement.

</aside>

```sql
SELECT account_id,
       channel,
       COUNT(id) as events
FROM web_events
GROUP BY account_id, channel
ORDER BY account_id, channel DESC
```

> Here first we have grouped by account_id and then channel. And we have chossed account_id as ASC[by default] and channel as DESC.

