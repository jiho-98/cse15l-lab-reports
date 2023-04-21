# CSE-15L Lab Report 2
This is lab report 2 for CSE-15L course from Jiho Kim.
## 1) PART 1
![lab_report_2 4](https://user-images.githubusercontent.com/129816454/233743743-c036a90f-0e5a-4103-b29d-6ec3fefd925b.png)
### The methods called in the code
* `HandleRequest`: This method is called when the server receives an HTTP request from a user. It takes a URI object representing the URL of the request and return string    
* `String`: representing the response to send back to the user.
* `Main`: This method is the entry point of the program. It takes an array of String arguments and starts the server on the specified port using a new instance of the Handler class.
### The relevant arguments and values for the methods and fields
* The function called **"HandleRequest"** is used in the part 1.
* `handleRequest(URI url)`: this method is called by the server to handle incoming HTTP requests. The URI argument represents the request URL. 
* `messageBuilder`: a StringBuilder object used to append and store messages passed in through the /add-message path.
* `url.getQuery()`: returns the query component of the URL as a string.
* `url.getPath()`: returns the path component of the URL as a string.
* `String.format()`: formats a string with variables to be inserted into the string.
* `Integer.parseInt()`: converts a string representation of an integer to an actual integer value.
### Changes for Part 1
* If the path is "/add-message", the value of the StringBuilder messageBuilder field will be changed. The query string of the URI is parsed to extract the value of the message parameter. 
* The value of messageBuilder is then appended with this parameter value, with a newline character appended to the existing value if the messageBuilder already has a non-zero length. 
* The new value of messageBuilder is then returned as a string in the response.
### Example
![lab_report_2 1](https://user-images.githubusercontent.com/129816454/233746955-bfa94262-b81d-4291-9acd-ce2c81dcdf75.png)
* The query string of the URI is parsed to extract the value of the message parameter
* The messageBuilder has zero lenght since this is first, messsageBuilder is returned as a string in the response






