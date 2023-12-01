# JSON Project: Climbing Shoes Database 

## Overview:
* This script essentially sends a GET request to the specified URL with the provided headers and logs the response body to the console. The result returns all of the documents from the climbing shoes collection database. 

## Import Module:
* The request module is imported to make HTTP requests.

## Configure Request Options:
* Options object is created to specify the details of the HTTP request.
* This includes the HTTP method (GET), the URL to make the request to, and headers such as cache control and API key for authentication.

## Make HTTP Request: 
* The request function is called with the specified options and a callback function.
* The callback function handles the response or any errors that may occur during the request.

## Handle Errors: 
* If there is an error during the request, it is caught and then thrown.

## Log Response:
* The reponse body is logged to the console. 

```
// Import the 'request' module
var request = require("request");

// Configure the options for the HTTP request
var options = {
    method: 'GET',  // HTTP method is GET
    url: 'https://inventory-fac4.restdb.io/appdeploy/climbingshoes',  // URL to make the request to
    headers: {   // Headers for the request
        'cache-control': 'no-cache',  // Disable caching
        'x-apikey': '560bd47058e7ab1b2648f4e7'  // API key for authentication
    } 
};

// Make the HTTP request using the 'request' module
request(options, function (error, response, body) {
    // Check for errors during the request
    if (error) {
        throw new Error(error);  // Throw an error if there is an issue
    }

    // Log the response body to the console
    console.log(body);
});

```
