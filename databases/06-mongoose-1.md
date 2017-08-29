Mongoose
===
Mongoose provides a straight-forward, schema-based solution to model your application data. It includes built-in type casting, validation, query building, business logic hooks and more, out of the box.

In simple words, Mongoose acts as an intermediate between mongodb and server side language(like NodeJs). 

### Installing Mongoose

Mongoose is a NPM-package, so you just need to npm install it in your project and require it.

`npm install --save mongoose`

```javascript
var mongoose = require(mongoose);
```

### Connecting to MongDB

```javascript
mongoose.connect('mongodb://localhost/db_name', {
  useMongoClient: true
})
```

Mongoose has a "connect" method that takes the path to the mongoDb instance as the first argument. Here you link to an existing database. If the database doesn't exist yet, if will be dynamically created by mongoose.

> The second parameter gets rid of an annoying warning message everything you start your application.

When using mLab you'll also have to enter a username and password. You should find the link in your database profile in your account.

```javascript
mongoose.connect('mongodb://<dbuser>:<dbpassword>@ds119533.mlab.com:19533/db_name', {
    useMongoClient: true
})
```

Simple Crud
---

### Creating a Schema

The database schema of a database system is its structure described in a formal language supported by the database management system (DBMS). The term "schema" refers to the organization of data as a blueprint of how the database is constructed (divided into database tables in the case of relational databases). The formal definition of a database schema is a set of formulas (sentences) called integrity constraints imposed on a database. These integrity constraints ensure compatibility between parts of the schema.

A simple schema example:

```javascript
var mongoose = require("mongoose");
var Schema = mongoose.Schema;

var UserSchema = Schema({
  first_name: {
    type: String,
    required: true
  },
  last_name: {
    type: String,
    required: true
  },
  age: {type: Number}
  username: {
    type: String,
    required: true,
    unique: true
  },
  password: {
    type: String,
    required: true
  }
})

var User = mongoose.model("User", UserSchema);
```
Above we've created a schema for storing user objects. We define 4 properties (first\_name, last\_name, username and password ) and add some integrity constraints (datatype, required, unique).

We then create a **model** based on the created schema.

> It's important to note that it's not necessary to define an ID property. Mongoose/MongoDb automatically creates an unique ID.

### Storing a document

The model can then be used to store **documents** based on the defined schema. Let's say we retrieve a user object through a form input:

```javascript
var userObj = {
  first_name: "Rien",
  last_name: "Cosyns",
  age: 29,
  username: "riebow",
  password: "G##@83r4r4f5!@$T^" 
}

User.save(userObj, (err, record) => {
  if (err){
    console.log(err);
  } else {
    console.log(record);
  }
})
``` 

We can use the .save method to store the user object in the database.

### Finding a document

```javascript
var username = {username: "riebow"};
User.findOne(username, (error, existingUser) => {
  if (error){
    console.log(error);
  } else if (!existingUser){
    console.log("No such user");
  } else {
    console.log("User found: " + existingUser);
  } 
})
```

You can find exactly one document with .findOne method. If you want to retrieve multiple documents, you can use the .find method. Probably the best way to find a specific entry is to use the .findById method. which retrieves the document based on the ID.

### Updating a document

```javascript
var username = {username: "riebow"};
var query = {age: 30};

User.findOneAndUpdate(username, query, (error, updatedUser) => {
  if (error) return false;
  return updatedUser
})
```

### Deleting a document

```javascript
var username = {username: "riebow"}
User.findOneAndDelete(username, (err) => {
  if (err) return false;
  console.log("User deleted"); 
})
```

[Super basic Mongoose app](https://github.com/jankeLearning/content-code/tree/master/Week%2006/super-basic-mongoose-app)
  
External resources
----
+ Mongoose playlist: https://www.youtube.com/playlist?list=PLGquJ_T_JBMQ1C0Pp41sykceli8G1UGtg