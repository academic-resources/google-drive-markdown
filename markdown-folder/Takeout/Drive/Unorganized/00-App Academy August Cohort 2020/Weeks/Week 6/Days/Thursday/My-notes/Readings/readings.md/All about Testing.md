\*\*

# All About Testing!

Let's talk about _automated testing_ - the how, the what, and most
importantly the **why**. The general idea across all testing frameworks
is to allow developers to write code that would specify the behavior of
a function or module or class. We've reached a point in software
development where developers can now run test code against their
application code and have confidence that their code will work as
intended.

## Why do we test?

With tests, you can aggressively refactor with confidence. If
anything breaks, you'll know. And you'll know exactly what the
expectations are for the module you're refactoring, so as long as it
meets the specs, you're good.

> When you are writing automated tests for an application you are
> writing the _specfications_ of how that application should behave. In
> the software industry **automated tests are often called "specs"**

- _Make collaboration easier_

  Complex applications are built by teams of developers. It may be
  that not all those developers will actually get the chance to talk
  to one another

  Specs allow teams to have confidence that each module performs a
  specific task and reduces the need for expensive coordination. The
  specs themselves become an effective form of communication.

- _Produce documentation_

  If the tests are written well, the tests can serve as documentation
  for the codebase.

## How we Test

### Testing frameworks vs Assertion libraries

An important distinction to understand is the difference between a
**_testing framework_** and an **_assertion library_**

- The job of a testing
  framework is to **run** tests and present them to a user.

- An assertion
  library is the backbone of any written test

  - it is the code that we use
    to **write** our tests.
  - Assertion libraries will do the heavy lifting of
    comparing and verifying our code.
  - Some testing frameworks will have
    built in assertion libraries, others will need you to import an
    assertion library to use.

### Mocha

