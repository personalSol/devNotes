---
created: 2025-04-03T12:15:07
status: 
source: 
updated: 2025-04-05T12:45
---
---

everything we store in mongodb is inside documents and documents are inside collections which are inside databases
- almost all the complex querries in mongoDB starts with $

### **Commands:**

**around database: **
- `db.dropDatabase()`: deletes the database we are in ( means deletes the current database )
- `exit`: exits you out of terminal
- `db`: to check our current database

**to insert data:**
- `db.users.insertOne({<object type data here>})`: use to insert single data/document
- `db.users.insertMany([<multiple objects here>])`: to add multiple documents/ data in database

**to find and filter data: **
- `db.users.find(<object with similar value to what we are searching>)`: gives us all data of current database. ex: `db.users.find({age: 25})`
	- we can add different things after `.find()`:
		- `.limit(<number>)`: only gives that much number of data from database
		- `.sort(<this takes an object with multiple values>)`: it takes `key: 1/-1` 
			-  `-1` means decending order  
			- `1` means ascending order
		- `skip(<number>)`: skips the number of docs given as argument white getting data
	- ex: `db.useers.find().sort({age: 1, name: -1}).limit(2)`: in this example this commands first gets name in decending from last and then put them in age ascending order. Also it gives only 2 documents

basically `.users({<condition>, {<filter>}})` :
- first argument object is the object we find similar data to
- second object is for filtering where 1 means give me this and 0 means don't give me this
- ex: `db.users.find({age: 50}, {address: 0})`: in this we have only set address as 0 so it will give us everthing except address.
- ex2: `db.users.find({age: 50}, {name: 1, age: 1})`: here we have only said yes to name and age so it will only give us name and age
- we can also create a complex query by using object inside condition object
	- like this: `db.users.find( age: { $gt: 19 })`

Complex querie values:

- `$gt`: greater than
- `$gte`: greater than + equal
- `$lt`: less than
- `$lte`: less than + equal
- `$eq`: equal to
- `$ne`: not equal
- `$in`: if that thing is in. Basically for multiple equal values. here we pass `array[]`
- `$nin`: not in
- `$exists`: as key with true or false. return the document with that type of data exists.like if we want only that data which have certain keys like age. false for doesn't exist.
	- true also returns null as it only check if that key exists or not

```js
db.users.find({name: { $in: [Sanskar, Anuj]}})
db.users.find({name: { $nin: [Sanskar, Anuj]}})
db.users.find({age: {$exists: true}})
```

**and/ or and not complex queries**:

- `db.users.find({ age: {$lte: 20, $gte: 40}})`: only returns the data where age is less than or equal to 20 and more than equal to 40. 
- `db.users.find({ age: {$lte: 20, $gte: 40}, name: 'Sally'})`
- `$and`
- `$or`: there is no other way to do or. 
- `$not`: negates everything that's inside it. Just like `!` in many programming languages
	- also return all queries that doesn't have that key

```js
db.users.find({$and: [{age: 26}, {name: Kaylee}]})// here it will check for both
db.users.find({$or: [{age: {lte: 20}}, {name: "Sanskar"}]})
db.users.find({age: { $not: {$gte: 20 }}}) // will give us all greater than and equal to 20 ++ all documents which doesn't have age

```


**Count documents based on query**:

```sh
db.<collection_name>.countDocuments({age: {$lte: 40}})
```


#### update commands

```sh
db.<database_name>.updateOne({age: 19}, {$set: {age: 20}}) // finds the data with age 19 and update it to 20

db.<database_name>.updateOne({age: 19}, {$inc: {age: 28}}) //inceases the age by 28

// to rename a key ( this renames key from name to firstName )
db.<database_name>.updateOne({_id: abc}, ($rename: {name: "firstName"}))

// to remove a key(property)
// here we can pass anytthing in age and it doesn't matter'
db.<collection_name>.updateOne({_id: abc}, {$unset: {age: ""}})
```


# Reference
`related link(if any)`

