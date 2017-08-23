Axios
===

Axios is a third-party module used in the browser and node to make request to internal or external API's. It makes use of the built-in XMLHttpRequest object to send or retrieve data.

As this is a third-party module it will need to be imported into your global environment. 

### Examples

```javascript
// Make a request for a user with a given ID
axios.get('/user?ID=12345')
  .then(function (response) {
    console.log(response);
  })
  .catch(function (error) {
    console.log(error);
  });

// performing a post request
axios.post('/user', {
    firstName: 'Fred',
    lastName: 'Flintstone'
  })
  .then(function (response) {
    console.log(response);
  })
  .catch(function (error) {
    console.log(error);
  });  
```

External Resources
---

+ Axios: https://github.com/mzabriskie/axios
+ https://medium.com/codingthesmartway-com-blog/getting-started-with-axios-166cb0035237