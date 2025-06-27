---
status: newBorn
related-links: 
created: 2025-06-26T20:44
updated: 2025-06-26T20:44
---
---


### 📊 Numeric Types

**INTEGER / INT**

- Whole number (4 bytes)
    
- Example: `10`, `-50`
    

**SERIAL**

- Auto-incrementing integer (4 bytes)
    
- Example: `1`, `2`, `3`
    

**BIGINT**

- Large whole number (8 bytes)
    
- Example: `9223372036854775807`
    

**DECIMAL(p,s) / NUMERIC(p,s)**

- Exact precision
- `p` = total digits, `s` = digits after decimal
- Up to **5 total digits**, and
- **2 digits after the decimal point**
- Example: `DECIMAL(5,2)` allows up to `999.99`
- invalid values: 
	- `1234.56` → ❌ Too many digits (6 digits total)
	- `12.345` → ❌ Too many decimal places
- valid values
	- `123.45`
	- `0.99`
	- `999.99`
	- `-12.34`

**REAL**

- 4-byte approximate float
    
- Example: `3.14`
    

**DOUBLE PRECISION**

- 8-byte float
    
- Example: `3.1415926535`
    

**SMALLINT**

- 2-byte small integer
    
- Range: `-32768` to `32767`
    

---

### 📝 Text Types

**TEXT**

- Unlimited-length text
    
- Example: `'Hello'`
    

**VARCHAR(n)**

- Variable-length string with max `n` chars
    
- Example: `'abc'` in `VARCHAR(5)`
    

**CHAR(n)**

- Fixed-length string padded with spaces
    
- Example: `'abc '` in `CHAR(5)`
    

---

### 📅 Date/Time Types

**DATE**

- Calendar date only
    
- Example: `2024-06-26`
    

**TIME**

- Time without date
    
- Example: `14:30:00`
    

**TIMESTAMP**

- Date + time without time zone
    
- Example: `2024-06-26 14:30:00`
    

**TIMESTAMPTZ**

- Timestamp with time zone
    
- Example: `2024-06-26 14:30:00+05:30`
    

---

### ✅ Boolean Type

**BOOLEAN**

- True or False
    
- Example: `TRUE`, `FALSE`
    

---

### 🎯 UUID Type

**UUID**

- Universally Unique Identifier
    
- Example: `550e8400-e29b-41d4-a716-446655440000`
    

---

### 📦 JSON & Arrays

**JSON**

- Text-based JSON, no indexing
    
- Example: `'{"a":1}'`
    

**JSONB**

- Binary JSON (faster queries)
    
- Example: `'{"a":1}'`
    

**ARRAY**

- Array of any type
    
- Example: `'{1,2,3}'::INT[]`

### decimal in detail

In PostgreSQL, `DECIMAL(5,2)` (also written as `NUMERIC(5,2)`) means:



#### ❌ Examples of invalid values:


    

#### ⚠️ Round-off:

If you insert a number like `1.999` into a `DECIMAL(5,2)` column, it will be **rounded to `2.00`**.

Let me know if you want the difference between `DECIMAL`, `NUMERIC`, and `FLOAT`.

