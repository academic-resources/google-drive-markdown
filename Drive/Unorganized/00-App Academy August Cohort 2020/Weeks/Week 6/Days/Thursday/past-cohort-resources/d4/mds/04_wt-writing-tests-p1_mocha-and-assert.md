# Writing Tests

For weeks you have been using one of JavaScript's most popular test frameworks,
`Mocha`, to run tests that ensure a function you've written works as expected.
It's time to dive deeper into **how** to write our own tests using `Mocha` as
our test framework coupled with Assertion libraries such as the built-in
`Assert` module of Node or the `Chai` library.

For the rest of the readings in this section we will be covering how to write
tests. These readings will be done in the style of a code-along demo so make
sure you follow these in order. When you have finished the next series of
reading you should know how to:

- properly format and denote your mocha tests using `describe`, `context` and
  `it` blocks
- write tests for individual functions as well as writing tests for class
  instance and static methods
- test that functions will throw certain errors
- use `chai-spies` to test how many times a function has been called
- recognize and utilize the Mocha hooks: `before`, `beforeEach`, `after`, and
  `afterEach`

In this reading we'll be covering:

- the file structure of testing with `Mocha`
- testing with `Mocha` and Node's built-in `Assert` module

## Part Zero: Testing file structure

We find that reading about testing is best understood when you can play around
within the functions being tested so for that reason this reading will be in the
style of a code along demo. We started this reading by created a directory
called `testing-demo` where all the code within this reading will be written.

Let's start off with how to write tests for a basic function. Say we've been
handed a directory with a function to test `problems/reverse-string.js`. Below
is the named function we'll be testing, `reverseString`, which will intake a
string argument and then reverse it:

```js
// in testing-demo/problems/reverse-string.js

const reverseString = str => {
  // throws a specific error unless the the incoming arg is a string
  if (typeof str !== "string") {
    throw new TypeError("this function only accepts string args");
  }

  return str
    .split("")
    .reverse()
    .join("");
};

// note this function is being exported!
module.exports = reverseString;
```

How would you go about testing the above function? Let's start by setting up our
file system correctly. Whenever you are running tests with `Mocha` the important
thing to know is that the `Mocha` CLI will automatically be looking for a
directory named `test`.

The created `test` directory's file structure should mirror that of the files
you intend to test - with each test file appending the word "spec" to the end of
the file name. So for the above example we would create
`test/reverse-string-spec.js` which should be on the same level as the
`problems` directory.

Our file structure should look like this:

```plaintext
testing-demo
  └──
  problems
    └── reverse-string.js
  test
    └── reverse-string-spec.js
```

Take a moment to ensure your file structure looks like the one above and that
you've copied and pasted the `reverseString` function into the
`reverse-string.js` file. Now that we've ensured our file structure is correct
let's write some tests!

## Part One: Writing tests with Mocha and Assert

The first step in any testing workflow is initializing our test file. Now let's
make a clear distinction before moving forward - `Mocha` is a test framework
that specializes in _running_ tests and presenting them in an organized user
friendly way. The code responsible for actually verifying things for us will
come from using an _Assertion Library_. Assertion Libraries will do the heavy
lifting of comparing and verifying code while `Mocha` will run those tests and
then present them to us.

The tests we'll be writing for this next section will use Node's built-in
`Assert` module as our Assertion Library.

So inside of `test/reverse-string-spec.js` at the top of the file we will
require the `assert` module and the function we intend to test:

```js
const assert = require("assert");
// this is a relative path to the function's location
const reverseString = require("../problems/reverse-string.js");
```

Take a moment to open up the [`Mocha`][mocha-docs] documentation - it will come
in handy as a reference for the syntax we'll be using. The `Mocha` DSL (Domain
Specific Language) comes with a few different interfaces or "flavors" of their
DSL for our purposes we'll be structuring our tests using the [BDD
interface][bdd-docs].

The `describe` function is an organizational function that accepts a descriptive
string and a callback. We'll use the `describe` function to **describe** what we
will be testing - in this case the `reverseString` function:

```js
// test/reverse-string-spec.js

const assert = require("assert");
const reverseString = require("../problems/reverse-string.js");

describe("reverseString()", function() {});
```

The callback handed to the `describe` function will be where we insert our
actual tests. We can now use the `it` function - the `it` function is an
organizational function we will use to wrap around each test we write. The `it`
function accepts a descriptive string and callback to set up our test:

```js
describe ('reverseString()', function () {
  it('should reverse the input string', function () {
    // a test will go here!
  })
}
```

The code written above will serve as a great template for future tests we wish
to write. Finally, we can insert the actual test we intend to write within the
callback handed to the `it` function. We'll use the
[`assert.strictEqual`][assert-equal] function which allows you to compare one
value with another value. We'll use `assert.strictEqual` to compare two
strings - one from our function's result and our expected result which we will
we define ourselves:

```js
// remember we required the assert module at the top of this file
describe("reverseString()", function() {
  it("should reverse the input string", function() {
    let test = reverseString("hello");
    let result = "olleh";
    // the line below is where the actual test is!
    assert.strictEqual(test, result);
  });
});
```

Now if we run `mocha` in the upper most `testing-demo` directory we will see:

```sh
reverseString()
  ✓ should reverse the input string


1 passing (5ms)
```

We now have a working spec! Take notice of how `Mocha` structures its response
in exactly the way we nested our test. The outer `describe` function's message
of `reverseString()` is on the upper level and the inner `it` function's message
of `should reverse the input string` is nested within.

Strictly speaking we aren't required to nest our `it` functions within
`describe` functions but it is best practice to do so. As you can see yourself -
it will make your tests a lot easier to read!

Let's add one more spec for `reverseString`, we'll do this by adding another
`it` function within the `describe` callback:

```js
describe("reverseString()", function() {
  it("should reverse the input string", function() {
    let test = reverseString("hello");
    let result = "olleh";

    assert.strictEqual(test, result);
  });

  it("should reverse the input string and output the same capitalization", function() {
    let test = reverseString("Apple");
    let result = "elppA";

    assert.strictEqual(test, result);
  });
});
```

Running the `mocha` command again will return:

```sh
reverseString()
  ✓ should reverse the input string
  ✓ should reverse the input string and output the same capitalization


2 passing (11ms)
```

Looking good so far - head to the next reading to learn how to test errors.

[assert-throw]:
  https://nodejs.org/api/assert.html#assert_assert_strictequal_actual_expected_message
[mocha-docs]: https://mochajs.org/#getting-started
[bdd-docs]: https://mochajs.org/#bdd
[assert-equal]:
  https://nodejs.org/api/assert.html#assert_assert_equal_actual_expected_message
[assert-docs]: https://nodejs.org/api/assert.html#assert_assert
