Functions
========

What are functions?
-------------------

Functions let us have re-usable chunks of code. Consider functions as code that is grouped together and can run upon calling.

    function compare(x,y){
      if(x > y){
        return(x + "is bigger than " + y)
      }else if(x < y){
        return(x + "is lesser than " + y)  
      }else{
        return("well well, we have equals here!")
      }
    }


And this is how I call the function: `compare(3,5)  // 3 is lesser than 5`.

You can find a great comprehensive introduction into functions [here](http://javascript.info/function-basics).

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

> ### Exercises
> Go over [this list](https://github.com/jankeLearning/content-code/Week 1/Functions/Simplest Passing Functions) of exercises in Content-Code: Read, modify and run the code.

Writing specs for functions
-------
Writing specs for functions is planning your functions by writing them out in plain English or pseudocode. As seen above in the Unit Test example, the spec should always _specify_ three things:

+ The arguments you're planning to give to your function.
+ The result you're expecting the function to return
+ How you expect the function to _behave_: what does the function do with the arguments and how will it be returned

> Here you have a simple example

    function butcher(cow) {
	    var food = cow.weight * .43; 
	    var message = 'deceased at ' + cow.age + ' years of age';
	    return [food, message];
    }

butcher: function
 + args: 1
    + cow: a cow object
 + return: array containing two values
    + food: the amount of food yeilded from this cow
    + message: a polite message commemorating the cow's life
 + behavior: calculates the amount of yield from the given cow and constructs a polite message
 

