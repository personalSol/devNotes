---
status: newBorn
related-links: 
created: 1970-01-01T05:30
updated: 2025-08-17T19:52
---
---

> allows us to check the path of component while using [[react-router-dom]]  and it can be used to conditionally render components or classes 

### used
- in my taskManager project I needed to render classes conditionally for dashboard which didin't need any but needed for signup and login as I wanted them to be in center and it needed parent div height and some things 
	- so I used useLocation to create conditional rendering and only give classes when it was not dashboard

```jsx
import { Outlet, useLocation } from "react-router-dom";
  const location = useLocation();
  const isDashboard = location.pathname === "/tasks";

<div
            className={
              isDashboard
                ? ""
                : "flex-1 overflow-auto flex items-center justify-center"
            }
          >
            <Outlet />
          </div>
```

