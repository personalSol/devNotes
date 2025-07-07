---
status: newBorn
related-links: 
created: 2025-06-26T18:05
updated: 2025-07-05T11:43
---
---

#### 8. GROUP BY Rules

- All non-aggregated columns in `SELECT` must be in `GROUP BY`.
    
- Aliases can be used in `GROUP BY` in PostgreSQL.
    
- Example:
    
    ```sql
    SELECT department AS dept, COUNT(*) FROM employees GROUP BY dept;
    ```
    

---

### 📅 Date Handling

#### 9. Date Format and Usage

- Enclose dates in **single quotes**.
    
- Default format in PostgreSQL is `'YYYY-MM-DD'`.
    
- Use `TO_DATE()` for custom formats:
    
    ```sql
    TO_DATE('25-06-2024', 'DD-MM-YYYY')
    ```
    

#### 10. BETWEEN and Dates

- `BETWEEN` is inclusive.
    
- For full date ranges, use exclusive upper bound to include end date:
    
    ```sql
    WHERE date >= '2016-01-01' AND date < '2017-01-01'
    ```

