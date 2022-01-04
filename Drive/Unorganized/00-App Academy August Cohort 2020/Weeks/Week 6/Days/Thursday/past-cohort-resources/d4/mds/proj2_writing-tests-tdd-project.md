# Test-Driven Development Project

So now it is finally time to flex your fingers and start writing some tests! For
this next project we'll be using test-driven development (TDD). A TDD approach
dictates that we'll follow the TDD workflow, meaning that you'll need to follow
the TDD workflow of **Red**, **Green**, **Refactor**.

![tdd-cycle][rgr]

[rgr]:
  https://appacademy-open-assets.s3-us-west-1.amazonaws.com/Module-JavaScript/testing/assets/rgr.png

So the three steps for approaching all of the below problems will be to:

1. **Red**: Write the tests and watch them fail (a failing test is red).
2. **Green**: Write the minimum amount of code to ensure the test passes.
3. **Refactor**: Refactor the code you just wrote to make it readable and
   maintainable.

You can assume for the rest of the project that you will be using Mocha as your
testing framework, and you can use either Node's built in `assert` module or the
Chai library unless otherwise specified.

Before beginning to write tests we'll start by installing the dependencies we'll
need for `chai` and `chai-spies`. Start by creating a directory for this project
on your computer named `tdd-project`. Navigate into the directory in your
terminal, then run `npm init --y` to create a `package.json`. Once that has been
created you can install `chai` and `chai-spies` by running
`npm install chai chai-spies`. Once the dependencies have been installed you are
ready to start writing tests!

## Phase 0: Testing the reverseString function

We'll begin by writing tests for a function named `reverseString`. Create two
directories in your `tdd-project` directory - one named `problems` and one named
`test`. In the `problems` directory create a new file named `reverse-string.js`,
then within the `test` folder create a corresponding `reverse-string-spec.js`
file.

This would be a good time to open up the documentation for [Mocha][mocha],
[Assert][assert], [Chai][chai], and [Chai Spies][chai-spies]. The tests you are
writing today will be good practice for the _rest of your programming career_ so
take your time and ensure you are writing the best tests you can!

For this first phase feel free to use either `assert` or `chai` as your
assertion library. Whichever you choose make sure you require it into
`reverse-string-spec.js`.

> Hint: You can look back at the Tower of Hanoi project if you can't remember the proper require lines for this.

Also make sure you require your `reverseString` function so you will have it available to test.

> Hint: Since the file lives in the `problems` folder you might need to use our old friend `..` in the path.

Now it's your time to shine - write a test that will ensure that when given the
input `"fun"` the `reverseString` function will return the reversed output
(`nuf`). Now run your spec and watch it fail. If you did this correctly you should have mocha telling you `TypeError: reverseString is not a function`.

Remember! This is expected because we are doing test-driven development and we have written the test before we have written the `reverseString` function.

Now that the _red_ step is complete, time to move onto the _green_ step. Write
the minimum amount of code to pass the spec you just wrote - make sure you
remember to properly import and export your function!

> Reminder: You can run all the tests in the `test` directory by running the
> `mocha` command in the top level directory that the `test` directory is
> located within. You can also run a single test file with Mocha by specifying
> the file path like so: `mocha test/reverse-string-spec.js`.

Once you've passed the spec you wrote it's time to _refactor_. Take a look at
your `reverseString` function and see how it could be improved to be more
readable. For example: could it be more DRY?

Okay, let's add another spec to this function to test how it handles errors. Use
`chai` or `assert`'s `throws` function to ensure that when the `reverseString`
function is invoked with an argument that is not a string it will throw a
`TypeError`.

Nice! As you are writing these tests make sure you are following the TDD
workflow and writing _readable_ tests. Each of your `describe`, `context`, and
`it` functions should always be passed a string that clearly indicates what is
being testing.

## Phase 1: Testing multiple functions

Create a new file within the `problems` directory named `number-fun.js`. Make
sure your create the corresponding testing file within the `test` directory.
We'll be using Node's `Assert` for this one so be sure you import it at the top
of your testing file. You'll be testing two functions in this file so you'll
want to make sure you set up two outer `describe` blocks - one for each
function.

We'll start off easy by writing a spec for a function called `returnsThree`.
Test that this function returns the number `3`. Now write the code to pass that
spec.

Cool, let's step it up a notch - in the second `describe` function you'll be
writing the tests for a function called `reciprocal(num)`. This function should
intake a number and then return the [reciprocal][reciprocal] of that number.
Start by writing a spec to ensure that your `reciprocal` function will return
the reciprocal of the given argument. For this test include more than one
assertion line (`assert.strictEqual(value, value)`) within your `it` callback
function to make sure your function will behave as expected with multiple
inputs.

Now write the code to pass those tests, then refactor that code. Once you've
finished we'll be adding some different **contexts** for your `reciprocal`
function. Your `reciprocal` function will now only intake arguments between 1 and 1000000. If the given argument is less than 1 or greater than 1,000,000 then a `TypeError` will be thrown with a descriptive string message.

