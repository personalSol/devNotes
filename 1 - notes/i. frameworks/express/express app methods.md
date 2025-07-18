---
status: newBorn
related-links: 
created: 2025-05-29T11:29
updated: 2025-07-18T22:32
---
---


- app.on() 
	- Used to **listen for events** on an `EventEmitter` (like an Express app or HTTP server).
	- Syntax: `app.on('eventName', callback)`
	- the below one catches error and return them
	- the below one is an error event to catch if database is connected but for some reason the server can't work with database
	![[general code copy block note#app on method]]
- 

|Method|Category|Description|
|---|---|---|
|`.get()`|HTTP Routing|Handles GET requests|
|`.post()`|HTTP Routing|Handles POST requests|
|`.use()`|Middleware registration|Applies middleware|
|`.on()`|Event listener (from EventEmitter)|Listens to events|
|`.listen()`|App lifecycle|Starts the server|
|`.set()`|Configuration|Sets app-level settings|



