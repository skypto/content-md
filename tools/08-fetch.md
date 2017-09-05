Fetch
===
The Fetch API is a built-in javascript interface for fetching resources (including across the network).

It has a relatively simple syntax and it uses Promises to handle results/callbacks.

The syntax looks like this: fetch(_URL_(required), _options_(optional)).then(_response_).catch(_error_).

So fetch sends a _request_ to an url to retrieve data from, and optionally some options, such as method (GET,POST,...). It will return a _response_ which can be handled in the `then` statement.

Let's make a request to an API. Introducing the Random People API!!

```javascript
fetch("https://randomuser.me/api/")
  .then(response => response.json()) // wil return JSON so let's parse that
  .then(data => console.log(data)) // let's examine what this returns

// I only want the name:

fetch("https://randomuser.me/api/")
  .then(response => response.json())
  .then(data => alert(data.results[0].name.first + " " + data.results[0].name.last))
```

[Fetch API](https://developers.google.com/web/updates/2015/03/introduction-to-fetch)
[headers](https://developer.mozilla.org/en-US/docs/Web/API/Headers)
[Request](https://developer.mozilla.org/en-US/docs/Web/API/Request)
[Response](https://developer.mozilla.org/en-US/docs/Web/API/Response)