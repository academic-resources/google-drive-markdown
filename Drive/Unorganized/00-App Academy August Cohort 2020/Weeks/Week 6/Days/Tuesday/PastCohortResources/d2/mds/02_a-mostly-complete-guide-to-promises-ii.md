# A Promise is a Promise: A Mostly Complete Guide to JavaScript Promises II

This is part two of an article about classic JavaScript promises. If you have
not read part one, we recommend that you navigate to the previous task to do so.

When you finish this article, you should be able to:

* Create your own `Promise`s
* Use `Promise` objects returned by language and framework libraries

## Handling success with `then`

Returning to another file-reading example, consider the following block of code.

```javascript
readFile("manifest.txt", "utf8", (err, manifest) => {
  if (err) {
    console.error("Badness happened", err);
  } else {
    const fileList = manifest.split("\n");
    console.log("Reading", fileList.length, "files");
  }
});
```

If this succeeds, then you would expect a statement like "Reading 12 files" to
appear if the file contained a list of 12 files.

Now, to rewrite that using a `Promise` and printing that same statement, you
would get a file-reading function that returns a `Promise` object. Later on,
you'll see how to create one for yourself. At this moment, just presume that a
function named `readFilePromise` exists. When you call it, it would return a
promise that, when _fulfilled_, would invoke the success handler registered for
the object through the `then` method. Very explicitly, you could write that code
like this.

```javascript
/* EXPLICIT CODE: NOT FOR REAL USE */

// Declare a function that will handle the content of
// the file read by readFilePromise.
function readFileSuccessHandler(manifest) {
  const fileList = manifest.split("\n");
  console.log("Reading", fileList.length, "files");
}

// Get a promise that will return the contents of the
// file.
const filePromise = readFilePromise("manifest.txt");

// Register a success handler to process the contents
// of the file. In this case, it is the function
// defined above.
filePromise.then(readFileSuccessHandler);
```

Most `Promise`-based code does **not** look like that, though. Idiomatic
JavaScript instructs to not create variables that don't need to be created. You
would see the above code in a real-live code base written like this, instead.
Spend a moment comparing and contrasting the forms from **very explicit** to
**idiomatic**.

```javascript
readFilePromise("manifest.txt").then(manifest => {
  const fileList = manifest.split("\n");
  console.log("Reading", fileList.length, "files");
});
```

That's slightly easier to read than the weird callback thing you had above. But,
you still have that nasty double indentation. The designers of the `Promise`
didn't want that for you, so they allow you to chain `then`s.

## Chaining `then`s.

In the above code that uses `readFilePromise`, it does not look like the ideal
code that JavaScript could give us because of the success-handling function
being on multiple lines that require another indent. It may be a little thing,
but it still prevents you from the most readable code. Again, the Technical
Committee 39 had your back. They designed "chainable thens" for you. The rules
are a little complex to read.

- Each `Promise` has a `then` method that handles what happens when the
  `Promise` transitions out of the **pending** state.
- Each `then` method returns a `Promise` that transitions out of its **pending**
  state when the `then` that created it completes.
- (One more condition described below.)

That chaining property gives you the ability to break apart the two lines of the
success handler in the previous example to two one-line functions that do the
same thing with less code! If you write that form explicitly, you'd have the
following.

```javascript
/* EXPLICIT CODE: NOT FOR REAL USE */

// Get a Promise that fulfills when the file is read
// with the value of the content of the file.
const filePromise = readFilePromise("manifest.txt");

// Register a success handler that takes the fulfilled
// value of the filePromise in the parameter named "manifest",
// which is the content of the file, split it on newline
// characters, and return a Promise whose fulfilled value is
// list of lines.
const fileListPromise = filePromise.then(manifest => manifest.split("\n"));

// Register a success handler to the fileListPromise that
// receives the fulfilled value in the "fileList" parameter
// and returns a Promise whose fulfilled value is the length 
// of the fileList array.
const lengthPromise = fileListPromise.then(fileList => fileList.length);

// Register a success handler to the lengthPromise that
// receives the fulfilled value in the "numberOfFiles" parameter
// and uses it to print the number of files to be read.
lengthPromise.then(numberOfFiles =>
  console.log("Reading", numberOfFiles, "files")
);
```

