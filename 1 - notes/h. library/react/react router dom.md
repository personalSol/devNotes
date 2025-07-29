---
status: newBorn
related-links: 
created: 2025-06-15T16:31
updated: 2025-07-29T19:20
---
---
## ✅ What is React Router DOM?

- A library for client-side routing in React applications.
- Enables navigation between components without page reloads.
- Suitable for Single Page Applications (SPAs).

---

## 🚀 Installation

```bash
npm install react-router-dom
```

---

## 🛠️ Core Components

### 1. **BrowserRouter**

- Wraps the entire app to enable routing in app.js

```jsx
// main.js
import { BrowserRouter } from 'react-router-dom';

<BrowserRouter>
  <App />
</BrowserRouter>
```

### 2. **Routes**

- Container for all the routes.

```jsx
// main.js
import { Routes, Route } from 'react-router-dom';

<Routes>
  <Route path="/" element={<Home />} />
  <Route path="/about" element={<About />} />
</Routes>
```

### 3. **Route**

- Maps a URL path to a specific component.

```jsx
<Route path="/contact" element={<Contact />} />
```

### 4. **Link**

- Navigation without page reload.

```jsx
import { Link } from 'react-router-dom';

<Link to="/about">Go to About</Link>
```

### 5. **useNavigate()**

- Hook to navigate programmatically.

```jsx
import { useNavigate } from 'react-router-dom';

const navigate = useNavigate();
navigate('/home');
```

### 6. **useParams()**

- Hook to access URL parameters.

```jsx
<Route path="/user/:id" element={<User />} />

const { id } = useParams();
```

### 7. **useLocation()**

- Hook to get the current location object.

```jsx
import { useLocation } from 'react-router-dom';

const location = useLocation();
console.log(location.pathname);
```

### 8. **Navigate**

- Redirects to another route.

```jsx
import { Navigate } from 'react-router-dom';

<Navigate to="/login" />
```

---

## 🛡️ Protected Routes Example

```jsx
const PrivateRoute = ({ isAuthenticated, children }) => {
  return isAuthenticated ? children : <Navigate to="/login" />;
};

<Route path="/dashboard" element={
  <PrivateRoute isAuthenticated={userLoggedIn}>
    <Dashboard />
  </PrivateRoute>
} />
```

---

## 📌 Key Points

- `BrowserRouter` is for simple SPAs.
- `Route` uses `element` (not `component`) in v6+.
- `Switch` is replaced by `Routes` in v6+.
- Use `Link` instead of `<a>` to prevent reload.
- Hooks like `useNavigate`, `useParams`, and `useLocation` are essential for dynamic routing.


