---
created: 2025-05-17T16:26
updated: 2025-05-17T16:27
status: newBorn
related-links:
  - "[[Node-JS-MOC]]"
---
---



### 🧩 What is a Proxy?

A **proxy** is a middle layer that forwards requests from one place (like a frontend app) to another server (like a backend API).

---

### ✅ Why Use a Proxy?

- **Bypass CORS** in development  
- **Hide backend URLs**  
- **Clean API calls** (use `/api/users` instead of full URL)  
- **Forward frontend requests** to the backend  

---

### 🚫 What is CORS? - [[cors]]

- **CORS (Cross-Origin Resource Sharing)** is a browser security feature.  
- It **blocks frontend requests** to different origins (even if it's just a different port).  
- Example: `localhost:5173` (frontend) to `localhost:3000` (backend) is considered **cross-origin**.

---

### 🛠️ How Proxy Solves CORS (Development)

### ⚙️ Setup Example (Vite):
```js
// vite.config.js
server: {
  proxy: {
    '/api': 'http://localhost:3000'
  }
}
```

#### 🧭 What Happens Step-by-Step:

1. **Frontend app** runs on `http://localhost:5173`  
2. **Backend server** runs on `http://localhost:3000`  
3. You call:
   ```js
   fetch('/api/users')
   ```
4. The browser sees this as a **same-origin** request to `5173`  
5. The **Vite dev server** intercepts `/api` requests  
6. It **proxies** (forwards) the request to `http://localhost:3000/api/users`  
7. The backend responds to `3000`  
8. Vite returns the response back to the frontend  
9. Browser never complains — ✅ no CORS issue

---

### 🔐 Is It Risky to Use a Proxy?

| Case            | Risk     | Explanation |
|-----------------|----------|-------------|
| **Development** | ❌ Low    | Local only, safe |
| **Production**  | ✅ Possible | If API is not secured (anyone can access if no auth) |

#### 🛡️ To Keep API Secure in Production:
- Use **authentication** (JWTs, sessions)  
- **Rate limit** requests  
- **Restrict public access** to sensitive routes  
- Only expose what's needed  

---

### 🧠 Final Summary

| Term           | Meaning                                      |
|----------------|----------------------------------------------|
| Proxy          | Forwards frontend requests to backend       |
| CORS           | Browser blocks cross-origin requests         |
| Proxy Use      | Trick browser into thinking it's same-origin |
| Who handles proxying | Dev server like Vite or Webpack (not browser) |
| Risk           | Safe in dev, secure properly in production   |
