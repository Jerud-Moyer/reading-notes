## Routing
- Routing refers to how an application’s endpoints (URIs) respond to client requests
- You define routing using methods of the Express app object that correspond to HTTP methods;
- These routing methods specify a callback function (sometimes called “handler functions”) called when the application receives a request to the specified route (endpoint) and HTTP method.
### route methods
- A route method is derived from one of the HTTP methods, and is attached to an instance of the express class
- Express supports methods that correspond to all HTTP request methods: get, post, and so on
### route paths
- Route paths, in combination with a request method, define the endpoints at which requests can be made
- The characters ?, +, *, and () are subsets of their regular expression counterparts. The hyphen (-) and the dot (.) are interpreted literally by string-based paths
### route parameters
- Route parameters are named URL segments that are used to capture the values specified at their position in the URL. The captured values are populated in the req.params object, with the name of the route parameter specified in the path as their respective keys
### route handlers
- You can provide multiple callback functions that behave like middleware to handle a request. The only exception is that these callbacks might invoke next('route') to bypass the remaining route callbacks. You can use this mechanism to impose pre-conditions on a route, then pass control to subsequent routes if there’s no reason to proceed with the current route.
### response methods
- res.download()	Prompt a file to be downloaded.
- res.end()	End the response process.
- res.json()	Send a JSON response.
- res.jsonp()	Send a JSON response with JSONP support.
- res.redirect()	Redirect a request.
- res.render()	Render a view template.
- res.send()	Send a response of various types.
- res.sendFile()	Send a file as an octet stream.
- res.sendStatus()	Set the response status code and send it string representation as the response body.
### app.route()
- You can create chainable route handlers for a route path by using app.route(). Because the path is specified at a single location, creating modular routes is helpful, as is reducing redundancy and typos. For more information about routes, see: Router() documentation
### express.router
- Use the express.Router class to create modular, mountable route handlers. A Router instance is a complete middleware and routing system; for this reason, it is often referred to as a “mini-app”.

## supertest
 - https://github.com/visionmedia/supertest

## Using Middleware
 - https://expressjs.com/en/guide/using-middleware.html
 - Express is a routing and middleware web framework that has minimal functionality of its own: An Express application is essentially a series of middleware function calls.
 - Middleware functions are functions that have access to the request object (req), the response object (res), and the next middleware function in the application’s request-response cycle. The next middleware function is commonly denoted by a variable named next 
 - Middleware functions can perform the following tasks
  - Application level middleware
  - Router-level middleware
  - error-handling middleware
  - Built in middleware
  - Third party middleware
### Application-level middleware
- Bind application-level middleware to an instance of the app object by using the app.use() and app.METHOD() functions, where METHOD is the HTTP method of the request that the middleware function handles (such as GET, PUT, or POST) in lowercase.
### Router-level middleware
- Router-level middleware works in the same way as application-level middleware, except it is bound to an instance of express.Router()
- Load router-level middleware by using the router.use() and router.METHOD() function
### Error-handling middleware
- Load router-level middleware by using the router.use() and router.METHOD() function
### Built in midddleware
- Express has the following built-in middleware functions:
  - express.static serves static assets such as HTML files, images, and so on
  - express.json parses incoming requests with JSON payloads. NOTE: Available with Express 4.16.0+
  - express.urlencoded parses incoming requests with URL-encoded payloads. NOTE: Available with Express 4.16.0+
### Third psrty middleware
- Use third-party middleware to add functionality to Express apps.

Install the Node.js module for the required functionality, then load it in your app at the application level or at the router level.

## ExpressJS middleware
- Middleware functions are functions that have access to the request object (req), the response object (res), and the next middleware function in the application’s request-response cycle. These functions are used to modify req and res objects for tasks like parsing request bodies, adding response headers, etc
- To restrict it to a specific route (and all its subroutes), provide that route as the first argument of app.use()
### Order of middleware calls
- One of the most important things about middleware in Express is the order in which they are written/included in your file; the order in which they are executed, given that the route matches also needs to be considered
### Third party middleware
- body parser
  - This is used to parse the body of requests which have payloads attached to them. To mount body parser, we need to install it using npm install --save body-parser and to mount it, include the following lines in your index.js 
- cookie parser
  - It parses Cookie header and populate req.cookies with an object keyed by cookie names. To mount cookie parser, we need to install it using npm install --save cookie-parser and to mount it, include the following lines in your index.js 

## Express Middleware list
- https://expressjs.com/en/resources/middleware.html

## HTTP status codes
- https://www.restapitutorial.com/httpstatuscodes.html
