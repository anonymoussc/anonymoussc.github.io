---
title:  "JSON web token definition and example"
date:   2015-09-28 08:00:00
categories: Software-Engineering JWT
summary: JSON Web Tokens are an open, industry standard RFC 7519 method for representing claims securely between two parties.
cover-image: wire-high-voltage_1024.jpg
---

> JSON Web Token (JWT) is a JSON-based open standard (RFC 7519) for passing claims between parties in web application environment. The tokens are designed to be compact, URL-safe and usable especially in web browser single sign-on (SSO) context.
> <small>- [JSON Web Token](https://en.wikipedia.org/wiki/JSON_Web_Token)</small>

In broad terms, there are three kinds of web application, traditional round-trip application, single-page application
and hybrid application.

1. Round-trip application
The browser (client) requests an initial HTML document from the server. User interactions, such as clicking a link or 
submitting a form led the browser to request and receive a completely new HTML document as a responses from the server. 

2. Single-page application
In single page application, initial page are loaded only once and data exchange between client and the server 
occur in the background asynchronously through xmlhttprequest.

3. Hybrid model
Somewhere between all of the above.

For single page applications that rely on an API, a better way to handle authentication is with JSON web tokens (JWT).

## JWT
JSON web token consist of three different part, header, payload, signature wich is encoded into Base64Encoded.
A JWT can be identify as a three strings separated by `.` (dot), example :

    eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiYWRtaW4iOnRydWV9.TJVA95OrM7E2cBab30RMHrHDcEfxjoYZgeFONFh7HgQ

### 1. HEADER:ALGORITHM & TOKEN TYPE

The header carries 2 parts:
a. The hashing algorithm to use (HS256 or RS256).
b. Declaring the type (JWT).
    
Example : 

    {
      "alg": "HS256",
      "typ": "JWT"
    }
    
Encoded :

    eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9

### 2. PAYLOAD:DATA
There are multiple claims that can be provide. Including registered claim names, public claim names, and private claim 
names, more information [jwt claims](http://self-issued.info/docs/draft-ietf-oauth-json-web-token.html#RegisteredClaimName).

Example : 

    {
      "sub": "1234567890",
      "name": "John Doe",
      "admin": true
    }
    
Encoded :

    eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiYWRtaW4iOnRydWV9

### 3. VERIFY SIGNATURE
This signature is made up of a hash of the following components:
a. The header
b. The payload
c. Secret

Example : 

    var encodedString = base64UrlEncode(header) + "." + base64UrlEncode(payload);
    
    HMACSHA256(encodedString, 'secret');
    
Encoded :

    TJVA95OrM7E2cBab30RMHrHDcEfxjoYZgeFONFh7HgQ

Final, all part of JWT :

    eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiYWRtaW4iOnRydWV9.TJVA95OrM7E2cBab30RMHrHDcEfxjoYZgeFONFh7HgQ
