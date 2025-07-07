---
status: newBorn
related-links: 
created: 2025-06-21T02:23
updated: 2025-06-21T02:23
---
---

- take provider from redux
- just like we use to give value in context in `useContext`, we give store here

```js
import {Provider} from "react-redux";
import {store} from "./app/store.js";

createRoot(document.getElementById("root")).render(
	<StrictMode>
		<Provider store={store}>
			<App />
		</Provider>
	</StrictMode>
);
```

