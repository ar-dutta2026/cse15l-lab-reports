# Lab Report 2 #
------
## Part 1: StringServer.java ## 
---- 
Below is the code I used to allow StringServer.java to function. 

<img width="1728" alt="Screen Shot 2023-01-29 at 8 16 51 PM" src="https://user-images.githubusercontent.com/112745073/215386796-fd69dfeb-58c2-4b25-b2e2-12bbc0468a84.png">

#### Example Cases ####

<img width="1728" alt="Screen Shot 2023-01-29 at 8 27 07 PM" src="https://user-images.githubusercontent.com/112745073/215390388-dd939dfc-161d-4e17-8143-61ced3b3c543.png">

Initially the stringServer class is called, along with main. The main method of stringserver creates the local host website with the designated number. Afterwards the class Handler is called with the method handleRequest. 

The first argument it passes through is the one that checks if there is anything proceeding the \ after the number. If not it returns what the list of strings are (if it's 0 it will return "Aritra's list is null"). 
The next argument is checks to see if there is a path proceeding after the "\", if the path is invalid (i.e. not \add-message?s= ), then it will return 404 Not Found.

Since there is an \add-message?s=, it proceeds into the argument, where it will now process the "have a good day"! message, and add it as a String object into the String ArrayList. Now when going back to the home page you would see the string object showing on the localhost website. 

The URI changes per request so now the current URI is "/add-message?s=have a good day!". The String value parameter[1] also changes to "have a good day!".


<img width="1728" alt="Screen Shot 2023-01-29 at 8 53 15 PM" src="https://user-images.githubusercontent.com/112745073/215390436-864204a4-566e-4eef-9aaa-55f0c8a1ecdc.png">

Here, the handleRequest method is called. 

As shown previously, the first argument  is the one that checks if there is anything proceeding the \ after the number, in this case there is as there is an /add-message?s=, This goes on to the next arguement where it detects that there is an /add-message in the url. 

Since there is an \add-message?s= it proceeds into the arguement where the message "you too" is now processed, and turned into a string object into a String Arraylist. In the home screen it will now showcase this message. 

The URI changes again here as this is a new request with a different message to be entered, the current URI is /add-message?s=you too! The string value parameter[1] also changed to the new message "you too!". 


------
## Part 2: J-Unit Bug Testing ## 
---- 
### Failure Inducing Input for the Buggy Program ###
````
public void mergeTest(){
        List<String> tester = new ArrayList<>();
        tester.add("a");
        tester.add("d");
        tester.add("f");
        List<String> t2 = new ArrayList<>();
        t2.add("b");
        t2.add("c");
        t2.add("e");
        t2.add("z");
        List<String> example = new ArrayList<>();
        example.add("a");
        example.add("b");
        example.add("c");
        example.add("d");
        example.add("e");
        example.add("f");
        example.add("z");
        assertEquals(example,ListExamples.merge(tester,t2));
    }
```` 


Result of Running the test
<img width="1728" alt="Screen Shot 2023-01-29 at 11 36 06 PM" src="https://user-images.githubusercontent.com/112745073/215415390-4c7d365d-e11e-4ed8-83da-9c9c44d8e497.png">


### Input that does not induce failure ### 
````
public void mergeTest(){
        List<String> tester = new ArrayList<>();
        tester.add("a");
        tester.add("d");
        tester.add("f");
        List<String> t2 = new ArrayList<>();
        t2.add("b");
        t2.add("c");
        t2.add("e");
        List<String> example = new ArrayList<>();
        example.add("a");
        example.add("b");
        example.add("c");
        example.add("d");
        example.add("e");
        example.add("f");
        assertEquals(example,ListExamples.merge(tester,t2));
    }
 ````

Result of running the J-Unit Test

<img width="1728" alt="Screen Shot 2023-01-29 at 11 37 09 PM" src="https://user-images.githubusercontent.com/112745073/215415624-4e31361a-1746-463b-8a2d-4b6f215a5727.png">

### The Bug that caused the error ###
````
  static List<String> merge(List<String> list1, List<String> list2) {
    List<String> result = new ArrayList<>();
    int index1 = 0, index2 = 0;
    while(index1 < list1.size() && index2 < list2.size()) {
      if(list1.get(index1).compareTo(list2.get(index2)) < 0) {
        result.add(list1.get(index1));
        index1 += 1;
      }
      else {
        result.add(list2.get(index2));
        index2 += 1;
      }
    }
    while(index1 < list1.size()) {
      result.add(list1.get(index1));
      index1 += 1;
    }
    while(index2 < list2.size()) {
      result.add(list2.get(index2));
      index1 += 1; //The bug in the code
    }
    return result;
  }
````


### The bug is fixed in the following code ##

````
  static List<String> merge(List<String> list1, List<String> list2) {
    List<String> result = new ArrayList<>();
    int index1 = 0, index2 = 0;
    while(index1 < list1.size() && index2 < list2.size()) {
      if(list1.get(index1).compareTo(list2.get(index2)) < 0) {
        result.add(list1.get(index1));
        index1 += 1;
      }
      else {
        result.add(list2.get(index2));
        index2 += 1;
      }
    }
    while(index1 < list1.size()) {
      result.add(list1.get(index1));
      index1 += 1;
    }
    while(index2 < list2.size()) {
      result.add(list2.get(index2));
      index2 += 1; //The bug in the code
    }
    return result;
  }
````

This fixes the issue as before when it was index1 +=1, it resulted in an infinite loop as index2 would always be less than list2.size(), and it would continually add 1 and nothing would stop it. Turning it to index2 would allow the while statement to run the way it was meant to be, and be able to effectively combine lists of different length. 

------
## Part 3: Reflection ## 
---- 

From week one and week two I learned a great deal about github. I learned how to effectively use github as a tool, and learned the fundementals behind github desktop as well. Additionally, I was able to learn how to effectively use J-Unit to find the bugs in code. 
