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

### Simple CRUD

[Super basic Mongoose app](https://github.com/jankeLearning/content-code/tree/master/Week%2006/super-basic-mongoose-app)
  
External resources
----
+ Mongoose playlist: https://www.youtube.com/playlist?list=PLGquJ_T_JBMQ1C0Pp41sykceli8G1UGtg