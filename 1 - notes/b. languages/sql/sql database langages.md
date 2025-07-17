---
status: newBorn
related-links: 
created: 2025-07-04T18:30
updated: 2025-07-04T18:40
---
---

> [!NOTE] Summary
> - we never deal with DTO ( it handles how data which is in tabular format will go in backend ). they are just some bunch of settings that we need to do
> - DQL only consists select even though it was already there in DML


#### 🔧 DDL (Data Definition Language)

DDL is used to define and manage database objects like tables, indexes, views, etc. DDL commands deal with the structure and schema of the database.

* `CREATE`: Creates a new database object (e.g., table, index, view).
* `ALTER`: Modifies an existing object (e.g., adds/removes columns, changes data type).
* `DROP`: Deletes an object (e.g., table, index).
* ~~`TRUNCATE`: Removes all rows from a table but keeps the structure.~~
* `RENAME`: Renames an existing object (e.g., table, column).

#### 🔄 DML (Data Manipulation Language)

Used to manage data within schema objects. and do CRUD on information stored in database

* `INSERT`: Inserts new data into a table.
* `UPDATE`: Modifies existing data in a table.
* `DELETE`: Removes rows from a table.
* `SELECT`: Retrieves data from a table.

---

#### 🔐 Data Control Language (DCL)

DCL commands deal with granting and revoking privileges on the database.

* `GRANT`: Gives privileges to users or roles.
* `REVOKE`: Takes away privileges from users or roles.

---

#### 🔁 Transaction Control Language (TCL)

TCL commands deal with transaction management in the database. Transactions ensure that a series of DML statements are executed successfully or not at all (atomicity).

* `BEGIN`: Starts a transaction.
* `COMMIT`: Saves changes made during the transaction.
* `ROLLBACK`: Undoes changes made during the transaction.
* `SAVEPOINT`: Sets a point to which a transaction can be rolled back.

---

#### 🔎 Data Query Language (DQL)

DQL is often considered a part of DML, specifically focusing on queries that retrieve data from the database.

* `SELECT`: The only DQL command used to retrieve data.

---

#### 📦 Data Transfer Objects (DTOs)

DTOs in SQL refer to objects or structures used to transfer data between different layers of an application, typically between the database and the application layer. DTOs are designed to be simple containers for carrying data. Though DTO is a concept applied at the application layer, SQL results are often mapped into DTOs.

```sql
-- This SELECT query represents a DTO that transfers product information
SELECT name, price, stock
FROM products;
```

```json
{
  "name": "T-shirt",
  "price": 500.00,
  "stock": 10
}
```


