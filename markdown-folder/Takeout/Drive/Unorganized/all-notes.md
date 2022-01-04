# 1. Monday:--------------------------------------

# **Notes**

## **HTTP Basics**

> "If you want to build a ship, don’t drum up the men and women to gather wood, divide the work, and give orders. Instead, teach them to yearn for the vast and endless sea." - Antoine de Saint-Exupery;

- **`HTTP`** : Hypertext Transfer Protocol.

  - **`HT`** : Hypertext - content with references to other content.
    - Term used to refer to content in computing.
    - What makes the Web a "web".
    - Most fundamental part of how we interact.
    - **`Hyperlinks`** : Links; references between HT resources.
  - **`TP`** : Transfer Protocol - set of guidelines surrounding the transmission of data.
    - Defines the expectations for both ends of the transer.
    - Defines some ways the transfer might fail.

- HTTP is a **`request/response`** protocol.
- HTTP works between **`clients`** & **`servers`**.
  - **`Clients`** : User Agent - the data consumer.
  - **`Servers`** : Origin - Data provider & where the application is running.

![pic](https://assets.aaonline.io/Module-Web/http/image-http-exchange.svg)

**Properties of HTTP**

- **`Reliable Connections`** : Messages passed between a client & server sacrifice a little speed for the sake of trust.

  - **`TCP`** is HTTP's preferred connection type.

- **`Stateless Transfer`** : HTTP is a stateless protocol - meaning it does not store any kind of information.

  - HTTP supports cookies.

- **`Intermediaries`** : Servers or devices that pass your request along which come in three types:
  - 1. **`Proxies`** : Modify your request so it appears to come from a different source.
  - 2. **`Gateways`** : Pretend to be the resource server you requested.
  - 3. **`Tunnels`** : Simply passes your request along.

![pic](https://assets.aaonline.io/Module-Web/http/image-http-proxy-tunnel-gateway.svg)

---

## **HTTP Requests**

**Structure of an HTTP Request**

```
GET / HTTP/1.1
Host: appacademy.io
Connection: keep-alive
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_5) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/76.0.3809.132 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9
```

> Example of how an HTTP request looks like for visiting appacademy.io

- **Request-line & HTTP verbs**

  - The first line of an HTTP Request made up of three parts:
    1. The **`Method`** : Indicated by an HTTP Verb.
    2. The **`URI`** : Uniform Resource Indicator that ID's our request.
    3. THe **`HTTP` Version** : Version we expect to use.
  - HTTP Verbs are a simply way of declaring our intention to the server.
    - **`GET`** : Used for direct requests.
    - **`POST`**: Used for creating new resources on the server.
    - **`PUT`**: Used to updated a resource on the server.
    - **`PATCH`** : Similar to PUT, but do not require the whole resource to perform the update.
    - **`DELETE`** : Used to destroy resources on the server.

- **Headers**

  - Key-Value pairs that come after the request line - they appear on sep. lines and define metadata needed to process the request.
  - Some common headers:
    - **`Host`** : Root path for our URI.
    - **`User-Agent`** : Displays information about which browser the request originated from.
    - **`Referer`** : Defines the URL you're coming from.
    - **`Accept`** : Indicates what the client will receive.
    - **`Content`-** : Define Details about the body of the request.

- **Body**
  - For when we need to send data that doesn't fit into the header & is too complex for the URI we can use the _body_.
  - **`URL encoding`** : Most common way form data is formatted.
  - `name=claire&age=29&iceCream=vanilla`
  - We can also format using JSON or XML.

**Sending an HTTP request from the command line**

- **netcat** : (nc) A Utility that comes as part of Unix-line environments such as Ubuntu and macOS.
  - Allows us to open a direct connection with a URL and manually send HTTP requests.
  - `nc -v appacademy.io 80`
  - `man nc` to open the netcat manual.

---

## **HTTP Responses**

**Structure of a Response**

```
HTTP/1.1 200 OK
Content-Type: text/html; charset=utf-8
Transfer-Encoding: chunked
Connection: close
X-Frame-Options: SAMEORIGIN
X-Xss-Protection: 1; mode=block
X-Content-Type-Options: nosniff
Cache-Control: max-age=0, private, must-revalidate
Set-Cookie: _rails-class-site_session=BAh7CEkiD3Nlc3Npb25faWQGOgZFVEkiJTM5NWM5YTVlNTEyZDFmNTNlN; path=/; secure; HttpOnly
X-Request-Id: cf5f30dd-99d0-46d7-86d7-6fe57753b20d
X-Runtime: 0.006894
Strict-Transport-Security: max-age=31536000
Vary: Origin
Via: 1.1 vegur
Expect-CT: max-age=604800, report-uri="https://report-uri.cloudflare.com/cdn-cgi/beacon/expect-ct"
Server: cloudflare
CF-RAY: 51d641d1ca7d2d45-TXL

<!DOCTYPE html>
<html>
...
...
</html>
```

- **Status**

  - First line of an HTTP response - gives us a high level overview of the server's intentions. (**`status line`**)
  - `HTTP/1.1 200 OK`
  - **`HTTP status codes`** : numeric way of representing a server's response.
    - Follow the structure: x: xxx - xxx;
    - **`Status codes 100 - 199: Informational`**
      - Allow the clinet to know that a req. was received, and provides extra info from the server.
    - **`Status codes 200 - 299: Successful`**
      - Indicate that the request has succeeded and the server is handling it.
      - Common Examples: 200 OK (req received and fulfilled) & 201 Created (received and new record was created)
    - **`Status codes 300 - 399: Redirection`**
      - Let the client know if there has been a change.
      - Common Examples: 301 Moved Permanently (resource you requested is in a totally new location) & 302 Found (indicates a temporary move)
    - **`Status codes 400 - 499: Client Error`**
      - Indicate problem with client's request.
      - Common Examples: 400 Bad Request (received, but could not understand) & 401 Unauthorized (resource exists but you're not allowed to see w/o authentication) & 403 Forbidden (resource exists but you're not allowed to see it at all ) & 404 Not Found (resource requested does not exist);
    - **`Status codes 500 - 599: Server Error`**
      - Indicates request was formatted correctly, but the server couldn't do what you asked due to an internal problem.
      - Common Examples: 500 Internal Server Error (Server had trouble processing) & 504 Gateway Timeout (Server timeout);

- **Headers** : Work just like HTTP requests.

  - Common Examples:
    - **`Location`** : Used by client for redirection responses.
    - **`Content-Type`** : Let's client know what format the body is in.
    - **`Expires`** : When response is no longer valid
    - **`Content-Disposition`** : Let's client know how to display the response.
    - **`Set-Cookie`** : Sends data back to the client to set on the cookie.

- **`Data`** : If the request is successful, the body of the response will contain the resource you have requested.
  Send a simple HTTP request to google.com - We can use netcat in the terminal to make a connection to a URL and send an HTTP request - `nc google.com 80` opens our connection to google.com - After we make our connection, we specify the three parts of an HTTP request: - Request line - Headers - Body - `GET / HTTP/1.1` creates the request-line, indicating our verb (GET), URI (/), and version (HTTP/1.1) - any other headers we would like (optional), such as `Accept: application/json` - body of the request (optional), such as `myKey=myValue`

Write a very simple HTTP server using ‘http’ in node with paths that will result in the common HTTP status codes.

```javascript
const http = require("http");

http
	.createServer(function (request, response) {
		if (request.url === "/200") {
			response.writeHead(200, { "Content-Type": "text/html" });
			response.write("<h1>Hello, world! Status 200 OK!</h1>");
		} else if (request.url === "/403") {
			response.writeHead(403, { "Content-Type": "text/html" });
			response.write("<h1>This is Forbidden! Status 403 Forbidden!</h1>");
		} else {
			response.writeHead(404, { "Content-Type": "text/html" });
			response.write("<h1>What is that? Status 404 Not Found!</h1>");
		}
		response.end();
	})
	.listen(8080, function () {
		console.log("Listening for requests on port 8080...");
	});
```

---

# 2. Tuesday:--------------------------------------

# **Notes**

## **Promises**

When you declare a function normally:

```js
function loudLog(message) {
	console.log(message.toUpperCase());
}
```

- Just declaring it like that does not actually run the function.
- It _does_ create a Function object and stores that in a variable named **loudLoud**.
- **Promises** are wrappers around asychronous code.

```js
readFile("~/Documents/todos.txt", "utf8", function (err, content) {
	console.log("YOUR FILE CONTAINS:");
	console.log(content);
});
```

- Javascript is idiomatic, so if you're only going to call a function once just set it directly into the callback of your readfile in this example.
- To take it up a notch, JS now just wants you to write the callback with an arrow function.

```js
readFile("~/Documents/todos.txt", "utf8", (err, content) => {
	console.log("YOUR FILE CONTAINS:");
	console.log(content);
});
```

- **`Promise`** : a commitment that sometime in the future, your code will get a value from some operation (like reading a file or getting JSON from a Website) or your code will get an error from that operation (like the file doesn't exist or the Web site is down).

  - Promises exist in three states:

  1. **`Pending`** : Promise object has not resolved. Once it does, the state of the Promise object may transition to either the fulfilled or rejected state.
  2. **`Fulfilled`** : Whatever operation the Promise represented succeeded and your success handler will get called. After fulfillment, the Promise:
     - _must not transition to any other state_
     - _must have a value, which must not change_
  3. **`Rejected`** : Whatever operation the Promise represented failed and your error handler will get called. When it is _rejected_:
     - _must not transition to any other state_
     - _must have a reason, which must not change_

- Promise objects use the following methods to go through these stages.
  - **`then`(successHandler, errorHandler)**
  - **`catch`(errorHandler)**

* **`Success Handler`** : function that has one parameter, the value that a fulfilled _promise_ has.

* **`Error Handler`** : funvtion that has one parameter, the reason that the _promise_ failed.

**Handling Success with Then**

```js
readFilePromise("manifest.txt").then((manifest) => {
	const fileList = manifest.split("\n");
	console.log("Reading", fileList.length, "files");
});
```

- Each promise has a then() method that handles what will happen when the Promise comes out fof the **pending** state.
- Each then, returns another Promise that transitions out of it's pending state when the **then** that created it completes.
- You can pass a second argument into the then method as the **error handler**; (essentially saying, if this then does not resolve, then this error handler will do something.)

```js
readFilePromise("manifest.txt")
	.then((manifest) => manifest.split("\n"))
	.then((fileList) => fileList.length)
	.then(
		(numberOfFiles) => console.log("Reading", numberOfFiles, "files"),
		(reason) => console.err("Badness happened", reason)
	);
```

- You can also use a **catch** error handler at the end of your then chain to catch any error that may happen along the way.

```js
readFilePromise("manifest.txt")
	.then((manifest) => manifest.split("\n"))
	.then((fileList) => fileList.length)
	.then((numberOfFiles) => console.log("Reading", numberOfFiles, "files"))
	.catch((reason) => console.err("Badness happened", reason));
```

**Using Promise.all**

- Promise.all is a method that accepts an array of values and returns another Promise object called a **`SUPER PROMISE`**; it converts all non-promise values into Promise objects that are immediately in the fulfilled state.
  - If any of the promises in the array fail, then the whole thing falls to an error.
  - All of the inner promises need to be fulfilled for the super promise to reach a **fulfilled state**.

**Flattening Promises**

```js
readFilePromise("manifest.txt")
	.then((manifestContent) => manifestContent.split("\n"))
	.then((manifestList) => manifestList[0])
	.then((fileName) => readFilePromise(fileName))
	.then((otherFileContent) => console.log(otherFileContent));

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

- You can pass another promise object inside a promise then chain, and the current then chain will not continue until the promise on the inside is resolved.

## Promises - Part 1 (W6D2) - Learning Objectives

### Promises

1. Instantiate a Promise object

- We can instantiate a Promise object using the `new` keyword.
- The Promise takes in a callback that we can invoke, taking in two arguments: typically labelled `resolve` and `reject`.
  - `resolve` is invoked when we want to indicate our function has successfully completed. A value can be passed as the successful return value.
  - `reject` is invoked when we want to indicate that our function failed in some way. A value can be passed as the fail value (what would be used in a `catch` or the second argument to `then`).

```javascript
function pause(numberOfSeconds) {
	return new Promise((resolve, reject) => {
		// resolve is invoked to indicate a success, reject is a failure
		// if a value is passed to resolve, it will be caught as the first argument to .then()
		// if a value is passed to reject, it will be caught as the first argument to .catch(), or the second argument to .then()
		setTimeout(() => resolve(), numberOfSeconds * 1000);
	});
}
```

2. Use Promises to write more maintainable asynchronous code

   - We can chain .then calls on Promises, ensuring that the callback will not be run until the previous statement has finished executing.
   - Prevents us from having to nest our callbacks

   ```javascript
   // Without Promises, we have to nest our code.
   // These can get very confusing; this is a simple example, but it's already hard to tell what each setTimeout's delay is connected to.
   setTimeout(() => {
   	console.log(message);
   	setTimeout(() => {
   		console.log(message.toUpperCase() + "!");
   		setTimeout(() => {
   			console.log(message + "?");
   			setTimeout(() => {
   				console.log(message.toLowerCase() + "...");
   			}, 1 * 1000);
   		}, 3 * 1000);
   	}, 2 * 1000);
   }, 1 * 1000);

   // With Promises, we write more code up front in order for us to have more readable and maintainable code
   // We define our promises
   function promise1(message, delay) {
   	return new Promise((resolve, reject) => {
   		setTimeout(() => {
   			resolve(message);
   		}, delay * 1000);
   	});
   }

   function promise2(message, delay) {
   	return new Promise((resolve, reject) => {
   		setTimeout(() => {
   			resolve(message.toUpperCase() + "!");
   		}, delay * 1000);
   	});
   }

   function promise3(message, delay) {
   	return new Promise((resolve, reject) => {
   		setTimeout(() => {
   			resolve(message + "?");
   		}, delay * 1000);
   	});
   }

   function promise4(message, delay) {
   	return new Promise((resolve, reject) => {
   		setTimeout(() => {
   			resolve(message.toLowerCase() + "...");
   		}, delay * 1000);
   	});
   }

   // Then we chain can chain them however we like.
   // Returning our strings from our Promises is adding flexibility to our code, allowing us to use the results however we like.
   // We replaced the complicated nesting with more modular chaining of .then
   promise1("hello", 1)
   	.then((res1) => {
   		console.log(res1);
   		return promise2("hi", 2);
   	})
   	.then((res2) => {
   		console.log(res2);
   		return promise3("hey", 3);
   	})
   	.then((res3) => {
   		console.log(res3);
   		return promise4("what's up", 1);
   	})
   	.then((res4) => {
   		console.log(res4);
   	});
   ```

3. Use the fetch API to make Promise-based API calls

```javascript
// init is an optional object argument to customize the method (default is 'GET'), headers, or body of the request
// For example, it could take the form:
// const init = { method: 'POST', headers: { 'Content-Type': 'application/json' }, body: '{"title": "Sir", "name": "Robin"}' }
fetch(url, init)
	.then((response) => {
		// do something with the response
		// common first action to take would be parsing the response
		// parsing json with response.json(), or text with response.text()
	})
	.then((data) => {
		// since fetch is returning a promise, we can chain on as many .then calls as we need
	});
```

# 3. Wednesday:----------------------------------

# **Notes**

## **Modern Promises with Async and Await**

```js
function walkTheDog() {
	return new Promise((resolve, reject) => {
		setTimeout(() => {
			resolve("happy dog");
		}, 1000);
	});
}

function doChores() {
	console.log("before walking the dog");
	walkTheDog().then((res) => {
		console.log(res);
		console.log("after walking the dog");
	});
	return "done";
}

console.log(doChores());
```

## Promises - Part 2 and HTML Review (W6D3) - Learning Objectives

### Promises

1. Use async/await with promise-based functions to write asynchrnous code that behaves synchronously.

```javascript
// Without async/await, we can use .then chains
// We use a .catch method to catch errors
function wrapper() {
	promise1("hello", 1)
		.then((res1) => {
			console.log(res1);
			return promise2("hi", 2);
		})
		.then((res2) => {
			console.log(res2);
			return promise3("hey", 3);
		})
		.then((res3) => {
			console.log(res3);
			return promise4("what's up", 1);
		})
		.then((res4) => {
			console.log(res4);
		})
		.catch((err) => {
			console.error("Error encountered:", err);
		});
}

wrapper();

// With async/await, our code looks more like synchronous code
// We use a standard try/catch block to handle errors
// In order for us to use `await` we must be in a function declared with `async`
async function wrapper() {
	try {
		console.log(await promise1("hello", 1));
		console.log(await promise2("hi", 2));
		console.log(await promise3("hey", 3));
		console.log(await promise4("what's up", 1));
	} catch (err) {
		console.error("Error encountered:", err);
	}
}

wrapper();
```

> Classic example of promise handling using two functions.

# 4. Thursday:-------------------------------------

# **Flashcards**

## **Javascript Errors**

**1. How do you halt program execution with an instance of an error object in JavaScript?**

- Using the keyword throw you can throw your own runtime errors that will stop program execution.

**2. What kind of error is thrown when a variable or parameter is not of a valid type?**

- A TypeError is thrown when an operation cannot be performed because the operand is a value of the wrong type.

**3. What kind of error will be thrown when the below code is executed?**

```js
function callPuppy() {
	const puppy = "puppy";
	console.log(pupy);
}

callPuppy();
```

- ReferenceError: pupy is not defined

**4. What kind of error will be thrown when the below code is run?**

```js
function broken () {
  console.log("I'm broke")
}}
```

- SyntaxError: Unexpected token '}'

**5. What kind of error will the below code throw when executed?**

```js
const puppy = "puppy";

puppy = "apple";
```

- TypeError: Assignment to constant variable.

**6. What kind of error will the below code throw when executed?**

```js
let dog;

dog();
```

- TypeError: dog is not a function

**7. What type of block will allow you to run an erroring function then continue the execution of code after that function is run?**

- We can use try...catch blocks with functions that might throw an error to catch that error and continue code execution after that error was thrown

**8. What type of error is thrown when a non-existent variable is referenced?**

- The ReferenceError object represents an error when a non-existent variable is referenced.

**9. When is a JavaScript Error Object thrown?**

- The Error object is how JavaScript deals with runtime errors - so at code runtime!

**10. When kind of error is thrown when the JavaScript engine attempts to parse code that does not conform to the syntax of the JavaScript language?**

- A SyntaxError is thrown when there is an error in the syntax of the executed code.

---

## **TDD**

**1. Identify at least two reasons why developers use TDD.**

- 1. Writing tests before code ensures that the code written works.
  2. Only required code is written.
  3. TDD helps enforce code modularity.
  4. Better understanding of what the code should be doing.

**2. What are the three steps of the TDD workflow?**

- Red, Green, Refactor

**3. What does a developer do in the Green step in the TDD workflow?**

- Write the minimum amount of code to ensure the tests pass (a
  passing test will be green).

**4. What does a developer do in the Red step in the TDD workflow?**

- Write the tests and watch them fail (a failing test is red). It's
  important to ensure the tests initially fail so that you don't have false
  positives.

**5. What does a developer do in the Refactor step in the TDD workflow?**

- Refactor the code you just wrote. Your job is not over when the
  tests pass! One of the most important things you do as a software developer
  is to ensure the code you write is easy to maintain and read.

**6. What does TDD stand for?**

- Test Driven Development.

---

### Testing

1. Explain the "red-green-refactor" loop of test-driven development.

- Red: Write tests and watch them fail (protect against false positives)
- Green: Write the minimum amount of code to get the test to pass
- Refactor: Refactor the written code so that it is easy to maintain and understand

2. Identify the definitions of SyntaxError, ReferenceError, and TypeError

- SyntaxError
  - an error in how the code is written
  - encountered at compile-time, ie the code cannot be parsed to determine the instructions
  - since our code cannot be run, SyntaxErrors cannot be caught by a try-catch block
  - common examples would be:
    - a misspelled function keyword (`funtion broken() {...}`)
    - incorrect number of curly braces
- ReferenceError

  - when a nonexistent variable is referenced
  - most commonly seen when you mistype a variable name, or refer to one out of the current scope

  ```javascript
  const puppy = "puppy";
  console.log(pupy); // mistyped variable name
  ```

  ```javascript
  function callPuppy() {
  	const puppy = "puppy";
  }
  console.log(puppy); // puppy is not in scope, it was created in the callPuppy function
  ```

3. Create, modify, and get to pass a suite of Mocha tests

- File Structure
  - Mocha will expect a `test` directory at the location that we are running our `mocha` command (typically the top level of our project)
  ```
  testing-demo
  └──
  problems
      └── reverse-string.js
  test
      └── reverse-string-spec.js
  ```
- Setting up `describe` and `it` blocks
  - We want to keep our tests organized just like our code.
  - A `describe` block gives a high level indication of what we are going to be testing, like the name of the function, module, or unit of code.
  - An `it` block tells us something that we are specifically testing. It defines an individual test that we are running.
  ```js
  describe ('reverseString()', function () {
      it('should reverse the input string', function () {
          // a test will go here!
      })
  }
  ```
- Using `assert` to test
  - Inside our `it` blocks we can use the `assert` module to execute a test.
  - There are many different functions we can use in this module.
  - A very common one is to use the `strictEqual` function, which compares two values. We can see other less common functions in the docs: https://nodejs.org/docs/latest-v12.x/api/assert.html#
  ```js
  // remember we required the assert module and reverseString function at the top of this file
  describe("reverseString()", function () {
  	it("should reverse the input string", function () {
  		let test = reverseString("hello");
  		let result = "olleh";
  		// the line below is where the actual test is!
  		assert.strictEqual(test, result);
  	});
  });
  ```
  - Another common thing to test is that a function throws an error appropriately. We can use the `throws` function, which accepts a callback to invoke, the error we expect when that callback is invoked, and a message to show if the fail doesn't go through correctly.
    - It's important to note here that if we expect our function to throw an error, we cannot invoke it immediately, or else our test file itself will error out. We need to surround it in another function creating a callback to be invoked later. Our assertion is then able to compare the error to the second argument.
  ```js
  // note that we are passing function(){reverseString(3);} as an argument, not reverseString(3) directly
  context("given an argument that is not a string", function () {
  	it("should throw a TypeError when given an argument that is not a string", function () {
  		assert.throws(
  			function () {
  				reverseString(3);
  			},
  			TypeError,
  			"this function only accepts string args"
  		);
  	});
  });
  ```

4. Use Chai to structure your tests using behavior-driven development principles.

- BDD vs. TDD => behavior driven development centers around what an application should do in plain english while TDD centers around how an application is implemented
- The Chai testing library provides additional functionality compared to using the basic `assert` module that comes with Node.
- Since it is external, we need to add it to our project with `npm install chai`
- After adding the library, we can require it just like the `assert` module with `const chai = require("chai");` at the top of our test files.
- Using `expect` from the `chai` library, we can chain "getters" together to construct tests that read like English. Since we use `expect` so much in our code, we generally separate it out at the top once instead of for each test: `const expect = chai.expect;`

```js
const chai = require("chai");
const expect = chai.expect;

// don't forget to import the class you are testing!
const Dog = require("../problems/dog.js");

describe("Dog Constructor Function", function () {
	it('should have a "name" property', function () {
		const layla = new Dog("Layla");
		expect(layla).to.have.property("name");
	});

	it('should set the "name" property when a new dog is created', function () {
		const layla = new Dog("Layla");
		// we are using the eql function to compare the value of layla.name
		// with the provided string
		expect(layla.name).to.eql("Layla");
	});
});
```

- This is a great cheatsheet for understanding what common chains are available to us: https://devhints.io/chai
- We can also reference the docs for a more detailed explanation: https://www.chaijs.com/api/bdd/

5. Use the pre- and post-test hooks provided by Mocha

- We learned about four hooks
  - before('description', callback): Callback is invoked before the block of test code is run
  - beforeEach('description', callback): Callback is invoked before each `it` statement in the block of test code
  - after('description', callback): Callback is invoked after the block of test code is run
  - afterEach('description', callback): Callback is invoked after each `it` statement in the block of test code
- before and beforeEach allows us to set up our test, pulling out common Arrange or Act portions of our tests
- after and afterEach are going to be less common for us, but allow us to do any kind of cleanup that may be necessary after a test has run
  - Looking forward, maybe we need to remove something from our database that our test created

6. Be familiar with `chai-spies` and its ability to test how many times a function is invoked

- After adding the `chai-spies` package to our project with `npm install chai-spies`, we can require it in our testing file. We are extending the functionality of the `chai` library, which has the `use` function to allow us to do so:

```js
const spies = require("chai-spies");
chai.use(spies);
```

- After this initial setup, we can spy on a particular function by creating a spy:

```js
// `on` takes in the object that we are spying on and the method we want to specifically watch
// Here we are saying to look at the layla object and track the calls to the chaseTail method
const chaseTailSpy = chai.spy.on(layla, "chaseTail");
```

- With our spy created, we can invoke whatever functions we would expect to call (or not call, if we are expecting 0 invocations) our method. We can then expect that our spy has been called any number of times:

```js
context("with a valid number parameter", function () {
	it("should call the chaseTail method n times", function () {
		const chaseTailSpy = chai.spy.on(layla, "chaseTail");
		layla.chainChaseTail(3);
		// below is our actual test to see how many times our spy was invoked
		expect(chaseTailSpy).to.have.been.called.exactly(3);
	});
});
```

```js
describe("myMap(array, callback)", () => {
	let inputArray;
	let callback = (el) => el + 1;
	beforeEach(() => {
		inputArray = [1, 2, 3];
	});
	// ...other tests
	it("should not call Array#map", () => {
		// The object we are spying on is the inputArray
		// We want to make sure we don't call `map` on it
		// We want our function do its own iteration and invocation
		// We are emulating Array#map instead of calling it directly
		const mapSpy = chai.spy.on(inputArray, "map");
		myMap(inputArray, callback);

		expect(mapSpy).to.not.have.been.called();
	});
});
```