In order to properly test the `reciprocal` function you'll need to create two
`context` blocks within the `reciprocal` `describe` function callback - one for
invalid arguments and one for valid arguments. Move the the spec you wrote
previously into the `context` callback for valid arguments. You'll want to write
at least two new specs within your invalid argument `context` block to ensure
your `reciprocal` is being fully tested.

Once you've passed all your written specs and refactored move on!

[reciprocal]: https://www.mathopenref.com/reciprocal.html

## Phase 2: Testing the myMap Function

Next let's write a spec for a function you've all undoubtedly grown to love,
good old `myMap`. Create a new file in your `problems` directory, with a
corresponding file in your `test` directory for testing this function. This
version of `myMap(array, callback)` will intake an array and a callback, and
then return a new array where the callback has been called upon each element in
the original array. The `myMap` should not mutate the original argument array.

We'll be using `chai` and `chai-spies` for this series of tests.

Here is a quick example of how we expect this to work:

```js
const arr = [1, 2, 3];
const callback = el => el * 2;

console.log(myMap(arr, callback)); // prints [2,4,6]
console.log(arr); // prints [1,2,3]
```

Start off by writing your tests. You want to ensure that your `myMap` works like
the built-in `Array#Map` method. Once you've written the test, write the code
that will pass the test, then refactor.

Nice! Now let's really thoroughly test the `myMap` function. However, before we
do that we'll want to make sure that any specs we write after this first spec
will be working with a fresh array to ensure each unit test is done in
_isolation_. The DRYest way to do this is by setting up a Mocha hook! Use the
`beforeEach` Mocha hook to reassign a new instance of an `Array` each time a
spec is run.

Now that our hook is in place we'll write two tests:

1. Ensure that `myMap` does not mutate the passed-in array argument
2. Ensure that `myMap` does not call the built-in `Array#map`
3. Ensure that the passed-in callback is invoked once for each element in the
   passed-in array argument.

Write the first of these specs now before moving on below.

For the described specs for 2-3 in the above list you will be required to use
`chai-spies` so make sure you have the documentation up! Approach these specs
one at a time - we recommend using the `chai.spy.on` function for both of the
above specs.

> Hint: In order to use `chai.spy.on` you'll want to think carefully about
> **what object** you are spying on the methods for. For spec 3 described above
> you'll need to make sure you have an object to spy on so don't be afraid to
> make an object just for testing purposes.
>
> Also in order to spy on a plain function instead of a property of an object you use `chai.spy` instead of `chai.spy.on` and then use the resulting spied function directly.

Once you've finished the above specs and written the code to pass them make sure
you refactor your code before moving on!

## Phase 3: Testing Classes

For this next phase you will be utilizing Chai to test a `Person` class. Create
the necessary files within your `test` and `problems` directories. Work one spec
at a time through the list below using Red, Green, Refactor as you go and don't
forget to use Mocha Hooks to make your specs super DRY!

Write specs for each of the described `Person` class methods below:

- The `Person` Constructor - will intake a name and age and set them as
  properties on the instance. Make sure you test that these properties exist on
  an instance, as well as ensuring they are set properly.
- `prototype.sayHello` - will return a string of the person instance's name and
  a greeting message
- `prototype.visit(otherPerson)` - will return a string stating that this
  instance visited the passed-in person instance (i.e. `person1.visit(person2)`
  returns `Mai visited Erin`).
- `prototype.switchVisit(otherPerson)` - will invoke the `visit` function of the
  parameter (`otherPerson`), passing in the current instance as the argument.
- `prototype.update(obj)` - this method will have two contexts if the incoming
  argument _is_ or _is not_ a valid object.
  - A: If the incoming argument is not an object throw a new TypeError with a
    clear message
  - B: If the incoming argument is an object then the instance's properties
    should be updated to match the passed-in object's values as shown below.
  - C: If the incoming object does not have a name and an age property, throw a TypeError with an appropriate message

```js
let coolPerson = new Person("mai", 32); // Person { name: 'mai', age: 32 }
coolPerson.update({ name: "lulu", age: 57 });
console.log(coolPerson); // Person { name: 'lulu', age: 57 }
```

- `prototype.tryUpdate(obj)` - this method will call the `prototype.update`
  method with the incoming argument, and it will have two contexts if the
  invocation of `prototype.update` was or was not successful:

  - A: If `prototype.update` is successfully invoked (it does not throw an
    error) then a `true` is returned indicating the update was successful (make
    sure that the instance was updated as well)
  - B: If `prototype.update` is not successfully invoked it should **not** throw
    an error, instead it should return `false`.

- `greetAll(obj)` - this static method will intake an array of `Person`
  instances. The `greetAll` method will then call the `sayHello` method on each
  `Person` instance and store each returned string in an array, before finally
  returning an array of the stored strings.

Once you've finished and you've refactored all your code feel free to run
`mocha` and look at all those passed specs! Give yourself a pat on the back for
starting your journey into TDD development.

[assert]: https://nodejs.org/api/assert.html
[mocha]: https://mochajs.org/#bdd
[chai]: https://www.chaijs.com/api/bdd/
[chai-spies]: https://www.chaijs.com/plugins/chai-spies/
