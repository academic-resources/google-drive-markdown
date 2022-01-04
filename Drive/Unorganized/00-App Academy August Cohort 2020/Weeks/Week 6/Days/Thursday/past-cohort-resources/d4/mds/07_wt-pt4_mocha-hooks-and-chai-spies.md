## Writing Tests

This will be the final demo in our writing tests series! In this reading we'll
be covering:

- Using `Mocha` Hooks to DRY up testing
- Using `Chai Spies` to "spy" on functions to see how many times they've been
  invoked

## Part Four: Mocha Hooks and Chai Spies

Let's jump right back in. We've written some nice unit tests up to this point:

```js
describe("Dog Constructor Function", function() {
  it('should have a "name" property', function() {
    const layla = new Dog("Layla");
    expect(layla).to.have.property("name");
  });

  it('should set the "name" property when a new dog is created', function() {
    const layla = new Dog("Layla");
    // we are using the eql function to compare the value of layla.name
    // with the provided string
    expect(layla.name).to.eql("Layla");
  });
});
```

This is how unit tests are supposed to work, buuuut it will be annoying over
time if we have to define a new `Dog` instance in _every single spec_. `Mocha`
has some built in functionality to help us with this problem though: Mocha
Hooks!

### Introducing Mocha Hooks

[Mocha Hooks][mocha-hooks] give you a convenient way to do set up prior to
running a related group of specs or to do some clean up after running those
specs. Using hooks helps to keep your testing code DRY so you don't
unnecessarily repeat set up and clean up code within each test.

Mocha Hooks have very descriptive function names and two levels of granularity -
before/after each block of tests _or_ before/after each test:

1. the hooks `before` and `after` will be invoked either before or after the
   block of tests is run (depending on which function is used)
2. the hooks `beforeEach` and `afterEach` will be invoked either before or after
   **each** test (depending on which function is used)

Let's look at a simple example that uses each of the available hooks to log a
message to the console. Two placeholder tests are also defined to help
demonstrate the differences between the available hooks:

```js
const assert = require('assert');

describe('Hooks demo', () => {
  before(() => {
    console.log('Before hook...');
  });

  beforeEach(() => {
    console.log('Before each hook...');
  });

  afterEach(() => {
    console.log('After each hook...');
  });

  after(() => {
    console.log('After hook...');
  });

  it('Placeholder one', () => {
    assert.equal(true, true);
  });

  it('Placeholder two', () => {
    assert.equal(true, true);
  });
});
```

Running the above spec produces the following output:

```sh
  Hooks demo
Before hook...
Before each hook...
    ✓ Placeholder one
After each hook...
Before each hook...
    ✓ Placeholder two
After each hook...
After hook...


  2 passing (5ms)
```

Notice that the `before` and `after` hooks only ran once while the `beforeEach`
and `afterEach` hooks each ran once per test.

Hooks are defined within a `describe` or `context` function. While hooks can be
defined before, after, or interspersed with your tests, keeping all of your
hooks together (before or after your tests) will help others to read and
understand your code.

Defining hooks out of their logical order has no effect on when they're ran.
Consider the following example that defines an `afterHook` before a `beforeEach`
hook:

```js
const assert = require('assert');

describe('Hooks demo', () => {
  afterEach(() => {
    console.log('After each hook...');
  });

  beforeEach(() => {
    console.log('Before each hook...');
  });

  it('Placeholder one', () => {
    assert.equal(true, true);
  });

  it('Placeholder two', () => {
    assert.equal(true, true);
  });
});
```

Running the above spec produces the following output:

```sh
  Hooks demo
Before each hook...
    ✓ Placeholder one
After each hook...
Before each hook...
    ✓ Placeholder two
After each hook...


  2 passing (6ms)
```

The order of your hooks only matters when you define multiple hooks of the same
type. When a hook type is defined more than once, they'll be ran in the order
that they're defined in:

```js
const assert = require('assert');

describe('Hooks demo', () => {
  beforeEach(() => {
    console.log('Before each hook #1...');
  });

  beforeEach(() => {
    console.log('Before each hook #2...');
  });

  it('Placeholder one', () => {
    assert.equal(true, true);
  });

  it('Placeholder two', () => {
    assert.equal(true, true);
  });
});
```

Running the above spec produces the following output:

```sh
  Hooks demo
Before each hook #1...
Before each hook #2...
    ✓ Placeholder one
Before each hook #1...
Before each hook #2...
    ✓ Placeholder two


  2 passing (5ms)
```

