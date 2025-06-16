---
status: newBorn
related-links: 
created: 2025-06-15T17:59
updated: 2025-06-15T21:49
---
---

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

### 5. **Outlets (Nested Routes)** - Children

- Allows nested routing structure.
    

```jsx
import { Outlet } from 'react-router-dom';

function Layout() {
  return (
    <div>
      <Navbar />
      <Outlet /> {/* Render child routes here */}
    </div>
  );
}

const router = createBrowserRouter([
  {
    path: '/',
    element: <Layout />,
    children: [
      { path: '', element: <Home /> },
      { path: 'about', element: <About /> },
    ]
  }
]);
```

### 6. **Children**

- Define nested routes using the `children` property in the router configuration.
- Works in combination with `Outlet` to render child routes.

### 7. **createRoutesFromElements** - 

- Converts JSX-based route definitions to an object-based structure compatible with `RouterProvider`.
    

```
import { createBrowserRouter, RouterProvider, createRoutesFromElements, Route } from 'react-router-dom';

const router = createBrowserRouter(
  createRoutesFromElements(
    <Route path="/" element={<Layout />}>
      <Route index element={<Home />} />
      <Route path="about" element={<About />} />
    </Route>
  )
);

function App() {
  return <RouterProvider router={router} />;
}
```

---

## 📌 Key Points

- `RouterProvider` is **data-driven and more advanced**.
    
- Supports loaders, actions, error boundaries, and nested routes (Outlets) natively.
    
- Offers **declarative and object-based routing.**
    
- Better for **medium to large apps** with complex data handling needs.
    

---

## ✅ Summary: BrowserRouter vs. RouterProvider

|Feature|BrowserRouter|RouterProvider|
|---|---|---|
|Routing|JSX-based|Object-based|
|Data Loading|Manual (useEffect)|Built-in loader support|
|Error Handling|Manual|Built-in errorElement|
|Nested Routes|Supported|Supported with Outlet|
|Use Case|Simple apps|Data-driven apps|

---

