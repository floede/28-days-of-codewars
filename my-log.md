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



### Day 4: February 5, 2017 (Example 4)

**Today's Challenge**: Test if a number is a prime

**Solution**:

```
function isPrime(num) {
  if (num <= 1) return false;
  if (num <= 3) return true;
  if (num == 5) return true;
  if (num == 7) return true;
  if (num % 2 == 0) {
    return false;
  } else if (num % 3 == 0) {
    return false;
  } else if (num % 5 == 0) {
    return false;
  } else if (num % 7 == 0) {
    return false;
  } else {
    return true;
  }
}
```

**Thoughts:** While this code passes the test, it's actually not correct. Or enough rather. 
Given that the list of primes goes towards infinity, I didn't quite know how to write some code that wouldn't have to test against infinity. I thought I had figured out that 7 is actually the highest divisor you need to test, since 9 is 3x3.

**Link to work:** [Is a number prime?](https://www.codewars.com/kata/is-a-number-prime/javascript)

**Better solution**:

```
function isPrime(num) {
  for (var i = 2; i * i <= num; i++) if (num % i == 0) return false;
  return num >= 2; 
}
```

**Link to Wikipedia about primes:**: [Primality Test](https://en.wikipedia.org/wiki/Primality_test)
