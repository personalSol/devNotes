---
created: 2025-06-27T12:37:06
status: 
source: 
updated: 2025-06-27T12:37
---
---

### 🟦 Lecture 7: Relational Model

1. **Relational Model (RM)** organises the data in the form of relations (tables).  
2. A relational DB consists of a collection of tables, each of which is assigned a unique name.  
3. A row in a table represents a relationship among a set of values, and the table is a collection of such relationships.  
4. **Tuple**: A single row of the table representing a single data point / a unique record.  
5. **Columns**: represent the attributes of the relation. For each attribute, there is a permitted value, called **domain** of the attribute.  
6. **Relation Schema**: defines the design and structure of the relation, contains the name of the relation and all the columns/attributes.  
7. Common RM-based DBMS systems, aka RDBMS: Oracle, IBM, MySQL, MS Access.  
8. **Degree of table**: number of attributes/columns in a given table/relation.  
9. **Cardinality**: Total number of tuples in a given relation.  
10. **Relational Key**: Set of attributes which can uniquely identify each tuple.  

---

### 🟩 Important Properties of a Table in Relational Model

1. The name of relation is distinct among all other relations.  
2. The values have to be atomic. Can’t be broken down further.  
3. The name of each attribute/column must be unique.  
4. Each tuple must be unique in a table.  
5. The sequence of row and column has no significance.  
6. Tables must follow **integrity constraints** — it helps to maintain data consistency across the tables.  

---

### 🟩 Relational Model Keys

#### 1. **Super Key (SK)**
- Any possible combination of attributes present in a table which can uniquely identify each tuple.

#### 2. **Candidate Key (CK)**
- Minimum subset of super keys, which can uniquely identify each tuple.  
- It contains no redundant attribute.  
- CK value **shouldn’t be NULL**.

#### 3. **Primary Key (PK)**
- Selected out of CK set, has the least number of attributes.

#### 4. **Alternate Key (AK)**
- All CK except PK.

#### 5. **Foreign Key (FK)**
- It creates relation between two tables.  
- A relation, say `r1`, may include among its attributes the PK of another relation, say `r2`. This attribute is called FK from `r1` referencing `r2`.  
- The relation `r1` is known as the **Referencing (Child)** relation of the FK dependency.  
- The relation `r2` is known as the **Referenced (Parent)** relation of the FK.  
- FK helps to **cross-reference** between two different relations.

#### 6. **Composite Key**
- PK formed using at least 2 attributes.

#### 7. **Compound Key**
- PK which is formed using 2 FK.

#### 8. **Surrogate Key**
- Synthetic PK.  
- Generated automatically by DB, usually an integer value.  
- May be used as PK.

---

### 🟩 Integrity Constraints

1. CRUD Operations must be done with some integrity policy so that DB is always consistent.  
2. Introduced so that we do not accidentally corrupt the DB.  

#### a. **Domain Constraints**
- Restricts the value in the attribute of relation, specifies the Domain.  
- Restrict the Data types of every attribute.  
- Example: We want to specify that the enrolment should happen for candidate birth year `< 2002`.

#### b. **Entity Constraints**
- Every relation should have PK.  
- `PK != NULL`.

#### c. **Referential Constraints**
- Specified between two relations & helps maintain consistency among tuples of two relations.  
- It requires that the value appearing in specified attributes of any tuple in referencing relation also appear in the specified attributes of at least one tuple in the referenced relation.  
- If FK in referencing table refers to PK of referenced table then every value of the FK in referencing table must be NULL or available in referenced table.  
- FK must have the matching PK for each value in the parent table or it must be NULL.

#### d. **Key Constraints**  
The six types of key constraints present in DBMS are:

1. **NOT NULL**: Restrict NULL values. Ensures every element has a value.  
2. **UNIQUE**: Ensures all values in a column are different.  
3. **DEFAULT**: Sets default value if no value is specified.  
4. **CHECK**: Maintains integrity of data before and after CRUD operations.  
5. **PRIMARY KEY**: Uniquely identifies each entity; must be unique and not null.  
6. **FOREIGN KEY**: Common attribute linking entities. Prevents actions breaking links between tables.


