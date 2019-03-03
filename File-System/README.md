# Snippets & Helpers Working with Files and the File System

### Write a JSON Object to a File
- Use the "fs" middleware.
- Use fs.writeFile(), template literals and JSON.stringify() to write a json object to a .json file.
```javascript
// import file-system middleware
const fs = require('fs');

const JSONToFile = (obj, filename) =>
  fs.writeFile(`${filename}.json`, JSON.stringify(obj, null, 2));
  
JSONToFile({ test: 'is passed' }, 'testJsonFile'); // writes the object to 'testJsonFile.json'
```
### Return an Array of Lines from a File
- Use readFileSync function in fs node package to create a Buffer from a file. convert buffer to string using toString(encoding) function. creating an array from contents of file by spliting file content line by line (each \n).
```javascript
// import "fs" middleware
const fs = require('fs');

const readFileLines = filename =>
  fs
    .readFileSync(filename)
    .toString('UTF8')
    .split('\n');

/*
contents of test.txt :
  line1
  line2
  line3
  ___________________________
*/
let arr = readFileLines('test.txt');
console.log(arr); // ['line1', 'line2', 'line3']
```
