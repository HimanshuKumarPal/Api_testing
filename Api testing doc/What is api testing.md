## What is API testing :- 
API testing is a type of software testing that validates `Application Programming Interfaces (APIs)`. The purpose is to check the functionality, reliability, performance and security of the programming interfaces.
                        API testing is typically performed at the integration level, after unit testing is completed and before user interface testing begins.

## Types of APIs:- There are two types of APIs :- 

1. Simple object access protocol (SOAP)
2. REST (Representational State Transfer)

SOAP supports only (XML) type of data but REST supports (XML, json, HTML and text) different types of data.

## Web services :-

When you keep an API on the Internet or if it is available on the web that is called web services." When you keep an API on the Internet and everyone can access it is called Web Services".

For ex -  
- google.com
- facebook.com

## REST API methods/HTTP requests :-
- get    -> request to the server to get a response (Retrieve the data from the database)
- post   -> sending our data to the server (Create new resource(data) on database)
- put    -> to update existing data (Update existing resource(data) on database)
- patch  -> Update partial details of resource
- delete -> delete the data (Delete existing resources from database)

## HTTP request/response :-
Communication between clients and servers is done by requests and responses -  
1. A client (browser) sends an HTTP request to web
2. Web server receives the request
3. Server runs an application to process the request
4. Server returns an HTTP response (output) to the browser
5. The client(browser) receives the response

For ex - **Request --------------- API ------------------ Response** 

## Postman - API testing tool
 We can do manual testing of API's using postman

 1. Workspace: Area where we maintain files and saved them, create workspace, rename, delete
 2. Collection: Contains number of folders and HTTP requests. Create, rename, delete run the collection we can create any number of collections under workspace.

``` table

    [/"host or domain"/] ->["https//reqres.in"]
    ["Path paremeter"] ->["/api/users?"]
    ["Query parameter"] ->["page=2"]

```

```json:table
{
    "items" : [
      {"Host": "www.example.com", "Path": "/api/v1", "Query Parameter": "?api_key=12345&format=json"},
      {"Host": "api.github.com", "Path": "/users/octocat", "Query Parameter": "?per_page=10&sort=desc"}
    ]
}
```
## Cookies :- 
Cookie is nothing just internet files(temporary files) that are created by the browsers which contains some data.

## Response validations :-
- Status code
- Headers
- Cookies
- Response time
- Response body

## HTTP Status codes :-
There are three levels of status codes -
1. 200 = Successful requests
2. 400 = Unauthorized access
3. 500 = Server or network error

Level 200 | Level 400 | Level 500
--|--|--|
200: OK |400: Bad request |500: Internal server error 
201: Created |401: Unauthorized |501: Not implemented 
202: Accepted |403: Forbidden |502: Bad gateway 
203: Non-authoritative information |404: Not found |503: Service unavailable 
204: No content |409: Conflict |504: Gateway timeout, 599: Network timeout

## How to create our Own API's :-
- Install node.js
  - check node & npm through command line after installation:
     1. `node --version Or node -v`
     2. `npm --version Or npm -v`

- Install json-server through command line
  - `npm install -g json-server`

- Now select any json file location & open it in the command line & after that run the following command-
  - `json-server (file name)` example - `json-server Addpatients.json`

### NOTE - JSON - `"Javascript Object Notation"`
## What is JSON :-
- JSON is a syntax for storing and exchanging data
- Designed for human-readable data interchange
- JSON is a text, written with javascript object notation
- The file name extension is `.json`
- JSON internet Media type is application/json.

## Use of JSON :- 
Whenever you are communicating between client and server the data will be communicated through JSON/XML format.

## JSON data types :-
- Number = 36
- String = "Ram"
- Boolean = `true`,`false`
- Null = null(unknown value)
- Object = Contains multiple key & value pairs
- Array =  One key with multiple value [12342,2322]

In JSON we have to represent data in the form of `["Key" : "Value"]` pair.

## JSON vs XML :-