That code block has a lot of words to describe what happens at each step of the
process of using "chainable thens". In the real world, were you to find that
code in a real application, it would likely look like the following.

```javascript
readFilePromise("manifest.txt")
  .then(manifest => manifest.split("\n"))
  .then(fileList => fileList.length)
  .then(numberOfFiles => console.log("Reading", numberOfFiles, "files"));
```

Here's a diagram of what happens in the above code.

<p>
<img src="https://appacademy-open-assets.s3-us-west-1.amazonaws.com/Module-JavaScript/promises/assets/promise-success-diagram-source.svg" alt="promise errors" style="width: 100%; height: auto">
</p>

You can see that each call to `then` creates a new `Promise` object that
resolves to the value of the output of the previous success handler. That's what
happens when everything works out. What happens when it doesn't?

## Handling failure with `then`

As you may recall from the section
[So, what is a "Promise"?](#so-what-is-a-promise), you learned that the `then`
method can also accept a second argument that is an error handler that takes
care of things should something go wrong. Back to the file reading example from
above, you add a second method to the `then` which accepts a **reason** that the
error happened. For reading a file, that could be that the file doesn't exist,
the current user doesn't have permissions to read it, or it ran out of memory
trying to read a _huge_ file.

```javascript
readFilePromise("manifest.txt").then(
  manifest => {
    const fileList = manifest.split("\n");
    console.log("Reading", fileList.length, "files");
  },
  reason => {
    console.error("Badness happened", reason);
  }
);
```

That works, but has taken you back to the original bad multiline form of the
success handler. What happens if you did it like this? How does this work?

```javascript
readFilePromise("manifest.txt")
  .then(
    manifest => manifest.split("\n"),
    reason => console.err("Badness happened", reason)
  )
  .then(fileList => fileList.length)
  .then(numberOfFiles => console.log("Reading", numberOfFiles, "files"));
```

Here's what happens with regard to the `Promise`s in this chain of `then`s.

<p>
<img src="https://appacademy-open-assets.s3-us-west-1.amazonaws.com/Module-JavaScript/promises/assets/promise-error-diagram-source.svg" alt="promise errors" style="width: 100%; height: auto">
</p>

As you can see, the first `Promise` object from the `readFilePromise` function
goes into the **rejected** state because, according to the error message, the
file didn't exist at the time the system tried to read it. That reason is
represented as an object that has a code of "ENOENT" which a Unix error code and
a message that provides a human-readable explanation of the error. That error
reason object gets passed to the error handler of the first `then`. It's what
happens after that that is crazy neat.

The second `Promise` object is **fulfilled**! Because the first `then` doesn't
have any errors, because the error handler in the first then completes without
any problem (printing out the error reason), the `Promise` returned by that
`then` _does not_ get **rejected**. Because of that, the `Promise` resolves with
the value returned by the `console.error('Badness happened', err)` call. The
`console.error` method returns `undefined`, so that becomes the value passed
into the next `then` handler.

Because the second `then` success handler relies on an object with a `length`
property, when it runs, an exception gets raised because the `undefined` value
has no `length` property. This causes the `Promise` returned by the second
`then` to become **rejected** because the code threw an exception.

Because that `Promise` is in the **rejected** state, it attempts to run the
error handler of the next (third) `then`. There is no error handler. In the
browser, it just looks like nothing happened. In Node.js, an
`UnhandledPromiseRejectionWarning` is emitted to the console. In a future
version of Node.js, it will cause the process to terminate with an exit code
indicating an error bringing your service to a halt.

To correctly handle the exception of no file to read and still have all of the
other lines of code run properly, you should write the following code.

```javascript
readFilePromise("manifest.txt")
  .then(manifest => manifest.split("\n"))
  .then(fileList => fileList.length)
  .then(
    numberOfFiles => console.log("Reading", numberOfFiles, "files"),
    reason => console.err("Badness happened", reason)
  );
```

Now, if an error occurs, the chain of `then`s evaluates like this:

1. First `then`: I do not have an error handler. I will pass the error on and
   not run the success handler.
1. Second `then`: I do not have an error handler. I will pass the error on and
   not run the success handler.
1. Third `then`: I have an error handler and will run it.

Now, the code looks almost like you'd imagined back in the
[Designing a better solution](#designing-a-better-solution) section. There's
still that annoying last double handler code that makes us use indentation and
passing in two function objects to a `then` which looks kind of yucky. The
Technical Committee gave you a solution for that, too.

> `then` can handle both success and failures. The success handler is called
> with the value of the operation of the `Promise` when the `Promise` object
> transitions to the **fulfilled** state. If an error condition occurs, them the
> error handler of the `then` is called.
>
> If a `Promise` object transitions to the **rejected** state and no error
> handler exists for the `then`, then that `then` is skipped altogether.
>
> If an error handler is called and does not raise an exception, then the next
> `Promise` object transitions to the **fulfilled** state and the next success
> handler is called.

## Handling failure with `catch`

Rather than using a `then` with a success and error handler, you can use the
similar `catch` method that takes just an error handler. By doing that, the code
from the last section ends up looking like this.

```javascript
readFilePromise("manifest.txt")
  .then(manifest => manifest.split("\n"))
  .then(fileList => fileList.length)
  .then(numberOfFiles => console.log("Reading", numberOfFiles, "files"))
  .catch(reason => console.err("Badness happened", reason));
```

That is exactly what the design expressed. The `catch` acts just like an error
handler in the last `then`. If the `catch` doesn't throw an exception, then it
returns a `Promise` in a fulfilled state with whatever the return value is, just
like the error handler of a `then`.

> `catch` is a convenient way to do error handling in a `then` chain that looks
> kind of like part of a try/catch block.

## Using `Promise.all` for many future values

You're almost to the place where you can read the manifest file, get the list,
and then count the characters in each of the files, and print out the result.
You need to learn about two more features of JavaScript `Promise`s.

Imagine that you have three files that you want to read with the
`readFilePromise` method. You want to wait until all three are done, but let
them read files simultaneously. How do you manage all three `Promise`s as one
`Promise`? That's what the `Promise.all` method allows you to do.

For example, imagine you have the following array.

```javascript
const values = [
  readFilePromise("file-boop.txt"), // this is a Promise object: pending
  readFilePromise("file-doop.txt"), // this is a Promise object: pending
  readFilePromise("file-goop.txt"), // this is a Promise object: pending
];
```

When you pass that array into `Promise.all`, it returns a `Promise` object that
manages all of the `Promise`s in the array!

```javascript
const superPromise = Promise.all(values);
// superPromise is a Promise object in the pending state.
//
// Inside superPromise is an array of Promise objects
// that look like this:
//
// 1. file reading promise in pending state, same as the one passed in
// 2. file reading promise in pending state, same as the one passed in
// 3. file reading promise in pending state, same as the one passed in
```

When all of the `Promise` objects in the super `Promise` transition out of the
pending state, then the super `Promise` will also transition out of the pending
state. If any one of the `Promise` objects in the array transition to the
**rejected** state, then the super `Promise` will immediately transition to the
**rejected** state with the same reason as the inner `Promise` failed with. If
_all_ of the internal `Promise` objects transition to the **fulfilled** state,
then the super `Promise` will transition to the **fulfilled** state and its
value will be an array of _all_ of the resolved values of the original array.

With that in mind, you could continue the above code with a `then` and a `catch`
that would demonstrate what happens.

```javascript
superPromise
  .then(values => console.log(values))
  .catch(reason => console.error(reason));

// If the function successfully reads the file, the values passed
// to the then come from the values that were in the superPromise
//
// 1. the content of file-boop.txt
// 2. the content of file-doop.txt
// 3. the content of file-goop.txt

// If something goes wrong with reading the file, then the `catch`
// gets called with the error reason from the Promise object that
// first failed.
```

> `Promise.all` accepts an array of values and returns a new `Promise` object in
> the **pending** state colloquially called a "super promise". It converts all
> non-`Promise` values into `Promise` objects that are immediately in the
> **fulfilled** state. Then,
>
> - If any one of the `Promise`s in the array transitions to the **rejected**
>   state, then the "super promise" transitions to the **rejected** state with
>   the same reason that the inner `Promise` object failed.
> - If all of the inner `Promise` objects in the array transition to the
>   **fulfilled** state, then the "super promise" transitions to the
>   **fulfilled** state with a value of an array populated, in order, of the
>   resolved values of the original array.

## Flattening `Promises`

The last thing you need to learn about `Promise`s is the coolest feature of them
all. If you return a `Promise` object from either a success or error handler,
the next step doesn't get run until that `Promise` object resolves! Here's what
happens when you type the following code. It's step 4 that is the amazing part.

```javascript
readFilePromise("manifest.txt")
  .then(manifestContent => manifestContent.split("\n"))
  .then(manifestList => manifestList[0])
  .then(fileName => readFilePromise(fileName))
  .then(otherFileContent => console.log(otherFileContent));

// Interpreted as:
// 1. Read the file of the manifest.txt file and pass the
//    content to the first then.
// 2. Split the content from manifest.txt on newline chars
//    to get the full list of files.
// 3. Return just the first entry in the list of files.
// 4. RETURN A PROMISE THAT WILL READ THE FILE NAMED ON THE
//    FIRST LINE OF THE manifest.txt! The next then method
//    doesn't get called until this Promise object completes!
// 5. Get the content of the file just read and print it.
```

Again, here's the rule.

> If you return a `Promise` from a success or error handler, the next handler
> isn't called until that `Promise` completes.

## Putting it all together

You can now use all of this knowledge to use `Promise`s to read a manifest file,
read each of the files in the manifest files, and count all of the characters in
those files with code that reads much better than this.

```javascript
readFile("manifest.txt", "utf8", (err, manifest) => {
  const fileNames = manifest.split("\n");
  const characterCounts = {};
  let numberOfFilesRead = 0;

  // Loop over each file name
  for (let fileName of fileNames) {
    // Read that file's content
    readFile(fileName, "utf8", (err, content) => {
      // Count the characters and store it in
      // characterCounts
      countCharacters(characterCounts, content);

      // Increment the number of files read
      numberOfFilesRead += 1;

      // If the number of files read is equal to the
      // number of files to read, then print because
      // we're done!
      if (numberOfFilesRead === fileNames.length) {
        console.log(characterCounts);
      }
    });
  }
});
```

Remember that you've created a `countCharacters` methods elsewhere that does the
grunt work of counting characters. So, now, if you were to list out the steps
that you'd like to have the code perform, you should be able to write a
`Promise`-based chain of `then`s that does that work.

1. Read `manifest.txt`.
1. Split the content into a list of files.
1. Read the contents of each file.
1. If all of them succeed, then
   - count the characters in each file and
   - print the character counts.
1. If anything fails, print the error.

So, in code, that you would translate that to the following.

```javascript
const characterCounts = {};
readFilePromise('manifest.txt')
  .then(fileContent => fileContent.split('\n'))
  .then(fileList => fileList.map(fileName => readFilePromise(fileName)))
  .then(lotsOfReadFilePromises => Promise.all(lotsOfReadFilePromises))
  .then(contentsArray => contentsArray.forEach(c => countCharacters(characterCounts, c))
  .then(() => console.log(characterCounts))
  .catch(reason => console.error(reason));
```

Through the magic of `Promise`s, you have now been able to do lots of
asynchronous work but make it look synchronous!

## Creating your own `Promise`s

Early on, you designed the way `Promise`s should work to look something like
this.

```javascript
log("Q")
  .then(() => log("W"))
  .then(() => pause(2))
  .then(() => log("E"))
  .then(() => log("R"))
  .then(() => pause(1))
  .then(() => log("T"));
```

That code uses two functions that you can define:

- a `log` function that takes a value to print and returns a `Promise` object
  that is in the **fulfilled** state; and,
- a `pause` function that takes a number and returns a `Promise` object that,
  after the indicated number of seconds, transitions to the **fulfilled** state.

Here is a way that you could create those functions.

```javascript
function log(message) {
  console.log(message);
  return Promise.resolve();
}
```

The above function logs the message passed to it and, then creates a `Promise`
object already transitioned to the **fulfilled** state. If you provide a value
to the resolve method, then that becomes the value of the `Promise` object.†

The `pause` method is a little more difficult. You have to create a new
`Promise` object from scratch to pause and then continue. To do that, you will
use the `Promise` constructor.

The `Promise` constructor accepts a function that has two parameters. Each of
those parameters will be functions, themselves. The first parameter is the
so-called **resolve** parameter which, when called, transitions the `Promise`
object to the **fulfilled** state. The second parameter is the so-called
**reject** parameter which, when called, transitions the `Promise` object to the
**rejected** state.

```javascript
function pause(numberOfSeconds) {
  return new Promise((resolve, reject) => {
    setTimeout(() => resolve(), numberOfSeconds * 1000);
  });
}
```

As you can see from the above code, the `new Promise` gets a single argument, a
two-parameter function that does some asynchronous thing. The two parameters are
the **resolve** and the **reject** functions that you can use to transition the
state of the `Promise` object being constructed. In this case, after a certain
amount of time, the `resolve()` method is invoked which transitions the
`Promise` object to the **fulfilled** state. The value is `undefined` because
you've passed no value into the `resolve()` function invocation. If you wanted
the `Promise` to have the value of 6.28, then you would invoke it like this
`resolve(6.28)`. You can pass any one value into the `resolve` function, be it a
number, a boolean, an array, an object, or whatever.

With that knowledge, think about how you would write a function using the
`readFile` function that would return a `Promise` object that would resolve to
the contents of the file on success and reject the `Promise` if an error
occurred. Take a moment to scratch that out into an editor or something.

If you wrote something similar to the following, then you did a great job! If
you didn't, work through the following in a Node.js JavaScript environment to
figure out how it works. You can use it like in any of the above examples.

```javascript
const { readFile } = require("fs"); // This is just the way to get
// the readFile method into the
// current file. If you don't
// understand it, that's ok.

function readFilePromise(path) {
  return new Promise((resolve, reject) => {
    readFile(path, "utf8", (err, content) => {
      if (err) {
        reject(err);
      } else {
        resolve(content);
      }
    });
  });
}
```

## What you've learned

In this reading, you learned some fancy new things that let's you turn
asynchronous code into seemingly synchronous-looking code. You did that by
learning that...

- `then` can handle both success and failures. The success handler is called
  with the value of the operation of the `Promise` when the `Promise` object
  transitions to the **fulfilled** state. If an error condition occurs, them the
  error handler of the `then` is called.
- If a `Promise` object transitions to the **rejected** state and no error
  handler exists for the `then`, then that `then` is skipped altogether.
- If an error handler is called and does not raise an exception, then the next
  `Promise` object transitions to the **fulfilled** state and the next success
  handler is called.
- `catch` is a convenient way to do error handling in a `then` chain that looks
  kind of like part of a try/catch block.
- `Promise.all` accepts an array of values and returns a new `Promise` object in
  the **pending** state colloquially called a "super promise". It converts all
  non-`Promise` values into `Promise` objects that are immediately in the
  **fulfilled** state. Then,
  - If any one of the `Promise`s in the array transitions to the **rejected**
    state, then the "super promise" transitions to the **rejected** state with
    the same reason that the inner `Promise` object failed.
  - If all of the inner `Promise` objects in the array transition to the
    **fulfilled** state, then the "super promise" transitions to the
    **fulfilled** state with a value of an array populated, in order, of the
    resolved values of the original array.
- If you return a `Promise` from a success or error handler, the next handler
  isn't called until that `Promise` completes.
- You can create a **fulfilled** `Promise` object by using the
  `Promise.resolve(value)` method.
- You can create your own `Promise` objects from scratch by using the `Promise`
  constructor with the form
  ```javascript
  new Promise((resolve, reject) => {
    // do some async stuff
    // call resolve(value) to make the Promise succeed
    // call reject(reason) to make the Promise fail
  });
  ```

## See also

- [Section: Promises, ECMAScript® 2015 Language Specification](https://www.ecma-international.org/ecma-262/6.0/#sec-promise-objects)
  is the minimum standard for how JavaScript Promises should act in **all**
  JavaScript environments. Language standards are dense and hard to read. You
  may want to give it a shot. The more you grow in your knowledge of how
  JavaScript works, the clearer it should become.
- [The Promises/A+ Specification](https://promisesaplus.com/) has a very nice
  terse description of how Promises work. It is mostly the standard that was
  adopted by the Technical Committee 39 when including the `Promise` object into
  JavaScript.

†: There's a corresponding `Promise.reject(reason)` method that creates a
  `Promise` object immediately in the **rejected** state.
