---
status: newBorn
related-links: 
created: 2025-07-05T11:26
updated: 2025-07-05T11:43
---
---

- `;` ends SQL statements
- case sensitivity
	- SQL keywords are not case-sensitive (SELECT, select, etc.).
	- Table and column names are case-insensitive **unless** enclosed in double quotes.
	- Example:
	    
	    ```sql
	    SELECT "Fathers name" FROM people;  -- Case-sensitive because of quotes
	    SELECT fathers_name FROM people;    -- Case-insensitive
	    ```
- for rows and columns names with spaces, we use quotes like for `Father name` we will do "Father name"
- null is a property
- Use ` = ` to compare values
- Use `IS NULL` or `IS NOT NULL` for NULLs.
	- Example:
	    ```sql
	    WHERE age = 25
	    WHERE last_login IS NULL
	    ```
- In a LEFT or RIGHT JOIN, the table listed in `FROM` appears first in the result.
	- Example:
	    ```sql
	    SELECT * FROM table1 LEFT JOIN table2 ON table1.id = table2.id;
	    -- table1's columns come first
	    ```
- Header row (column names) is **not counted** when using `COUNT(*)`.
- `ORDER BY` uses `ASC` (ascending) by default.