---
status: newBorn
related-links: 
created: 1970-01-01T05:30
updated: 2025-08-19T14:10
---
---

- frontend goes in vercel
- backend goes in render
- proior preparations: 
	- know the folder of backend and just add it's name on option
	- also know the project start command
		- can add `node ./src/main.js` in package.json script for start
		- and add `npm start` in render start command option
- now after getting backend url, you have to change it in frontend
	![[Pasted image 20250819134250.png]]
- like above you must have a centralised place for the url to be used in frontend to send request to backend.
- also in backend you will have to change cors according to url frontend url which you will get after deploying vite

### error that i need to not do
- in cors, just give the url: `https://task-manger-backend-3l7m.onrender.com` don't add a trailing slash in end because that will make root default and only route allowed

