---
created: 2025-03-24T13:53:45
status: 
source: 
updated: 2025-05-28T02:24
---
---

GitHub Link: https://github.com/utk-281/mongodb_1330


**Data**: Raw facts and figures 

**Information**: processed data which is meaningful

**Database**: collection of information in organised manner

**Database Management System**: a system through which we can perform crud operations on Database




Schema is called structure

````tabs
--- SQL
- structured querry language
- have defined schema/structure
- also called relational database
- stores data in table format ( rows and columns )
- it supports vertical scaling
	- in this if the server is down then the whole server will not work
- writing complex querries is easier
- ex: mySQL, oracle, postgreSQL
- in this relation between data is considered
- here data can be restored ( rolled back ) even after deleted

--- NoSQL
- not only structured querry language
- no schema by default
- non relational
- stores data in non table ( document format, key-value pair, graph, dynamic value )
- supports horizontal scaling
	- also called distributed network, means if one server goes down then the server will overall still work
- writing complex queries is easier
- ex: mongoDB, cassendra, couch, etc
- store large amount of data better
- can't restore or roll back data after deletion so we keep same data in different places sometimes


````



1. document based database
2. key-value pair based database
3. graph based database
4. wide/dynamic column database



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
- 


# Reference
`related link(if any)`

