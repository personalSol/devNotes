---
status: newBorn
related-links: 
created: 2025-07-22T20:59
updated: 2025-07-22T20:59
---
---

- so well when we fetch user ( mostly in `userAuth` middleware), the user we get already have `_id` with format `ObjectId(somethingsomething)`
- and if we have a model where we have given reference to another model object id
- and we feed user object id in thatat variable
- then it automatically removes `ObjectId()` from it and save it properly 

ex:
we have :
```js
// we have task model:
const taskSchema = new mongoose.Schema({
    userId: {
        type: mongoose.Schema.Types.ObjectId,
        ref: "User",
        required: true
    },
    taskStatus: {
        type: String,
        enum: ['not-started','planning', 'in-progress', 'done'],
        required: true,
    },
    title: {
        type: String,
        required: true
    },
    description: {
        type: String,
        default: null
    }
}, {timestamps: true});

// here we have userId which we will take from req.user._id
// this id will be in `new ObjectId(somethingsomething)` format
// and when we will do 

const task = await Task.insertOne({
        userId: req.user._id,
        title,
        description,
        taskStatus
    })

// mongoose will understand this is an id and will properly store it in task document
// not like taking as it is and saving it there
```

