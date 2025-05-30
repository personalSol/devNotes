---
status: newBorn
related-links:
  - "[[Basic-Concepts-MOC]]"
created: 2025-03-03T19:32
updated: 2025-05-18T15:25
---
---


In simple terms: library is like a like cool dude types which gives you more freedom
framework is like military which has rules set in stone. 



**Library** 
- It’s a collection of tools and functions which we want to use again and again.
- In code we call the library
- Ex: jQuery, etc

**Framework**
- Collection of library is a framework ( standard definition )
- In framework, framework calls the code which then calls the library.
- has a set of rules to properly use it
- Ex: Django, node js, etc.

| Feature           | Library                         | Framework                      |
|-------------------|----------------------------------|--------------------------------|
| Control           | You call it                     | It calls you                  |
| Flexibility       | You control structure            | It gives you structure        |
| Examples          | Mongoose, Axios, Lodash          | Express, React, Angular       |

#### 🧠 Trick to Remember
> **"I call the library, the framework calls me."**


### example

 **Mongoose (Library)**
```js
// You control when this runs
const user = new User({ name: "Alice" });
await user.save();
```

**Express (Framework)**
```js
// Express controls when this runs
app.post('/users', (req, res) => {
  // handler called by Express
});
```



# Reference
`related tags + notes + source + link(if any)`
 

- 