[`Mocha`](https://mochajs.org/#getting-started) is a
JavaScript _testing framework_ that specializes in _running_ tests and
presenting them in an organized user friendly way.

The
`Mocha` testing framework is widely used because of
it's flexibility.

`Mocha` supports a whole variety
of different assertion libraries and DSL interfaces for writing tests in
the way the best suites the developer.

When writing tests with Mocha we will be using `Mocha`'s [DSL](https://en.wikipedia.org/wiki/Domain-specific_language)
(Domain Specific Language). A Domain Specific Language refers to a
computer language specialized for a particular purpose - in
`Mocha` 's case the DSL has been engineered for
providing structure for writing tests. A DSL is it's own language that
will usually be familiar but syntactically a little different from the
languages you know. That being said you don't have to worry about
memorizing every single piece of syntax for writing tests - just get a
good grasp of the basics of testing and use the documentation to fill in
any knowledge gaps.

You've seen what `Mocha` looks like already because
all the specs for your assessments and projects so far have been written
utilizing `Mocha` as the testing framework.

We'll be talking more about different assertion libraries a little later
when we talk about _writing_ tests.

## What do we test?

So now that we talked about why we test and what we use to test...what
exactly do we test?

### Test the public interface

When you're trying to figure out what you should be testing, ask
yourself, "What is (or will be) the public interface of the module or
class I'm writing?" That is, what are the functions that the outside
world will have access to and rely on?

Ideally, you'd have thorough test coverage on the entire public
interface. When that's not possible, ensure that your tests cover the
most important and/or complex parts of that interface - that is, the
pieces that you need to make sure work as intended (and expected).

Kent Dodds has a [great
article](https://kentcdodds.com/blog/how-to-know-what-to-test) on how to
identify what you should be testing.

### The testing pyramid

A common metaphor used to group software tests into separate levels of
testing is the testing pyramid.

![test-pry](./All%20about%20Testing_files/image02.png)

Let's quickly go over each level before talking about the pyramid as a
whole:

- **Unit Tests**: The smallest unit of testing - used to test the
  smallest pieces of your application in isolation to ensure each
  piece works before you attempt to put those pieces together. Each
  unit test should focus on testing **one** thing. These are generally
  the fastest tests to write and run.
- **Integration Tests**: Once you have your unit tests in place you
  know each piece works in isolation - but what about when those
  pieces interact with each other? Integration tests are the next
  level up, they will test the interactions between two pieces of your
  application. Integration tests will ensure the units you've written
  work coherently together.
- **End-to-End (E2E) Tests**: End-to-end tests are the highest level
  of testing - these will test the whole of your application.
  End-to-end tests are the closest automated tests come to testing the
  an actual user experience of your application. These are generally
  the slowest tests to write and run.

For a real life example of how you'd utilize each of these tests imagine
coding a Chess game and wanting to test it. Unit tests would be best for
testing each class your wrote in isolation - like ensuring each piece's
instance methods work as you expect them to before involving them with
any other pieces. Next you'd write integration tests - so you'd want to
ensure that each piece instance interacted correctly with the
`Board` class. The final level would be End-to-End
tests which would be like testing a round of chess - testing the
`Board` , `Game` , and
`Piece` classes all working together.

According to the testing pyramid - you want to have a solid base of a
lot of Unit tests, then a medium amount of integration tests built upon
that base, then finally a smaller amount of End-to-End tests. Writing
tests in this way is practical for a couple of reasons. As we said
before, unit tests ensure each piece of your application works in
isolation - if you know each piece works then you can more easily find
errors. Unit tests are also _fast_. The bigger your application gets the
longer your testing suite will take to run - if all your tests are
end-to-end tests your tests could be running for **hours**.

Here is a great blog from google about why they use the [testing
pyramid](https://testing.googleblog.com/2015/04/just-say-no-to-more-end-to-end-tests.html).

## Reading Tests

No matter what kind of test you are encountering the most important
thing about a test is that it is **readable** and **understandable**.
Good tests use descriptive strings to enumerate what they are testing as
well as how they are testing it.

We'll be diving more into the actual syntax of writing tests soon but
for right now let's see what you can glean without knowing the syntax:

```{style="color: rgb(248, 248, 242); background: rgb(45, 45, 45); font-family: Consolas, Monaco, "Andale Mono", "Ubuntu Mono", monospace; text-align: left; white-space: pre; word-spacing: normal; word-break: normal; overflow-wrap: normal; line-height: 1.5; tab-size: 4; hyphens: none; padding: 1em; overflow: auto; font-size: 16px;"}
describe("avgValue()", function() {
  it("should return the average of an array of numbers", function() {
    assert.equal(avgValue([10, 20]), 15);
  });
});
```

So without knowing the specfic syntax we can tell a few things from the
outset - the outer function has a string with the name of a function
`avgValue()` which is most likely the function we
will be testing.
Next we see a description string
`should return the average of an array of numbers` .

So even without understanding the syntax for the test above we can tell
_what_ we are testing - the `avgValue` function, and
how we are testing it -
`should return the average of an array of numbers` .

Being able to read tests is an important skill. You'll sometimes find
yourself working with unfamiliar testing libraries, but if the test is
well written you should be able to determine what the test is doing
regardless of the syntax it uses.

Below we've re-written the above example using the Ruby language testing
library RSpec:

```{style="color: rgb(248, 248, 242); background: rgb(45, 45, 45); font-family: Consolas, Monaco, "Andale Mono", "Ubuntu Mono", monospace; text-align: left; white-space: pre; word-spacing: normal; word-break: normal; overflow-wrap: normal; line-height: 1.5; tab-size: 4; hyphens: none; padding: 1em; overflow: auto; font-size: 16px;"}
describe "avg_value" do
  it "should return the average of an array of numbers" do
    expect(avg_value([10, 20])).to eq(15)
  end
end
```

Now you probably don't know Ruby - but using the same methods of
deduction as we used above we can figure out what is being testing in
the above snippet. The outer block mentions `avg_value` which is probably the method or function being tested and the
inner block says how things are being tested -
`"should return the average of an array of numbers"` . Without knowing the language, or the testing library, we can
still figure out generally what what is being tested. That is the
important thing about reading tests - having the patience to parse the
information before you.

## What you learned

We covered a high level overview of testing - the _why_, the _what_ and
the _how_ of testing as well as the basics of how to read a test
regardless of the syntax used in writing that test.

Did you find this lesson helpful?

No

Yes

✔︎ Mark As Complete

Finished with this task? Click **Mark as Complete** to continue to the
next page!
