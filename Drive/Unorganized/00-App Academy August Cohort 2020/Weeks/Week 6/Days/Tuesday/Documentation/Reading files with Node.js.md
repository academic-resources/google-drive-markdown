[](https://nodejs.dev/)

![Node.js](./Reading%20files%20with%20Node.js_files/nodejs-logo-light-mode-d8cbf6c670c6befc286bc5c456b20f39.svg)![Node.js](./Reading%20files%20with%20Node.js_files/nodejs-logo-dark-mode-ba22af1048345de03fc5ad42f273d6e8.svg)

- [Learn](https://nodejs.dev/learn)
- [Documentation](https://nodejs.org/en/docs/)
- [Download](https://nodejs.org/en/download/)

- Toggle Dark Mode*nights_stay\*\*wb_sunny*
- [GitHub](https://github.com/nodejs/nodejs.dev)

Menu

# Reading files with Node.js {.article-reader\_\_headline}

The simplest way to read a file in Node.js is to use the
`fs.readFile()`{.language-text} method, passing it the file path,
encoding and a callback function that will be called with the file data
(and the error):

```{.language-javascript}
const fs = require('fs')

fs.readFile('/Users/joe/test.txt', 'utf8' , (err, data) => {
  if (err) {
    console.error(err)
    return
  }
  console.log(data)
})
```

Alternatively, you can use the synchronous version
`fs.readFileSync()`{.language-text}:

```{.language-javascript}
const fs = require('fs')

try {
  const data = fs.readFileSync('/Users/joe/test.txt', 'utf8')
  console.log(data)
} catch (err) {
  console.error(err)
}
```

Both `fs.readFile()`{.language-text} and
`fs.readFileSync()`{.language-text} read the full content of the file in
memory before returning the data.

This means that big files are going to have a major impact on your
memory consumption and speed of execution of the program.

In this case, a better option is to read the file content using streams.

- [![flaviocopes](./Reading%20files%20with%20Node.js_files/flaviocopes.png)](https://github.com/flaviocopes "flaviocopes")
- [![
MylesBorins](./Reading%20files%20with%20Node.js_files/MylesBorins.png)](https://github.com/MylesBorins " MylesBorins")
- [![
fhemberger](./Reading%20files%20with%20Node.js_files/fhemberger.png)](https://github.com/fhemberger " fhemberger")
- [![
LaRuaNa](./Reading%20files%20with%20Node.js_files/LaRuaNa.png)](https://github.com/LaRuaNa " LaRuaNa")
- [![
ahmadawais](./Reading%20files%20with%20Node.js_files/ahmadawais.png)](https://github.com/ahmadawais " ahmadawais")

[Edit this page on
GitHub](https://github.com/nodejs/nodejs.dev/edit/master/src/documentation/0043-node-reading-files/index.md)

- [←   Prev](https://nodejs.dev/learn/nodejs-file-paths)
- [Next   →](https://nodejs.dev/learn/writing-files-with-nodejs)

- [Trademark Policy](https://nodejs.org/en/about/trademark/)
- [Privacy Policy](https://nodejs.org/en/about/privacy/)
- [Code of
  Conduct](https://github.com/openjs-foundation/cross-project-council/blob/master/CODE_OF_CONDUCT.md#contributor-covenant-code-of-conduct)
- [Security Reporting](https://nodejs.org/en/security/)
- [About](https://nodejs.org/en/about/)
- [Blog](https://nodejs.org/en/blog/)

- © OpenJS Foundation
- [GitHub](https://github.com/nodejs/node)
- [](https://twitter.com/nodejs)
- [](https://slack.openjsf.org/)
