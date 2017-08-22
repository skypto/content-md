Async 1: Callbacks
====

JavaScript is asynchronous
---

### Synchronous Code
In _synchronous_ programs, if you have two lines of code (L1 followed by L2), then L2 cannot begin running until L1 has finished executing.

You can imagine this as if you are in a line of people waiting to buy train tickets. You can't begin to buy a train ticket until all the people in front of you have finished buying theirs. Similarly, the people behind you can't start buying their tickets until you have bought yours.

### Asynchronous Code
In _asynchronous_ programs, you can have two lines of code (L1 followed by L2), where L1 schedules some task to be run in the future, but L2 runs before that task completes.

You can imagine as if you are eating at a sit-down restaurant. Other people order their food. You can also order your food. You don't have to wait for them to receive their food and finish eating before you order. Similarly, other people don't have to wait for you to get your food and finish eating before they can order. Everybody will get their food as soon as it is finished cooking.

Note that asynchronous does not mean the same thing as _concurrent_ or _multi-threaded_. JavaScript can have asynchronous code, but it is generally **single-threaded**. This is like a restaurant with a single worker who does all of the waiting and cooking. But if this worker works quickly enough and can switch between tasks efficiently enough, then the restaurant seemingly has multiple workers.

Let's show this with an example:

```javascript
// Say Hello
console.log("Hello");
// Say Goodbye 2 seconds from now
setTimeout(function(){
    console.log("Goodbye")
}, 2000);
// Say Hello again
console.log("Hello");
```

How do you expect this code to be run? In which order will the three statements be executed? Run the code in the console to check if your thought were correct.

Because of its asynchronousity JS will not wait until the setTimeout function is finished before it moves on to the next line. Instead it will store the code momentarily away in a _callback queue_ and execute the next line.

Watch this great [video](http://latentflip.com/loupe/?code=JC5vbignYnV0dG9uJywgJ2NsaWNrJywgZnVuY3Rpb24gb25DbGljaygpIHsKICAgIHNldFRpbWVvdXQoZnVuY3Rpb24gdGltZXIoKSB7CiAgICAgICAgY29uc29sZS5sb2coJ1lvdSBjbGlja2VkIHRoZSBidXR0b24hJyk7ICAgIAogICAgfSwgMjAwMCk7Cn0pOwoKY29uc29sZS5sb2coIkhpISIpOwoKc2V0VGltZW91dChmdW5jdGlvbiB0aW1lb3V0KCkgewogICAgY29uc29sZS5sb2coIkNsaWNrIHRoZSBidXR0b24hIik7Cn0sIDUwMDApOwoKY29uc29sZS5sb2coIldlbGNvbWUgdG8gbG91cGUuIik7!!!PGJ1dHRvbj5DbGljayBtZSE8L2J1dHRvbj4%3D) to have a better understanding of how this works. It has also has a litte sandbox where you can test this out.

Understanding asynchronousity is the bread and butter of JS and web development. Often you will send requests to API's and you'll want to do something with the response. If you misunderstand JS, you will run into a whole lot of trouble. JS has a couple of ways to handle this kind of requests. The _traditional_ way and the one you absolutely need to know if you want to find a job in this field is called a _callback function_. We'll describe this more in detail in below. Later we'll also talk about **Promises**, which were introduced with ES6 to tackle these kind of problems. With the advent of ES7 you now also have something called _async functions_, but these only run in Google Chrome for now and we won't go deeper into those.

Callbacks
---

Unlike some other programming languages, in JavaScript you can pass a function as an argument in another function. In JavaScript, functions are **first-class objects**; that is, functions are of the type _Object_ and they can be used in a first-class manner like any other object (String, Array, Number, etc.) since they are in fact objects themselves.

Because functions are first-class objects, we can pass a function as an argument in another function and later execute that passed-in function or even return it to be executed later. This is the essence of using **callback functions** in JavaScript.

A callback function, also known as a **higher-order function**, is a function that is passed to another function (let’s call this other function “otherFunction”) as a parameter, and the callback function is called (or executed) inside the otherFunction. A callback function is essentially a pattern (an established solution to a common problem), and therefore, the use of a callback function is also known as a callback pattern.

When you were using event listeners as part of the DOM manipulation, you were already using callback functions!!

```javascript
var someDiv = document.getElementById("someDiv");
someDiv.addEventListener("click", function(){ //This is a callback function! It says, after a "Click" run this function
    alert("I clicked some div");
})
```

Alternatively, you could split up the code like this:

```javascript
var someDiv = document.getElementById("someDiv");

someDiv.addEventListener("click", myFunction); // No parentheses here!

function myFunction(){
    alert("I clicked some div")
};
```

And when you see this code, do you have a better understanding of what it does:

```javascript
var arr = [1, 2, 3];
arr.forEach(function(el){ // Yes, that's a callback function!
    return el * 2
})
```

So how would you go about writing functions that take callback functions as arguments? Let's look at this example:


```javascript
var db = [];
// A user data object
var userData = {
    name: "Evan Cole",
    age: 26,
    nationality: "\'Murican"
};

// a function that prints out user data
function printData(userData){
    for (key in userData){
        console.log(key + ": " + userData[key]);
    }
};

// a function that takes as arguments the data and a callback function
function getData(inputData, callback){
    // do something with the data. Store it to a DB for example
    db.push(inputData);
    callback(inputData);
};

//call the function with the data and the callback function
getData(userData, printData);

```

In the above example you want to make sure the printing of the data only happens **after** you've received the data. That's why you write a function that gets data first and then call a second function that prints the data. This way you're avoiding that JS moves on to next line, without having retrieved all the data.

```javascript
// without callback. You've defined a function that gets data from an external API
// you store it in a var
var data = getData(someURI); // connects to a server, gets the data, processes the data,...

// Immediately afterwards, display the data in your page
document.getElementById("someDiv").innerHTML = data;
``` 
Chances are that in above example the page will remain empty! JS will run the getData function, but may move on to the next line before receiving all the data. That's why you need to wrap this up in a callback!

Exercises
---

Go [here](https://github.com/jankeLearning/content-code/tree/master/Week%2003/callbacks);

Project
---

Click [here](https://github.com/jankeLearning/projects/tree/master/03-callbacks%2Bdata_models) to go the project.
