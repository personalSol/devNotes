---
status: newBorn
related-links: 
created: 2025-06-05T18:18
updated: 2025-06-05T18:39
---
---

#### **Q1. How do we send JSON data in Postman (like for a login form)?**

- **Method**: `POST`
- **Tab**: `Body > raw > JSON`
- **Steps**:
    1. Select `POST` method.
    2. Go to **Body** tab.
    3. Choose **raw**.
    4. Select `JSON` from the dropdown.
    5. Example:
```js
{
  "email": "test@example.com",
  "password": "123456"
}
```

#### **Q2. How to send `x-www-form-urlencoded` data (like HTML form submission)?**

- **Method**: `POST`
- **Tab**: `Body > x-www-form-urlencoded`
- **Steps**:
    1. Choose `POST` method.
    2. Go to **Body** tab.
    3. Select `x-www-form-urlencoded`.
    4. Add key-value pairs:
        - `email: test@example.com`
        - `password: 123456`

---

#### **Q3. How to send multipart/form-data (for file uploads using Multer)?**

- **Method**: `POST`
- **Tab**: `Body > form-data`
- **Steps**:
    1. Select `POST` method.
    2. Go to **Body** tab.
    3. Choose `form-data`.
    4. Add key-value pairs:
        - For text: set type as **Text** (default).
        - For file: set type as **File** and select a file to upload.
        - Key should match `upload.single("avatar")` or the multer field.

---

#### **Q4. How to send query params (for GET requests)?**

- **Method**: `GET`
- **Tab**: `Params`
- **Steps**:
    1. Select `GET` method.
    2. Go to **Params** tab.
    3. Add key-value query pairs.
        - Example: `search=hello`, `limit=5`
        - URL becomes: `example.com?search=hello&limit=5`

---

#### **Q5. How to send custom headers (like `Authorization`)?**

- **Tab**: `Headers`
- **Steps**:
    1. Go to **Headers** tab.
    2. Add keys like:
        - `Authorization: Bearer <token>`
        - `Content-Type: application/json` (if not set automatically)

---

#### **Q6. How to test routes with PATCH, PUT, or DELETE methods?**

- Simply select the desired method (PATCH/PUT/DELETE).
- Use **Body** tab like in `POST` if request requires a body.

---

#### 💡 Common Mistake

- Don’t send JSON when uploading files with Multer.[]()
- Use `multipart/form-data` for file upload or Multer will not receive the file.
