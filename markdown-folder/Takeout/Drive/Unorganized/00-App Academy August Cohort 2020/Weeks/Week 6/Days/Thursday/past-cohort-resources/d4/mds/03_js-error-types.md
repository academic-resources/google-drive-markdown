# A Comedy of Errors in JavaScript

You know that feeling when you've just finished your perfect function then you
go to run your code and: BAM! A big error is thrown? We all have felt that pain
from the starting student to the experienced engineer. Runtime errors are a part
of daily life when writing code. It is now time to dive into what each type of
error you encounter means in order to more quickly and efficiently fix the
problem that created that error.

When you finish this reading you should be able to: identify the difference
between `SyntaxError`, `ReferenceError`, and `TypeError`s as well as create and
`throw` new errors.

## JavaScript Errors

In JavaScript the `Error` constructor function is responsible for creating
different instances of `Error` objects. The `Error` object is how JavaScript
deals with runtime errors and the _type_ of error created and thrown will
attempt to communicate _why_ that error occurred.

[error-docs]:
  https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error

### Creating your own errors

Since the [`Error`][error-docs] constructor is just a constructor function we
can use it to create new `Error` object instances with the following syntax:

```js
new Error([message[, fileName[, lineNumber]]])
```

As seen above you can optionally supply a `message`, `fileName` and `lineNumber`
where the error occurred. The `Error` constructor is also somewhat unique in
that you can call it with or without the `new` keyword and it will return a new
`Error` object:

```js
const first = Error("I am an error object!");
const second = new Error("I am too an error object!");

console.log(first); // Error: I am an error object!
console.log(second); // Error: I am too an error object!
```

Let's take a look at what we can do with our newly created `Error` objects.

### Throwing your own errors

Tired of JavaScript being the only one to throw errors? Well you can too! Using
the keyword `throw` you can throw your own runtime errors that will stop program
execution.

Let's take a look at the syntax for `throw`:

```js
function giveMeNumber(num) {
  if (typeof num !== "number") {
    throw new Error("Give me a number!");
  } else {
    return "yay number!";
  }
}

console.log(giveMeNumber(1)); // prints "yay number!";
console.log(giveMeNumber("apple")); // Uncaught Error: Give me a number!
console.log(giveMeNumber(1)); // doesn't get run
```

Now as we can see in the above example throwing an error is a powerful tool that
stops program execution. If we wanted to throw an error _without_ stopping
program execution we can use a `try...catch` block.

Let's look at the syntax for using the `try...catch` block syntax:

```js
try {
  // statements that will be attempted to here
} catch (error) {
  // if an error is thrown it will be "caught"
  // allowing the program to continue execution
  // these statements will be run and the program will continue!
}
```

We normally use `try...catch` blocks with functions that might throw an error.
Let's look at an example where an error _will not_ be thrown:

```js
function safeDivide(a, b) {
  if (b === 0) {
    throw new Error("cannot divide by zero");
  } else {
    return a / b;
  }
}

try {
  console.log(safeDivide(30, 5)); // prints 6
} catch (error) {
  console.error(error.name + ": " + error.message);
}

console.log("hello"); // prints hello
```

**Note**: We can use `console.error` instead of `console.log` to make logged
errors more noticeable.

Above you can see our `safeDivide` function ran as expected. Now let's see what
happens when an error will be thrown and **caught** inside a `try...catch`
block:

```js
function safeDivide(a, b) {
  if (b === 0) {
    throw new Error("cannot divide by zero");
  } else {
    return a / b;
  }
}

try {
  console.log(safeDivide(30, 0));
} catch (error) {
  console.error(error.name + ": " + error.message); // Error: cannot divide by zero
}
// the above error will be caught allowing our program to continue!
console.log("hello"); // prints  "hello"
```

Those are the basics of creating and throwing your own errors. You can `throw`
your newly created `Error` to stop program execution or use a `try...catch`
block to catch your error and continue running your code. Now that we've learned
how to create new errors let's go over the core errors built into JavaScript and
what they signify.

## Types of JavaScript errors

There are seven core errors you'll encounter in JavaScript and each type of
error will try to communicate why that error occurred:

1. `SyntaxError` - represents an error in the syntax of the code.
2. `ReferenceError` - represents an error thrown when an invalid reference is
   made.
3. `TypeError` - represents an error when a variable or parameter is not of a
   valid type.
4. `RangeError` - representing an error for when a numeric variable or parameter
   is outside of its valid range.
