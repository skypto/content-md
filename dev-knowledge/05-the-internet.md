How Does the Web Work?
====

Before you can understand how to program the web, you need to understand the web itself on a more granular level than you probably do now. Some of this stuff is necessary just to have a more holistic understanding of the ecosystem in which you will be working (and to not sound like a total newbie when talking to other developers about it).

So without further ado, here's a bunch of great content to get a better understanding of how the web works.

1. Watch this [BBC short](https://vimeo.com/128575085) for an overview of how the Internet works.
2. Supplement this with a [reading](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/How_does_the_Internet_work#Summary) and a [video](https://www.youtube.com/watch?v=7_LPdttKXPc&feature=youtu.be&t=46s).
3. Read up on the [differences](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/Pages_sites_servers_and_search_engines#Summary) between a webpage, web server and a search engine.
4. Watch this [Google short](https://www.youtube.com/watch?v=BrXPcaRlBqo&feature=youtu.be) explaining what a web browser is; then find out what web browser you are using right [now](https://whatbrowser.org/).
5. Now read about how one part of the web [interacts with another](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/How_the_Web_works#Clients_and_servers) and [read](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_domain_name#How_does_a_DNS_request_work) or [watch](https://www.youtube.com/watch?v=72snZctFFtA&feature=youtu.be&t=45s) a DNS request in action.

HTTP: Request/response cycle
---
Whether you're a programmer or not, you have seen it everywhere on the web. At this moment your browsers address bar shows something that starts with "http://". Even your first Hello World script sent HTTP headers without you realizing it. In this segment we are going to learn about the basics of HTTP headers and how we can use them in our web applications.

### What are HTTP Headers?
HTTP stands for "Hypertext Transfer Protocol". The entire World Wide Web uses this protocol. It was established in the early 1990's. Almost everything you see in your browser is transmitted to your computer over HTTP. For example, when you opened this article page, your browser probably have sent over 40 HTTP requests and received HTTP responses for each.

HTTP headers are the core part of these HTTP requests and responses, and they carry information about the client browser, the requested page, the server and more.

<img src="https://cdn.tutsplus.com/net/uploads/legacy/511_http/http_diagram.png" alt="HTTP">

### How to see HTTP Headers?
In chrome, got to the developers tools and click on the **network** tab. When you go to any site, you can see a number of items on the left. Click on any of them and you'll see the request and response headers.

<img src="https://www.midnightfreddie.com/videos/view-http-headers-with-chrome.png" alt="HTTP Headers">

External Resources
----
+ An [entertaining TED talk](https://www.ted.com/talks/jonathan_zittrain_the_web_is_a_random_act_of_kindness) about how the Internet works.
+ A comprehensive list of web development resources lives at the [Web Standards Curriculum](https://www.w3.org/wiki/Web_Standards_Curriculum).
+ [How the Internet Works [For Web Developers] - Part 1](https://www.youtube.com/watch?v=e4S8zfLdLgQ)
+ [How the Internet Works [For Web Developers] - Part 2](https://www.youtube.com/watch?v=FTAPjr7vgxE)