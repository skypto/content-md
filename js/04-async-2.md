Async 2: Promises
===

A **Promise** is an object representing the eventual completion or failure of an asynchronous operation. A promise may be created using its constructor. However, most people are consumers of already-created promises returned from functions. This segment will therefore explore consumption of returned promises first.

Essentially, a promise is a returned object you attach callbacks to, instead of passing callbacks into a function.

### Syntax

We won't worry about the Promise constructor just now. If you're interested you can read more about it [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise "Promises").

What you need to know now is how to handle API's that return a Promise-object. We will talk about a couple examples of this later.

For now this is the syntax you need to worry about:

function(_arguments_).then(_onfulfill_).catch(_onreject_).

1. function returning a promise: this is a function that will return a Promise-object, i.e it will send a _request_ and receive a _response_ back which will have to be _fulfilled_ .
2. When the promise has been _fulfilled_ we write code in the _thenable_ what should happen next.
3. If the promise failed or has been _rejected_, we write code in the _catch_ statement for error handling.

Let's look back at our previous example to see the difference: 

```javascript
//with a callback
function getData(inputData, callback){
    db.push(inputData);
    callback(inputData);
};

getData(userData, printData);
```

Let's assume getData returns a Promise, to resolve it would look something like this:

```javascript
// instead of a callback we add a thenable
getData(userData)
  .then(function(result){
      return printData(result)
      })
  .catch(function(error){return error})

// or in ES6
getData(userData).then(result => printdata(result)).catch(error => error)  // much neater
```

<img src="https://www.google.be/imgres?imgurl=https://mdn.mozillademos.org/files/8633/promises.png&imgrefurl=https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise&h=297&w=801&tbnid=lU8YHMKZ5uaoLM:&tbnh=78&tbnw=211&usg=__eF1Bbb0o_NOekpMN7DEobYN0VBQ=&vet=10ahUKEwiF89n18N3VAhWNLlAKHa1jCrkQ9QEIKjAA..i&docid=-0TFsZsXOAec5M&sa=X&ved=0ahUKEwiF89n18N3VAhWNLlAKHa1jCrkQ9QEIKjAA">

### Promises vs Callbacks
Unlike old-style passed-in callbacks, a promise comes with some guarantees:

+ Callbacks will never be called before the completion of the current run of the JavaScript event loop.
+ Callbacks added with .then even after the success or failure of the asynchronous operation, will be called, as above.
+ Multiple callbacks may be added by calling .then several times, to be executed independently in insertion order.

But the most immediate benefit of promises is **chaining**.

### **Chaining**
A common need is to execute two or more asynchronous operations back to back, where each subsequent operation starts when the previous operation succeeds, with the result from the previous step. We accomplish this by creating a **promise chain**.

Imagine if the `then` statement would also return a promise:

```javascript
doSomething() // returns a promise
  .then(function(result){
      return doSomethingElse(result) // This also returns a promise, so we can chain another thenable
  })
  .then(function(newResult){
      return printNewResult(newResult)
  })
  .catch(function(failure){
      return failure
  })

// Much neater in ES6
doSomething()
  .then(result => doSomethingElse(result))
  .then(newResult => printNewResult(newResult))
  .catch(failure => failure)
```

### Fetch and Axios
The Fetch API is a built-in javascript interface for fetching resources (including across the network).

It has a relatively simple syntax and it uses Promises to handle results/callbacks.

The syntax looks like this: fetch(_URL_(required), _options_(optional)).then(_response_).catch(_error_).

So fetch sends a _request_ to an url to retrieve data from, and optionally some options, such as method (GET,POST,...). It will return a _response_ which can be handled in the `then` statement.

Let's make a request to an API. Introducing the Random People API!!

```javascript
fetch("https://randomuser.me/api/")
  .then(response => response.json()) // wil return JSON so let's parse that
  .then(data => console.log(data)) // let's examine what this returns

// I only want the name:

fetch("https://randomuser.me/api/")
  .then(response => response.json())
  .then(data => alert(data.results[0].name.first + " " + data.results[0].name.last))
```

Axios is a third-party Promise based HTTP client for the browser and node.js. Axios is NOT built-in, so that means we need to import that somehow (more about that in the NPM and module.export sections).

The same code in axios would look like this:

```javascript
axios.get("https://randomuser.me/api/")
.then(response => response.json())
.then(data => alert(data.results[0].name.first + " " + data.results[0].name.last))
```

Exercises
---

Need to create some exercises using API requests and promises

Project
---

Link to Project: https://github.com/jankeLearning/projects/tree/master/04-twitz

External Resources
---
+ From the people at Google: https://developers.google.com/web/fundamentals/getting-started/primers/promises
+ For dummies: https://scotch.io/tutorials/javascript-promises-for-dummies
+ Fetch API: https://developers.google.com/web/updates/2015/03/introduction-to-fetch
+ Axios: https://github.com/mzabriskie/axios
+ you get the gist: https://gist.github.com/domenic/3889970
+ [learning promises](https://colintoh.com/blog/staying-sane-with-asynchronous-programming-promises-and-generators)  
+ a sick [github of examples](https://github.com/vasanthk/async-javascript)  
+ [a library](https://caolan.github.io/async/) to help with async programming.  
+ https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Promise
+ https://scotch.io/tutorials/javascript-promises-for-dummies
+ http://www.telerik.com/blogs/what-is-the-point-of-promises