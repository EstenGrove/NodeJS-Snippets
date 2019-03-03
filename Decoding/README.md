# Decoding/Encoding Data in Various Forms (ie. base-64, ASCII, SHA-256 etc.)

### Decode a String from Base-64 Encoding
```javascript
// Test Case
const tc1 = 'Zm9vYmFy';

const decodeBase64 = str => Buffer.from(str, 'base64').toString('binary');

decodeBase64(tc1); // 'foobar'
decodeBase64('RXN0ZW5Hcm92ZQ=='); // 'EstenGrove'
```
