# Decoding/Encoding Data in Various Forms (ie. base-64, ASCII, SHA-256 etc.)

### Decode a String from Base-64 Encoding
```javascript
// Test Case
const tc1 = 'Zm9vYmFy';

const decodeBase64 = str => Buffer.from(str, 'base64').toString('binary');

decodeBase64(tc1); // 'foobar'
decodeBase64('RXN0ZW5Hcm92ZQ=='); // 'EstenGrove'
```
### Encode a Base-64 ASCII String from a String Object
- Each character in the string is treated as a byte of binary data.
```javascript
const tc1 = 'foobar';

const encodeBase64 = str => Buffer.from(str, 'binary').toString('base64');

encodeBase64(tc1); // Zm9vYmFy
encodeBase64('EstenGrove'); // 'RXN0ZW5Hcm92ZQ=='
```
### Create a Hash Using SHA-256
- Uses the "crypto" API to create a hash for a given value.
- Use setTimeout() to prevent blocking during a long operation and use a Promise for better readability.
```javascript
// Import the Crypto API
const crypto = require('crypto');

const hashNode = val =>
  new Promise(resolve =>
    setTimeout(
      () =>
        resolve(
          crypto
            .createHash('sha256')
            .update(val)
            .digest('hex')
        ),
      0
    )
  );
  
hashNode(JSON.stringify({ a: 'a', b: [1, 2, 3, 4], foo: { c: 'bar' } })).then(console.log);
// RESULT: '04aa106279f5977f59f9067fa9712afc4aedc6f5862a8defc34552d8c7206393'
```
