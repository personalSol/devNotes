---
status: newBorn
related-links: 
created: 2025-07-05T12:02
updated: 2025-07-05T12:02
---
---

```sql
CREATE TABLE CUSTOMER(
	customer_id INT PRIMARY KEY,
	customer_name VARCHAR(60)
);

CREATE TABLE ORDERS(
	order_id INT PRIMARY KEY,
	cust_id INT,
	order_name VARCHAR(50),
	order_quantity INT NOT NULL,
	FOREIGN KEY (cust_id) REFERENCES CUSTOMER(customer_id)
);

INSERT INTO CUSTOMER(customer_id, customer_name) VALUES
(1, 'Alok'),
(2, 'Anand'),
(3, 'Armin'),
(4, 'Aryan'),
(5, 'Anurag');


INSERT INTO ORDERS(order_id, cust_id, order_name, order_quantity) VALUES
(001, 1, 'jacket', 2),
(002, 1, 'pant', 1),
(003, 2, 'jeans', 3),
(004, Null, 'shirt', 5);


SELECT * FROM CUSTOMER;
SELECT * FROM ORDERS;


SELECT c.customer_name, o.order_name, o.order_quantity
FROM CUSTOMER c
JOIN ORDERS o -- same as INNER JOIN
ON c.customer_id = o.cust_id;

SELECT c.customer_name, o.order_name, o.order_quantity
FROM CUSTOMER c
LEFT JOIN ORDERS o -- same as INNER JOIN
ON c.customer_id = o.cust_id;

SELECT c.customer_name, o.order_name, o.order_quantity
FROM CUSTOMER c
RIGHT JOIN ORDERS o -- same as INNER JOIN
ON c.customer_id = o.cust_id;

SELECT c.customer_name, o.order_name, o.order_quantity
FROM CUSTOMER c
FULL OUTER JOIN ORDERS o -- same as INNER JOIN
ON c.customer_id = o.cust_id;

-- not sure about cross join though
SELECT c.customer_name, o.order_name, o.order_quantity
FROM CUSTOMER c
CROSS JOIN ORDERS o -- same as INNER JOIN

```

