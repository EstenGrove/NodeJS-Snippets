# Snippets & Helper Functions Relating to Files and the File System

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
