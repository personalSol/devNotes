---
status: newBorn
related-links: 
created: 2025-06-26T20:42
updated: 2025-06-26T22:15
---
---

### 🗂️ Database Commands

```sql
-- Create database
CREATE DATABASE dbname;

-- Connect to database
\c dbname

-- List databases
\l

-- List tables
\dt

-- Drop database
DROP DATABASE dbname;
```

---

### 📦 Table Operations

```sql
-- Create table
CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  name TEXT NOT NULL,
  age INT,
  email TEXT UNIQUE,
  created_at TIMESTAMP DEFAULT NOW()
);

-- Drop table
DROP TABLE users;

-- Rename table
ALTER TABLE users RENAME TO customers;

-- Around column
ALTER TABLE users ADD COLUMN phone TEXT;
ALTER TABLE chai_store ADD COLUMN stock INT DEFAULT 0;
ALTER TABLE chai_store ALTER COLUMN "Temp Colm" type VARCHAR(50);
ALTER TABLE chai_store RENAME COLUMN "Temp Colm" TO temp_column;

-- Drop column
ALTER TABLE users DROP COLUMN phone;
```

---

### 📥 Insert Data

```sql
-- Insert one row
INSERT INTO users (name, age, email) VALUES ('John', 25, 'john@email.com');

-- Insert multiple rows
INSERT INTO users (name, age, email) VALUES
  ('Alice', 30, 'alice@email.com'),
  ('Bob', 22, 'bob@email.com');

-- Insert with default timestamp
INSERT INTO users (name) VALUES ('Sam');
```

---

### 📤 Select Data

```sql
SELECT * FROM users;
SELECT name, age FROM users;
SELECT * FROM users WHERE age > 20;
SELECT * FROM users ORDER BY age DESC;
SELECT * FROM users LIMIT 5 OFFSET 10;
```

---

### 🛠️ Update & Delete

```sql
UPDATE users SET age = 26 WHERE name = 'John';

DELETE FROM users WHERE age < 18;
```

---

### 🔍 WHERE Clause

```sql
-- for exact value
WHERE age = 25
WHERE chai_name = 'Black chai';

-- for when we need something similar
WHERE name LIKE 'jo%'     -- case-insensitive like
WHERE chai_name LIKE 'Iced%'


WHERE age BETWEEN 18 AND 30
WHERE email IS NULL
WHERE name IN ('Alice', 'Bob')
```

---

### 🟦 `ORDER BY` – Sort the result

```sql
SELECT * FROM table_name
ORDER BY column_name ASC;  -- or DESC for descending

-- You can sort by multiple columns:
ORDER BY col1 ASC, col2 DESC;
```

### 🔢 Aggregations

```sql
SELECT COUNT(*) FROM users;
SELECT AVG(age) FROM users;
SELECT MIN(age), MAX(age) FROM users;
```

---

### 👥 GROUP BY and HAVING

```sql
SELECT age, COUNT(*) FROM users GROUP BY age;
SELECT age, COUNT(*) FROM users GROUP BY age HAVING COUNT(*) > 1;
```

---

### 🔗 Joins

```sql
-- INNER JOIN
SELECT * FROM orders o
JOIN users u ON o.user_id = u.id;

-- LEFT JOIN
SELECT * FROM users u
LEFT JOIN orders o ON u.id = o.user_id;

-- RIGHT JOIN
SELECT * FROM users u
RIGHT JOIN orders o ON u.id = o.user_id;

-- FULL OUTER JOIN
SELECT * FROM users u
FULL JOIN orders o ON u.id = o.user_id;
```

---

### 🧠 Subqueries

```sql
SELECT name FROM users
WHERE id IN (
  SELECT user_id FROM orders WHERE total > 500
);
```

---

### 📎 Constraints

```sql
-- On column
id SERIAL PRIMARY KEY
email TEXT UNIQUE NOT NULL
created_at TIMESTAMP DEFAULT NOW()

-- Foreign key
FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE
```

---

### 🧮 CASE Statement

```sql
SELECT name,
  CASE
    WHEN age < 18 THEN 'Minor'
    WHEN age >= 18 THEN 'Adult'
    ELSE 'Unknown'
  END AS category
FROM users;
```

---

### 🧰 Useful PostgreSQL Tips

```sql
-- Show table structure
\d users

-- Create enum type
CREATE TYPE mood AS ENUM ('happy', 'sad', 'neutral');

-- JSON column
ALTER TABLE users ADD COLUMN preferences JSONB;

-- UPSERT (Insert or Update)
INSERT INTO users (id, name)
VALUES (1, 'John')
ON CONFLICT (id)
DO UPDATE SET name = EXCLUDED.name;
```