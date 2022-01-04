# A Promise is a Promise: A Mostly Complete Guide to JavaScript Promises I

This article is about a JavaScript feature formally introduced into the language
in 2015: the `Promise` object. The technical committee that governs the
JavaScript language recognized that programmers had a hard time reasoning about
and maintaining asynchronous code. They included `Promise`s as a way to
encourage writing asynchronous code in a way that *appeared* synchronous.

When you finish this article, you should be able to:

* Provide examples of why `Promise`-based code is easier to maintain than
  traditional asynchronous callbacks;
* Recall the three states of a `Promise`, what each state means, and any
  associated data with that state.

## A quick review of function declarations

It's important to remember about how JavaScript handles the declaration of a
function. Please look at the following code.

```javascript
function loudLog(message) {
  console.log(message.toUpperCase());
}
```

When JavaScript encounters that code, it does not run the function. You probably
know that, but it's important to read again. When JavaScript encounters that
code, it does not run the function.

It _does_ create a `Function` object and stores that in a variable named
`loudLog`. At some time later, you can run the function object in that variable
with the syntax `loudLog("error occurred");`. That _runs_ the function. Just
declaring a function doesn't run it. Look at this following code.

```javascript
function () {
  console.log('How did you call me?');
}
```

JavaScript will, again, create a `Function` object. However, there's no name for
the function, so it doesn't get assigned to any variable, and just disappears
with no way for us to use it. So, why would you declare functions without names?

## The looming problem of asynchronous code with callbacks

Let's look at the documentation for how to read files in Node.js. Don't worry if
you haven't used Node.js, yet. It's just like any other JavaScript.

```
readFile(path, encoding, callback)

Arguments:
  path      <string>    path to the file
  encoding  <string>    the encoding of the file
  callback  <function>  two arguments:
                        err      <error object>
                        content  <string>

Asynchronously reads the entire contents of a file.
```

The function named `readFile` accepts three arguments: a string that contains
the `path` to the file, the `encoding` of the file, and a callback function that
`readFile` calls once it's read the content of the file. If you wanted to write
out the content of the file with a header, you could write code like this.

```javascript
function writeWithHeader(err, content) {
  console.log("YOUR FILE CONTAINS:");
  console.log(content);
}

readFile('~/Documents/todos.txt', 'utf8', writeWithHeader);
```

Recall that when JavaScript found the function declaration at the beginning of
that code block, it created a `Function` object and stored it in a variable
named `writeWithHeader`. Now, that variable contains the actual function that
can later be run. That code passes the value of that variable, the `Function`
object, into the `readFile` function so the `readFile` function can run it
later.

If you're not going to use the `writeWithHeader` function anywhere else in your
code, idiomatic JavaScript instructs you to get rid of the name of the function
and declare it directly as the second argument of the `readFile` functions. That
would turn the above code block into the following.

```javascript
readFile('~/Documents/todos.txt', 'utf8', function (err, content) {
  console.log("YOUR FILE CONTAINS:");
  console.log(content);
});
```

Since 2015, idiomatic JavaScript would instruct you to get rid of the function
keyword and just use an arrow function.

```javascript
readFile('~/Documents/todos.txt', 'utf8', (err, content) => {
  console.log("YOUR FILE CONTAINS:");
  console.log(content);
});
```

The key to remember here is that you have only declared that function that
`readFile` will call later, `readFile` is in charge of running that function.

Imagine that you have a file that has a list of other file names in it named
`manifest.txt`. You want to read the file and read each of the files listed in
it. Then, you want to count the characters in each of those files and print
those numbers.

You would start out by reading `manifest.txt` and splitting the content on the
newline character to get the names of the files. That would look like this:

```javascript
readFile('manifest.txt', 'utf8', (err, manifest) => {
  const fileNames = manifest.split('\n');

  // More to come
});
```

Now that you have the list of file names, you can loop over them to read each
of those files. As each of those files are read, you want to count the characters
in each file. Imagine that you already have the function named `countCharacters`
somewhere. The looping code could look like this:

