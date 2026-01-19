---
status: newBorn
related-links:
created: 1970-01-01T05:30
updated: 2026-01-15T21:17
---
---

> in next js which is used in insta when we open a profile then what we get initally is just a html page with images. The js at that time is not awake. And only after few seconds when the browser downloads the react js file of it then it activates. before it is just a html page with no functionality. 
> 
> it is like a wax statue coming alive but the only difference it that it comes alive so fast you would realize that it was a wax statue.


- **Problem:** React apps are "empty" HTML until the huge JavaScript file downloads. This is bad for SEO and slow for users.
    
- **The Journey:**
    1. **SSR (Server-Side Rendering):** The server generates the HTML with your photos already inside. You see the page instantly.
    2. **The "Wax Statue":** This HTML is non-interactive. You can see the "Like" button, but it doesn't work yet.
    3. **Hydration:** The React JS file arrives. React scans the existing HTML and "attaches" its brain (event listeners) to the existing buttons.
    4. **The Awakening:** The page is now "Alive." It can now handle things like Infinite Scroll without needing a full page refresh.

