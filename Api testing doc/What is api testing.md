## What is API testing:- 
API testing is a type of software testing that validates `Application Programming Interfaces (APIs)`. The purpose is to check the functionality, reliability, performance and security of the programming interfaces.
                        API testing is typically performed at the integration level, after unit testing is completed and before user interface testing begins.

## Types of APIs:- There are two types of APIs - 

1. Simple object access protocol (SOAP)
2. REST (Representational State Transfer)

SOAP supports only (XML) type of data but REST supports (XML, json, HTML and text) different types of data.

## Web services:-

When you keep an API on the Internet or if it is available on the web that is called web services." When you keep an API on the Internet and everyone can access it is called Web Services".

For ex -  
- google.com
- facebook.com

## REST API methods/HTTP requests:-
- get    -> request to the server to get a response (Retrieve the data from the database)
- post   -> sending our data to the server (Create new resource(data) on database)
- put    -> to update existing data (Update existing resource(data) on database)
- patch  -> Update partial details of resource
- delete -> delete the data (Delete existing resources from database)

## HTTP request/response:-
Communication between clients and servers is done by requests and responses -  
1. A client (browser) sends an HTTP request to web
2. Web server receives the request
3. Server runs an application to process the request
4. Server returns an HTTP response (output) to the browser
5. The client(browser) receives the response

For ex - **Request --------------- API ------------------ Response** 

## Postman - API testing tool
 We can do manual testing of API's using postman

 1. Workspace : Area where we maintain files and saved them, create workspace, rename, delete
 2. Collection: Contains number of folders and HTTP requests. Create, rename, delete run the collection we can create any number of collections under office workspace.