```javascript
readFile('manifest.txt', 'utf8', (err, manifest) => {
  const fileNames = manifest.split('\n');
  const characterCounts = {};

  // Loop over each file name
  for (let fileName of fileNames) {
    // Read that file's content
    readFile(fileName, 'utf8', (err, content) => {
      // Count the characters and store it in
      // characterCounts
      countCharacters(characterCounts, content);
    });
  }
});
```

At this point, you feel pretty good. There's only one thing left to do: print out the
total of all the characters in the files. So, where do you put that `console.log`
statement?

This is kind of a trick question because there's no place to put it in the way the code
works now.

If you put it here:

```javascript
readFile('manifest.txt', 'utf8', (err, manifest) => {
  const fileNames = manifest.split('\n');
  const characterCounts = {};

  // Loop over each file name
  for (let fileName of fileNames) {
    // Read that file's content
    readFile(fileName, 'utf8', (err, content) => {
      // Count the characters and store it in
      // characterCounts
      countCharacters(characterCounts, content);
    });
  }

  // MY PRINT STATEMENT HERE
  console.log(characterCounts);
});
```

then you will get the output `{}` every time because the code in the inner
`readFile`s doesn't run until after the `console.log` because `readFile` doesn't
run the function with the arguments `(err, content)` until _after_ the file is
read and the current function completes.

If you put it here:

```javascript
readFile('manifest.txt', 'utf8', (err, manifest) => {
  const fileNames = manifest.split('\n');
  const characterCounts = {};

  // Loop over each file name
  for (let fileName of fileNames) {
    // Read that file's content
    readFile(fileName, 'utf8', (err, content) => {
      // Count the characters and store it in
      // characterCounts
      countCharacters(characterCounts, content);

      // MY PRINT STATEMENT HERE
      console.log(characterCounts);
    });
  }
});
```

then it will print the number of times that your code reads a file. That's not
what you want, either. To get it to work, you have to count the number of files
that have been read each time one completes. Then, you only print when that
number equals the total number of files to be read. The code could like this:

```javascript
readFile('manifest.txt', 'utf8', (err, manifest) => {
  const fileNames = manifest.split('\n');
  const characterCounts = {};
  let numberOfFilesRead = 0;

  // Loop over each file name
  for (let fileName of fileNames) {
    // Read that file's content
    readFile(fileName, 'utf8', (err, content) => {
      // Count the characters and store it in
      // characterCounts
      countCharacters(characterCounts, content);

      // Increment the number of files read
      numberOfFilesRead += 1;

      // If the number of files read is equal to the
      // number of files to read, then print because
      // you're done!
      if (numberOfFilesRead === fileNames.length) {
        console.log(characterCounts);
      }
    });
  }
});
```

The asynchronous nature of this code requires you to do a lot of housekeeping
just to figure out when everything is done. Imagine writing this code and going
back to it in six months to add a new feature. It's not the clearest code in the
world, even with code comments. That leads to a maintenance nightmare. The
JavaScript community wanted a way to code better and clearer.

<a name="designing-a-better-solution"></a>
## Designing a better solution

Look at the following code that has numbers in the order in which the
`console.log` statements are run. It will print out "Q", "W", "E", "R", and "T"
on separate lines.†

```javascript
console.log('Q'); //---- 1
setTimeout(() => {
  console.log('E'); //-- 3
  setTimeout(() => {
    console.log('T'); // 5
  }, 100);
  console.log('R'); //-- 4
}, 200);
console.log('W'); //---- 2
```

What would really help is if you could get those numbers in order so that what
appears in the code at least **appears** to be synchronous even though it might
be asynchronous in nature. As humans, we understand things from top-to-bottom
much better than in the order 1, 3, 5, 4, 2.

Reordering the code above to reflect how it really runs, you'd get this somewhat
more maintainable block.

