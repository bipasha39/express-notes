# Express Cheatsheet

## A minimal server with 4 lines of code

```
//load the 'express' module which makes writing webservers easy
const express = require('express');

const app = express();

app.get('/', function(request, response) {
  response.send("hello Express world!")
});

//Start our server so that it listens for HTTP requests!
app.listen(process.env.PORT);
```


## Accessing request.body in a POST request
If you are going to use the body of a POST request in a route, you will have to add one of two lines to first process the body.  If the request has come from
### ...from an HTML form:

if it has come from a HTML form you need to add the line
```app.use(express.urlencoded({ extended: false }))```

### ...from fetch (e.g. in React), or from Postman
if it has come from a HTML form you need to add the line
```app.use(express.json())```


[Here is the official Express.js documentation on the topic of req.body](https://expressjs.com/en/api.html#req.body)