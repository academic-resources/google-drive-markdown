# Well-Tested Full-Stack To-Do Items

In this project, you will test a full-stack JavaScript and HTML application! You
will write tests to make sure the code that was written for the project will
meet the expectations of the requirements. Your tests will not have to be
exhaustive. Instead, there are guidelines for your tests in each test file. Use
those guidelines to implement the Web application.

The upcoming video provides you a full walk-through of the system as it is
created. Then, once you understand how the application works from watching it
be built, you will need to apply your knowledge of writing tests.

It may be hard. However, stick with it. You'll do great. Just take your time,
write good tests, and you will be amazed at how much confidence that you will
gain in writing code that comes together.

One of the ways that you can make this project more enjoyable is to vary the
way that you pair on it. For each step,

- Discuss what the next feature is that you want to write
- One person writes a unit test to test the code
- Both examine the code and determine if there is any duplication to refactor
  into common functions or classes
- Loop, but swap who writes the unit test and who writes the code

At the end, you will leverage your test by swapping out the mechanism used to
generate the HTML. This is the other part of writing good tests: tests give you
the confidence to change code. If you do something that is "wrong" in that it
breaks current expectations, the tests will tell you!

Tests are such an important part of a developers life. While some developers
will complain about having to write them, when you start working on an existing
"legacy" code base, making changes can cause a lot of stress unless you have the
work of other developers' tests to make sure you don't unintentionally change a
method in such a way to break code that you're not working on.

To get started,

- clone the project from
  https://github.com/appacademy-starters/testing-an-existing-app-project
- change directory into the project
- run `npm install` to install the modules

If you want to run the server, type `node server.js` and go to
http://localhost:3000/items to see what it does. You can add categories, add
items, search for items, and complete items.

The code that you will test are the functions used to create the functionality
of the data and the creation of the views, not the actual HTTP server. The
video after shows a person writing the entire application. You will see what
each piece does. Then, you will understand the _intent_ of the code that you
have to test.
