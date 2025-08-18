---
status: newBorn
related-links: 
created: 2025-05-29T11:12
updated: 2025-05-29T12:39
---
---

> [!summary]- `res.send()`
> 
> - Used at the **very end** to send data.  
> - Automatically calls `res.end()`, so **you can't send another response after this**.  
> - Sends **raw content as-is**.  
> - ⚠️ Not used for rendering templates like EJS.

---

> [!summary]- `res.status()`
> 
> - Sets the **HTTP status code** before sending a response.  
> - Common use:  
>   ```js
>   res.status(404).send("Not Found");
>   ```

---

> [!summary]- `res.sendFile()`
> 
> - Sends a **file** as the response.  
> - Example:  
>   ```js
>   res.sendFile(path.join(__dirname, 'file.html'));
>   ```

---

> [!summary]- `res.render()`
> 
> `res.render()` on the other hand:
> 
> 1. Takes your EJS file  
> 2. Processes EJS tags (`<%= %>`, `<%- %>`, etc.)  
> 3. Replaces variables with actual values  
> 4. Converts it to plain HTML  
> 5. Sends the HTML to the browser  
> 
> **Used to render template files** (like `.ejs`, `.pug`) with **dynamic data**  
> **Always looks for registered view engine**
> 
> ```js
> app.set('view engine', 'ejs');
> app.set('views', 'view'); // Optional if folder is named 'views'
> ```
> 
> **Particularly useful when you:**
> - Need rendered HTML as a string (e.g., for emails)  
> - Want to render views outside a route handler  
> - Need to render multiple views before sending a response  
> 
> **Arguments:**
> - **First argument**: Template name (no extension)  
> - **Second**: Object with dynamic values  
> - **Third**: Callback for error or rendered HTML  
> 
> ```js
> app.render('email', (err, html) => {
>   // handle html or error
> });
> 
> app.render('email', { name: 'Tobi' }, (err, html) => {
>   // handle html or error
> });
> ```

---

> [!Summary]- `res.json()`
> - used to send json response to server
> - docs: [Express 5.x - API Reference](https://expressjs.com/en/5x/api.html#res.json)
> ```js
> res.json({
            success: false,
            message: err.message
        })
>```

