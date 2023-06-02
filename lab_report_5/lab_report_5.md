# CSE-15L Lab Report 5
This is lab report 5 for CSE-15L course from Jiho Kim.
## PART 1) Debugging Scenario
### What environment are you using (computer, operating system, web browser, terminal/editor, and so on)?
* I am using VScode, the operation system of my labtop is window
* I am using git-bash terminal in VScode    
### Detail the symptom you're seeing. Be specific; include both what you're seeing and what you expected to see instead. Screenshots are great, copy-pasted terminal output is also great. Avoid saying “it doesn't work”.
* I expect to see the array lists are in the reverse order by using a data-structure name "Stack"
* By debugging in a Junit test, it seems to be the array lists are not in the reverse order
* Below is a screenshot of the output
![1](https://github.com/jiho-98/cse15l-lab-reports/assets/129816454/87e3d975-59d8-4590-b3c5-a2e7588b528e)    
### Detail the failure-inducing input and context. That might mean any or all of the command you're running, a test case, command-line arguments, working directory, even the last few commands you ran. Do your best to provide as much context as you can.
* This is the code for testing j-unit
```console
dudwl@DESKTOP-JNKL4JN MINGW64 ~/Documents/GitHub/lab3 (main)
$ javac -cp ".;lib/hamcrest-core-1.3.jar;lib/junit-4.13.2.jar" *.java

dudwl@DESKTOP-JNKL4JN MINGW64 ~/Documents/GitHub/lab3 (main)
$ java -cp ".;lib/junit-4.13.2.jar;lib/hamcrest-core-1.3.jar" org.junit.runner.JUnitCore ArrayTests
```
* This is a code in the ArrayExamples.java
```java
import java.util.*;
import java.util.ArrayList;
public class ArrayExamples {

  // Changes the input array to be in reversed order
  public static void reversedInPlace(ArrayList<Integer> arr, int Size) {
    Stack<Integer> s = new Stack<>();
    
    for (int i = arr.size()-1; i >= 0; i--) {
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
* This is an ArrayTests.java
```java
import static org.junit.Assert.*;
import org.junit.*;
import java.util.*;
import java.util.ArrayList;
public class ArrayTests {
  @Test 
	public void testReverseInPlace() {
    ArrayList<Integer> arr = new ArrayList<>(Arrays.asList(1, 2, 3, 4, 5));
    ArrayExamples.reversedInPlace(arr, arr.size());
    assertArrayEquals(new int[]{5,4,3,2,1},arr.stream().mapToInt(i -> i).toArray());
	}
}
```
* This is my pwd 
```java
dudwl@DESKTOP-JNKL4JN MINGW64 ~/Documents/GitHub/lab3 (main)
$ pwd
/c/Users/dudwl/Documents/GitHub/lab3
```    
---
### Response from a TA
* From TA: I think there an error in your code in the ArrayExamples. What is the feature of a stack? which element pop out the first in the stack? Make sure to understand the features of a stack completely!    
### Screenshot of fixed version
![4](https://github.com/jiho-98/cse15l-lab-reports/assets/129816454/0dba2ce3-3543-4dd8-a11c-6cfe349dfa6d)    
* The bug was logic error of a stack. Since, a stack first element that is pushed, would be the last element that will pop out.
* I error that I occured was if I put element in reverse way in stack, I thought it would give me a reverse array list. In fact, it will give a reverse way of expected array lists
### All information
##### The file&directory structure    
![2](https://github.com/jiho-98/cse15l-lab-reports/assets/129816454/cbc3348f-55bb-4be1-bc26-5401173d2357)
##### The content of each arraytest and arrayexample(those 2 are only used)
```java

import java.util.*;
import java.util.ArrayList;
public class ArrayExamples {

  // Changes the input array to be in reversed order
  public static void reversedInPlace(ArrayList<Integer> arr, int Size) {
    Stack<Integer> s = new Stack<>();

    for (int i = arr.size()-1; i >= 0; i--) {
        s.push(arr.get(i));
    }
    int i = 0;
    while (!s.empty()) {
        arr.set(i, s.pop());
        i++;
    }
  }
}


  // Returns a *new* array with all the elements of the input array in reversed
  // order
  /*static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    int left = 0;
    int right = arr.length - 1;
    int temp;
    
    while (left < right) {
        // swap the elements at the left and right indices
        temp = arr[left];
        arr[left] = arr[right];
        arr[right] = temp;
        
        // move the left and right indices toward each other
        left++;
        right--;
    }
    return newArray;
  }*/

  // Averages the numbers in the array (takes the mean), but leaves out the
  // lowest number when calculating. Returns 0 if there are no elements or just
  // 1 element in the array
  /*static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
   
    double lowest = arr[0];
    for(double num: arr) {
      if(num < lowest) { lowest = num; }
    }
    double sum = 0;
    for(double num: arr) {
      if(num != lowest) { sum += num; }
    }
    return sum / (arr.length - 1);
  }*/
```    
```java
import static org.junit.Assert.*;
import org.junit.*;
import java.util.*;
import java.util.ArrayList;
public class ArrayTests {
  @Test 
	public void testReverseInPlace() {
    ArrayList<Integer> arr = new ArrayList<>(Arrays.asList(1, 2, 3, 4, 5));
    ArrayExamples.reversedInPlace(arr, arr.size());
    assertArrayEquals(new int[]{ 5,4,3,2,1},arr.stream().mapToInt(i -> i).toArray());
	}
}
```    
##### The full lines of code to trigger the bug
```java
for (int i = arr.size()-1; i >= 0; i--) {
        s.push(arr.get(i));
    }
```    
##### The description of what to edit to fix the bug
* what I did to fix the bug is that I changed the for-loop. In the first place, I push the elements in the array from the end to first element
* I fixed it to push the elements in the array from the first to end
* The stack will pop the last-in element from a stack-list, therefore, the array now be reverse order
```java
  public static void reversedInPlace(ArrayList<Integer> arr, int Size) {
    Stack<Integer> s = new Stack<>();

    for (int i = 0; i < arr.size(); i++) {
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
---
## PART 2) Reflection
I've learned so many things in CSE-15L. Definitely, the numbers of commands, and how to add ssh keys to my laptop and remote server in GitHub. The useful thing was how to debug. The great thing was week6 that I made a program like a gradescope, which can grade the assignment. That was very impressive. Also, I learned how to make a comment on people's code as we did in the lab, comparing code with my code, I was able to recognize amazing ideas from the codes in my group folks. By using Java, we could also convert bash to java, so the bash comment worked in Java program by using only Java code, which was great to learn.





