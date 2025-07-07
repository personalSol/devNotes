---
status: newBorn
related-links: 
created: 2025-06-16T19:47
updated: 2025-06-16T19:47
---
---

### Explanation:

1. **Import `useNavigate`**:
    
    - `useNavigate` is a hook provided by `react-router-dom` to programmatically navigate to a different route.
2. **Initialize `useNavigate`**:
    
    - Call `useNavigate()` inside your component to get the `navigate` function.
3. **Redirect on Submit**:
    
    - Use `navigate("/desired-path")` to redirect the user to the specified route after the form submission.

### Example:

If you want to redirect to `/dashboard`, ensure that the route `/dashboard` is defined in your `react-router-dom` setup. For example:

```jsx
<Route path="/dashboard" element={<Dashboard />} />
```

This will navigate the user to the `/dashboard` route after clicking "Submit".



#### example

To redirect to another URL when the "Submit" button is clicked, you can use the `useNavigate` hook from `react-router-dom`. Here's how you can modify your [Login](vscode-file://vscode-app/d:/Program%20Files/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-sandbox/workbench/workbench.html) component:
```jsx
import {useState} from "react";
import UserContext from "../context/userContext";
import {useContext} from "react";
import {useNavigate} from "react-router-dom"; // Import useNavigate

function Login() {
    const {setUser} = useContext(UserContext);
    const [username, setUsername] = useState("");
    const [password, setPassword] = useState("");
    const navigate = useNavigate(); // Initialize useNavigate

    const submitHandler = (e) => {
        e.preventDefault();
        setUser({
            username,
            password,
        });
        navigate("/dashboard"); // Redirect to the desired URL
    };

    return (
        <>
            <div>
                <input
                    type="text"
                    value={username}
                    placeholder="username"
                    onChange={(e) => {
                        setUsername(e.target.value);
                    }}
                />
                <input
                    type="text"
                    value={password}
                    placeholder="password"
                    onChange={(e) => {
                        setPassword(e.target.value);
                    }}
                />
                <button onClick={submitHandler}>Submit</button>
            </div>
        </>
    );
}

export default Login;
```


