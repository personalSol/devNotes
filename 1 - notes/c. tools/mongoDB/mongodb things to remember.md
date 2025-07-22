---
status: newBorn
related-links: 
created: 2025-05-19T07:03
updated: 2025-07-22T20:02
---
---

⭐⭐"Remember that database is always in another continent"



- each mongodb document have a size limit of upto 16mb
- to store big files like images, pdfs, videos, etc it is prefered that we use a cloud service or server and not mongodb
- `mongodb_uri` should end with `clustersomething.something.mongodb.net` anything after that are basically filters ^zevslo
	- adding these filters would do any good but
	- will stop you from naming a database
	- so remove them
