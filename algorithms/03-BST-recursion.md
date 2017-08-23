just that.  oo binary search tree  
  
diagrams  
  
link to finished code  

	https://github.com/tivrama/DataStructures
	https://github.com/mgechev/javascript-algorithms/tree/master/src/data-structures

Is the task I’m trying to achieve composed of sub-tasks?
Are those subtasks pretty much the same thing?
If you answered ‘yes’ to these questions, it’s recursion time -->

What is the simplest task that composes my main goal?
What’s the smallest component on which I can perform this task?
How do I break the large component into smaller ones?
How do I know when I’m at the smallest component?
How do I rebuilt my smaller solutions back into the large one?

use bst for this

var demo = function recurse(word) {
    console.log(word);
    recurse(word);
};

demo('sucka!');