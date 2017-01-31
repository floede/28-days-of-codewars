# 28 Days Of Codewars - Log

### Day 1: February 1, 2017 (Example 1)
##### (delete me or comment me out)

**Today's Challenge**: Count the number of vowels in a string.

**Solution**:

```
function getCount(str) {
  var vowelsCount = 0;
  var vowels = str.match(/[aeiou]/gi);
  vowelsCount = vowels ? vowels.length : 0;
  return vowelsCount;
}
```

**Thoughts:** As usual I find that others come up with much much simpler solutions than I do.

**Link to work:** [Vowel Count](https://www.codewars.com/kata/vowel-count/javascript)

### Day 2: February 2, 2017 (Example 2)
##### (delete me or comment me out)

**Today's Change**: Add numbers together, return the binary.

**Solution**:

```
function addBinary(a,b) {
  return (a + b >>> 0).toString(2);
}
```

**Thoughts**: I'm not strong in binary, so I basically had to look up the entire solution. However it was quite easy to shorten it down to just one line.

**Link(s) to work**: [Binary Addition](https://www.codewars.com/kata/binary-addition/javascript)
