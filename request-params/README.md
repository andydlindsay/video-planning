# Understanding Request Parameters

## Summary/Motivation
* Students have shown confusion around the `req.params` object and how parameters are passed from client to server

## Script/Outline
* Routes like `/home` and `/about` work fine for unique pages
* However, when we have multiple versions of a resource such as `users`, `products`, or `urls`, we could create routes like this: `users/1`, `users/2`, `users/3`
* But this would result in extremely similar route handlers and templates/HTML files and our code would be WET instead of DRY
* So we need a way to create a dynamic route, a route capable of handling many different requests
*	To let Express know to expect a variable value, we use the colon syntax
*	Everything else that doesn't have a colon is considered static (unchanging)
* We could then parse the url ourselves using `req.url` maybe with `.split` or something, but that seems like too much work
*	Instead, Express adds these values as key/value pairs to the request object in a key called `params` to help us out
* The key is the name following the colon, the value is the actual value that the route received
* In the client, the parameter in the route is static
* Demo `GET` request in browser address bar
* On the server, console.log the `req.params` object

* Review
* Parameters are used to pass specific values from the client to the server (to request a specific resource)
* In the route `/users/:id` with a request to `/users/7`, the key is `id` and the value is `7` (accessible as `req.params.id`)

## Learning Outcomes
* Understand request parameters and how they are passed from client to server
* Understand what `req.params` is, where it comes from, and how to use it

## Prerequisites
* Objects - dot notation
* ExpressJS - route handlers, request and response objects
* HTTP - specifically GET request and request/response cycle
* Client/Server relationship

## Position in Curriculum
* W3D1 between URL Shortening Parts 1 and 2
