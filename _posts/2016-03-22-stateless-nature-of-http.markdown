---
title:  "Stateless nature of HTTP"
date:   2016-03-21 06:05:00
summary: HTTP is stateless, which means every single request is independent from any other requests.
---

HTTP is stateless, which means every single request is independent from any other requests. By state it's mean an application remembers some details about a client from one request to another.

### HTTP verbs

The primary or most-commonly-used HTTP verbs (or methods) are POST, GET, PUT, PATCH, and DELETE. These correspond to create, read, update, and delete (CRUD) operations, respectively. There are a number of other verbs, but are utilized less frequently.

1. GET: The GET verb is a means of retrieving information from the Request-URI.
2. POST: The POST verb is intended as a way to create a new resource on the server.
3. PUT: The PUT verb is used as a method to update an existing resource on the server.
4. DELETE: remove a resource from the server.

### 1. Http Status Codes

Status codes are three digit codes paired with a phrase explaining whether or not the status completed successfully. By looking at the first digit a user can tell whether the response is providing information (100); was successful (200); has been redirected (300); there was an error in the request (400); or there was an error on the server (500).

#### 2. Informational (100)
These indicate a provisional response. They are not supported by HTTP/1.0, because that version of the protocol did not define 1xx codes.

- 100 Continue
- 101 Switching Protocols

#### 3. Success (200)
A 2xx code indicates the server successfully received, understood, and accepted the client request.

- 200 OK
- 201 Created
- 202 Accepted
- 203 Non-Authoritative Information
- 204 No Content
- 205 Reset Content
- 206 Partial Content

#### 4. Redirection (300)
Servers use this class of code to indicate to a client further action needs to be taken to fulfill the original request.

- 300 Multiple Choices
- 301 Moved Permanently
- 302 Found
- 303 See Other
- 304 Not Modified
- 305 Use Proxy
- 307 Temporary Redirect

#### 5. Client Error (400)
This set of status codes are meant to indicate the client made some sort of error in their request, such as being malformed or not allowed.

- 400 Bad Request
- 401 Unauthorized
- 402 Payment Required
- 403 Forbidden
- 404 Not Found
- 405 Method Not Allowed
- 406 Not Acceptable
- 407 Proxy Authentication Required
- 408 Request Time-out
- 409 Conflict
- 410 Gone
- 411 Length Required
- 412 Precondition Failed
- 413 Request Entity Too Large
- 414 Request-URI Too Large
- 415 Unsupported Media Type
- 416 Requested Range Not Satisfiable
- 417 Expectation Failed

#### 6. Server Error (500)
A complement to 400 level errors, this status code indicates the server encountered some unexpected condition and could not fulfill the client’s request.

- 500 Internal Server Error
- 501 Not Implemented
- 502 Bad Gateway
- 503 Service Unavailable
- 504 Gateway Time-out
- 505 HTTP Version not supported


Reference :

1. [Using HTTP Methods for RESTful Services](http://www.restapitutorial.com/lessons/httpmethods.html)
2. Frost, Matthew. Integrating Web Services with OAuth and PHP. Alexandria: musketeers.me, LLC. 2016.


---
> The keystone of the Fascist doctrine is its conception of the State, of its essence, its functions, and its aims. For Fascism the State is absolute, individuals and groups relative.
> <small>- [Benito Mussolini](http://www.brainyquote.com/quotes/quotes/b/benitomuss408638.html)</small>