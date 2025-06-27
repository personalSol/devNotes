---
status: newBorn
related-links: 
created: 2025-06-26T18:05
updated: 2025-06-26T18:05
---
---

## PostgreSQL SQL Notes (Long-Term Memory)

### 1. Case Sensitivity

- SQL keywords are not case-sensitive (SELECT, select, etc.).
    
- Table and column names are case-insensitive **unless** enclosed in double quotes.
    
- Example:
    
    ```sql
    SELECT "Fathers name" FROM people;  -- Case-sensitive because of quotes
    SELECT fathers_name FROM people;    -- Case-insensitive
    ```
    

### 2. Names with Spaces

- Enclose column or table names with spaces or special characters in **double quotes**.
    
- Example:
    
    ```sql
    SELECT "Fathers name" FROM people;
    ```
    

### 3. Semicolon Usage

- `;` ends SQL statements.
    
- Optional in some tools (e.g., pgAdmin) but recommended for consistency.
    

### 4. Column Order in Joins

- In a LEFT or RIGHT JOIN, the table listed in `FROM` appears first in the result.
    
- Example:
    
    ```sql
    SELECT * FROM table1 LEFT JOIN table2 ON table1.id = table2.id;
    -- table1's columns come first
    ```
    

### 5. Row Counting

- Header row (column names) is **not counted** when using `COUNT(*)`.
    
- Example:
    
    ```sql
    SELECT COUNT(*) FROM table;
    ```
    

### 6. ORDER BY Default

- `ORDER BY` uses `ASC` (ascending) by default.
    
- Example:
    
    ```sql
    SELECT * FROM users ORDER BY age;  -- Same as ORDER BY age ASC
    ```
    

### 7. Date Format and Usage

- Enclose dates in **single quotes**.
    
- Default format in PostgreSQL is `'YYYY-MM-DD'`.
    
- Use `TO_DATE()` for custom formats:
    
    ```sql
    TO_DATE('25-06-2024', 'DD-MM-YYYY')
    ```
    

### 8. Equality and NULL

- Use `=` to compare values.
    
- Use `IS NULL` or `IS NOT NULL` for NULLs.
    
- Example:
    
    ```sql
    WHERE age = 25
    WHERE last_login IS NULL
    ```
    

### 9. BETWEEN and Dates

- `BETWEEN` is inclusive.
    
- For full date ranges, use exclusive upper bound to include end date:
    
    ```sql
    WHERE date >= '2016-01-01' AND date < '2017-01-01'
    ```
    

### 10. GROUP BY Rules

- All non-aggregated columns in `SELECT` must be in `GROUP BY`.
    
- Aliases can be used in `GROUP BY` in PostgreSQL.
    
- Example:
    
    ```sql
    SELECT department AS dept, COUNT(*) FROM employees GROUP BY dept;
    ```

