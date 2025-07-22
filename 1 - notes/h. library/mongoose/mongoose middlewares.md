---
status: newBorn
related-links: 
created: 2025-05-29T20:42
updated: 2025-07-21T22:36
---
---

mongoose hooks or middlewares ( can change interchangably )

types: [Mongoose v8.15.1: Middleware](https://mongoosejs.com/docs/middleware.html#types-of-middleware)

> literally just basically middlewares that allows us to do things before a certain thing happens.
> we can even use next in this. though it does not have req, res


- plugin
	- allows us to add plugins to things or only schema ( not sure )
	- like this: `videoSchema.plugin(mongooseAggregatePaginate)`



#### **middleware functions**

There are **only two core middleware functions** in Mongoose:

|Function|Purpose|
|---|---|
|`.pre()`|Run logic **before** a certain hook|
|`.post()`|Run logic **after** a certain hook|

- Schema.pre
```js
userSchema.pre("save", async function (next){
    if(!this.isModified("password")) return next();
    this.password = await bcrypt.hash(this.password, 10);
    next();
})
```