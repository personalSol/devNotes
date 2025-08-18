---
status: newBorn
related-links: 
created: 2025-06-09T13:00
updated: 2025-06-09T15:40
---
---

- stands for **JavaScript Object Notation**.
- a lightweight, text-based format used for data interchange
-  a type of file
- very similar to a javascript object
- only difference is:
    - both side must have quotation marks `""` for normal names/strings

`usecase`
- While fetching data from API. we get the data in JSON fromat.

```json
{
  "name": "John Doe",
  "age": 30,
  "isEmployed": true,
  "address": {
    "street": "123 Main St",
    "city": "Anytown"
  },
  "phoneNumbers": ["123-456-7890", "987-654-3210"]
}
```


### json methods

-  [[json methods brief]]

| Function/Method     | Purpose                                        | Input                           | Output                                              |
| ------------------- | ---------------------------------------------- | ------------------------------- | --------------------------------------------------- |
| `JSON.stringify()`  | Convert JS object to JSON string               | JS object/value                 | JSON string                                         |
| `JSON.parse()`      | Convert JSON string to JS object               | JSON string                     | JS object/value                                     |
| `.json()` (Fetch)   | Parse HTTP response JSON asynchronously        | None (called on response)       | Promise resolving to JS object                      |
| `.json()` (Express) | Send JS object as JSON HTTP response           | JS object/value                 | Sends JSON response                                 |
| `express.json()`    | Middleware to parse incoming JSON request body | Raw JSON string in request body | converts into JS object and populates on `req.body` |