You can also define hooks within nested `describe` or `context` functions:

```js
const assert = require('assert');

describe('Hooks demo', () => {
  before(() => {
    console.log('Before hook...');
  });

  beforeEach(() => {
    console.log('Before each hook...');
  });

  afterEach(() => {
    console.log('After each hook...');
  });

  after(() => {
    console.log('After hook...');
  });

  it('Placeholder one', () => {
    assert.equal(true, true);
  });

  it('Placeholder two', () => {
    assert.equal(true, true);
  });

  describe('nested tests', () => {
    before(() => {
      console.log('Nested before hook...');
    });
  
    beforeEach(() => {
      console.log('Nested before each hook...');
    });
  
    afterEach(() => {
      console.log('Nested after each hook...');
    });
  
    after(() => {
      console.log('Nested after hook...');
    });

    it('Placeholder one', () => {
      assert.equal(true, true);
    });
  
    it('Placeholder two', () => {
      assert.equal(true, true);
    });  
  });
});
```

Running the above spec produces the following output:

```sh
  Hooks demo
Before hook...
Before each hook...
    ✓ Placeholder one
After each hook...
Before each hook...
    ✓ Placeholder two
After each hook...
    nested tests
Nested before hook...
Before each hook...
Nested before each hook...
      ✓ Placeholder one
Nested after each hook...
After each hook...
Before each hook...
Nested before each hook...
      ✓ Placeholder two
Nested after each hook...
After each hook...
Nested after hook...
After hook...


  4 passing (7ms)
```

Notice that the `before` and `after` hooks defined in the top-level `describe`
function run only once while the `beforeEach` and `afterEach` hooks run before
and after (respectively) for each of the tests defined in the top-level
`describe` function _and_ for each of the tests defined in the nested `describe`
function.

