# Overview

This repository is a part of the Java language training plan. Please read the following guidelines before start.

# Getting Start

## Basic Principals

Each repository contains a gradle java project with a number of unit tests. The initial state of all unit tests are *FAILED*. So the aim is to correct the failed test. Please follow the following steps to get the best experience:

* Read the test code and try to understand what it says.
* Trying to fix the test **WITHOUT RUNNING**. This is very important. Because once you run the test, you may find the failure message of the test telling you the expected result. That means you may lose the chance to figure it out by yourself. Note that you should **ONLY** be able to modify code within the **TODO AREA**. The code outside the **TODO AREA** is **NOT** changable.
* Run the test to examine if the fix is correct.
* Answer the following 4 questions after the test is passed.

The 4 questions are:

1. What is the knowledge point of the test? Where is the offical document to the knowledge point?
1. Why the test failed at first?
1. Why you corrected the test that way?
1. Do you have further questions on this knowledge point?

## Example

Let's take a look at an example:

```java
@Test
void should_pass_by_value() {
  int value = 5;

  tryingToUpdateValue(value);

  // TODO: please modify the following code to pass the test
  // <--start
  final int expected = 0;
  // --end-->

  assertEquals(expected, value);
}
```

First, read the test. From the title and code we can know that the test what to examine the behavior when passing an argument. We are not sure what `tryingToUpdateValue` does, so we can jump into its implementation:

```java
private static void tryingToUpdateValue(int value) {
  value += 2;
}
```

Now we have got the full context of the test. The argument is passed by value so the integer will be copied when passing into `tryingToUpdateValue`. Thus the value from the caller site will not change.

Notice that the todo area is in the test method. So we can modify codes within the todo area to pass the test:

```java
  // TODO: please modify the following code to pass the test
  // <--start
  final int expected = 5;
  // --end-->
```

Please note that not all todo areas are located in test method. And some todo area may have further restrictions, for example:

```java
  // TODO: You should not write concrete number here. Please find a property or constant instead.
  // <!--start
  final int maximumSymbol = 0;
  final int minimumSymbol = 0;
  // --end-->
```

The hint indicates that we should not write concrete number here. So I should not write `3` or `0xffffffff`, but write symbol (e.g. `Integer.MAX_VALUE`).

## Running Test

You could run unit tests with the help of IntelliJ. But it is also possible to run unit test via command line: `./gradlew build`.

If you just want to build your code without running test. Please use `./gradlew build -x test
`
****Answer****
1. should_be_immutable
  What is the knowledge point of the test? Where is the official document to the knowledge point? 
  - The knowledge point of the test is to know about the behavior of optional list and on how it return value. 
    And on how to replace certain value in a string. 
  - The test failed because it's returning null. 
  Why you corrected the test that way?
  - I use Optional.of() because the data type of expected return is in boolean. 
  Do you have further questions on this knowledge point?
  - none. 
  
2. all_modification_method_will_create_new_string
 What is the knowledge point of the test? Where is the official document to the knowledge point? 
 - The knowledge point of the test is to know about the behavior of optional list and on how it return value. 
  And on how the to trim trailing spaces. 
 - The test failed because it's returning null. 
 Why you corrected the test that way?
 - I use Optional.of() because the data type of expected return is in boolean. 
 Do you have further questions on this knowledge point?
 - none.  
     
3. will_create_new_string_when_concat
 What is the knowledge point of the test? Where is the official document to the knowledge point? 
 - The knowledge point of the test is to know about the behavior of optional list and on how it return value. 
  And on how to create new string when concat
 - The test failed because it's returning null. 
 Why you corrected the test that way?
 - I use Optional.of() because the data type of expected return is in boolean. 
 Do you have further questions on this knowledge point?
 - none. 
 
 4. should_taken_string_apart
  What is the knowledge point of the test? Where is the official document to the knowledge point? 
  - The knowledge point of the test is to know how to  use substring. 
  Why the test failed at first?
  - The test failed because it's returning null value. 
  Why you corrected the test that way?
  - I used substring to get specific word that is same in the expected result. 
  Do you have further questions on this knowledge point?
  - none. 
********Additional question in String apart******** 
  What if the input arguments is out of range of the string?
  - It return no value. 
  What will happen if the the starting index is greater than the ending index?
  - It will failed and shows your inputed begin and end index and the exact length of the string. 
  What will happen if the input string is of null reference?
  - It return no value. 
  
  5. should_taken_string_apart_continued
    What is the knowledge point of the test? Where is the official document to the knowledge point? 
    - The knowledge point of the test is to know how to  use substring. 
    Why the test failed at first?
    - The test failed because it's returning null value. 
    Why you corrected the test that way?
    - I used substring to get specific word that is same in the expected result. 
    Do you have further questions on this knowledge point?
    - none. 
  ********Additional question in String apart******** 
    What if the input arguments is out of range of the string?
    - It return no value. 
    What will happen if the the starting index is greater than the ending index?
    - It will failed and shows your inputed begin and end index and the exact length of the string. 
    What will happen if the input string is of null reference?
    - It return no value. 
    
    6. should_break_string_into_words
      What is the knowledge point of the test? Where is the official document to the knowledge point? 
      - The knowledge point of the test is to know how to break string into words using delimiters and put it in array.  
      Why the test failed at first?
      - The test failed because it's returning null value. 
      Why you corrected the test that way?
      - I used split and delimeter space to split the sentence that will be put in the array.  
      Do you have further questions on this knowledge point?
      - none. 
      
     7. should_break_string_into_words_customized
      What is the knowledge point of the test? Where is the official document to the knowledge point? 
         - The knowledge point of the test is to know how to break string into words using delimiters and put it in array.  
       Why the test failed at first?
       - The test failed because it's returning null value. 
       Why you corrected the test that way?
       - I used split and delimeter "/" to split the sentence that will be put in the array.  
       Do you have further questions on this knowledge point?
       - none. 

    8.
    9.
    10
    11. should_reverse_a_string
       What is the knowledge point of the test? Where is the official document to the knowledge point? 
         - The knowledge point of the test is to know how to reverse a string through creating new string. 
       Why the test failed at first?
       - The test failed because it's returning null value. 
       Why you corrected the test that way?
       - I reversed the string using string buffer class. 
       Do you have further questions on this knowledge point?
       - none. 
       
    12. should_compare_string_with_different_cases
      What is the knowledge point of the test? Where is the official document to the knowledge point? 
        - The knowledge point of the test is to know how to compare string using cases and comparing string ignoring case.
      Why the test failed at first?
      - The test failed because it's returning null value. 
      Why you corrected the test that way?
      - actualResultOfEqual is false because it comparing the 2 sting. 
      - actualResultOfEqualIgnoreCase is true because it comparing the word value and ignoring the case. 
      Do you have further questions on this knowledge point?
      - none. 
      
     13. should_format_string
       What is the knowledge point of the test? Where is the official document to the knowledge point? 
         - The knowledge point of the test is to know how to format the string through assigning variable value. 
       Why the test failed at first?
       - The test failed because it's returning null value. 
       Why you corrected the test that way?
       - I input the correct ansswer when the string was format. 
       Do you have further questions on this knowledge point?
       - none. 
       


  

 