# Express Middlewares

### What are express middlewares?

"A web server can be seen as a function that takes in a request and outputs a response. Middlewares are functions executed in the middle after the incoming request then produces an output which could be the final output passed or could be used by the next middleware until the cycle is completed, meaning we can have more than one middleware and they will execute in the order they are declared"

 Middleware functions are functions that have access to the request object (req), the response object (res), and the next middleware function in the application’s request-response cycle. The next middleware function is commonly denoted by a variable named next.
 
 ![](https://miro.medium.com/max/1400/1*WTcjbYL3fmFw5XW6fq408g.png)

An Express application can use the following types of middleware:

- Application-level middleware
    Bind application-level middleware       to an instance of the app object       by using the app.use() and      app.METHOD() functions
- Router-level middleware
    Router-level middleware works in       the same way as application-level       middleware, except it is bound to       an instance of express.Router().
- Error-handling middleware
    Error-handling middleware functions is the same as other middleware functions, except that it takes four arguments instead of three, specifically with the signature (err, req, res, next)):
- Built-in middleware
Starting with version 4.x Express has the following built-in middleware functions
    * express.static serves static assets such as HTML files, images, and so on.
    * express.json parses incoming requests with JSON payloads. NOTE: Available with Express 4.16.0+
    * express.urlencoded parses incoming requests with URL-encoded payloads. NOTE: Available with Express 4.16.0+
- Third-party middleware
    example of use
    
    ```javascript=
    $ npm install cookie-parser
    var express = require('express')
    var app = express()
    var cookieParser =     require('cookie-parser')
    app.use(cookieParser())
    ```
    For a partial list of third-party middleware functions that are commonly used with Express, see:[Third-party middleware.](https://expressjs.com/en/resources/middleware.html) 



### What functionality do they provide?

Middleware functions can perform the following tasks:

- Execute any code.
- Make changes to the request and the response objects.
- End the request-response cycle.
- Call the next middleware function in the stack.

If the current middleware function does not end the request-response cycle, it must call next() to pass control to the next middleware function. Otherwise, the request will be left hanging.

The following figure shows the elements of a middleware function call:


![](https://i.imgur.com/TTr4FIo.png)


<hr>

### What are some examples of useful express middleware and how do you use them:

An Express application can use the following types of middleware:


### Built-in middleware
1. express.urlencoded([options]);
   It parses incoming requests with urlencoded payloads

2. express.json([options]);
Parses incoming requests with JSON anad this method takes few args, i.e
    - limit: Controls the maximum request body size.
    - type: this is used what type the middleware will parse.
    - strict: Enables accepting only arrays and bjects.
###  Third-party middleware
1.   **express-fileupload** -
 Simple express middleware for uploading files. https://www.npmjs.com/package/express-fileupload

    



     ```javascript=
      app.post('/upload',function(req,res){
         console.log(req.files.foo); //     the uploaded file object
     });
     ```


 
2. **Passport**

    Passport is authentication middleware for Node. It is designed to serve a singular purpose: authenticate requests.
    Passport recognizes that each application has unique authentication requirements. Authentication mechanisms, known as strategies, are packaged as individual modules. Applications can choose which strategies to employ, without creating unnecessary dependencies.

- Authenticate example

    ```
    $ npm install passport
    ```

    ```javascript=
    var passport = require('passport')

    app.post('/login',
      passport.authenticate('local'),
      function(req, res) {
        // If this function gets called, authentication was successful.
        // `req.user` contains the authenticated user.
        res.redirect('/users/' + req.user.username);
      });
    ```
By default, if authentication fails, Passport will respond with a 401 Unauthorized status, and any additional route handlers will not be invoked. If authentication succeeds, the next handler will be invoked and the req.user property will be set to the authenticated user.

for more information on how to use passport check the link:
:::info 
http://www.passportjs.org/docs/
:::

3. **Helmet**

    ```
    $npm install helmet --save
    ```

    ```javascript=
    const express = require('express')
    const helmet = require('helmet')

    const app = express()

    app.use(helmet())
    ```

    It's best to use Helmet early in your middleware stack so that its headers are sure to be set.

    You can also use its pieces individually:

    ```javascript=
    app.use(helmet.xssFilter())
    app.use(helmet.frameguard())
    ```

    You can disable a middleware that's normally enabled by default. This will disable frameguard but include the other defaults.
    ```javascript=
    app.use(helmet({
    frameguard: false
    }))
    ```

    You can also set options for a middleware. Setting options like this will always include the middleware, whether or not it's a default.
    ```javascript=
    app.use(helmet({
    frameguard: {
    action: 'deny'
      }
    }))
    ```

<hr>

   


### resources
- [Using middleware ](https://expressjs.com/en/guide/using-middleware.html)
- [Express Middleware explanation](https://medium.com/@agoiabeladeyemi/a-simple-explanation-of-express-middleware-c68ea839f498)
- [express.text(): ](https://expressjs.com/en/api.html)
- [Passport documentation](http://www.passportjs.org/docs/)
- [Helmet documentation](https://github.com/helmetjs/helmet)
