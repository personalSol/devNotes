---
status: newBorn
related-links: 
created: 2025-05-28T19:55
updated: 2025-05-28T20:07
---
---

- Parses requests with `Content-Type: application/x-www-form-urlencoded` (default HTML form submissions)
- Converts URL-encoded data like `name=Alice&age=30` into a JavaScript object in `req.body`
- `extended` option:
    - `false` — parses simple, flat objects (uses Node’s built-in `querystring`)
    - `true` — allows nested objects (uses `qs` library)
- `limit`:
	- limits the size of data we can get, same as with [[express.json() method#^pcxzos]]
- Used to handle traditional form data, not JSON

> in simple terms, when we give any data to url and basically make a post request. Sometimes it sets data with + and sometimes with %20 ( which is for space ) so it becomes difficult for express to understand the data. that's where urlencoded come and decode the data to return a JS object

for more info go: [[express.json() and express.urlencoded()]]