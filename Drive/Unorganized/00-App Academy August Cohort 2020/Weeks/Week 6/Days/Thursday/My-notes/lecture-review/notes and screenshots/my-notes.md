# Why do we test

- Make collaboration easier

- Produce documentation

### The job of a testing framework is to run tests and present them to a user.

### An assertion library is the backbone of any written test - it is the code that we use to write our tests.

![](2020-09-17-11-09-33.png)

# Mocha

- ## Mocha is a JavaScript testing framework that specializes in running tests and presenting them in an organized user friendly way.
- ### The Mocha testing framework is widely used because of it's flexibility. Mocha supports a whole variety of different assertion libraries and DSL interfaces for writing tests in the way the best suites the developer.
- #### When writing tests with Mocha we will be using Mocha's DSL (Domain Specific Language). A Domain Specific Language refers to a computer language specialized for a particular purpose - in Mocha's case the DSL has been engineered for providing structure for writing tests.
- #### A DSL is it's own language that will usually be familiar but syntactically a little different from the languages you know.

[what you should be testing](https://kentcdodds.com/blog/how-to-know-what-to-test)

![](2020-09-17-01-10-39.png)

- unit tests ensure each piece of your application works in isolation
- if you know each piece works then you can more easily find errors.
- Unit tests are also fast.
- The bigger your application gets the longer your testing suite will take to run
- if all your tests are end-to-end tests your tests could be running for hours.

[testing pyramid](https://testing.googleblog.com/2015/04/just-say-no-to-more-end-to-end-tests.html)

## the most important thing about a test is that it is readable and understandable.

### Good tests use descriptive strings to enumerate what they are testing as well as how they are testing it.

![](2020-09-17-01-15-36.png)

- the outer function has a string with the name of a function avgValue() which is most likely the function we will be testing.
- Next we see a description string should return the average of an array of numbers.

#### So even without understanding the syntax for the test above we can tell what we are testing:

- the avgValue function, and how we are testing it
- should return the average of an array of numbers.

![](2020-09-17-01-18-06.png)

- The outer block mentions avg_value which is probably the method or function being tested
- the inner block says how things are being tested -
- **"should return the average of an array of numbers"**

# Test-Driven Development

In software engineering a collection of automated tests, _also known as **test suite**s_, are a common way to ensure that when a piece of code is run it will perform the minimum of a specified set of behaviors.

## Test-driven development or TDD

### TDD is a quick repetitive cycle that revolves around first determining what a piece of code should do and writing tests for that behavior before actually writing any code

#### Test-driven development dictates that tests, not application code, should be written first, and then application code should only be written to pass the already written tests.

- Imagine being handed a file of 10 functions that all invoke each other and being told to add a new function to the mix and ensure all the previous functions work properly.
  - First you'd have to figure out what each function actually did, then determine if they did what they were supposed to do.

### Using TDD is one way for developers to ensure that the code written by every member of their team is testable and modular.

- ## Here are some of the biggest motivations for why developers use test-driven development:

  1. Writing tests before code ensures that the code written works.

  - Code written to pass specs is guaranteed to be testable.
  - Code with pre-written tests easily allows other developers to add and test new code while ensuring nothing else breaks along the way.

  2. Only required code is written.

  - In the face of having to write tests for every piece of added functionality TDD can help reduce bloated un-needed functionality.

3.  TDD helps enforce code modularity.

- A TDD developer is forced to think about their application in small, testable chunks -
- this ensures the developer will write each chunk to be modular and capable of individual testing.

4.  Better understanding of what the code should be doing.

- Writing tests for a piece of code ensures that the developer writing that code knows what the piece of code is trying to achieve.

![](2020-09-17-01-30-49.png)

# JS Error Types: (use `open file` extension) (-- my-notes.js --)

## JavaScript Errors

- ### In JavaScript the Error constructor function is responsible for creating different instances of Error objects.

- ### The Error object is how JavaScript deals with runtime errors and the type of error created and thrown will attempt to communicate why that error occurred.

## Creating your own errors

- ### Since the Error constructor is just a constructor function we can use it to create new Error object instances with the following syntax:

![](2020-09-17-01-34-44.png)

### Throwing your own errors:

- #### Using the keyword throw you can throw your own runtime errors that will stop program execution.

![](2020-09-17-01-41-42.png)

![](2020-09-17-01-46-35.png)

### You can throw your newly created Error to stop program execution or use a try...catch block to catch your error and continue running your code.

![](2020-09-17-01-48-31.png)

## Types of JavaScript errors

![](2020-09-17-01-49-03.png)

1.  `SyntaxError` - represents an error in the
    syntax of the code.
2.  `ReferenceError` - represents an error thrown
    when an invalid reference is made.
3.  `TypeError` - represents an error when a
    variable or parameter is not of a valid type.
4.  `RangeError` - representing an error for when a
    numeric variable or parameter is outside of its valid range.
5.  `InternalError` - represents an error in the
    internal JavaScript engine.
6.  `EvalError` - represents an error with the
    global `eval` function.
7.  `URIError` - represents an error that occurs
    when `encodeURI()` or `decodeURI()` are passed invalid parameters.

## the three most common errors you have encountered so far:

- ### SyntaxError,
- ### ReferenceError, and
- ### TypeError.

![](2020-09-17-01-56-39.png)

[compile time errors can't be caught using try catch](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ReferenceError)

## Reference Error:

- ### The ReferenceError object represents an error when a non-existent variable is referenced
- ### This is the error that you'll encounter when attempting to reference a variable that does not exist (either within your current scope or at all).

## Another common cause for a thrown ReferenceError is attempting to access a variable that is not in scope:

![](2020-09-17-02-03-27.png)
![](2020-09-17-02-05-49.png)

## TypeError:

### (often if a function gets a type error we forgot to export it)

### attempt to invoke a declared but not assigned variable (which will evaluate to undefined).

![](2020-09-17-02-11-21.png)

### Next let's look at a example of attempting to change a value that cannot be changed:

![](2020-09-17-02-17-24.png)

## Catching known errors:

#### - how to use a try...catch block we can combine these two ideas to catch specific types of errors using instanceof:

![](2020-09-17-02-20-50.png)

# Writing Tests (WT) Part One: Mocha and Assert

- properly format and denote your mocha tests using
  `describe`, `context` and
  `it` blocks
- write tests for individual functions as well as writing tests for
  class instance and static methods
- test that functions will throw certain errors
- use `chai-spies` to test how many times a
  function has been called
- recognize and utilize the Mocha hooks: `before` ,
  `beforeEach` , `after` , and
  `afterEach`

- the file structure of testing with `Mocha`
- testing with `Mocha` and Node's built-in
  `Assert` module

## Part Zero: Testing file structure

We find that reading about testing is best understood when you can play
around within the functions being tested .

We started this reading by
created a directory called `testing-demo` where all
the code within this reading will be written.

Let's start off with how to write tests for a basic function. Say we've
been handed a directory with a function to test
`problems/reverse-string.js` . Below is the named
function we'll be testing, `reverseString` , which
will intake a string argument and then reverse it:

- ##The created test directory's file structure should mirror that of the files you intend to test
  - with each test file appending the word "spec" to the end of the file name.

![](2020-09-17-02-34-34.png)
![](2020-09-17-02-34-55.png)

## Part One: Writing tests with Mocha and Assert:

![](2020-09-17-11-29-03.png)

-concentrate on one spec at a time!!!

### The first step in any testing workflow is initializing our test file.

### Mocha is a test framework that specializes in running tests and presenting them in an organized user friendly way

### The code responsible for actually verifying things for us will come from using an **Assertion Library**.

- #### Assertion Libraries will do the heavy lifting of comparing and verifying code while Mocha will run those tests and then present them to us.

##### The tests we'll be writing for this next section will use Node's built-in Assert module as our Assertion Library.

- So inside of test/reverse-string-spec.js at the top of the file we will require the assert module and the function we intend to test:

![](2020-09-17-02-38-55.png)

[mocha doccumentation](https://mochajs.org/#getting-started)

- ##### DSL stands for DSL (Domain Specific Language)

- ##### we will be using the BBD interface for Mocha:
- [BBD interface](https://mochajs.org/#bdd)

#### INTERFACES

- Mocha’s “interface” system allows developers to choose their style of DSL. Mocha has BDD, TDD, Exports, QUnit and Require-style interfaces.

#BDD

- The BDD interface provides describe(), context(), it(), specify(), before(), after(), beforeEach(), and afterEach().

  - context() is just an alias for describe(), and behaves the same way; it provides a way to keep tests easier to read and organized. Similarly, specify() is an alias for it().

- The **describe function** is an organizational function that accepts _`a descriptive string and a callback`_.
- We'll use the describe function to describe what we will be testing -
- #### `in this case the reverseString function:`

![](2020-09-17-03-31-11.png)

### Now if we run mocha in the upper most testing-demo directory we will see:

![](2020-09-17-03-32-35.png)

```
Take notice of how Mocha structures its response in exactly the way we nested our test.
The outer describe function's message of reverseString() is on the upper level
and the inner it function's message of should reverse the input string is nested within.
Strictly speaking we aren't required to nest our it functions within describe functions but it is best practice to do so.
```

##### Let's add one more spec for reverseString,

- ##### we'll do this by adding another it function within the describe callback:
  ![](2020-09-17-04-08-03.png)
  ![](2020-09-17-04-09-06.png)
  ![](2020-09-17-05-24-00.png)
