---
created: 2025-05-12T19:20:16
status: 
source: 
updated: 2025-05-12T20:52
---
---

DSA:

- to find an element in array
	- if array is sorted then use binary
	- if unsorted then linear search

**LLD vs DSA**
- with a problem in hand like building a riding app, a DSA person will directly try to jump to the problems he/she can come up with. Ex: 
	- finding shortest distance between two points
	- arranging the nearest rider for user
- with same problem a person wiith knowledge of LLD will figure out it's entire architecture:
	- objects/entities
		- user
		- rider
		- location
		- notification
		- payment
	- relationship between entities
	- data security
		- making sure no important informations gets leaked like:
			- phone number of user and rider, , etc
	- making sure the application is sustainable for million of users
- after figuring out all this, now he/she will start with problems and build algorithms
	- benefits of doing this before jumping to algorithms:
		- better clarity of system andd entities involved
		- less prone to future changes because of unseen scenarios 
		- better security
		- scalable
		- etc


### LLD

LLD focuses on:
- scalibility
	- how the application perform on scale with million of users
	- how fast can we integrate scale a new feature
- maintainability
	- new code should be easily managable and should create problem for the old one
	- code should be easily debugable
- re-usability
	- works on plug and play model
	- not tightly coupled 

### what is not LLD

- **HLD** : high level design
	- focuses on:
		- tech stack ( Java or JS)
		- Database ( SQL or NoSQL )
		- server scale
		- cost optimization
- ![[Pasted image 20250512204932.png]]

### Conclusion

> if DSA is the brain of an application
> LLD is the skeleton

# Reference
`related link(if any)`

