---
status: newBorn
related-links: 
created: 2025-06-01T18:10
updated: 2025-06-01T18:10
---
---

**how it happens**
- user logs in, we generat an ID for him which we map to him, user now uses that ID to stay logged in
- whenever this user makes a request, we will check the session id to verify who he is and give him the resources
- whenever the user logs out or refresh or close the tab the state gets errased.
	- also get's deleted from the server
	- idk how our server knows that the user did that, let's see


**what it is**
- maintains data or state( also data basically ) on server side
- also call it sessions
- we keep the data of session in the database itself
- used where we need to give short time access




**advantages**
- have better security
- can control sessions from backend (better control)
	- as we have access to session id in backend and we can remove it if we want to logout a person


**disadvantages:**
- sessions are gone as soon we close the tab reloads
- database intensive so yeah increases the cost
- somehow if there is an error in the server and server have to restart then it will log out all the users because it will wipe the session ID data ( idk how only the session id data will go on restart and why )
- can't work on serverless architecture directly as then we will have to buy additional database