```javascript
console.log('Q'); //---- 1
console.log('W'); //---- 2
setTimeout(() => {
  console.log('E'); //-- 3
  console.log('R'); //-- 4
  setTimeout(() => {
    console.log('T'); // 5
  }, 100);
}, 200);
```

But, now you're stuck with those human-necessary indents to understand the
function calls that occur in the code. And, to know how long the `setTimeout`s
run, you have to go way to the bottom of the code blocks. The JavaScript
community agreed with you and decided it'd be great if they could somehow just
chain a bunch of those things together without the indentation, something like
this. (The function names are completely invented for this code block.);

```javascript
log('Q')
  .then(() => log('W'))
  .then(() => pause(200))
  .then(() => log('E'))
  .then(() => log('R'))
  .then(() => pause(100))
  .then(() => log('T'));
```

The JavaScript community realized that they'd have to use functions in the
`then` blocks lest the function be immediately invoked. Remember, a function
declaration is not invoked when interpreted. That means each function in each of
the `then` calls is passed into the `then` function for it to run at a later
time, presumably when the previous thing finishes, a previous `log` or `pause`
in this example. They decided to create a new kind of abstraction in JavaScript
named the "Promise".

<a name="so-what-is-a-promise"></a>
## So, what is a "Promise"?

Look at a line of code using the `readFile` method found in Node.js. Don't worry
if you don't know the specifics about this function. It's the _form_ of the code
to which you should draw your attention.

```javascript
readFile('manifest.txt', 'utf8', (err, manifest) => {
```

You could interpret that line of code as "Read the file named "manifest.txt"
and, when done, call the method that is declared with `(err, manifest) => {`.

The important part to understand is the "when done, call the method...". That's
the part that's potentially asynchronous, the part that is beyond your control.
When it calls that function, it will either provide an error in the `err`
parameter or a value in the `manifest` parameter. When you change it to the
`then` version, you still get the same kind of guarantee: eventually, you will
get an error or the value of the operation. So that's what a `Promise` is.

> A `Promise` in JavaScript is a commitment that sometime in the future, your
> code will get **a value** from some operation (like reading a file or getting
> JSON from a Web site) or your code will get **an error** from that operation
> (like the file doesn't exist or the Web site is down).

Promises can exist in three states. They are:

* **Pending**: The `Promise` object has not resolved. Once it does, the state of
  the `Promise` object may transition to either the fulfilled or rejected state.
* **Fulfilled**: Whatever operation the `Promise` represented succeeded and your
  success handler will get called. Now that it's _fulfilled_, the `Promise`:
  * must not transition to any other state.
  * must have a value, which must not change.
* **Rejected**: Whatever operation the `Promise` represented failed and your
  error handler will get called. Now that it's _rejected_, the `Promise`:
  * must not transition to any other state.
  * must have a reason, which must not change.

`Promise` objects have the following methods available on them so that you can
handle the state change from _pending_ to either _fulfilled_ or _rejected_.

* `then(successHandler, errorHandler)` is a way to handle a `Promise` when it
  leaves the _pending_ state.
* `catch(errorHandler)`

The handlers mentioned in the previous list are:

* **Success Handler** is a function that has one parameter, the value that a
  _fulfilled_ `Promise` has.
* **Error Handler** is a function that has one parameter, the reason that the
  `Promise` failed.

We'll elaborate on these methods in part two of this article.

## What you've learned

In this reading, you learned some fancy new things that allows you to turn
asynchronous code into seemingly synchronous-looking code. You did that by
learning that...

- A `Promise` in JavaScript is a commitment that sometime in the future, your
  code will get **a value** from some operation (like reading a file or getting
  JSON from a Web site) or your code will get **an error** from that operation
  (like the file doesn't exist or the Web site is down).

†: One can argue that the code following this statement is already very bad
      and shouldn't be written that way. I would agree. Please don't write code
      like that. It is *only* for demonstration purposes. However, do not be
      surprised if you find **someone else** wrote code like that. ;-)
