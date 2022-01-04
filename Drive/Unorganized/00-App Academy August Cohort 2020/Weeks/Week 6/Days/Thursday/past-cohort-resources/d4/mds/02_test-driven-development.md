# Test-Driven Development

At this point of the course you have all encountered an automated test also
known as a "spec" - short for specification. In software engineering a
collection of automated tests, also known as test suites, are a common way to
ensure that when a piece of code is run it will perform the minimum of a
specified set of behaviors. We've used the JavaScript testing framework, Mocha,
up to this point to test the behavior of functions of all kinds from `myForEach`
to `avgValue` to ensure each function runs as intended.

The main question we should be able to answer when writing any piece of code is:
what does this code do? How should this code behave? One of the popular ways to
answer this question is through a software development process called
Test-driven development or TDD. TDD is a quick repetitive cycle that revolves
around _first_ determining what a piece of code should do and writing tests for
that behavior _before actually writing any code_.

_Test-driven development_ dictates that tests, not application code, should be
written first, and then application code should only be written to pass the
already written tests. When you finish this reading you should be able to
identify the three steps of Test Driven Development as well as identify the
advantages of using TDD to write code.

## Motivations for TDD

Imagine being handed a file of 10 functions that all invoke each other and being
told to add a new function to the mix and ensure all the previous functions work
properly. First you'd have to figure out what each function actually did, then
determine if they did what they were supposed to do. Sounds like a total pain
right? A modern web application is thousands of lines of code that are worked on
and maintained by teams of developers. Using TDD is one way for developers to
ensure that the code written by every member of their team is testable and
modular.

Here are some of the biggest motivations for why developers use test-driven
development:

1. Writing tests before code ensures that the code written _works_.
   - Code written to pass specs is guaranteed to be testable.
   - Code with pre-written tests easily allows other developers to add and test
     new code while ensuring nothing else breaks along the way.
2. Only required code is written.
   - In the face of having to write tests for every piece of added functionality
     TDD can help reduce bloated un-needed functionality.
   - TDD and YAGNI ("you ain't gonna need it") go hand in hand!
3. TDD helps enforce code modularity.
   - A TDD developer is forced to think about their application in small,
     testable chunks - this ensures the developer will write each chunk to be
     modular and capable of individual testing.
4. Better understanding of _what_ the code should be doing.
   - Writing tests for a piece of code ensures that the developer writing that
     code knows what the piece of code is trying to achieve.

Now that we've covered why developers would want to use TDD let's go into _how_
to do TDD.

## The three steps of TDD: red, green, refactor!

![tdd-cycle][rgr]

The Test-driven development workflow can be broken down intro three simple
steps. **Red, Green, Refactor**:

1. **Red**: Write the tests and watch them fail (a failing test is red). It's
   important to ensure the tests initially fail so that you don't have false
   positives.
2. **Green**: Write the minimum amount of code to ensure the tests pass (a
   passing test will be green).
3. **Refactor**: Refactor the code you just wrote. Your job is not over when the
   tests pass! One of the most important things you do as a software developer
   is to ensure the code you write is easy to maintain and read.

Generally, the TDD workflow loop of Red, Green, Refactor is quick. TDD
developers will write small tests ensuring each individual part of their
application works properly and their code looks good before moving on - making
for a short development cycle.

[rgr]:
  https://appacademy-open-assets.s3-us-west-1.amazonaws.com/Module-JavaScript/testing/assets/rgr.png

## What you learned

TDD stands for test-driven development. TDD is a repetitive process that
revolves around three steps: Red, Green, Refactor.
