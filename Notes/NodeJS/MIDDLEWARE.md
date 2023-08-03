#node/middleware
# Middleware :
 - tldr; list of function that executes, in order, before your controller.
 - Allow you to execute functions on an incoming request with guaranteed order.
 - Great for authenticating, transforming the request, tracking and error handling.
 - Middleware can also respond to request like a controller would, but that is not their intent.