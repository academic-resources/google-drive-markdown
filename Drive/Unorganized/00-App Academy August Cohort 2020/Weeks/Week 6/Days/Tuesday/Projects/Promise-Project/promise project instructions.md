**


-   Promise Project

Curl Up With A Nice Promise
===========================

You've learned about how to use Promise objects to help master the
problems of asynchronous program logic. Now, you can really get your
hands dirty by building a Node.js-based version of the popular
[curl](https://curl.haxx.se/) utility!

You may not know, but `curl` is a command line
program to get the `c`ontent at `URL`.
 `cURL`. Get it?

This project
------------

You will create a version of the `curl` utility that
will be able to

-   Download content from the Internet
-   Save it into files
-   Modify the HTTP request using command-line arguments
-   Send data with the HTTP request
-   Save the metadata of the HTTP response

Getting started
---------------

To get started, create a project directory, create file in it named
"curl.js", and open it up in Visual Studio Code.

Now, use the `npm` command to install "node-fetch".

### A word about fetch

The `fetch` command allows you to call another
server or service hosted on the web and returns you the results. 

**Since`fetch` is asynchronous, you will need to use a
promise to handle the response when it returns from the remote server.**

Specifically, `fetch` makes HTTP requests for XML,
JSON, text, files or any content that can be sent through the REST
protocol.

The **node-fetch** package includes a `fetch`
**function which has two arguments**:

 **a url and an options object**. 
 
 This
function **returns a promise**. The promise is what allows you to 
**wait for the response and `then` handle it**.

The **response from the fetch promise includes a `text()` function that also returns a promise**. That is because the text
can stream when it's long streaming is when the first part is available after a
short time and the rest continues to load in the background.

To learn more about using fetch within NodeJS, you may look at the npm
page for [node-fetch](https://www.npmjs.com/package/node-fetch),
specifically the [section on
fetch](https://open.appacademy.io/learn/js-py---aug-2020-online/week-6-aug-2020-online/promise-project)
and [section on body
text](https://www.npmjs.com/package/node-fetch#bodytext), or additional
documentation such as [body
content](https://flaviocopes.com/fetch-api/#body-content) and [catching
errors](https://flaviocopes.com/fetch-api/#catching-errors).

### As you go along

Every new feature that you add should *not* break a
previously-implemented feature. If your utility can print out a file to
the console and then it doesn't after you add the "save to a file"
feature, you broke it. Make sure everything works every time you do
something new.

A good way to help with this is to initialize a Git repository at the
beginning of your project. Then, whenever you get something to work, add
and commit those changes. That way, you can get yourself out of an "oh,
geez, I really messed it up right now" moment by doing something like
`git checkout -- .`.

Step 1: Just getting a URL
--------------------------

The first feature that you need to support is making a normal GET
request to a URL and printing out the content to "standard out"
(console.logging it).

This service is a great starting point:
[https://artii.herokuapp.com/make?text=curl++this](https://artii.herokuapp.com/make?text=curl++this)

It points to the ASCII art API. It takes some text in the URL and turns
it into ASCII art. You can try it in standard `curl`{.sc-cMljjf .hbDMZX}
if you'd like to see how it works before you write your code. In you
terminal, run this command.

``` {style="color: rgb(248, 248, 242); background: rgb(45, 45, 45); font-family: Consolas, Monaco, "Andale Mono", "Ubuntu Mono", monospace; text-align: left; white-space: pre; word-spacing: normal; word-break: normal; overflow-wrap: normal; line-height: 1.5; tab-size: 4; hyphens: none; padding: 1em; overflow: auto; font-size: 16px;"}
> curl https://artii.herokuapp.com/make?text=curl++this
```

Now write code in your **curl.js** file to make the fetch call using a
promise to grab the result and log it out to the console.

> Tip: Put the above url into a constant or variable as you'll be
> replacing it soon with a command-line parameter.

When you run your program you should see the following.

``` {style="color: rgb(248, 248, 242); background: rgb(45, 45, 45); font-family: Consolas, Monaco, "Andale Mono", "Ubuntu Mono", monospace; text-align: left; white-space: pre; word-spacing: normal; word-break: normal; overflow-wrap: normal; line-height: 1.5; tab-size: 4; hyphens: none; padding: 1em; overflow: auto; font-size: 16px;"}
> node curl.js https://artii.herokuapp.com/make?text=curl++this
                  _    _   _     _
                 | |  | | | |   (_)
   ___ _   _ _ __| |  | |_| |__  _ ___
  / __| | | | '__| |  | __| '_ \| / __|
 | (__| |_| | |  | |  | |_| | | | \__ \
  \___|\__,_|_|  |_|   \__|_| |_|_|___/

>
```

Congrats! That's ASCII art. :)

### Just failing to get a URL

Let's say the host server doesn't exist. You should handle that
gracefully. You're using Promises. That means this probably goes in a
`catch`{.sc-cMljjf .hbDMZX} handler somewhere.

Since you are emulating the `curl`{.sc-cMljjf .hbDMZX} command, you can
see what it does with an invalid url.

``` {style="color: rgb(248, 248, 242); background: rgb(45, 45, 45); font-family: Consolas, Monaco, "Andale Mono", "Ubuntu Mono", monospace; text-align: left; white-space: pre; word-spacing: normal; word-break: normal; overflow-wrap: normal; line-height: 1.5; tab-size: 4; hyphens: none; padding: 1em; overflow: auto; font-size: 16px;"}
> curl https://artii.herokuFLAP.com/make?text=curl++this
  curl: (6) Could not resolve host: artii.herokuFLAP.com
>
```

You can check for this error (hint 1 - the code is
`ENOTFOUND`{.sc-cMljjf .hbDMZX}) to output an equivalent message (hint 2
- the `URL`{.sc-cMljjf .hbDMZX} object can help you get the
`host`{.sc-cMljjf .hbDMZX} property from a url string). Since the error
message is showing that the process ended with status code "6", you can
and should do the same from your program.

``` {style="color: rgb(248, 248, 242); background: rgb(45, 45, 45); font-family: Consolas, Monaco, "Andale Mono", "Ubuntu Mono", monospace; text-align: left; white-space: pre; word-spacing: normal; word-break: normal; overflow-wrap: normal; line-height: 1.5; tab-size: 4; hyphens: none; padding: 1em; overflow: auto; font-size: 16px;"}
process.exit(6);
```

Any other errors can be sent as-is through to console as an error.

You can temporarily change the URL in your code to see both of these
errors.

-   ENOTFOUND:
    `https://artii.herokuappxxxx.com/make?text=curl++this`{.sc-cMljjf
    .hbDMZX}
-   Other error:
    `https://artii.herokuapp.com/makexxxx?text=curl++this`{.sc-cMljjf
    .hbDMZX}

> Hint: Remember to change the URL back to the working one before
> continuing.

Step 2: Command-line arguments
------------------------------

Instead of hard-coding the URL, it would be nice to pass it to the
program for more flexibility and reuse. When you've completed this
upgrade, the command to run your program will look like this.

``` {style="color: rgb(248, 248, 242); background: rgb(45, 45, 45); font-family: Consolas, Monaco, "Andale Mono", "Ubuntu Mono", monospace; text-align: left; white-space: pre; word-spacing: normal; word-break: normal; overflow-wrap: normal; line-height: 1.5; tab-size: 4; hyphens: none; padding: 1em; overflow: auto; font-size: 16px;"}
> node curl.js https://artii.herokuapp.com/make?text=curl++this
```

There are three types of command-line arguments.

-   arguments with values (e.g. `-o output-file.txt`{.sc-cMljjf
    .hbDMZX})
-   arguments without values, sometimes referred to as "flags" (e.g.
    `-h`{.sc-cMljjf .hbDMZX} and `--help`{.sc-cMljjf .hbDMZX} are often
    used to output help or usage information)
-   positional arguments (e.g. the url or urls to fetch)

Throughout the rest of this project you'll get to try them all.

In order to accept command-line arguments, you'll want to include a
package to help you access them. One of the better options is
[dashdash](https://www.npmjs.com/package/dashdash). Install it now using
`npm`{.sc-cMljjf .hbDMZX}.

To get you started quickly, here's some code you can add to your
**curl.js**.

``` {style="color: rgb(248, 248, 242); background: rgb(45, 45, 45); font-family: Consolas, Monaco, "Andale Mono", "Ubuntu Mono", monospace; text-align: left; white-space: pre; word-spacing: normal; word-break: normal; overflow-wrap: normal; line-height: 1.5; tab-size: 4; hyphens: none; padding: 1em; overflow: auto; font-size: 16px;"}
const dash = require('dashdash');

const options = {
  allowUnknown: true,
  options: [],
};
const parser = dash.createParser(options);

const opts = parser.parse(options);
console.log('Options are:', opts);
```

Remember to run your program with some options following the program
name.

``` {style="color: rgb(248, 248, 242); background: rgb(45, 45, 45); font-family: Consolas, Monaco, "Andale Mono", "Ubuntu Mono", monospace; text-align: left; white-space: pre; word-spacing: normal; word-break: normal; overflow-wrap: normal; line-height: 1.5; tab-size: 4; hyphens: none; padding: 1em; overflow: auto; font-size: 16px;"}
> node curl.js
> node curl.js -h
> node curl.js https://appacademy.io
> node curl.js -o output.txt https://appacademy.io
```

### Predefined options

Now, try adding a predefined option to the configuration, one that you
would use to specify the output file name. (This isn't the *entire*
JavaScript file, here. It's just the snippet of the `options`{.sc-cMljjf
.hbDMZX} variable declaration. Please just modify the
`options`{.sc-cMljjf .hbDMZX} variable.)

``` {style="color: rgb(248, 248, 242); background: rgb(45, 45, 45); font-family: Consolas, Monaco, "Andale Mono", "Ubuntu Mono", monospace; text-align: left; white-space: pre; word-spacing: normal; word-break: normal; overflow-wrap: normal; line-height: 1.5; tab-size: 4; hyphens: none; padding: 1em; overflow: auto; font-size: 16px;"}
const options = {
  allowUnknown: true,
  options: [{
    names: ['output', 'o'],
    type: 'string',
    help: 'file in which to store the fetched content'
  }],
};
```

Run the last command again and see how the output differs from before.

``` {style="color: rgb(248, 248, 242); background: rgb(45, 45, 45); font-family: Consolas, Monaco, "Andale Mono", "Ubuntu Mono", monospace; text-align: left; white-space: pre; word-spacing: normal; word-break: normal; overflow-wrap: normal; line-height: 1.5; tab-size: 4; hyphens: none; padding: 1em; overflow: auto; font-size: 16px;"}
> node curl.js -o output.txt https://appacademy.io
Options are: {
  output: 'output.txt',
  _order: [ { key: 'output', value: 'output.txt', from: 'argv' } ],
  _args: [ 'https://appacademy.io' ]
}
...
```

Notice that you can get the list of URLs from the `_args`{.sc-cMljjf
.hbDMZX} property. Then, you can get the value of the "output" argument
that you wrote using the `-o`{.sc-cMljjf .hbDMZX} signifier through the
`output`{.sc-cMljjf .hbDMZX} property on the `opts`{.sc-cMljjf .hbDMZX}
value.

Go ahead and add the option for `-h`{.sc-cMljjf .hbDMZX} as well. (Hint:
the `type`{.sc-cMljjf .hbDMZX} of a flag option is `bool`{.sc-cMljjf
.hbDMZX}.) Verify it's working by running `node curl.js -h`{.sc-cMljjf
.hbDMZX}.

### Url from command-line

Now change your `url`{.sc-cMljjf .hbDMZX} variable (or constant) to use
the argument instead of a hard-coded string. Then test it with several
calls to your program with different urls.

``` {style="color: rgb(248, 248, 242); background: rgb(45, 45, 45); font-family: Consolas, Monaco, "Andale Mono", "Ubuntu Mono", monospace; text-align: left; white-space: pre; word-spacing: normal; word-break: normal; overflow-wrap: normal; line-height: 1.5; tab-size: 4; hyphens: none; padding: 1em; overflow: auto; font-size: 16px;"}
> node curl.js https://appacademy.io
> node curl.js https://artii.herokuapp.com/make?text=curl++this
```

It is pleasing for users if you provide a message when they forget to
include a required option, such as at least one url. Go ahead and add
that (obviously before using `args`{.sc-cMljjf .hbDMZX} to set the
`url`{.sc-cMljjf .hbDMZX} so the program doesn't crash). Verify by
running `node curl.js`{.sc-cMljjf .hbDMZX}.

Also, you may comment out or remove the logging of the options whenever
you feel you don't need them any more.

### Help message

It is useful to map variables to the various properties of the options,
if you'd like. For example, you might want to do something like this.

``` {style="color: rgb(248, 248, 242); background: rgb(45, 45, 45); font-family: Consolas, Monaco, "Andale Mono", "Ubuntu Mono", monospace; text-align: left; white-space: pre; word-spacing: normal; word-break: normal; overflow-wrap: normal; line-height: 1.5; tab-size: 4; hyphens: none; padding: 1em; overflow: auto; font-size: 16px;"}
const { help, output, _args: urls } = opts;
```

Also output the help information, if that flag is set.

``` {style="color: rgb(248, 248, 242); background: rgb(45, 45, 45); font-family: Consolas, Monaco, "Andale Mono", "Ubuntu Mono", monospace; text-align: left; white-space: pre; word-spacing: normal; word-break: normal; overflow-wrap: normal; line-height: 1.5; tab-size: 4; hyphens: none; padding: 1em; overflow: auto; font-size: 16px;"}
if (help) {
    console.log('node curl.js [OPTIONS] URL');
    console.log('OPTIONS:');
    console.log(parser.help().trimRight());
    return;
}
```

Step 3: Now, put it in a file
-----------------------------

When the person using your utility specifies that they'd like the
content of the fetch to be stored in a file, they will do it with one of
these forms. Of course the string "«file-name»" will be an actual file
name and not have those fancy guillemets (or those funky double bracket
things).

-   `-o «file-name»`{.sc-cMljjf .hbDMZX}
-   `--output «file-name»`{.sc-cMljjf .hbDMZX}

When your program gets that argument, it will *not* "console log" it.
Instead, it will write it to the specified file. It should do that
*asynchronously*, as well. In fact, node-fetch is designed to work
directly with writing files, so it has built-in support for [streams
with node-fetch](https://www.npmjs.com/package/node-fetch#streams).

Remember to import `fs`{.sc-cMljjf .hbDMZX} (you don't need to install,
of course, because it is a native part of NodeJS), then use the
documentation to write the fetched content to the `output`{.sc-cMljjf
.hbDMZX} file, if provided by the user calling your program. (Hint:
`process.stdout`{.sc-cMljjf .hbDMZX} works like a file stream.)

Make sure you can still run without the `-o`{.sc-cMljjf .hbDMZX} flag or
if the filename is missing (after the `-o`{.sc-cMljjf .hbDMZX} option in
the command line).

> Test a variety of different commands to ensure all supported
> variations and previous error handling are still working.

### Error handling for writing files

If the file fails to get written, then it should look like this. You
need to modify your code to make this happen.

``` {style="color: rgb(248, 248, 242); background: rgb(45, 45, 45); font-family: Consolas, Monaco, "Andale Mono", "Ubuntu Mono", monospace; text-align: left; white-space: pre; word-spacing: normal; word-break: normal; overflow-wrap: normal; line-height: 1.5; tab-size: 4; hyphens: none; padding: 1em; overflow: auto; font-size: 16px;"}
> node curl.js -o node_modules https://artii.herokuapp.com/make?text=curl++this
curl: (23) Failed writing body
```

(Though you're still using Promises, because you're saving as a writable
stream, then it's at that point that you're getting this error. Hint:
`on('error')`{.sc-cMljjf .hbDMZX} is a good place to begin according to
the [node error handling
documentation](https://nodejs.org/api/errors.html#errors_error_propagation_and_interception)
under the bullet that starts with "When an asynchronous method is
called" because "use of the 'error' event mechanism is most common for
stream-based ... APIs".)

Congratulations!
----------------

You made it through the minimum project exploring promises and
command-line arguments. As time and desire permits, you may continue
with the following bonus rounds to make your program more like the
`curl`{.sc-cMljjf .hbDMZX} command.

Bonus A: Setting an arbitrary header
------------------------------------

Have a look at [Examples using
Fetch](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/fetch#Examples)
to see how to add headers on an invocation of `fetch`{.sc-cMljjf
.hbDMZX} in the second code example of the section. You may also want to
check out the [Syntax of
Fetch](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/fetch#Syntax)
for a property on the object you pass into for the "init" parameter that
would allow you to set the *headers* of the request. Or, [let me
DuckDuckGo that for
you](https://lmgtfy.com/?q=fetch+set+request+headers&s=d).

Use that knowledge to be able to handle one or more of the
`-H`{.sc-cMljjf .hbDMZX} or `--header`{.sc-cMljjf .hbDMZX} command line
option. It's value should have the form "«Header Name»: «Header Value»"
like "Accept: application/json" or "Content-Type: application/json".

### Setting special headers

Now that you can set arbitrary headers, support the command line
arguments and their meaning.

  Command Line Argument               Meaning                                                                                             HTTP Header
  ----------------------------------- --------------------------------------------------------------------------------------------------- ------------------------
  `-A «string»`{.sc-cMljjf .hbDMZX}   Set the [user agent header](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/User-Agent)   "User-Agent: «string»"
  `-e «URL»`{.sc-cMljjf .hbDMZX}      Set the [referer header](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referer)         "Referer: «URL»"

Bonus B: Capturing response headers
-----------------------------------

Sometimes the person using the command wants to see the output of the
metadata of the request, too. That's where the "--dump-header" flag
comes into play. When someone issues the command with that flag

``` {style="color: rgb(248, 248, 242); background: rgb(45, 45, 45); font-family: Consolas, Monaco, "Andale Mono", "Ubuntu Mono", monospace; text-align: left; white-space: pre; word-spacing: normal; word-break: normal; overflow-wrap: normal; line-height: 1.5; tab-size: 4; hyphens: none; padding: 1em; overflow: auto; font-size: 16px;"}
> node curl.js --dump-header ./headers.txt \
               https://artii.herokuapp.com/make?text=curl++this
```

Then it will print out the content of the response like it normally
does. In addition to that, though, it will create a file named
"./headers.txt" and put the HTTP response status line and all of the
headers of the response in it. An example content of the file would look
like this.

``` {style="color: rgb(248, 248, 242); background: rgb(45, 45, 45); font-family: Consolas, Monaco, "Andale Mono", "Ubuntu Mono", monospace; text-align: left; white-space: pre; word-spacing: normal; word-break: normal; overflow-wrap: normal; line-height: 1.5; tab-size: 4; hyphens: none; padding: 1em; overflow: auto; font-size: 16px;"}
HTTP/1.1 200 OK
Connection: keep-alive
Content-Type: text/plain
Content-Length: 319
Server: Goliath
Date: Tue, 03 Feb 2019 05:52:55 GMT
Via: 1.1 vegur
```

Bonus C: Sending data
---------------------

When someone adds the `-d «string»`{.sc-cMljjf .hbDMZX} or
`--data «string»`{.sc-cMljjf .hbDMZX} flag to the command, that should
become the body of the HTTP request. So, make it the body of your
`fetch`{.sc-cMljjf .hbDMZX}. Check out the [Syntax of
Fetch](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/fetch#Syntax)
for a property on the object you pass into for the "init" parameter that
would allow you to set the *body* of a request. This should also set the
method of the request to POST.

### Overriding the method of the request

When someone adds the `-X`{.sc-cMljjf .hbDMZX} command line argument
followed by an HTTP method, then set that method on the fetch request.
You'll want to find the property on the "init" parameter that would
allow you to override the *method* of the HTTP request.

``` {style="color: rgb(248, 248, 242); background: rgb(45, 45, 45); font-family: Consolas, Monaco, "Andale Mono", "Ubuntu Mono", monospace; text-align: left; white-space: pre; word-spacing: normal; word-break: normal; overflow-wrap: normal; line-height: 1.5; tab-size: 4; hyphens: none; padding: 1em; overflow: auto; font-size: 16px;"}
> node curl.js -X 'POST'                              \
               -d '{"title": "Sir", "name": "Robin"}' \
               -H 'Content-Type: application/json'    \
               https://jsonplaceholder.typicode.com/posts
```

which should result in something like

``` {style="color: rgb(248, 248, 242); background: rgb(45, 45, 45); font-family: Consolas, Monaco, "Andale Mono", "Ubuntu Mono", monospace; text-align: left; white-space: pre; word-spacing: normal; word-break: normal; overflow-wrap: normal; line-height: 1.5; tab-size: 4; hyphens: none; padding: 1em; overflow: auto; font-size: 16px;"}
{
  "title": "Sir",
  "name": "Robin",
  "id": 101
}
```

Bonus D: Multiple files, multiple output destinations
-----------------------------------------------------

Now that you can download a single file, make it like the way
`curl`{.sc-cMljjf .hbDMZX} handles multiple URLs and `-o`{.sc-cMljjf
.hbDMZX} parameters.

-   Do the transfers in parallel, not one right after another
-   For each URL provided, a corresponding `-o`{.sc-cMljjf .hbDMZX} or
    `--output`{.sc-cMljjf .hbDMZX} is its target. If there are more URLs
    than there are output targets, the remainder of the content gets
    output to standard out.

Here are some examples to get you used to it.

Prints both files to standard out

``` {style="color: rgb(248, 248, 242); background: rgb(45, 45, 45); font-family: Consolas, Monaco, "Andale Mono", "Ubuntu Mono", monospace; text-align: left; white-space: pre; word-spacing: normal; word-break: normal; overflow-wrap: normal; line-height: 1.5; tab-size: 4; hyphens: none; padding: 1em; overflow: auto; font-size: 16px;"}
> node curl.js https://artii.herokuapp.com/make?text=curl++this \
              https://artii.herokuapp.com/make?text=curl++that
```

Saves the first to the file "first.txt" and prints the second to
standard out

``` {style="color: rgb(248, 248, 242); background: rgb(45, 45, 45); font-family: Consolas, Monaco, "Andale Mono", "Ubuntu Mono", monospace; text-align: left; white-space: pre; word-spacing: normal; word-break: normal; overflow-wrap: normal; line-height: 1.5; tab-size: 4; hyphens: none; padding: 1em; overflow: auto; font-size: 16px;"}
> node curl.js -o first.txt \
               https://artii.herokuapp.com/make?text=curl++this \
               https://artii.herokuapp.com/make?text=curl++that
```

Saves the first to the file "first.txt" and saves the second to the file
"second.txt"

``` {style="color: rgb(248, 248, 242); background: rgb(45, 45, 45); font-family: Consolas, Monaco, "Andale Mono", "Ubuntu Mono", monospace; text-align: left; white-space: pre; word-spacing: normal; word-break: normal; overflow-wrap: normal; line-height: 1.5; tab-size: 4; hyphens: none; padding: 1em; overflow: auto; font-size: 16px;"}
> node curl.js -o first.txt \
               -o second.txt \
               https://artii.herokuapp.com/make?text=curl++this \
               https://artii.herokuapp.com/make?text=curl++that
```

Bonus E: List globbing
----------------------

If a person specifies a "list glob", then expand it to all of the files
that it represents. A list glob uses curly braces to specify a list.

``` {style="color: rgb(248, 248, 242); background: rgb(45, 45, 45); font-family: Consolas, Monaco, "Andale Mono", "Ubuntu Mono", monospace; text-align: left; white-space: pre; word-spacing: normal; word-break: normal; overflow-wrap: normal; line-height: 1.5; tab-size: 4; hyphens: none; padding: 1em; overflow: auto; font-size: 16px;"}
> node curl.js https://artii.herokuapp.com/make?text={this,that,the+other}
```

The previous statement would "expand" to the following equivalent
command.

``` {style="color: rgb(248, 248, 242); background: rgb(45, 45, 45); font-family: Consolas, Monaco, "Andale Mono", "Ubuntu Mono", monospace; text-align: left; white-space: pre; word-spacing: normal; word-break: normal; overflow-wrap: normal; line-height: 1.5; tab-size: 4; hyphens: none; padding: 1em; overflow: auto; font-size: 16px;"}
> node curl.js https://artii.herokuapp.com/make?text=this \
              https://artii.herokuapp.com/make?text=that \
              https://artii.herokuapp.com/make?text=the+other
```

Nightmare round A: The progress meter
-------------------------------------

When your utility saves all of its contents into files, then show a
progress meter for the download. It should show the percent total that
it is at. You'll need to look at the "Content-Length" header of the
*response* headers. Then, you can get a reader from the response body to
monitor how much has been read.

``` {style="color: rgb(248, 248, 242); background: rgb(45, 45, 45); font-family: Consolas, Monaco, "Andale Mono", "Ubuntu Mono", monospace; text-align: left; white-space: pre; word-spacing: normal; word-break: normal; overflow-wrap: normal; line-height: 1.5; tab-size: 4; hyphens: none; padding: 1em; overflow: auto; font-size: 16px;"}
      %  Total
     --  -----
make 18  151M
```

Nightmare round B: Progress meter for multiple files
----------------------------------------------------

What you just did for the download progress meter, do it so that it can
track multiple files, too.

``` {style="color: rgb(248, 248, 242); background: rgb(45, 45, 45); font-family: Consolas, Monaco, "Andale Mono", "Ubuntu Mono", monospace; text-align: left; white-space: pre; word-spacing: normal; word-break: normal; overflow-wrap: normal; line-height: 1.5; tab-size: 4; hyphens: none; padding: 1em; overflow: auto; font-size: 16px;"}
      %  Total
     --  -----
make 18  151M
make 14  111M
```

Did you find this lesson helpful?

No

Yes

**✔︎ Submit Project**

Archive your file into a **.zip** folder and click **Submit Project** to
upload.

Solutions become available after uploading.