5. `InternalError` - represents an error in the internal JavaScript engine.
6. `EvalError` - represents an error with the global `eval` function.
7. `URIError` - represents an error that occurs when `encodeURI()` or
   `decodeURI()` are passed invalid parameters.

For this reading we'll be going in depth of the three most common errors you
have encountered so far: `SyntaxError`, `ReferenceError`, and `TypeError`.

### SyntaxError

A SyntaxError is thrown when the JavaScript engine attempts to parse code that
does not conform to the syntax of the JavaScript language. When learning the
JavaScript language this error is a constant companion for any missing `}` or
misspelled `function` keywords.

Let's look at a piece of code that would throw a syntax error:

```js
funtion broken () { // Uncaught SyntaxError: Unexpected identifier
  console.log("I'm broke")
}
```

Another example with an extra curly brace `}`:

```js
function broken () { // Uncaught SyntaxError: Unexpected identifier
  console.log("I'm broke")
}} // Uncaught SyntaxError: Unexpected token '}'
```

The examples go on and on - you can count on a `SyntaxError` to be thrown
whenever you attempt to run code that is not syntactically correct JavaScript.

**Important!** One thing to note about Syntax Errors is that many of them can't be caught using `try` `catch` blocks.

For instance, the following code will throw a `SyntaxError` and no matter how hard you try, you can't catch it.

```js
try {
    if (true { // throws "SyntaxError: Unexpected token '{'"
        console.log("SyntaxErrors are the worst!");
    }
} catch (e) {
    console.log(e);
}
```

The missing parenthesis after `true` will throw a `SyntaxError` but can't be caught by the `catch` block.

This is because this kind of `SyntaxError` happens at *compile time* not *run time*.  Any errors that happen at *compile time* can't be caught using `try` `catch` blocks.

### ReferenceError

Straight from the [MDN docs][mdn-reference]: "The `ReferenceError` object
represents an error when a non-existent variable is referenced." This is the
error that you'll encounter when attempting to reference a variable that does
not exist (either within your current scope or at all).

Let's take a took at some examples for the causes of this error. One common
cause for this error is misspelling a variable name:

```js
function callPuppy() {
  const puppy = "puppy";
  console.log(pupy);
}

callPuppy(); // ReferenceError: pupy is not defined
```

Another common cause for a thrown `ReferenceError` is attempting to access a
variable that is not in scope:

```js
function callPuppy() {
  const puppy = "puppy";
}

console.log(puppy); // ReferenceError: puppy is not defined
```

[mdn-reference]:
  https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ReferenceError

The aptly named `ReferenceError` will be thrown whenever you attempt to
_reference_ a variable that doesn't exist.

### TypeError

A `TypeError` is commonly thrown for a couple of reasons:

1. When an operation cannot be performed because the operand is a value of the
   wrong type.
2. When you are attempting to modify a value that cannot be changed.

Let's look at a couple of examples that will each throw a `TypeError` for a
different reason. Below we are attempting an operation (in this case a function
call) on a value of the wrong type:

```js
let dog; // Remember unassigned variables are undefined!

dog(); // TypeError: dog is not a function
```

In the above example we attempt to invoke a declared but not assigned variable
(which will evaluate to `undefined`). This will cause a `TypeError` because
`undefined` cannot be invoked - it is the wrong type.

Next let's look at a example of attempting to change a value that cannot be
changed:

```js
const puppy = "puppy";

puppy = "apple"; // TypeError: Assignment to constant variable.
```

Attempting te reassign a `const` declared variable will result in a `TypeError`.
You've probably run into many other examples of `TypeError` yourself but, the
most important thing to know is that a `TypeError` is thrown when you attempting
to perform an operation on the wrong type of value.

### Catching known errors

Now that we've covered the the names of common JavaScript errors as well as how
to use a `try...catch` block we can combine these two ideas to catch specific
types of errors using `instanceof`:

```js
function callThatArg(arg) {
  arg(); // this will cause a TypeError because callThatArg is being passed a number
}

try {
  callThatArg(42);
  console.log("call successful"); // this line never executes
} catch (error) {
  if (error instanceof TypeError) {
    console.error(`Wrong Type: ${error.message}`); // prints: Wrong Type: arg is not a function
  } else {
    console.error(error.message); // prints out any errors that aren't TypeErrors;
  }
}

console.log("done"); // prints: done
```

## What you learned

If you read an error and know _why_ that error is being thrown it'll be much
easier to find the cause of the problem! In this reading we went over how to
create and throw new `Error` objects as well as the definitions for some of the
most common types of errors: `SyntaxError`, `ReferenceError`, and `TypeError`s.
