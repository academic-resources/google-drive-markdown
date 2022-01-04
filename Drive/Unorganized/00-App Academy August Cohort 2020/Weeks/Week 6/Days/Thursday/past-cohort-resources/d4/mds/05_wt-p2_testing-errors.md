# Writing Tests

In this reading we'll be covering:

- how to test errors using `Mocha` and `Assert`
- test organization using `context` functions

## Part Two: Testing errors

Let's jump right in where we left off! We've written a couple of nice _unit
tests_ - ensuring that this function works in isolation by testing the input we
provided matches the expected output. One aspect of this function is not yet
being tested - the error thrown when the argument is not of type `String`:

```js
// str is the passed in parameter
if (typeof str !== "string") {
  throw new TypeError("this function only accepts string args");
}
```

### Organizing tests

Now the above error actually sets up two _different_ scenarios - one where the
incoming argument is a string and the second where the incoming argument isn't a
string and an error is thrown. We can denote these two different states by
adding an additional level of organizational nesting to our tests. You can nest
`describe` function callbacks arbitrarily deep - but this quickly becomes
unreadable. When nesting, we make use of the `context` function, which is an
alias for the `describe` function - the `context` function denotes that we are
setting up the **context** for a particular set of tests.

Let's refactor our tests from before with some `context` functions before moving
on:

```js
describe("reverseString()", function() {
  context("given a string argument", function() {
    it("should reverse the given string", function() {
      let test = reverseString("hello");
      let result = "olleh";

      assert.strictEqual(test, result);
    });

    it("should reverse the given string and output the same capitalization", function() {
      let test = reverseString("Apple");
      let result = "elppA";
      assert.strictEqual(test, result);
    });
  });

  context("given an argument that is not a string", function() {});
});
```

Running the above test will give us this readable output:

```sh
reverseString()
  given a string argument
    ✓ should reverse the given string
    ✓ should reverse the given string and output the same capitalization
  given an argument that is not a string

2 passing (11ms)
```

### Testing errors

Nice now that we have our `context` functions in place we can work on our second
scenario where the incoming argument is _not_ a string. When using an assertion
library like Node's built in [`Assert`][assert-docs] we will have access to many
functions that will allow us the flexibility to test all kinds of things. For
testing errors using Node's built in `Assert` module we can use the
[`assert.throws`][assert-throw] function.

Now we'll setup up our `it` function within the `context` function we setup
above:

```js
context("given an argument that is not a string", function() {
  it("should throw a TypeError when given an argument that is not a string", function() {
    assert.throws();
  });
});
```

The `assert.throws` function works different from the `assert.strictEqual`
function in that it does not compare the return value of a function, but it
attempts to invoke a function in order to verify that it will throw a particular
error. The `assert.throws` function accepts a function as the first argument,
then the error that should be thrown as the second argument with an optional
error message as our third argument.

So following that logic, we can test the `TypeError` error thrown by
`reverseString` with something like this:

```js
context("given an argument that is not a string", function() {
  it("should throw a TypeError when given an argument that is not a string", function() {
    assert.throws(reverseString(3), TypeError);
  });
});
```

However, when we run the `mocha` command we will get:

```sh
reverseString()
#  etc.
  given an argument that is not a string
    1) should throw a TypeError when given an argument that is not a string


2 passing (11ms)
1 failing

1) reverseString()
    given an argument that is not a string should throw a TypeError when given an
    argument that is not a string:
    TypeError: this function only accepts string args
```

We are failing the above spec because we passed the invoked version of the
`reverseString` function with a number argument - which as we know will throw a
`TypeError` and halt program execution. This is a common mistake made everyday
by developers when writing tests. We can get around this by wrapping our error
expecting function within another function. This will ensure we can still invoke
the `reverseString` function with an argument but not throw the error until
`assert.throws` is ready to catch it.

We can also add the explicit error message that `reverseString` throws to make
our spec as specific as possible:

```js
context("given an argument that is not a string", function() {
  it("should throw a TypeError when given an argument that is not a string", function() {
    assert.throws(
      function() {
        reverseString(3);
      },
      TypeError,
      "this function only accepts string args"
    );
  });
});
```

Now when we run `mocha` we will see:

```js
reverseString()
  given a string argument
    ✓ should reverse the given string
    ✓ should reverse the given string and output the same capitalization
  given an argument that is not a string
    ✓ should throw a TypeError when given an argument that is not a string


3 passing (13ms)
```

Awesome! So we've covered writing unit tests using `describe`, `context`, and
`it` functions for organization. We have also covered how to test for equality
and thrown errors using Node's built-in assertion library, `Assert`.

Head to the next reading to learn about how to test classes using `Mocha` and
another assertion library named `Chai`.

[assert-throw]:
  https://nodejs.org/api/assert.html#assert_assert_throws_fn_error_message
[mocha-docs]: https://mochajs.org/#getting-started
[bdd-docs]: https://mochajs.org/#bdd
[assert-equal]:
  https://nodejs.org/api/assert.html#assert_assert_equal_actual_expected_message
[assert-docs]: https://nodejs.org/api/assert.html#assert_assert
