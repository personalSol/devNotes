---
created: 2025-06-27T12:31:43
status: 
source: 
updated: 2025-06-27T12:31
---
---

### 🟦 Lecture 4: Extended ER Features

#### 1. Basic ER Features
- Studied in the LEC-3, can be used to model most DB features.
- But when complexity increases, it is better to use some Extended ER features to model the DB Schema.

---

#### 2. Specialisation
- In ER model, we may require to subgroup an entity set into other entity sets that are distinct in some way with other entity sets.
- Specialisation is splitting up the entity set into further sub entity sets on the basis of their functionalities, specialities and features.
- It is a **Top-Down approach**.
- Example:
  - `Person` entity set can be divided into `Customer`, `Student`, `Employee`.
  - `Person` is superclass and other specialised entity sets are subclasses.
  - We have **“is-a”** relationship between superclass and subclass.
  - Depicted by **triangle** component.

**Why Specialisation?**
1. Certain attributes may only be applicable to a few entities of the parent entity set.
2. DB designer can show the distinctive features of the sub entities.
3. To group such entities we apply Specialisation, to overall refine the DB blueprint.

---

#### 3. Generalisation
- It is just a **reverse of Specialisation**.
- DB Designer may encounter certain properties of two entities are overlapping. Designer may consider to make a new generalised entity set.
- That generalised entity set will be a **super class**.
- “**is-a**” relationship is present between subclass and super class.
- Example:
  - `Car`, `Jeep`, `Bus` all have some common attributes.
  - To avoid data repetition for the common attributes, DB designer may generalise them to a new entity set `Vehicle`.
- It is a **Bottom-up approach**.

**Why Generalisation?**
1. Makes DB more refined and simpler.
2. Common attributes are not repeated.

---

#### 4. Attribute Inheritance
- Both Specialisation and Generalisation have attribute inheritance.
- The attributes of higher level entity sets are inherited by lower level entity sets.
- Example: `Customer` & `Employee` inherit the attributes of `Person`.

---

#### 5. Participation Inheritance
- If a **parent entity set** participates in a relationship, then its **child entity sets** will also participate in that relationship.

---

#### 6. Aggregation
- How to show **relationships among relationships**? → **Aggregation** is the technique.
- Abstraction is applied to treat relationships as higher-level entities. We can call it **Abstract entity**.
- Avoid redundancy by aggregating relationship as an entity set itself.

