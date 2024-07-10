---
title:  "Jsonp definition and example"
date:   2015-09-06 00:03:03
categories: Software-Engineering JSONP
summary: JSONP definition (wikipedia) and implementation example. 
---

JSONP (JSON with Padding) is a technique used to enable cross-domain communication in web applications by bypassing the same-origin policy enforced by web browsers. It involves making a request to a different domain that returns JSON data wrapped in a function call.

Here's a simple code example demonstrating how JSONP works:

1. Create a script tag dynamically to make a JSONP request.
2. Define a callback function to handle the JSON data received from the remote server.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JSONP Example</title>
</head>
<body>
    <div id="result"></div>

    <script>
        // Define the callback function to process the JSON data
        function handleResponse(data) {
            document.getElementById('result').innerText = JSON.stringify(data);
        }

        // Create a script tag for the JSONP request
        const script = document.createElement('script');
        const url = 'https://example.com/data?callback=handleResponse';
        script.src = url;

        // Append the script tag to the document to make the request
        document.body.appendChild(script);
    </script>
</body>
</html>
```

In this example:
- The `handleResponse` function is defined to handle the JSON data received from the server.
- A script tag is created dynamically with a `src` attribute pointing to the URL of the remote server endpoint that returns JSON data wrapped in the `handleResponse` function call.
- The script tag is appended to the document, triggering the request and executing the callback function with the JSON data returned from the server.

## Example (simple jQuery-driven AJAX call) :
The code snippet bellow uses jQuery's `$.ajax()` method to make a JSONP request to a remote server endpoint (`https://path/to/resource/`) and handle the response.

```javascript
$.ajax({
    url         : "https://path/to/resource/",
    dataType    : 'jsonp',
    crossDomain : true,
    success     : function (data) {
        $('#list').html(data.count + 'True');
    },
    error       : function (data) {
        $('#list').html('False');
    }
});
```

Here's an explanation of each part of the code:

1. `url: "https://path/to/resource/"`: Specifies the URL of the resource to which the AJAX request is made.

2. `dataType: 'jsonp'`: Indicates that the expected data type of the response is JSONP, allowing the browser to recognize the response as a JSONP callback.

3. `crossDomain: true`: Enables cross-domain requests, which is necessary for making requests to a different domain than the one hosting the web page.

4. `success: function(data) { ... }`: Defines a callback function that executes if the request is successful. It takes the `data` parameter, which contains the response from the server.

5. `$('#list').html(data.count + 'True');`: Sets the content of the element with the id `list` to the value of `data.count` concatenated with the string `'True'`. This will display the count received from the server followed by the word 'True'.

6. `error: function(data) { ... }`: Defines a callback function that executes if the request encounters an error.

7. `$('#list').html('False');`: Sets the content of the element with the id `list` to the string `'False'` if an error occurs during the request.

In summary, this code snippet uses jQuery's AJAX function to make a JSONP request to fetch data from a remote server, and based on the success or failure of the request, it updates the content of an HTML element with the relevant information.


---
> The kind of programming that C provides will probably remain similar absolutely or slowly decline in usage, but relatively, JavaScript or its variants, or XML, will continue to become more central. 
> <small>- [Dennis Ritchie](https://www.brainyquote.com/quotes/quotes/d/dennisritc274077.html)</small>