> While the need to define nested hooks won't come up very often (especially
> when you're just starting out with unit testing), it is very helpful to be
> able to define a `beforeEach` hook in a top-level `describe` function that
> will run before every test in that block _and_ before every test within nested
> `describe` or `context` functions (you'll do exactly that in just a bit).

You can also optionally pass a description for a hook or a named function:

```js
beforeEach('My hook description', () => {
  console.log('Before each hook...');
});

beforeEach(function myHookName() {
  console.log('Before each hook...');
});
```

If an error occurs with executing the hook, the hook description or function
name will display in the console along with the error information to assist with
debugging. 

### Using the `beforeEach` Mocha Hook

Let's go back to our spec and see how we can use hooks to DRY up our code.
Here's where we left off:

```js
describe("Dog Constructor Function", function() {
  it('should have a "name" property', function() {
    const layla = new Dog("Layla");
    expect(layla).to.have.property("name");
  });

  it('should set the "name" property when a new dog is created', function() {
    const layla = new Dog("Layla");
    // we are using the eql function to compare the value of layla.name
    // with the provided string
    expect(layla.name).to.eql("Layla");
  });
});
```

Let's refactor our code to use a `beforeEach` hook to assign the value of
our new dog instance:

```js
describe("Dog", function() {
  // we'll declare our variable here to ensure it's available within the scope
  // of all the specs below
  let layla;

  // now for each test below we'll create a new instance to ensure each of our
  // dog instances is exactly the same
  beforeEach("set up a dog instance", function() {
    layla = new Dog("Layla");
  });

  describe("Dog Constructor Function", function() {
    it('should have a "name" property', function() {
      expect(layla).to.have.property("name");
    });

    it('should set the "name" property when a new dog is created', function() {
      expect(layla.name).to.eql("Layla");
    });
  });
});
```

Now let's write a test from the next method on the `Dog` class:
`Dog.prototype.bark()`. For testing classes we'll create a new `describe`
function to test each individual method. We'll now write our unit test inside
taking advantage of our `beforeEach` hook:

```js
describe("Dog", function() {
  let layla;

  beforeEach("set up a dog instance", function() {
    layla = new Dog("Layla");
  });

  // etc, etc.

  describe("prototype.bark()", function() {
    it("should return a string with the name of the dog barking", function() {
      expect(layla.bark()).to.eql("Layla is barking");
    });
  });
});
```

Not only are we avoiding repeating our setup code within each test but we've
improved the readability of our code by making it more self-descriptive. The
code that runs before each test is literally contained with a hook named
`beforeEach`!

The `after` and `afterEach` hooks are generally used less often than the
`before` and `beforeEach` hooks. Most of the time, it's preferable to avoid
using the `after` and `afterEach` hooks to perform clean up tasks after your
tests. Instead, simply use the `before` and `beforeEach` hooks to create a clean
starting point for each of your tests. Doing this will ensure that your tests
run in a consistent, predictable manner.

### Using Chai Spies

Sweet - let's now look to the next method on the `Dog.prototype` -
`Dog.prototype.chainChaseTail`. This instance method intakes a number (num) and
will then invoke the `Dog.prototype.chaseTail` function `num` number of times.
The `chaseTail` function will just `console.log` a string - meaning that we have
no function output to test. The `Dog.prototype.chainChaseTail` function will
additionally throw a `TypeError` if the incoming argument is not a number.

We'll start by setting up our outer `describe` block for the
`prototype.chainChaseTail` method. Next we'll add two `context` functions for
our two contexts - valid **or** invalid parameters:

> `context` is just an alias for `describe` it's just another way to make your
> tests more understandable and readable, in this case we are testing our method
> with different parameters, and thus in different contexts. (not to be confused
> with "context" in the javascript sense of the value of `this`)

```js
describe("prototype.chainChaseTail()", function() {
  context("with an invalid parameter", function() {});
  context("with a valid number parameter", function() {});
});
```

We'll start by writing our test for when the method is invoked with invalid
parameters. To do this we'll use Chai's [`throw`][chai-throw] method ensuring to
wrap our error throwing function in another function:

```js
context("with an invalid parameter", function() {
  it("should throw a TypeError when given an argument that is not a number", function() {
    expect(() => layla.chainChaseTail("3")).to.throw(TypeError);
  });
});
```

> Note here we are passing the literal string `"3"` not the number 3.

Nice, now we can concentrate on our other context with a valid parameter - and
how to go about testing this function. In order to test `chainChaseTail`
properly we'll need to see _how many times_ the `chaseTail` method is invoked.
Which means we'll need to import another library that will add extra
functionality to `Chai`. We'll import the [`Chai Spies`][chai-spies] library
using `npm install chai-spies` in our top level directory.

Now we'll insert a few lines of code to the top of file to set up our shiny new
Chai Spies:

```js
// top of dog-spec.js
const chai = require("chai");
const expect = chai.expect;
const spies = require("chai-spies");
chai.use(spies);
```

We now have access to the `chai-spies` module in our tests. The `Chai Spies`
library provides a lot of added functionality including the ability to determine
if a function has been called and how many times that function has been called.

So let's get started spying! We'll setup our `it` function with an appropriate
string:

```js
context("with a valid number parameter", function() {
  it("should call the chaseTail method n times", function() {});
});
```

Now in order to spy on a function we first need to tell Chai which function we'd
like to spy on using the `chai.spy.on` method. In this case we'd like to spy on
the instance of a Dog that will be invoking the `chainChaseTail` method to
determine how many times the `chaseTail` method is then invoked.

So we will set up our spy on the dog instance in question, as well as tell our
chai spy which method to keep track of:

```js
context("with a valid number parameter", function() {
  it("should call the chaseTail method n times", function() {
    // the first argument will be the instance we are spying on
    // the second argument will be the method we want to keep track of
    const chaseTailSpy = chai.spy.on(layla, "chaseTail");
  });
});
```

Now that our spy is set up we now need make sure our dog instance will actually
call the `chainChaseTail` function! Otherwise our spy won't have anything to spy
on:

```js
context("with a valid number parameter", function() {
  it("should call the chaseTail method n times", function() {
    const chaseTailSpy = chai.spy.on(layla, "chaseTail");
    // we need to invoke chainChaseTail because that is the method that
    // will invoke chaseTail which is the method we are spying on
    layla.chainChaseTail(3);
  });
});
```

Finally, we need to add our actual test - otherwise this is all for naught! Chai
has some really nice chaining methods when it comes to checking how many times a
function has been invoked. Here we'll use the method chain of
`expect(func).to.have.been.called.exactly(n)` to test that the method we are
spying on - `chaseTail` was invoked a certain number of times:

```js
context("with a valid number parameter", function() {
  it("should call the chaseTail method n times", function() {
    const chaseTailSpy = chai.spy.on(layla, "chaseTail");
    layla.chainChaseTail(3);
    // below is our actual test to see how many times our spy was invoked
    expect(chaseTailSpy).to.have.been.called.exactly(3);
  });
});
```

### Testing static methods on classes

Sweet! We are almost done testing this class - just one more method to go. We'll
now work on testing the class method `Dog.cleanDogs`. To denote that this is a
class method, not an instance method, our `describe` string will not use the
word `prototype`:

```js
describe("cleanDogs()", function() {
  it("should return an array of each cleaned dog string", function() {});
});
```

Now the `Dog.cleanDogs` class method will intake an array of dogs and output an
array where each element is a string noting that the passed in dog instance's
paws are now clean. In order to properly test this function we'll probably want
an array of more than one dog instance. Let's create a new dog and pass an array
of two dog instances to the `Dog.cleanDogs` method:

```js
describe("cleanDogs()", function() {
  it("should return an array of each cleaned dog string", function() {
    const zoey = new Dog("Zoey");
    let cleanDogsArray = Dog.cleanDogs([layla, zoey]);
  });
});
```

Then we'll create a variable for our expected output and compare the output we
received from `Dog.cleanDogs`:

```js
describe("cleanDogs()", function() {
  it("should return an array of each cleaned dog string", function() {
    const zoey = new Dog("Zoey");
    let cleanDogsArray = Dog.cleanDogs([layla, zoey]);
    let result = ["I cleaned Layla's paws.", "I cleaned Zoey's paws."];
    expect(cleanDogsArray).to.eql(result);
  });
});
```

Awesome! We have fully testing the `Dog` class's methods and learned a lot about
testing along the way.

Here is our full testing file so you can ensure you got everything:

```js
const chai = require("chai");
const expect = chai.expect;
const spies = require("chai-spies");
chai.use(spies);

// this is a relative path to the function location
const Dog = require("../problems/dog.js");

describe("Dog", function() {
  let layla;

  beforeEach("set up a dog instance", function() {
    layla = new Dog("Layla");
  });

  describe("Dog Constructor Function", function() {
    it('should have a "name" property', () => {
      expect(layla).to.have.property("name");
    });

    it('should set the "name" property when a new dog is created', () => {
      expect(layla.name).to.eql("Layla");
    });
  });

  describe("prototype.bark()", function() {
    it("should return a string with the name of the dog barking", () => {
      expect(layla.bark()).to.eql("Layla is barking");
    });
  });

  describe("prototype.chainChaseTail()", function() {
    context("with a valid number parameter", function() {
      it("should call the chaseTail method n times", function() {
        const chaseTailSpy = chai.spy.on(layla, "chaseTail");
        layla.chainChaseTail(3);

        expect(chaseTailSpy).to.have.been.called.exactly(3);
      });
    });

    context("with an invalid parameter", function() {
      it("should throw a TypeError when given an argument that is not a number", function() {
        expect(() => layla.chainChaseTail("3")).to.throw(TypeError);
      });
    });
  });

  describe("cleanDogs()", function() {
    it("should return an array of each cleaned dog string", function() {
      const zoey = new Dog("Zoey");
      let cleanDogsArray = Dog.cleanDogs([layla, zoey]);
      let result = ["I cleaned Layla's paws.", "I cleaned Zoey's paws."];
      expect(cleanDogsArray).to.eql(result);
    });
  });
});
```

[mocha-hooks]: https://mochajs.org/#hooks
[chai-docs]: https://www.chaijs.com/
[chai-expect-docs]: https://www.chaijs.com/api/bdd/
[prop-docs]: https://www.chaijs.com/api/bdd/#method_property
[chai-cheatsheet]: https://devhints.io/chai
[chai-throw]: https://www.chaijs.com/api/bdd/#method_throw
[chai-spies]: https://www.chaijs.com/plugins/chai-spies/

## What you learned

In the upcoming project we'll be covering a lot more Chai syntax - but don't
worry about memorizing this syntax! The point we are trying to make is that in
the future you'll be using a variety of software testing frameworks and
assertion libraries - the most important things are to know the basics of how to
structure tests as well as being able to read and parse documentation to write
tests.

In this series of readings we covered the basics of how to:

- properly format and denote your mocha tests using `describe`, `context` and
  `it` blocks
- write tests for individual functions as well as writing tests for classes
- use `chai-spies` to test how many times a function has been called
- test that functions will throw certain errors
- recognize and utilize the Mocha hooks: `before`, `beforeEach`, `after`, and
  `afterEach`
