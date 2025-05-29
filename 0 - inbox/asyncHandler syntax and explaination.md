---
status: newBorn
related-links:
  - "[[utility function asyncHandler]]"
  - "[[Express-MOC]]"
created: 2025-05-29T11:55
updated: 2025-05-29T11:55
---
---

there are two ways to write this

**first with async**

- it's a higher order function which is taking a function as a parameter and returning a function
	- we are not using {} so that we don't have to explicitly write return
- the `fn` function is a route handler which will have `req, res, next` from the request and if we don't give that as a parameter to return function then we wouldnt be able to access these inside return function
- we are not directly writing `async fn(req, res, next)` because we use try catch to handle errors as well

```js
const asyncHandler = (fn) => async (req, res, next) => {
    try {
        await fn(req, res, next)
    } catch (err) {
        res.status(err.code || 500).json({
            success: false,
            message: err.message
        })
    }
}
```

this function is shorthand of 
```js
const asyncHandler = (fn) => {
    return async (req, res, next) => {
        try {
            await fn(req, res, next);
        } catch (error) {
            res.status(error.code || 500).json({
                success: false,
                message: error.message
            });
        }
    };
};
```



**second with promise**

- this one is easy
- we are again writing a higher order function
- this function directly runs the requestHandler function which is a routerHandler and if we get any error then it catches that error and pass it to next middleware.

```js
const asyncHandler = (requestHandler) => {
    return (req, res, next) => {
        Promise.resolve(requestHandler(req, res, next)).catch((err) => next(err))
    }
}
```