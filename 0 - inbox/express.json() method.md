---
status: newBorn
related-links:
  - "[[build-in middleware]]"
created: 2025-05-28T19:48
updated: 2025-05-28T20:07
---
---

for more info go: [[express.json() and express.urlencoded()]]

- Parses incoming requests with `Content-Type: application/json`
- Converts JSON payload into a JavaScript object stored in `req.body`
- Requires middleware to populate `req.body` (otherwise `req.body` is `undefined`)
- `limit` option: sets max JSON payload size (e.g., `'100kb'`) — protects against large payloads and DoS attacks ^pcxzos
- Default `type` is `'application/json'`; usually no need to change
- Throws HTTP 413 error if payload exceeds limit

```js
express.json({
  limit: '1mb',         // Max size of JSON body
  strict: true,         // Only parses objects/arrays, not primitives (default: true)
  inflate: true,        // Allow gzip/deflate (default: true)
  type: 'application/json'  // Which content-types to parse
})
```


|Option|Purpose|
|---|---|
|`limit`|Max size of JSON payload (e.g., `'100kb'`, `'1mb'`)|
|`strict`|Only allow arrays or objects (reject strings, numbers)|
|`inflate`|Accept gzip/deflate compressed bodies|
|`type`|Match requests based on `Content-Type` header|

