---
status: newBorn
related-links: "[[MongoDB-MOC]]"
created: 2025-05-21T07:47
updated: 2025-06-11T15:35
---
---

- it is mongodb but with online hosted server
- so that we don't have to host it somewhere ourself
- atlas is build specifically to host mongodb database and works perfectly
	- behind the scene, it uses cloud services.
- **Cluster**: a machine with abc specifications that we take to host our database 
- network access: option is used to give access to database to anyone
	- in production, we only give access ip of server
- database access: option is used to give permissions and create user for accessing database
- we need 3 things to connect
	- user
	- password
	- and a uri/url connection string that contains both id and password and database address
	- ![[Pasted image 20250521080702.png||400]]
	- ![[Screenshot_2024-09-14_at_6.29.28_PM.webp||450]]
	- always remember to remove `/` from end of string 


