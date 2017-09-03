# Abstractions

write a script

wrap it in a function

use the function in a script

put the script in a function 

...

this is abstraction

___

pitfalls of abstraction:
	native js methods
	.1 + .2


> _Abstraction_ :  keep this?  probs not
The process of considering something independently of its associations, attributes, or concrete accompaniments.   - Mr. MacDictionary


Whenever you write a function, or assign a name to a variable you are writing your own abstractions

You write with a pen but don't know the chemistry that causes the ink to stick to the paper.  

You can't deduce how these things work, the scientific method is a terrible idea in programming.  read the documentation - if its any good someone who knows the tools better than you will explain how it works.

In the world of programming, everything is an abstraction - a simplification of something more fundamental and more complex.  Assembly code is an abstraction over machine code. Machine code is an abstraction over electrical currents in your computer. JS is an abstraction over machine (though perhaps a few layers up).  jQuery is an abstraction over JS.  Express is an abstraction over JS. Axios is an abstraction over fetch. Nothing is 'natural'.  Every inch of JS, every library you use, every application or runtime is built from smaller pieces, by a human, to make a particular task easier for _you_.

This is the purpose of abstractions, to make something easier.  You are here to build web apps, but probably will never learn to parse HTTP or write network protocol.  You're writing in JS but will probably never learn to code in machine.  Very few people, if anyone, know how everything in a computer or in the internet works.  Everyone involved understands how to use their tools (Microsoft Word, Node.js, Mac OS), and rely on other people to provide them with those tools.  We call these tools __abstractions__.




Jeff Goodell: Would you explain, in simple terms, exactly what object-oriented software is?
Steve Jobs: Objects are like people. They’re living, breathing things that have knowledge inside them about how to do things and have memory inside them so they can remember things. And rather than interacting with them at a very low level, you interact with them at a very high level of abstraction, like we’re doing right here.
Here’s an example: If I’m your laundry object, you can give me your dirty clothes and send me a message that says, “Can you get my clothes laundered, please.” I happen to know where the best laundry place in San Francisco is. And I speak English, and I have dollars in my pockets. So I go out and hail a taxicab and tell the driver to take me to this place in San Francisco. I go get your clothes laundered, I jump back in the cab, I get back here. I give you your clean clothes and say, “Here are your clean clothes.”
You have no idea how I did that. You have no knowledge of the laundry place. Maybe you speak French, and you can’t even hail a taxi. You can’t pay for one, you don’t have dollars in your pocket. Yet I knew how to do all of that. And you didn’t have to know any of it. All that complexity was hidden inside of me, and we were able to interact at a very high level of abstraction. That’s what objects are. They encapsulate complexity, and the interfaces to that complexity are high level.