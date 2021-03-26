```javascript
/**
 * @param {string} a
 * @param {string} b
 * @return {string}
 */
 
var addBinary = function(a, b) {
    // using the BigInt method allows it possible to correctly perform integer arithmetic but declaring the type of ('0b' is the binary prefix to convert a string into a Binary Number)
    sum = (BigInt('0b' + a) + BigInt('0b' + b))
    // returns the sum string representing the specified Number object to the radix of 2 ( which is binary)
    return sum.toString(2)
};
```
