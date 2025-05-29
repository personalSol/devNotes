---
status: newBorn
related-links: 
created: 2025-05-29T14:17
updated: 2025-05-29T14:37
---
---


#### ✅ What is a Constructor?

- A special method named `constructor()` inside a class.
- Automatically called when a new object is created using `new`.

```js
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
}
const p = new Person("Alice", 30);
```

---

#### ✅ Setting Properties

- No need to pre-declare class properties like in Java or C++.
	- like in java/cpp we used to first clear class level variables and then use `this.` to assign values using constructor
- Just assign with `this.property = value` inside the constructor.
	- this **define and assign** those properties on the fly
	- no need to declare the variable separately

```js
class Car {
  constructor(brand, year) {
    this.brand = brand;
    this.year = year;
  }
}
```

