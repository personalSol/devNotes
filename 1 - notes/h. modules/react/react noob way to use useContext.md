---
status: newBorn
related-links: 
created: 2025-06-17T14:36
updated: 2025-06-17T14:36
---
---

- we create two files
```js

// UserContext.js
import React from "react";

const UserContext = React.createContext()

export default UserContext

// UserContextProvider.jsx

import React from "react";
import UserContext from "./userContext";  

const UserContextProvider = ({children}) => {
    const [user, setUser] = React.useState(null);
    return (
        <UserContext.Provider value={{user, setUser}}>
            {children}
        </UserContext.Provider>
    )
}

export default UserContextProvider
```

- and then in every file we use our UserContext in
	- we have to import both UserContext and useContext to access the data/values



