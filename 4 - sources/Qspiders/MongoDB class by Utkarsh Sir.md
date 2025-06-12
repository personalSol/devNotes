---
created: 2025-03-24T13:53:45
status: 
source: 
updated: 2025-06-12T14:50
---
---

GitHub Link: https://github.com/utk-281/mongodb_1330













### a. Document based database
- in noSQL database there is no need to define the schema/structure
- data is stored inside an object
- key value pair separated by comma


below is a document
```javascript
{
	name: "varun",
	age: 24,
	id: "123",
	email: "abc@gmail.com",
	gender: "male"
}
```


examples are: mongodb, couchdb, etc...

- it can be empty too
	it's possibl because we don;t have any schema by default
```javascript
{

}
```


### b. Key - Value pair

- stored in key value pair
- each pair is a separate entity
	- means they are independent of each other
- we use it for performance
- use reidis-caching

example: redisDB, amazon dynamoDB, etc...



### c. Graph based database





### d. Dynamic col/wide col/ col oriented

same as sql database but cols are dynamic in nature





## mongoDB
- we will learn 2 things
	- crud
	- aggregation


---

- document oriented database
- stores data in JSON/BSON like objects
- doesn't have structure by default
- open source
- cross-platform
- disctributed database


## hierarchy

- collection


#### Document
---

- id
	- unique
	- immutable
	- each document contains atleast one id





## Mongosh Commands:




> mongodb storage engine: it temperoarily stores the database until we create connection or inside data in database. it comes with compass ( told by sir )




In compass, write command `ctrl + r` to refresh the database


IMPPP notes::

> if we want to see all commands then we can write half command like db.c and press tab twice to see all related commands

Side notes:
- database and collection can have same name


# Reference
`related link(if any)`

