---
status: newBorn
related-links: 
created: 2025-07-30T15:35
updated: 2025-07-30T17:09
---
---

### 🧾 Summary Table

|Feature|`Link`|`Navigate`|`useNavigate`|
|---|---|---|---|
|Type|Component|Component|Hook|
|Style|Declarative (JSX)|Declarative (JSX)|Imperative (logic-driven)|
|Triggers|On click|On render|On function call|
|Use Case|Navigation link|Conditional redirect|Event/logic-based redirect|
|Common In|Navbars, menus|Protected routes|Handlers, `useEffect`|

---

### 🔗 `Link`

- **What it is**: A component used for navigation via clicking.
    
- **Usage**:
    
    ```jsx
    <Link to="/about">Go to About</Link>
    ```
    
- **When to use**: For user-initiated route changes like in navbars, menus, etc.
    
- **Note**: It doesn't perform automatic redirects.
    

---

### 🔁 `Navigate`

- **What it is**: A component that causes an automatic redirect when rendered.
    
- **Usage**:
    
    ```jsx
    return <Navigate to="/login" />;
    ```
    
- **When to use**: For conditional redirects during render, such as protected routes or post-logout.
    
- **Note**: Not usable inside event handlers or logic blocks.
    

---

### 🧠 `useNavigate`

- **What it is**: A hook that returns a `navigate()` function for programmatic navigation.
    
- **Usage**:
    
    ```jsx
    const navigate = useNavigate();
    navigate("/dashboard");
    ```
    
- **When to use**: To redirect inside event handlers, async functions, or `useEffect`.
    
- **Note**: Must be used inside React components or hooks, not directly in JSX.