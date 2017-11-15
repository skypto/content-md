# REACT?

REACT is part of a greater trend to move more of your application to the frontend, lightning the load on your backend services and making it easier to build apps of small reusable pieces.  

REACT is not the reason things are changing, it's a symptom of where things are going.  To use REACT effectively it is imporant to understand the development paradigms that are causing it's rise in popularity.

REACT is not only important to learn because its REACT.  
REACT is important to learn because to use it well is to master the skills of modern development.

Strong Recommendation:
> Tell yourself you're using REACT to study development.
Don't tell yourself you're studying REACT.


It's a mental game, but it will pay off.


___
### State

STATE.  

A super important concept.  Moving towards REACT-style apps is moving away from the comfort of a single database.  Much of what you need to learn to master REACT has nothing to do with REACT and everything to do with managing app state:
* Stateless/Statefull components
* MVVM and other not-MVC architectures
* Immutable Dataflow
* Functional Programming
* Asynchronous data handling
* Distributed systems
* ...
___
### Components

COMPONENTS

A super important concept.  Moving towards REACT-style apps is moving towards modularity.  Just like pure functions can be strung together to build larger functions, so tiny UI components can be nested and combined to make full UIs.

You can think of a component being a DOM function that writes one simple div.  The idea is to build your view from many re-usable divs and redrawing each div as needed.

Similar to mirco-services, components allow you to build larger applications out of reusable, single-purpose pieces.  A picture please:

![](http://coenraets.org/blog/wp-content/uploads/2014/12/uimockscript.png)

Each of these different colored boxes is it's own REACT component.  You could "very easily" reuse them however you like in any REACT application
___
### REACT

Some major points:
* does not enforce any architecture
* can be used for static sites 
* not opinionated
  *  great if you really know what your'e doing
  *  not if you don't
* move more logic to the frontend
* don't render pages and send html, redraw the dom with new data
* move routing to the front-end
* backends are basically static serving, REST apis, and confidential business logic
___
### REACT vs ...
* full frameworks
  * angular, meteor, rails, ...
  * REACT has nothing to do with these.  
  * Most common frameworks are actually compatible with REACT
  * Paired with things like Redux, REACT can be a piece of a pseudo-framework

[All frameworks are terrible](https://medium.com/@mattburgess/all-javascript-frameworks-are-terrible-e68d8865183e)
[All frameworks are great](https://medium.com/@mattburgess/javascript-frameworks-are-great-2df4a3f0b24d)

___
### Resources


Why REACT
* https://firstdoit.com/how-i-learned-to-stop-worrying-and-love-react-4e22b0bb6c2a
* https://www.andrewhfarmer.com/what-is-react/

What REACT
* https://medium.freecodecamp.org/yes-react-is-taking-over-front-end-development-the-question-is-why-40837af8ab76
* https://medium.com/front-end-hacking/ok-fine-ill-learn-react-bc2200fa1937
* https://developer.telerik.com/featured/5-steps-for-learning-react-application-development/
* https://remysharp.com/2016/08/15/what-is-react
* https://medium.com/front-end-hacking/a-year-with-react-or-how-i-learned-to-stop-worrying-and-love-javascript-af6784400b7e
* https://www.quora.com/Is-React-js-really-worth-learning-or-is-it-just-a-fad#!n=18
* https://medium.com/react-weekly/embracing-immutable-architecture-dc04e3f08543
* https://thinkster.io/tutorials/what-exactly-is-react
* https://blog.designveloper.com/2017/07/12/free-reactjs-resources/