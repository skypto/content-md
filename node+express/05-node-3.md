Node and HTTP
===

To get a quick handle on node.js applications, we can write a simple http server in node.js. Procedures: • We will create a folder named nodeapps in our machine. • We will create a file named exampleServer.js in the folder. And we will write the following code in the exampleServer.js file, as follows: exampleServer.js:

```javascript
var http = require("http");

function dealWithWebRequest(request, response){
    response.writeHead(200, {"Content-Type": "text/plain"});
    response.write("Hello Node.js");
    response.end();
}

var webServer = http.createServer(dealWithWebRequest).listen(3000, "127.0.0.1");
webServer.once("listening", function(){
    console.log("Server running at http://127.0.0.1/3000);
});
```

Now, go to your console and hit this: `node exampleServer.js`.

We are using the Node.js http module. We are doing a lookup for the http module in the function call. We are calling the http module and assigning the functionality to any variable (here it is "http"). This variable further serves for functional references in next calls. → `var webserver = http.createServer(dealWithWebRequest).listen(3000,"127.0.0.1"); http.createServer` will create an http server here and will assign it to variable webserver. Also, at the end of the closure, the TCP port and server address are given. These define where the server will run. Here, the server address is 127.0.0.1 and the TCP port is 3000. → `function dealWithWebRequest(request, response) { //Our code }` This is the callback function, which is passed as argument in `http.createServer(. . . )` module which is a normal function passing as argument in Javascript.

Three inner lines in the function: → `response.writeHead(200, {’Content-Type’: ’text/plain’}); response.write(’Hello Node.js\n’); response.end();` We are writing an HTTP header specifying the content type of the response. So, for this sample server we have set the content type as text/plain in the first line.
Next, we are writing the message with response.write and ending the HTTP server response object to render message to the browser. This means the response.end will send the message to browser and tell HTTP Protocol to end the response. → `response.write(’Hello Node.js\n’); response.end();`

After completing the whole work we have the listener setup for the server → `server.once(’listening’, function() { console.log(’Server running at http://127.0.0.1:3000/’); });` Once the server is listening on that port, the listening event is firing. We have instructed node.js to log a message in that particular listening event. 

### Obligatory "Hello World" in Node.js

```javascript
var http = require("http");

http.createServer(function (req, res){
    res.writeHead(200, {"Content-Type": "plain/text"});
    res.end("Hello World!\n");
}).listen(3000);
```

Run this script in node and go to port 3000 in your browser. You should see "Hello World!" appearing on your screen.

External Resources
---
+ Beginner Node: https://drive.google.com/open?id=0B0hGsLRwLpo3T0NZTzhwQTRlRzg
+ https://code.tutsplus.com/tutorials/nodejs-for-beginners--net-26314
+ W3 Schools: https://www.w3schools.com/nodejs/
