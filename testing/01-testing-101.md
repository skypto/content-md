# TESTING 101
Testing is an empassioned topic.  If you search online you'll find great debates over which frameworks to use and how to fit tests into your development cycle.  
Underlying all sides of the arguments are a few universal tenants:  
  * pure functions  
  * specifications
  * unit tests
  
This lesson will cover each of these topics individually than look at how they come together to form a **testing suite**. 
***  
### PURE FUNCTIONS
A pure function must meet these 3 criteria: 
1. The same arguments will ALWAYS produce the same return value.  
2. It will NEVER modify anything outside of it's lexical scope (ie. defined outside it's curly braces, anything it needs is passed in as an argument).  
        * With one exception: a method can modify it's object's properties.  
3. It will return the results of it's logic as a new object/list/number/...  To make use of a pure function you must capture the returned value in a new (or old) variable.  

An important concept for understanding why you use pure functions is __side effects__.  
* SIDE EFFECT: The modification of variables in one scope by code in a different scope.  

Side effects are caused by impure functions that reach outside of their scope to find variables they need.  When this happens you can get mysterious **runtime errors** when a value is no longer what you expect it to be because some arbitrary process has changed it.

Avoiding side effects entirely in full applications is a larger discussion and relies on __immutable data flow__.  This is an advanced design paradigm and requires a solid understanding of functional programming so we'll discuss it in week 9.  For now just do your best.

Below is a simple and pure function for division.  This function will be used through the rest of **testing 101** so take the time you need to understand it.
```javascript
function division(a, b) {
	var result = 0000;
	// logic
	return result;
};
```
***
### SPECIFICATIONS
A specification is plain text that describes everything needed for someone to build code with a given functionality.  If specs are well written (and well followed) all implementations will be interchangeable.   My code may be faster than yours, and hers may be easier to read, and his uses less memory, but we could close our eyes to pick one and the application will still work the same.  
  
If you are careful to build pure functions you only need to specify 3 things to fully describe your code: 
1. ARGUMENTS:  The number of arguments your function needs and the type of each one. 
2. RETURN TYPE: The type of whatever is to the right of your return statement.  If there is no return statement, Javascript defaults to returning 'undefined'.   
3. BEHAVIOR:  A high level description of what happens between the curly braces. If this gets longer than 2 lines you should think about breaking your function into littler functions.

Specs for the division function above.  It's import that everything is spelt the same in your specs and your function:
* division: function  
  * ARGS: 2  
    1. a: number  
    2. b: number or undefined 
  * RETURN: number  
  * BEHAVIOR: Divides a by b if b is not 0.  Returns the result or 'undefined', depending on the inputs.
 ---
### UNIT TESTS

These are the atoms of all testing.  The principle is very simple, coming up with them is easy but time consuming.  Coming up with good ones is challenging and worth the effort.  There is no better way to understand a function than coming up with a good set of test cases.  

Unit Tests are the simplest possible example of something called a __higher order function__.  Higher order functions are functions that take other functions as arguments.  Let's take a look at some specs to see how this works: 
* unit_test: function
  * ARGS: 1
    1. testee: function
  * RETURN: boolean
  * BEHAVIOR: Executes testee with a hard-coded set of arguments and compares the returned value against the expected result.  Returns the result of this comparison.
 
Take a moment to notice how much more difficult this would be if testee weren't a pure function.  
  
Below is a series of unit tests for the division function.  Coming up with a good collection of unit tests means determining what are the important classifications of input/output pairs and testing each one.  

```javascript
function test_1_division(testee) {  // positive, positive
	var a = 3;
	var b = 3;
	var expected = 1;
	var result = testee(a, b);
	if(result == expected) {
		return true;
	} else {
		return false;
	};
};
function test_2_division(testee) { // negative, negative
	var a = -3;
	var b = -3;
	var expected = 1;
	var result = testee(a, b);
	if(result == expected) {
		return true;
	} else {
		return false;
	};
};
function test_3_division(testee) { // positive, negative
	var a = 3;
	var b = -3;
	var expected = -1;
	var result = testee(a, b);
	if(result == expected) {
		return true;
	} else {
		return false;
	};
};
function test_4_division(testee) { // negative, positive
	var a = -3;
	var b = 3;
	var expected = -1;
	var result = testee(a, b);
	if(result == expected) {
		return true;
	} else {
		return false;
	};
};
function test_5_division(testee) { // non-0, 0
	var a = 3;
	var b = 0;
	var expected = undefined;
	var result = testee(a, b);
	if(result == expected) {
		return true;
	} else {
		return false;
	};
};
function test_6_division(testee) { // 0, non-0
	var a = 0;
	var b = 3;
	var expected = 0;
	var result = testee(a, b);
	if(result == expected) {
		return true;
	} else {
		return false;
	};
};
```
___
### ALL TOGETHER NOW
The __testing suite__ is what ties this all together.   It's no huge conceptual leap forward, but it makes life a lot easier.  
This one isn't a pure function, what would you have to change to make it one?
```javascript
function division_test_suite(testee) {
	var result = [];
	if(test_1_division(testee)) {  // +/+
		result.push('PASS +/+');
	} else {
		result.push('fail +/+');
	};
	if(test_2_division(testee)) {  // -/-
		result.push('PASS -/-');
	} else {
		result.push('fail -/-');
	};
	if(test_3_division(testee)) {  // +/-
		result.push('PASS +/-');
	} else {
		result.push('fail +/-');
	};
	if(test_4_division(testee)) {  // -/+
		result.push('PASS -/+');
	} else {
		result.push('fail -/+');
	};
	if(test_5_division(testee)) {  // +/0
		result.push('PASS +/0');
	} else {
		result.push('fail +/0');
	};
	if(test_6_division(testee)) {  // 0/+
		result.push('PASS 0/+');
	} else {
		result.push('fail 0/+');
	};
	return result;
};
```

---
### N L S

If you're a real programmer you'll be annoyed by all the repetition in the above __unit tests__ and this __testing suite__. 

figure out how to use all this stuff

```javascript
function unit_test(testee, args, expected) {
    var result = testee(...args);
    return result == expected;
};

function division(a, b) {
	var result = 0000;
	// logic
	return result;
};

var division_test_cases = [
    { args: [3, 3], expected: 1, name: '+/+' },
    { args: [-3, -3], expected: 1, name: '-/-' },
    { args: [3, -3], expected: -1, name: '+/-' },
    { args: [-3, 3], expected: -1, name: '-/+' },
    { args: [3, 0], expected: undefined, name: 'non-0/0' },
    { args: [0, 3], expected: 0, name: '0/non-0' }
];

function test_suite(test, testee, cases) {
    var results = [];
    for(var test_case in cases) {
        result.push(test(testee, test_case.args, test_case.expected)); 
    };
    return results;
};

function result_interpreter(test_results, test_cases) {
    var interpretation = [];
    for(var i = 0; i < test_results.length; i++) {
        if(test_results[i]) {
            interpretation.push('PASS: ' + test_cases[i].name);
        } else {
            interpretation.push('fail: ' + test_cases[i].name);
        };
    };
    return interpretation;
};
```



















