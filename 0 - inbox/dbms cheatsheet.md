---
status: newBorn
related-links: 
created: 2025-06-11T12:33
updated: 2025-06-11T12:33
---
---

- **Data**: Raw facts and figures 
- **Information**: processed data which is meaningful
- **Database**: collection of information in organised manner
- **Database Management System**: a system through which we can perform crud operations on Database
- Schema: is the design of database which tells us the flow and way the data will be stored.
	- gives us structure of database

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

### types of no sql database


1. document based database
2. key-value pair based database
3. graph based database
4. wide/dynamic column database

