---
status: newBorn
related-links: 
created: 2025-06-26T21:26
updated: 2025-06-26T21:26
---
---

### 🔶 Single Quotes `' '` — Used for **Values / Literals**

Used for any kind of **string, date, or pattern literal**.

**Examples:**

- `WHERE name = 'Alice'` → Match string value
    
- `WHERE name LIKE 'A%'` → Match values starting with A
    
- `INSERT INTO users (name) VALUES ('John')` → Insert string
    
- `'2024-01-01'::date` → Cast string to date
    

> ✅ Always use `'` when you’re referring to **actual content values** (not identifiers).

---

### 🔷 Double Quotes `" "` — Used for **Identifiers**

Used when referring to **column names, table names, or aliases** that are case-sensitive, contain spaces, or are reserved words.

**Examples:**

- `SELECT "Fathers Name" FROM people;` → Identifier with space
    
- `SELECT name AS "Employee Name" FROM employees;` → Alias with space
    
- `SELECT "FullName" FROM users;` → Case-sensitive identifier
    
- `SELECT "user" FROM accounts;` → "user" is a reserved word
    

> ✅ Use `"` when identifiers include **spaces, uppercase letters, or keywords**.

---

### ❌ Common Mistakes

|Mistake|What Happens|
|---|---|
|`SELECT 'name' FROM users`|Returns literal string `'name'` in every row|
|`WHERE name = "John"`|Error: column "John" does not exist|

---

### 🧠 Tip to Remember

- Use `' '` for **Data** (values like names, dates, text)
    
- Use `" "` for **Design** (columns, tables, aliases)

