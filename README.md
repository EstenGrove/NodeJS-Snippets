# NodeJS-Snippets
A collection of Node.js snippets.

### Colorize Console Output
- Print in color in the console in Node
- Regular Colors
  - Use template literals and special characters to output in color.
- For Background Colors
  - Add a special character that resets the background color at the end of the string.
```javascript
const colorize = (...args) => ({
  black: `\x1b[30m${args.join(' ')}`,
  red: `\x1b[31m${args.join(' ')}`,
  green: `\x1b[32m${args.join(' ')}`,
  yellow: `\x1b[33m${args.join(' ')}`,
  blue: `\x1b[34m${args.join(' ')}`,
  magenta: `\x1b[35m${args.join(' ')}`,
  cyan: `\x1b[36m${args.join(' ')}`,
  white: `\x1b[37m${args.join(' ')}`,
  bgBlack: `\x1b[40m${args.join(' ')}\x1b[0m`,
  bgRed: `\x1b[41m${args.join(' ')}\x1b[0m`,
  bgGreen: `\x1b[42m${args.join(' ')}\x1b[0m`,
  bgYellow: `\x1b[43m${args.join(' ')}\x1b[0m`,
  bgBlue: `\x1b[44m${args.join(' ')}\x1b[0m`,
  bgMagenta: `\x1b[45m${args.join(' ')}\x1b[0m`,
  bgCyan: `\x1b[46m${args.join(' ')}\x1b[0m`,
  bgWhite: `\x1b[47m${args.join(' ')}\x1b[0m`
});

console.log(colorize('foobar').red); // Will output "foobar" in red in the console.
console.log(colorize('foo', 'bar').bgBlue); // Will add a blue background color to the text output in the console.
```
### Creates a Directory If It Doesn't Already Exist
- Use fs.existsSync() to check if the directory exists, fs.mkdirSync() to create it.
```javascript
const fs = require('fs');

const createDirIfNotExists = dir => (!fs.existsSync(dir) ? fs.mkdirSync(dir) : undefined);

createDirIfNotExists('foobar'); // creates the directory 'foobar', if it doesn't exist
```
### Write a JSON Object to a File
- Use the "fs" middleware
- Use fs.writeFile(), template literals and JSON.stringify() to write a json object to a .json file.
```javascript
// import the middleware
const fs = require('fs');

const JSONToFile = (obj, filename) =>
  fs.writeFile(`${filename}.json`, JSON.stringify(obj, null, 2));
  
JSONToFile({ test: 'is passed' }, 'testJsonFile'); // writes the object to 'testJsonFile.json'
```
