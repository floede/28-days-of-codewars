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



### Day 9: February 10, 2017 (Example 9)

**Today's Challenge**: Fold an array by adding the first element to the last, the second to the second to last and so forth 

**Solution**:

```
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
```

**Thoughts:** Another challenge I'm unable to pass. The above code works in isolation, but the test cases doesn't define input each time, and then my code fails. 

**Link to work:** [Fold an array](https://www.codewars.com/kata/fold-an-array/train/javascript)


### Day 9: February 10, 2017 (Example 10)

**Today's Challenge**: A man sees a clock in the mirror. What time is it?

**Solution**:

```
function WhatIsTheTime(timeInMirror)
{
  var fixedTime = "";
  var fixedMins = 60 - parseInt(timeInMirror.slice(3,5));
  fixedMins = fixedMins < 10 ? "0" + fixedMins : fixedMins;
  fixedMins = fixedMins === 60 ? "00" : fixedMins;
  if (fixedMins === "00") { var fixedHours = 12 - parseInt(timeInMirror.slice(0,2)); } 
  else { var fixedHours = 11 - parseInt(timeInMirror.slice(0,2)); }
  if (fixedHours === 0) { fixedHours = "12"};
  if (fixedHours === -1) { fixedHours = "11"};
  fixedHours = fixedHours < 10 ? "0" + fixedHours : fixedHours;
  fixedTime = fixedHours + ":"  + fixedMins;
  return fixedTime; 
}
```

**Thoughts:** I figured that this could be solved much prettier, as I felt that I basically brute forced it. But actually a lot of the solutions are quite similar to this.

**Link to work:** [Clock In Mirror](https://www.codewars.com/kata/clock-in-mirror/javascript)



### Day 10: February 11, 2017 (Example 11)

**Today's Challenge**: Put all the zeroes at the end of the array

**Solution**:

```
var moveZeros = function (arr) {
  var zeroes = [];
  while(arr.indexOf(0)>=0) {
    zeroes.push(parseInt(arr.splice(arr.indexOf(0),1).join()));
  }
  arr = arr.concat(zeroes);
  return arr;
}
```

**Thoughts:** This was quite interesting as I originally had something far more complex, but by solving a couple of problems, I ended up with something far simpler.

**Link to work:** [Moving zeroes to the end](https://www.codewars.com/kata/moving-zeros-to-the-end/javascript)


### Day 11: February 12, 2017 (Example 12)

**Today's Challenge**: Can I write one string with the letters in another?

**Solution**:

```
function scramble(str1, str2) {
 //code me
  var org = str2.split('');
  var result = [];
    for (var i = 0; i < org.length; i ++) {
      if (str1.indexOf(org[i]) < 0) {
        return false;
      } else {
        str1 = str1.replace(org[i],"");
      }
    } 
  return true;
}
```

**Thoughts:** I looked for something better than the standard for loop, but couldn't quite find. And so my code works, but actually fails a performance test.

**Link to work:** [Scramblies](https://www.codewars.com/kata/scramblies/train/javascript)


### Day 12: February 13, 2017 (Example 13)

**Today's Challenge**: Return seconds in a readable format

**Solution**:

```
function formatDuration (seconds) {
  if (seconds <= 0) { return "now";}
  var text = [];
  if (seconds >= 31536000) {
    var yArr = getDivisionAndRemain(seconds , 31536000);
    text.push(yArr[0] + " year" + (yArr[0] > 1 ? "s" : ""));
    seconds = yArr[1];
  }
  if (seconds >= 86400) {
    var dArr = getDivisionAndRemain(seconds , 86400);
    text.push(dArr[0] + " day" + (dArr[0] > 1 ? "s" : ""));
    seconds = dArr[1];
  } 
  if (seconds >= 3600) {
    var hArr = getDivisionAndRemain(seconds , 3600);
    text.push(hArr[0] + " hour" + (hArr[0] > 1 ? "s" : ""));
    seconds = hArr[1];
  }
  if (seconds >= 60) {
    var mArr = getDivisionAndRemain(seconds , 60);
    text.push(mArr[0] + " minute" + (mArr[0] > 1 ? "s" : ""));
    seconds = mArr[1];
  }
  if (seconds > 0) {
    text.push(seconds + " second" + (seconds > 1 ? "s" : ""));
  }
  for (var i = 0; i < text.length -1; i++) {
    if (text.length === 1) {break;}
    else if (text.length === 2) {text.splice(1, 0, " and "); break;}
    else if (i < text.length - 2) {
      text[i] = text[i] + ", ";
    } else { text.splice(-1, 0, " and "); break;}
  }
  return (text.join(""));
}

function getDivisionAndRemain (num, factor) {
  var remains = num % factor;
  var division = (num - remains) / factor;
  return [division, remains];
}
```

**Thoughts:** I had quite some trouble with this, but it turned out I had the wrong amount of seconds in a year. I was also very much looking forward to how it could be written shorter.  

**Link to work:** [Human readable duration](https://www.codewars.com/kata/human-readable-duration-format/javascript)


### Day 13: February 14, 2017 (Example 14)

**Today's Challenge**: Check parentheses 

**Solution**:

```
function validParentheses(parens){
  var parensCount = 0;
  for (var i = 0; i < parens.length; i++) {
    if (parens[i] === "(") { parensCount++}
    else if (parens[i] === ")") { parensCount--}
    if (parensCount < 0) return false;
  }
  return parensCount ? false : true;
}
```

**Thoughts:** This was quite easy, I'm a little surprised that it scores so much.

**Link to work:** [Valid Parentheses](https://www.codewars.com/kata/valid-parentheses/javascript)


### Day 14: February 15, 2017 (Example 15)

**Today's Challenge**: Count the number of 1's in a binary string

**Solution**:

```
var countBits = function(n) {
  // Program Me
  if (n > 1) return 0;
  return (n >>> 0).toString(2).match(/1/g).length;
};
```

**Thoughts:** Another fun little task. Gave me a reason to look into binary numbers

**Link to work:** [Bit counting](https://www.codewars.com/kata/bit-counting/javascript)


### Day 15: February 16, 2017 (Example 16)

**Today's Challenge**: Return the factorial 

**Solution**:

```

function factorial(n){
  // Add some code
  if (n < 0) return null;
  if (n === 0) return 1;
  var factorial = 1;
  for (var i = 1; i <=n; i++) {
    factorial = factorial * i;
  }
  console.log(factorial)
  //return factorial.toString();
}
```

**Thoughts:** This was a little confusing as the solution is pretty straight forward. However the tests tried running very big numbers, and apparently they aren't supported in javascript. Which I guess was the real task.
Looking for solutions, I found nothing but different libraries to use, so I had to give up trying to find a home made solution.

**Link to work:** [Large Factorials](https://www.codewars.com/kata/large-factorials/javascript)


### Day 16: February 18, 2017 (Example 17)

**Today's Challenge**: Turn a simple string into pig latin

**Solution**:

```
function pigIt(str){
  var pigStr = [];
  var words = str.split(" ");
  for (var i = 0 ;i < words.length ;i++) {
    var input = words[i];
    var firstLetter = input.charAt(0);
    input = input.substring(1);
    input = input + firstLetter + "ay";
    pigStr.push(input);
  }
  return pigStr.join(" ");
}
```

**Thoughts:** This was quite simple. It can be done with just a regex, but I don't have that skill yet.

**Link to work:** [Simple Pig Latin](https://www.codewars.com/kata/simple-pig-latin/javascript)



### Day 17: February 19, 2017 (Example 18)

**Today's Challenge**: Find the domain in a URL

**Solution**:

```
function domainName(url){
  //your code here
  var domain = "";
  var arr = url.split(".");
  if (arr[0].indexOf("www") >= 0) {
    domain = arr[1];
  } else if (arr[0].indexOf("http") < 0) {
    domain = arr[0];
  } else {
    arr = arr[0].split("//");
    domain = arr[1];
  }
  //console.log(domain);
  return domain;
}
```

**Thoughts:** I knew this was pretty crude, but I still don't have the regex skills to do that.

**Link to work:** [Extract the Domain](https://www.codewars.com/kata/extract-the-domain-name-from-a-url-1/javascript)



### Day 18: February 20, 2017 (Example 19)

**Today's Challenge**: Get the letter(s) in the middle 

**Solution**:

```
def get_middle(s)
  #your code here
   if s.length % 2 == 0
   return s[s.length / 2 - 1, 2]
   else
   return s[(s.length - 1) / 2, 1]
   end
end
```

**Thoughts:** Decided to switch it up a little by trying Ruby. I need to familiarize myself with Ruby again. Return isn't needed for instance :-)

**Link to work:** [Get the middle character](https://www.codewars.com/kata/get-the-middle-character/ruby)


### Day 18: February 20, 2017 (Example 20)

**Today's Challenge**: Take a string and capitalize each word

**Solution**:

```
class String
  def toJadenCase
    self.split(' ').map { |word| word.capitalize }.join(' ')
  end
end
```

**Thoughts:** I'm still super rusty in Ruby, and I actually had to look up the solution to this, as I'm still not used to the implicit nature of Ruby. 

**Link to work:** [Jaden Casing](https://www.codewars.com/kata/jaden-casing-strings/ruby)
