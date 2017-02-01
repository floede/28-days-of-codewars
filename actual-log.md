```
const binaryArrayToNumber = arr => {
  // your code
  var int = "";
  arr.forEach(function(element) {
    int = int + element.toString();
  });
  return parseInt( int, 2 );
};
```
