---
created: 2025-06-27T12:46:05
status: 
source: 
updated: 2025-06-27T12:56
---
---

### 🟦 Lecture 8: Transform - ER Model to Relational Model

#### 1. Purpose
- Both **ER-Model** and **Relational Model** are abstract logical representations of real-world enterprises.
- Since the two models follow similar design principles, we can convert ER design into Relational design.

---

#### 2. Process
- Converting a DB representation from an ER diagram to a table format helps arrive at **Relational DB-design** from ER diagram.

---

#### 3. ER diagram notations to relations:

---

##### 🔷 Strong Entity
1. Becomes an individual table with entity name.
2. Attributes become columns of the relation.
3. Entity’s **Primary Key (PK)** is used as Relation’s PK.
4. **Foreign Keys (FKs)** are added to establish relationships with other relations.

---

##### 🔷 Weak Entity
1. A table is formed with all the attributes of the entity.
2. PK of corresponding Strong Entity is added as FK.
3. PK of the relation will be a **composite key**: `{FK + partial discriminator key}`.

---

##### 🔷 Single-Valued Attributes
- Represented as columns directly in the tables/relations.

---

##### 🔷 Composite Attributes
1. Each sub-attribute becomes a column in the relation.
2. The main composite attribute is ignored.
3. Example:
   - `Address = {street-name, house-no}`  
     ⇒ Columns added: `address-street-name`, `address-house-no`.

---

##### 🔷 Multi-Valued Attributes
1. A new table is created for each multi-valued attribute.
2. PK of the entity becomes a FK in the new table.
3. A column for the multi-valued attribute is also added.
4. PK of new table: `{FK + multi-valued attribute}`.
5. Example:
   - Entity: `Employee`, multivalued: `dependent-name`.
   - New Table: `dependent-name(emp-id, name)`
     - PK: `{emp-id, name}`
     - FK: `{emp-id}`

---

##### 🔷 Derived Attributes
- **Not** considered in the relational tables.

---

##### 🔷 Generalisation

**Method 1 (Standard):**
- Create a table for the higher-level entity set.
- For each lower-level entity set, create a table with:
  - Its own attributes
  - Plus PK of the higher-level entity
- Example (Banking System):
  - `account(account-number, balance)`
  - `savings-account(account-number, interest-rate, daily-withdrawal-limit)`
  - `current-account(account-number, overdraft-amount, per-transaction-charges)`

**Method 2 (Alternative — if disjoint & complete):**
- Do not create a table for the higher-level entity.
- Each lower-level table contains:
  - All its own attributes
  - Plus inherited attributes from the higher-level entity
- Example:
  - `savings-account(account-number, balance, interest-rate, daily-withdrawal-limit)`
  - `current-account(account-number, balance, overdraft-amount, per-transaction-charges)`

**Drawbacks of Method 2:**
1. Redundant storage of inherited attributes (e.g., balance).
2. Cannot represent accounts not belonging to any subclass.

---

##### 🔷 Aggregation
1. Create a table for the **aggregated relationship**.
2. Include:
   - PKs of participating entity sets.
   - PKs of any relationship being aggregated.
   - Any descriptive attribute on the relationship.


