---
status: newBorn
related-links: 
created: 2025-06-15T17:42
updated: 2025-06-15T17:57
---
---



---

### 📘 React Router DOM Notes (RouterProvider)



## ✅ What is RouterProvider?

- Introduced in **React Router v6.4+**.
- Works with `createBrowserRouter`.
- Supports advanced features like **data loading, actions, and error boundaries**.

---

## 🚀 Installation

```bash
npm install react-router-dom
```

---

## ⚙️ Basic Setup with RouterProvider

```jsx
import { createBrowserRouter, RouterProvider } from 'react-router-dom';

const router = createBrowserRouter([
  { path: '/', element: <Home /> },
  { path: '/about', element: <About /> }
]);

function App() {
  return <RouterProvider router={router} />;
}
```

---

## 🛠️ Key Features

### 1. **Loader** (Data Fetching)

```jsx
{
  path: '/',
  element: <Home />,
  loader: async () => {
    const response = await fetch('/api/data');
    return response.json();
  }
}
```

### 2. **useLoaderData()**

- Access the data loaded by the loader.

```jsx
import { useLoaderData } from 'react-router-dom';

const Home = () => {
  const data = useLoaderData();
  return <div>{JSON.stringify(data)}</div>;
};
```

### 3. **Actions**

- Handle form submissions.

```jsx
{
  path: '/submit',
  element: <SubmitForm />,
  action: async ({ request }) => {
    const formData = await request.formData();
    // Handle form submission
  }
}
```

### 4. **Error Boundary**

- Route-specific error handling.

```jsx
{
  path: '/',
  element: <Home />,
  errorElement: <ErrorPage />
}
```

---

## 📌 Key Points

- `RouterProvider` is **data-driven and more advanced**.
- Supports loaders, actions, and error boundaries natively.
- Offers **declarative and object-based routing.**
- Better for **medium to large apps** with complex data handling needs.

---

## ✅ Summary: BrowserRouter vs. RouterProvider

|Feature|BrowserRouter|RouterProvider|
|---|---|---|
|Routing|JSX-based|Object-based|
|Data Loading|Manual (useEffect)|Built-in loader support|
|Error Handling|Manual|Built-in errorElement|
|Use Case|Simple apps|Data-driven apps|

---

