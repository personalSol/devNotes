---
status: newBorn
related-links: 
created: 2025-06-22T09:51
updated: 2025-06-22T09:51
---
---

### Declaring Environment Variables in React (Vite)

#### Vite Method (Frontend)

- **Create `.env` file** at project root.
    
- **Prefix required:** `VITE_`
    

#### Accessing Variables

- Vite: `import.meta.env.VITE_API_KEY`
    

#### Notes

- `dotenv.config()` does **not work** in React (browser environment).
    
- Variables **without proper prefix will not be exposed**.
    

#### Example (Vite)

```env
VITE_API_URL=https://api.example.com
```

```js
console.log(import.meta.env.VITE_API_URL);
```


### ✅ Quick Note:

- No need to install `dotenv`.
    
- No need to write `dotenv.config()`.
    
- Just create the `.env` file with `VITE_` prefix, and Vite will handle everything.