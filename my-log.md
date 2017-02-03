# 28 Days Of Codewars - Log

### Day 1: February 1, 2017 (Example 1)

**Today's Challenge**: Treat an array of 1's and 0's as a binary and return the integer.

**Solution**:

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

**Thoughts:** This can be way shorter. I looked into .join, but thought it would always create a seperator.

**Link to work:** [Ones and zeroes](https://www.codewars.com/kata/ones-and-zeros/javascript)


### Day 2: February 2, 2017 (Example 2)

**Today's Challenge**: A Narcissistic Number is a number of length n in which the sum of its digits to the power of n is equal to the original number.

**Solution**:

```
function isNarcissistic( value ) {
  // Code me
  var power = value.toString().length;
  var numbers = [];
  var math = 0
  for (i = 0; i < power; i++) { 
      numbers.push(value.toString().slice(i,i+1));
      math = parseInt(math) + parseInt(Math.pow(numbers[i], power));
  }
  return value == math;
}
```

**Thoughts:** I struggled a bit with this. Possibly you could be cleverer about the string and int conversions.

**Link to work:** [Narcissistic Numbers](https://www.codewars.com/kata/narcissistic-numbers/javascript)


### Day 3: February 3, 2017 (Example 3)

**Today's Challenge**: Return a string with all vowels removed.

**Solution**:

```
function disemvowel(str) {
  return str.replace(/[aeiou]/gi, '');
}
```

**Thoughts:** This was pretty easy as I've already done another challenge that is the opposite. However I did learn that "y" is not always a vowel. TIL.

**Link to work:** [Disemvowel Trolls](https://www.codewars.com/kata/disemvowel-trolls/javascript)
