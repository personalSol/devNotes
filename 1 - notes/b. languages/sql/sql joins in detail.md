---
status: newBorn
related-links: 
created: 2025-07-05T11:59
updated: 2025-07-05T11:59
---
---

# JOIN and ON statement

> **JOIN**s are useful for allowing us to pull data from multiple tables.
> 
> With the addition of the **JOIN** statement to our toolkit, we will also be adding the **ON** statement.
> 
> We use **ON** clause to specify a **JOIN** condition which is a logical statement to combine the table in `FROM` and `JOIN` statements.
> 
> **JOIN** holds a table, and **ON** is a link for our **PK** to equal the **FK**.

Syntax:

```sql
SELECT orders.<column names or *>,
       accounts.*
FROM <first Table>
JOIN <Table you want to join>
ON <first Table>.<common column> = <Table you want to join>.<common column>;
```

Example:

```sql
SELECT orders.*,
       accounts.*
FROM orders 
JOIN accounts
ON orders.account_id = accounts.id;
```

If we want to specify the column we want to see from the joint table, we can do that by this method:

```sql
SELECT orders.account_id, accounts.name, accounts.website
FROM orders
JOIN accounts
ON orders.account_id = accounts.id;
```

This query pulls all the columns from both the tables.

```sql
SELECT *
FROM orders
JOIN accounts
ON orders.account_id = accounts.id;
```

# For joining more than 2 tables

> We can use the same method to join any number of tables by repeating the same method:

```sql
SELECT *
FROM web_events
JOIN accounts
ON web_events.account_id = accounts.id
JOIN orders
ON accounts.id = orders.account_id
```

## To fetch selected data from more than 2 tables:

```sql
SELECT web_events.channel, accounts.name, orders.total
FROM web_events
JOIN accounts
ON web_events.account_id = accounts.id
JOIN orders
ON accounts.id = orders.account_id
```

## Alias names for tables

```sql
FROM tablename AS t1
JOIN tablename2 AS t2
```

For arithmetic:

```sql
SELECT col1 + col2 AS total, col3
```

> But we can use this same format without AS and it will give the same result.

```sql
FROM tablename t1
JOIN tablename2 t2
```

```sql
SELECT col1 + col2 total, col3
```

Example:

```sql
SELECT o.*, a.*
FROM orders o
JOIN accounts a
ON o.account_id = a.id
```

# **Aliases for Columns in Resulting Table**

```sql
Select t1.column1 aliasname, t2.column2 aliasname2
FROM tablename AS t1
JOIN tablename2 AS t2
```

> If you have two or more columns in your SELECT that have the same name after the table name such as [accounts.name](http://accounts.name/) and sales_reps.name you will need to alias them. Otherwise it will only show one of the columns. You can alias them like [accounts.name](http://accounts.name/) AS AcountName, sales_rep.name AS SalesRepName

<aside> 💡 Until now we were studying INNER JOINs [which have always pulled rows only if they exist as a match across two tables.], but now we are going to see more types of JOINs.

</aside>

---

## Other Types of JOINs

![[Pasted image 20250705120119.png]]

> To show data of rows which have nothing common in both table. We use a method: 1st: LEFT JOIN 2nd: RIGHT JOIN

Here are tables names according to how we used them in QUERY.

![[Pasted image 20250705120059.png]]

## NULLs and Inner JOIN

> If there is not matching information in the **JOIN**ed table, then you will have columns with empty cells. These empty cells introduce a new data type called **NULL.**

## Code for LEFT JOIN

```sql
SELECT a.id, a.name, o.total
FROM orders o
LEFT JOIN accounts a
ON o.account_id = a.id
```

<aside> 💡 `LEFT OUTER **JOIN` is same as LEFT JOIN**

</aside>

## Code for RIGHT JOIN

```sql
SELECT a.id, a.name, o.total
FROM orders o
RIGHT JOIN accounts a
ON o.account_id = a.id
```

<aside> 💡 `RIGHT OUTER **JOIN` is same as RIGHT JOIN**

</aside>

## FULL OUTER JOIN

This will return the inner join result set, as well as any unmatched rows from either of the two tables being joined. We might see the language **FULL OUTER JOIN**, which is the same as **OUTER JOIN**.

## **JOINs and Filtering**

```sql
SELECT orders.*, accounts.*
FROM orders
LEFT JOIN accounts
ON orders.account_id = accounts.id 
WHERE accounts.sales_rep_id = 321500
```

> In this, all those rows that have sales rep id as 321500 will appear, any row that has sales rep id will be restricted. So if we want to see all those rows which doesn’t have a sales rep id. We can use AND instead of where, this will execute before JOIN and filter out all the accounts table to only have rows that have sales_rep_id as 321500, and when the filtered accounts table will combine with orders table, all those rows which don’t combine with the id in new accounts (even those rows who could have possibly combined with account table if filter wasn’t there will appear as well, the only difference it will have is that this time it will appear without getting combined with the corrosponded [account.id](http://account.id) row.) will be shown in last.

```sql
SELECT orders.*, accounts.*
FROM orders
LEFT JOIN accounts
ON orders.account_id = accounts.id 
AND accounts.sales_rep_id = 321500
```

<aside> 💡 REMEMBER: Without left or right join using AND after ON will give the same result.

</aside>

