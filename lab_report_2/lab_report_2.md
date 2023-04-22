# CSE-15L Lab Report 2
This is lab report 2 for CSE-15L course from Jiho Kim.
## 1) PART 1
![lab_report_2 4](https://user-images.githubusercontent.com/129816454/233743743-c036a90f-0e5a-4103-b29d-6ec3fefd925b.png)
* This is a code that I modify in VScode for PART 1
---
## The requests "add-message?s=String" for PART 1
 `/add-message?s=Jiho`
![lab_report_2 1](https://user-images.githubusercontent.com/129816454/233746955-bfa94262-b81d-4291-9acd-ce2c81dcdf75.png)    
---
  `/add-message?s=is`
![lab_report_2 2](https://user-images.githubusercontent.com/129816454/233747190-1ca335ea-396e-4c00-93bc-524772227c68.png)     
--- 
  `/add-message?s=Korean`
![lab_report_2 3](https://user-images.githubusercontent.com/129816454/233747363-ce236fb2-86fc-4e49-a84d-c156cb0181d5.png)    
---
### The methods called in the code
* `HandleRequest`: This method is called when the server receives an HTTP request from a user. It takes a URI object representing the URL of the request and return string    
* `String`: representing the response to send back to the user.
* `Main`: This method is the entry point of the program. It takes an array of String arguments and starts the server on the specified port using a new instance of the Handler class.
---
### The relevant arguments and values for the methods and fields and commands
* The function called **"HandleRequest"** is used in the part 1.
* `handleRequest(URI url)`: this method is called by the server to handle incoming HTTP requests. The URI argument represents the request URL. 
* `messageBuilder`: a StringBuilder object used to append and store messages passed in through the /add-message path.
* `url.getQuery()`: returns the query component of the URL as a string.
* `url.getPath()`: returns the path component of the URL as a string.
* `String.format()`: formats a string with variables to be inserted into the string.
* `Integer.parseInt()`: converts a string representation of an integer to an actual integer value.
* `javac Server.java NumberServer.java`: "javac Server.java NumberServer.java" are used to compile two Java source code files, "Server.java" and "NumberServer.java", into bytecode that can be executed by the Java Virtual Machine (JVM).
* `java NumberServer port(integer value)`: is used to start the execution of the Java program compiled from the "NumberServer.java" source code file, and it specifies the port number as an argument to the program.
---
### Changes for Part 1
* If the path is "/add-message", the value of the StringBuilder messageBuilder field will be changed. The query string of the URI is parsed to extract the value of the message parameter. 
* The value of messageBuilder is then appended with this parameter value, with a newline character appended to the existing value if the messageBuilder already has a non-zero length. 
* The new value of messageBuilder is then returned as a string in the response
---
## 2) PART 2
### Reversed Array Bug from the lab 3
---
* A failure-inducing input
```java
import static org.junit.Assert.*;
import org.junit.*;

public class ArrayTests {
  @Test
  public void testReversed() {
    int[] input1 = null;
    assertArrayEquals(new int[]{}, ArrayExamples.reversed(input1));
  }
}
```
* An input does not induce a failure
```java
import static org.junit.Assert.*;
import org.junit.*;

public class ArrayTests {
  @Test
  public void testReversed() {
    int[] input1 = {1,2,3,4,5};
    assertArrayEquals(new int[]{5,4,3,2,1}, ArrayExamples.reversed(input1));
  }
}
```
* The symptom of the image is that "cannot read the array" because parameter is null
![lab_report_2 5](https://user-images.githubusercontent.com/129816454/233754766-3e2b797d-d515-48a3-8382-59f9ccb164d8.png)
* The symtom of image is that the second element in the array should be 4 but it was 5
![lab_report_2 6](https://user-images.githubusercontent.com/129816454/233754778-c3fa1d75-ff8f-4488-9198-70c9f7fe6172.png)
---
* fix the bug
* Code that is before fix the bug
```java
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
* Code that is after fix the bug
```java
public static void reversedInPlace(ArrayList<Integer> arr, int Size) {
    Stack<Integer> s = new Stack<>();

    for (int i = 0; i < Size; i++) {
        s.push(arr.get(i));
    }
    int i = 0;
    while (!s.empty()) {
        arr.set(i, s.pop());
        i++;
    }
  }
}
```









