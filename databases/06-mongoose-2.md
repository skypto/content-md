Mongoose 2: many-to-many relationships
===
### Types of relationships

A type of relationship where two entities are solely linked to each other, e.g a country has only one capital city, and a capital city is the capital of only one country, is called a **one-to-one relationship**. An element of A may only be linked to one element of B, and vice versa.

If an element of A can only be linked to one element of B, but B can be linked to many elements of A, this is called **one-to-many relationships**. For example, a child has only one biological mother, but the mother can have multiple children.

Finally, when elements of both A and B can be linked to multiple elements of each other, we call this a **many-to-many relationship**. For example, an author can write many books, and a book can have multiple authors.

.populate method
----

Population is the process of automatically replacing the specified paths in the document with document(s) from other collection(s). We may populate a single document, multiple documents, plain object, multiple plain objects, or all objects returned from a query. Let's look at some examples.

```javascript
var mongoose = require('mongoose');
var Schema = mongoose.Schema;

var personSchema = Schema({
  _id: Schema.Types.ObjectId,
  name: String,
  age: Number,
  stories: [{ type: Schema.Types.ObjectId, ref: 'Story' }]
});

var storySchema = Schema({
  author: { type: Schema.Types.ObjectId, ref: 'Person' },
  title: String,
  fans: [{ type: Schema.Types.ObjectId, ref: 'Person' }]
});

var Story = mongoose.model('Story', storySchema);
var Person = mongoose.model('Person', personSchema);
```

So far we've created two **Models**. Our _Person_ model has its stories field set to an array of ObjectIds. The ref option is what tells Mongoose which model to use during population, in our case the _Story_ model. All \_ids we store here must be document \_ids from the _Story_ model.

### Saving refs

Saving refs to other documents works the same way you normally save properties, just assign the _id value:

```javascript
var author = new Person({
  _id: new mongoose.Types.ObjectId(),
  name: 'Ian Fleming',
  age: 50
});

author.save(function (err) {
  if (err) return handleError(err);
  
  var story1 = new Story({
    title: 'Casino Royale',
    author: author._id    // assign the _id from the person
  });
  
  story1.save(function (err) {
    if (err) return handleError(err);
    // thats it!
  });
});
```

### Population

So far we haven't done anything much different. We've merely created a Person and a Story. Now let's take a look at populating our story's author using the query builder:

```javascript
Story.
  findOne({ title: 'Casino Royale' }).
  populate('author').
  exec(function (err, story) {
    if (err) return handleError(err);
    console.log('The author is %s', story.creator.name);
    // prints "The author is Ian Fleming"
  });
```

Populated paths are no longer set to their original _id , their value is replaced with the mongoose document returned from the database by performing a separate query before returning the results.

Project
---

[Link](https://github.com/jankeLearning/projects/tree/master/06-RESTFUL-app) to project.