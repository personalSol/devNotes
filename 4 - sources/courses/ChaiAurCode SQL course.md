---
created: 2025-04-09T17:01:15
status: 
source: 
updated: 2025-06-26T17:10
---
---

## basics

working around sql can be required for three types of roles:
- web dev
	- use it on basic level to create websites
- database admin
	- experienced people who design database
	- main from securely saving it to backup and other things
- data analyst
	- write complex sql queries to get particular data from database and do analysis and find trends/information from them
	- basically extraction any and all sort of knowledge from data
	- these information are then used by executives and helps them in making decision

SQL Terminologies + basics:

- datum : is a single data entity
- database: collection of data
- table: rows and column
- record: a single row
- relational database management system (rdbms). 
	- system where we manage database
	- ex: mysql, postgres, sqlite
- schema: the structure of database ( gets created before entering data). it includes what rows and columns will the database consist.
- all rdbms have a gui tool which can be used to interact with the database using gui.
	- just like we have compass and atlas for mongodb
	- for mysql we have mySQL workbench
	- for postgreS we have pgadmin
	- some softwares like `db browser` ( though it looks like it's only for sqlite ) can be used to interact with multiple types of rdbms
		- db browser is the industry standard
		- open source hence available for free
		- cons is that its very old looking and we have some better options with newer ui but they are paid
- there are some companies which can handle some part of database admin job like management and backup prt ( not the creation part tho ) 
- in any database, we have two paths
	- main installation path
	- data path where data will be saved





#### MySQL:
- is a rdbms, also termed as database but it's actually rdbms
- we can write sql querries on vs code but rdbms are preferred to be used
- mysql itself is a database and comes with it is mysql workbench with is an rdbms


## PostgreSQL

- comes with postgre is pgadmin which is a gui
	- **pgAdmin** is kind of like **MongoDB Compass**, but for **PostgreSQL**.
- stackbuilder is used to install addons which we might need while working with postgres
- it also has an SQL shell ( i am assuming it's like mongosh ) where we can can postgres querries directly
- in pg admin we see that postgres gives us 
	- a database by default named `postgres` which we shouldn't touch as ( asumming this part but it has things we we require to work with other databases)
	- login/signup thing which stores passwords and all for different users etc
	- tablespaces ( don't know it's use )


#### in a postgres database

- we have query tool where we can write query around that database inside pgadmin itself
- we have ERD ( entity relationship diagram) for database where we can see how different tables connect and data flows
	- there are some paid tools which shows these diagrams in better way
		- like moon modler for mongodb ( it's good and recommended by hitesh sir )
		- sql dbm for sql ( not sure if its good )
		- we also have 
	


#### extras:
---
- sqlite also gets used in production and in so many places we don't know including mobile apps. 
- mysql have a paid enterprise version
	- also have another division called mariadb which was a branch that came out of mysql and it's opensource
- in vs code we have an extension which gives us more functionality and that's the preferred way to work with databases.
	- it supports all the databases
	- we can write queries inside vs code directly using it
	- we can also create specific functions which I am assuming are just queries but frequently used ones which are imp as well
	- in any table for database if we want to do quickly something with data then we can use `Data` section in upper menu after selecting a table and work there




# Reference
`related link(if any)`

