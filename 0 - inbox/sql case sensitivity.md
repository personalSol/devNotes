---
status: newBorn
related-links: 
created: 2025-06-26T17:52
updated: 2025-06-26T17:52
---
---

### Is SQL Case Sensitive?

SQL is **partially case sensitive** depending on what you're referring to.

---

### 1. SQL Keywords (e.g., SELECT, FROM)

- ❌ Not case sensitive
    
- Examples:
    
    ```sql
    SELECT * FROM users;
    select * from users;
    SeLeCt * FrOm users;
    ```
    
    All of these work the same.
    

---

### 2. Table and Column Names

- ⚠️ Case sensitivity depends on the **DBMS** and **OS**
    

#### MySQL:

- **Table names**:
    
    - Case sensitive on **Linux**
        
    - Case insensitive on **Windows**
        
- **Column names**: Not case sensitive
    
- Using **backticks** doesn't make it case sensitive
    

#### PostgreSQL:

- Converts unquoted identifiers to **lowercase**
    
    ```sql
    SELECT Name FROM users; -- Looks for "name"
    ```
    
- Quoted identifiers **are case sensitive**:
    
    ```sql
    SELECT "Name" FROM users; -- Will work only if column is exactly "Name"
    ```
    

#### SQL Server:

- Case sensitivity is based on the **collation** (more below)
    

---

### 3. String Comparison: Collation

#### What is Collation?

- Defines how **text is compared and sorted**
    
- Controls case sensitivity in string comparison
    

#### Examples:

```sql
SELECT * FROM users WHERE name = 'John';
```

- If collation is case-insensitive → matches 'JOHN', 'john', etc.
    
- If collation is case-sensitive → only matches exact 'John'
    

#### MySQL Collation Examples:

|Collation|Case Sensitive?|Notes|
|---|---|---|
|utf8_general_ci|❌ No|Default, case-insensitive|
|utf8_bin|✅ Yes|Binary, case-sensitive|

#### SQL Server Collation Examples:

|Collation|Case Sensitive?|
|---|---|
|SQL_Latin1_General_CP1_CI_AS|❌ No|
|SQL_Latin1_General_CP1_CS_AS|✅ Yes|

#### PostgreSQL:

- Follows OS-level locale and collation settings
    

#### Force collation in query (MySQL):

```sql
SELECT * FROM users WHERE name = 'John' COLLATE utf8_bin;  -- Case-sensitive
SELECT * FROM users WHERE name = 'John' COLLATE utf8_general_ci;  -- Case-insensitive
```

---

### Final Summary

|Element|Case Sensitive?|Depends On|
|---|---|---|
|SQL Keywords|❌ No|Always case-insensitive|
|Table/Column Names|⚠️ Sometimes|Depends on DBMS, OS, quotes|
|Quoted Identifiers|✅ Yes|e.g., "Name" is not same as "name"|
|String Comparison|⚠️ Sometimes|Depends on collation|

