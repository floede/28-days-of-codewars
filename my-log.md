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


### Day 5: February 6, 2017 (Example 5)

**Today's Challenge**: How many times will the mother see the ball bounce?

**Solution**:

```
function bouncingBall(h, bounce, win) {
  if (h > 0 && 0 < bounce && bounce < 1 && h > win) {
    var ballHeight = h;
    var views = 1;
    do {
      ballHeight = ballHeight * bounce;
      if (ballHeight > win) views += 2;
    } while (ballHeight > win);
    return views;
  } else {
    return -1;
  }
}
```

**Thoughts:** The tests for this were a little annoying and it was hard to figure out why it failed. Also I think my solution is more correct in the context than a lot of the other solutions. 
Because we're counting views twice for each bounce (up and down), a lot of people start with -1 to offset the fact that the final view count logically is uneven.
I'm starting a 1 because will always see the ball at least once, and then I don't count the last run of the loop.

**Link to work:** [Bouncing ball](https://www.codewars.com/kata/bouncing-balls/javascript)


### Day 6: February 7, 2017 (Example 6)

**Today's Challenge**: Format a string to an american phone number

**Solution**:

```
function createPhoneNumber(numbers){
  function numSlice(x,y) {
    return numbers.slice(x,y).join("");
  }
  return ("(" + numSlice(0,3) + ") " + numSlice(3,6) +"-"+numSlice(6,10));
}
```

**Thoughts:** Definitely on the easy side. The biggest challenge was probably trying to deliberately make a function for the slice and join part. 

**Link to work:** [Create Phone Number](https://www.codewars.com/kata/create-phone-number/javascript)



### Day 7: February 8, 2017 (Example 7)

**Today's Challenge**: Assign a value to different creatures, see which side wins

**Solution**:

```
function goodVsEvil(good, evil){
  var the_good = good.split(" ");
  var the_evil = evil.split(" ");
  var good_value = 
      the_good[0] * 1 +
      the_good[1] * 2 +
      the_good[2] * 3 +
      the_good[3] * 3 +
      the_good[4] * 4 +
      the_good[5] * 10;
  var evil_value = 
      the_evil[0] * 1 +
      the_evil[1] * 2 +
      the_evil[2] * 2 +
      the_evil[3] * 2 +
      the_evil[4] * 3 +
      the_evil[5] * 5 +
      the_evil[6] * 10;
  if (good_value < evil_value) {
    return "Battle Result: Evil eradicates all trace of Good";
  } else if (good_value > evil_value) {
    return "Battle Result: Good triumphs over Evil";
  } else {
    return "Battle Result: No victor on this battle field";
  }
}
```

**Thoughts:** This was kinda fun. I knew it could be done smarter, but didn't quite see how. 

**Link to work:** [Good vs Evil](https://www.codewars.com/kata/good-vs-evil/javascript)


### Day 8: February 9, 2017 (Example 8)

**Today's Challenge**: 

**Solution**: Chaining function calls

```
function add() {
    var a = "";
    // note you can rename it to anything you want, just keep all names in sync
    function F(arg){
        a = a + arg;
        //console.log(a);
        return F;
    }
    return F;
};

add(1)(2)(3);
```

**Thoughts:** This I just couldn't figure out. I found something that supposedly solves this, but I can't make it work. Basically I just don't know what goes on here.

**Link to work:** [A Chain adding function](https://www.codewars.com/kata/a-chain-adding-function/javascript)

function foldArray(array, runs)
{
  var folded = [];
  var temp = array;
  for(var i = 1; i <= runs; i++) {
    console.log("for loop");
    while (temp.length > 0) {
      if (temp.length<=1) {
        folded.push(parseInt(temp.splice(0,1)));
      } else {
        var a = parseInt(temp.splice(0,1));
        var b = parseInt(temp.splice(-1,1));
        folded.push(a + b);
      }
    }
    if (i<runs) console.log("temp: " , temp);
  }
  //return [ 0 ];
  console.log("folded:" , folded);
}

var input = [ 1, 2, 3, 4, 5 ];
//var expected = [ 6, 6, 3 ];
//foldArray(input, 1)
    
//expected = [ 9, 6 ];
foldArray(input, 2);
    
//expected = [ 15 ];
//foldArray(input, 3);
