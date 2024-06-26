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
JSON | XML 
--|--|
JSON is simple to read and write |XML is less simple as compared to JSON
It also supports array |It doesn't supports array
JSON is more human-readable than XML files |XML is less human-readable
It supports only text & number datatype |It supports many datatype such as text, number, images, charts, graphs etc.


### NOTE :- 
There is a library provided by Postman that is called "pm".In pm library there are so many functions are available.

## Types of functions :-
There are two types of function we used in Postman to check any assertion on a API.
- Normal function
- Arrow function

Normal function | Arrow function
--|--|
pm.test("Test name", function()| pm.test("Test name",() =>
{                              |{
  //assertion;                 |  //assertion;
})                             |}

## Scripts :-
There are two place where we can write our scripts in Postman -
- Tests = (After request & response is completed)
- Pre-request scripts = (Executed before starting the request)

**Pre-request script------------>Request----------->Response-------------->Tests script**

Pre-request & test script is available in three levels -
1. Collection
2. Folder
3. Request

## Variable :-
We can create variables at following levels(scope) =>
1. Global - (accessible workspace level)
2. Collection - (accessible collection level)
3. Environment - (accessible all collections, but need to change environment)
4. Local - (accessible request level)
5. Data - (external files [CSV/text])

#### Important notes
- All local variables (request level variables) are created under `Pre-request script`.
- We can create `Global`,`Environment` & `Collection` variables under a request 

  For ex:- 
     `pm.environment.set("restful_local","https://restful-booker.herokuapp.com");`
- After creating `Global`,`Environment` & `Collection` variables under a request if we want to delete them after getting the response we use unset() in post-response section.

   For ex:- 
     `pm.globals.unset("variable name");`
- To get & print the all different variables data in console window enter the following script under post-response section -

      console.log(pm.globals.get("variable name"));
      console.log(pm.collectionVariables.get("variable name"));
      console.log(pm.environment.get("variable name"));
 

## Chaining of API's :-
"API chaining in Postman is a technique that allows you to extract data from the response of one API request and use it as input for another API request". 
This way, you can create a sequence of API calls that depend on each other and test complex scenarios without manually coping and pasting data.


     ┌───────────┐      ┌───────────┐      ┌───────────┐
     │ Request 1 │----->│  API 1    │----->│ Response  │
     └───────────┘      └───────────┘      └───────────┘
                                               │
                                               │
                                               ▼
     ┌───────────┐      ┌───────────┐      ┌───────────┐
     │ Response  │<-----│  API 2    │<-----│ Request 2 │
     └───────────┘      └───────────┘      └───────────┘


## Authorization :- 
We can add The `Bearer token` authorization at collection even instead of every request.

NOTE - For every request under that collection each request authorization must be set to [inherit auth from parent].

## What is Data-driven testing (DDT) :-

Data-driven testing (DDT) is a software testing methodology where test scripts are designed to execute a series of test cases using input data from external sources such as databases, spreadsheets, CSV files, or any other data repositories. The primary goal of data-driven testing is to increase test coverage by running the same test logic with multiple sets of data, thereby validating different scenarios and edge cases efficiently.

**Here's an explanation of how data-driven testing works:**

- Identify Test Scenarios: First, you identify the test scenarios that need to be validated. These scenarios can range from basic functionality to complex workflows.
- Define Test Data: Next, you gather or generate test data that covers various input combinations, including valid, invalid, and boundary cases. This data is typically stored externally in a format that can be easily accessed by the test script.
- Develop Test Scripts: You create test scripts that are capable of reading test data from external sources and executing the test logic for each set of data. These scripts should be designed to be reusable and modular to accommodate different data sets.
- Execute Tests: The test script iterates through each set of test data, feeding it into the system under test (SUT) and verifying the expected outcomes against the actual results. Each iteration of the test is considered a test case.
- Report Results: During test execution, results are captured for each test case, including pass/fail status and any relevant details or errors encountered. These results are then compiled into a test report for analysis.

## Benefits of Data-Driven Testing :-

1. Improved Test Coverage: DDT allows for testing a wide range of input data combinations, helping to identify defects in different scenarios and edge cases.
2. Reusability: Test scripts can be reused with different sets of data, reducing the effort required to maintain and update test suites.
3. Efficiency: By automating the execution of tests with multiple data sets, DDT helps save time and effort compared to manual testing.
4. Maintainability: Since test data is stored externally, it's easier to update or modify test cases without changing the underlying test logic.
5. Early Defect Detection: DDT helps in detecting defects early in the development cycle by running tests with diverse data sets, enabling quicker resolution of issues.
6. Overall, data-driven testing is a valuable approach for ensuring software quality by systematically testing various input combinations and scenarios, leading to more robust and reliable software products.


## How to perform DDT in postman :- 
In Postman, data-driven testing involves using external data sources to drive the execution of API tests. This is typically achieved using the "Collection Runner" feature in Postman combined with external data files like CSV, JSON, or spreadsheets.

**Here's how you can perform data-driven testing in Postman:**

- `Create API Tests:` First, create your API tests using Postman's intuitive interface. These tests can include requests to your API endpoints along with assertions to verify the expected responses.
- `Prepare Data Source:` Prepare your test data in an external file such as a CSV, JSON, or spreadsheet. Each row in the data file represents a set of input values for your API requests. For example, if you're testing a user registration endpoint, each row might contain different combinations of username, email, and password.
- `Set Up Environment Variables (Optional):` If your API requests use dynamic data (e.g., authentication tokens), you can set up environment variables in Postman to store and reuse this data across multiple requests.
- `Configure Collection Runner:` Open the Postman app and navigate to the collection containing your API tests. Click on the "Runner" button to open the Collection Runner. Here, you can select the collection to run and specify the data file to use for data-driven testing.
- `Run Tests:` Start the Collection Runner, and Postman will execute your API tests iteratively for each set of data from the data file. For each iteration, the variables in your requests will be replaced with values from the corresponding row in the data file.
- `View Results:` After the tests have completed execution, you can view the results in the Collection Runner interface. Postman will provide detailed information about the status of each request, including whether it passed or failed, along with any assertions that were evaluated.


## What is RestAssured :- 

RestAssured is a Java library that provides a domain-specific language (DSL) for writing powerful and maintainable automated tests for RESTful APIs. It simplifies the process of sending HTTP requests and validating responses, making it easier to perform integration testing on API endpoints.

Key features of RestAssured include:

1. **DSL for Requests**: Allows you to construct HTTP requests (GET, POST, PUT, DELETE, etc.) using a fluent interface, making the code readable and concise.

2. **Validation of Responses**: Provides built-in assertions to validate response status codes, headers, body content (JSON, XML, etc.), and more.

3. **Support for Authentication**: Supports various authentication mechanisms (basic, digest, OAuth, etc.) to simulate different authorization scenarios.

4. **Handling Cookies and Sessions**: Enables handling of cookies and sessions for scenarios requiring stateful interactions.

5. **Integration with Testing Frameworks**: Integrates seamlessly with popular testing frameworks like JUnit and TestNG, allowing API tests to be executed alongside other tests.

6. **Logging and Error Handling**: Includes logging capabilities for request/response details and provides mechanisms to handle errors gracefully.

RestAssured is widely used in automated testing for REST APIs due to its simplicity, expressiveness, and the ease with which tests can be written and maintained. It's particularly useful for API testing in Java-based projects where there's a need for comprehensive API validation and integration testing.


## Structure of Maven Project :-

A Maven project follows a specific directory structure that helps organize source code, resources, and configuration files in a standardized way. Here’s the typical structure of a Maven project along with explanations for each directory and file:

```
project-root
│
├── pom.xml
├── src
│   ├── main
│   │   ├── java
│   │   │   └── package
│   │   │       └── (source files)
│   │   ├── resources
│   │   │   └── (resource files)
│   │   └── webapp (for web applications)
│   │       └── (web application resources)
│   └── test
│       ├── java
│       │   └── package
│       │       └── (test source files)
│       └── resources
│           └── (test resource files)
└── target
    └── (compiled output and build artifacts)
```

### Explanation of the Structure:

1. **`pom.xml`**: This is the Project Object Model (POM) file for Maven. It is an XML file that contains information about the project and configuration details to build the project, such as dependencies, plugins, build profiles, and more.

2. **`src`**: This directory contains all the source code and resources for the project.

   - **`main`**: This directory contains the main source code and resources for your application.

     - **`java`**: Contains Java source files (.java) organized into packages. This is where your application’s Java code resides.

     - **`resources`**: Contains non-Java resources used by the application, such as property files, XML configuration files, etc.

     - **`webapp`** (for web applications): If your project is a web application, this directory contains resources like HTML files, JSP files, web.xml, and other static content.

   - **`test`**: This directory contains the test source code and resources.

     - **`java`**: Contains Java source files (.java) for unit tests. This mirrors the structure of the `main/java` directory but contains test-specific code.

     - **`resources`**: Contains resources required for testing, such as test-specific configuration files, test data files, etc.

3. **`target`**: This directory is where Maven stores all the compiled output, packaged JARs/WARs, and other build artifacts. It is created during the build process and typically contains subdirectories like `classes` (compiled .class files), `test-classes` (compiled test .class files), and the final artifact (e.g., `project-name.jar` or `project-name.war`).

## What is Gherkin language:-

Gherkin is a domain-specific language used in behavior-driven development (BDD) to describe software behavior without detailing how that functionality is implemented. It is used to write human-readable tests that describe the behavior of a system in a way that non-technical stakeholders can understand. Gherkin syntax is simple and structured to facilitate communication between technical and non-technical team members.

## Key Features of Gherkin :-

1. **Readable by Humans and Machines**: Gherkin is designed to be easy to read by both humans and machines, enabling clear communication between all stakeholders.
  
2. **Given-When-Then Structure**: Scenarios in Gherkin are written in a Given-When-Then format:
   - **Given**: Describes the initial context of the system.
   - **When**: Describes an action or event.
   - **Then**: Describes the expected outcome.

3. **Feature Files**: Gherkin scenarios are stored in feature files, which usually have a `.feature` extension.

4. **Keywords**: Common keywords in Gherkin include:
   - **Feature**: A high-level description of a software feature.
   - **Scenario**: A concrete example of a feature's behavior.
   - **Given**: The initial context or setup.
   - **When**: The action or event that triggers the behavior.
   - **Then**: The expected outcome.
   - **And**: Used to add more Given, When, or Then steps.
   - **But**: Used to add a negative condition to a step.

## Example of Gherkin Syntax :-

```gherkin
Feature: Login functionality

  Scenario: Successful login
    Given the user is on the login page
    When the user enters valid credentials
    Then the user is redirected to the dashboard

  Scenario: Unsuccessful login
    Given the user is on the login page
    When the user enters invalid credentials
    Then an error message is displayed
```

In this example:
- The **Feature** keyword provides a high-level description of the login functionality.
- Each **Scenario** provides a specific example of how the login functionality should behave under certain conditions.
- The **Given-When-Then** structure describes the steps for each scenario.

Gherkin is primarily used with BDD frameworks such as Cucumber, SpecFlow, and Behave, which parse the Gherkin feature files and execute the corresponding test code.

