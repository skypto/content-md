Functions
========

What are functions?
-------------------

Functions let us have re-usable chunks of code. Consider functions as code that is grouped together and can run upon calling.

```javascript
function compare(x,y){
  if(x > y){
    return(x + "is bigger than " + y)
  }else if(x < y){
    return(x + "is lesser than " + y)  
  }else{
    return("well well, we have equals here!")
  }
}
```

And this is how I call the function: `compare(3,5)  // 3 is lesser than 5`.

You can find a great comprehensive introduction into functions [here](http://javascript.info/function-basics).

### Different kinds of functions

By now you've have probably noticed that there are different ways to write functions. There are three distinct ways of writing functions that you'll encounter in your programming career: _function declarations_, _function expressions_ and _arrow functions_.

+ **Function Declaration**

 A function declaration is _declared_ as a separate statement in the main code flow. Its syntax will look this:

 ```javascript
function sayHi(name){
	return "Hi " + name + "!"
}
```

 You declare a function by its keyword (_function_) followed by a name and the arguments it will take.

+ **Function expression**

 Here you'll explicitly assign a function to a variable, just like any other value. It will look something like this:

 ```javascript
var sayHi = function(name){
  return "Hi " + name + "!"
}
```

 Here you create the function and assign it to a variable.

+ **Function declaration vs Function expression**

 So what's the difference you ask? In most cases they can be used interchangeably. Both functions are called the exact same way: `sayHi("Evan") // will return "Hi Evan! `.

 So why have two different ways of writing functions? There is one important difference and that has to do with _when_ the function is created by the JavaScript engine.

 Try running these two chunks of code in the console:

 ```javascript
  sayHi("Evan");

  function sayHi(name){
    return "Hi " + name + "!"
  }
 ```

 ```javascript
  sayHello("Evan");

  var sayHello = function(name){
    return "Hi " + name + "!"
  }
  ```

 The first code will run as expected and will return "Hi Evan!". However, the second one will return a TypeError. Why is that? Remember that JavaScript runs your code from top to bottom, however before that it will look for any function _declarations_. And after all Function Declarations are processed, the execution goes on.

 A Function Expression however, works as any other value assignment and will only be created when it's _reached_. That's why you can call a function created as a Function Declaration everywhere in your script, even before the JS engine has reached the declaration in your script.

+ **ES6: Arrow functions**

 Once you progress in this course, you will also get familiar with a third kind of function: **the arrow function**. This is a ES6 (EcmaScript 2015) command and may not be supported in every browser.

 An arrow Function will look like this: `let SayHi = (name) => {return "Hi " + name + "!"}`.

 An Arrow Function is a shorter way of writing Function Expressions. It simply takes the arguments between parentheses, followed by an arrow (hence the name) and a return statement

 > In fact you can even write this function even more concise: `let sayHi = (name) => "Hi " + name + "!"`
 > You can leave out the curly braces and return keyword if you only want to return something.

 > If there are no arguments, you just use empty parentheses: `let printHelloWorld = () => "Hello World!"`

 We'll talk more about arrow functions later in the course. For now it's enough that you know that they exist.

### Exercises: 

Try the following exercises:
+ clone **day2_arrays_and_functions** from [this repo](https://github.com/Turfie/Elium-exercises/tree/master/week%201)

Minimal Passing Functions and Unit Tests
-------
Minimal possible functions play an important role in the structured approach to development we teach.
By planning ahead the architecture and specs of your project, you can break down the development 
process into solving several isolated and manageable chunks. 
Each of these chunks can be built up using the Minimal Passing paradigm to trouble shoot your app
from the first line of code to the last.

A unit test is the fundamental component of any testing strategy. This week we will discuss how to write basic ones in pure javascript. Unit tests can be used as part of a well organized development process 
to hold yourself to your own standards and to keep yourself focused. (single-purpose functions)

Testing and it's role in larger-scale development is a whole nother discussion.
We will be looking at Test Driven Development in week 6.
This series of exercises is simply an introduction to what tests are.

* Unit Tests:
  * args: the function to test
  * returns: an informative message
  * behavior: unit tests will take in a function to test, run the function with predetermined arguments and tell you whether the function did the right thing or not


> A very simple unit test for addition
```javascript
  function additionTester(testee) {
    var tested = testee(4, 5);
    var message = '';
    if (tested == 9) {
        message = 'success';
    } else {
        message = 'failure';
    };
    return message;
  }
```

> ### Exercises
> Go over [this list](https://github.com/jankeLearning/content-code/Week 1/Functions/Simplest Passing Functions) of exercises in Content-Code: Read, modify and run the code.

Writing specs for functions
-------
Writing specs for functions is planning your functions by writing them out in plain English or pseudocode. As seen above in the Unit Test example, the spec should always _specify_ three things:

+ The arguments you're planning to give to your function.
+ The result you're expecting the function to return
+ How you expect the function to _behave_: what does the function do with the arguments and how will it be returned

> Here you have a simple example
```javascript
    function butcher(cow) {
	    var food = cow.weight * .43; 
	    var message = 'deceased at ' + cow.age + ' years of age';
	    return [food, message];
    }
```

butcher: function
 + args: 1
    + cow: a cow object
 + return: array containing two values
    + food: the amount of food yeilded from this cow
    + message: a polite message commemorating the cow's life
 + behavior: calculates the amount of yield from the given cow and constructs a polite message
 

