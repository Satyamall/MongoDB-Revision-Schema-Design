
Schema Design

# Create a schema design for Twitter
```js
// User Schema
const mongoose = require("mongoose");

const userSchema = new mongoose.Schema({
    firstname: { type: String, required: true},
    lastname: { type: String, required: true},
    middlename: { type: String},
    email: {type: String, required: true},
    profileImage:{type: String}, 
})

const Twitter = mongoose.modal("users", twitterSchema);
module.exports = Twitter;

// Twitter schema
const mongoose = require("mongoose");

const twitterSchema = new mongoose.Schema({
    text: {type: String, required: true},
    timeTweeted: {type: Date},
    links: [{type: String}],
    posts:[{type: String}],
    tags: [{type: String}],
    userDetails: {
        type: mongoose.Schema.Types.ObjectId,
        ref: "users",
        required: true
    }
})

const Twitter = mongoose.modal("twitter", twitterSchema);
module.exports = Twitter;

// comment Schema
const mongoose = require('mongoose');

const commentSchema = new mongoose.Schema(
    {
        body: String,
        userDetails:{
            type: mongoose.Schema.Types.ObjectId,
            ref: "users",
            required: true
        }
    },
    { timestamps: true}
);

const Comment = mongoose.model("comment", commentSchema);

module.exports = Comment;
```

# create diagrams to explain how the schema for database will look like
![eOAiN](https://user-images.githubusercontent.com/80479635/164514324-31e4ab72-d24b-43ae-9750-7d8c790d8b8e.png)


