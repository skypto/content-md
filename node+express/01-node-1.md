What is Node?
====
According to the nodejs.org site:

“Node.js is a platform built on Chrome’s V8 JavaScript runtime for easily building fast, scalable network applications. Node.js uses an event-driven, non-blocking I/O model that makes it lightweight and efficient, perfect for data-intensive real-time applications that run across distributed devices.” 

What does this mean? It means node is not a programming language, it's a command line application with 3 main features:
1. JavaScript runtime - node can execute javascript files.
2. HTTP server - node can listen on the internet and handle the HTTP req/res cycle.
3. File system access - node can read and write to your computer's file system

Fun fact: Node is written in C/C++, not JavaScript.

**What type of Web Applications are we able to build using Node?**

We can build apps like: 
+ Web Applications 
+ HTTP Proxy based Applications
+ SMTP Servers used for mails
+ Other network intensive apps.

__Remember, the applications we will be building will be constructed in JS.__

### Node Package Manager

Node Package Manager, or also called NPM, is a library management tool that lets us use different packages and versions at each project we have. We will talk more about NPM later in this course.

### Using node to run pure js files.

Running JS files with node is pretty straightforward. All you have to do is to make sure you're in the same directory as the JS file and run: node _JS file_.

> PS: If you're not sure if node is properly installed, just run node -v in your terminal. This should return the current version of node that's running on your machine. If you get an error, it means node is not installed.

+ a nice vide: https://www.youtube.com/watch?v=kEeC2sY1AE8