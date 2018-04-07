## [warmup-1](http://codingbat.com/python/Warmup-1)
Simple warmup problems to get started, no loops (solutions available)

* sleep_in
* monkey_trouble
* sum_double
* diff21
* parrot_trouble
* makes10
* near_hundred
* pos_neg
* not_string
* missing_char
* front_back
* front3

---

###[sleep_in](http://codingbat.com/prob/p173401)
The parameter weekday is True if it is a weekday, and the parameter vacation is True if we are on vacation. We sleep in if it is not a weekday or we're on vacation. Return True if we sleep in.
* sleep_in(False, False) → True
* sleep_in(True, False) → False
* sleep_in(False, True) → True

#### My solution
```r
def sleep_in(weekday, vacation):
  if weekday == False and vacation == False:
    return True
  elif weekday == True and vacation == False:
    return False
  elif weekday == False and vacation == True:
    return True
  else:
    return True
```
#### Codingbat solution
```r
def sleep_in(weekday, vacation):
  if not weekday or vacation:
    return True
  else:
    return False
  # This can be shortened to: return(not weekday or vacation)
```

---

###[monkey_trouble](http://codingbat.com/prob/p120546)
We have two monkeys, a and b, and the parameters a_smile and b_smile indicate if each is smiling. We are in trouble if they are both smiling or if neither of them is smiling. Return True if we are in trouble.
* monkey_trouble(True, True) → True
* monkey_trouble(False, False) → True
* monkey_trouble(True, False) → False

#### My solution
```r
def monkey_trouble(a_smile, b_smile):
  if a_smile == True and b_smile == True:
    return True
  if a_smile == False and b_smile == False:
    return True
  if a_smile == True and b_smile == False:
    return False
  if a_smile == False and b_smile == True:
    return False
```
#### Codingbat solution
```r
def monkey_trouble(a_smile, b_smile):
  if a_smile and b_smile:
    return True
  if not a_smile and not b_smile:
    return True
  return False
  ## The above can be shortened to:
  ##   return ((a_smile and b_smile) or (not a_smile and not b_smile))
  ## Or this very short version (think about how this is the same as the above)
  ##   return (a_smile == b_smile)
```

---

###[sum_double](http://codingbat.com/prob/p120546)
Given two int values, return their sum. Unless the two values are the same, then return double their sum.
* sum_double(1, 2) → 3
* sum_double(3, 2) → 5
* sum_double(2, 2) → 8

#### My solution
```r
def sum_double(a, b):
  if a == b:
    return (a+b)*2
  else:
    return a+b
```
#### Codingbat solution
```r
def sum_double(a, b):
  # Store the sum in a local variable
  sum = a + b

  # Double it if a and b are the same
  if a == b:
    sum = sum * 2
  return sum
```

---

###[diff21](http://codingbat.com/prob/p197466)
Given an int n, return the absolute difference between n and 21, except return double the absolute difference if n is over 21.
* diff21(19) → 2
* diff21(10) → 11
* diff21(21) → 0

#### My solution
```r
def diff21(n):
  if n>21:
    return abs(n-21)*2
  else:
    return abs(n-21)
```
#### Codingbat solution
```r
def diff21(n):
  if n <= 21:
    return 21 - n
  else:
    return (n - 21) * 2
```

---

###[parrot_trouble](http://codingbat.com/prob/p166884)
We have a loud talking parrot. The "hour" parameter is the current hour time in the range 0..23. We are in trouble if the parrot is talking and the hour is before 7 or after 20. Return True if we are in trouble.
* parrot_trouble(True, 6) → True
* parrot_trouble(True, 7) → False
* parrot_trouble(False, 6) → False

#### My solution
```r
def parrot_trouble(talking, hour):
  if (talking == True and (hour < 7 or hour > 20)):
    return True
  else:
    return False
```
#### Codingbat solution
```r
def parrot_trouble(talking, hour):
  return (talking and (hour < 7 or hour > 20))
  # Need extra parenthesis around the or clause
  # since and binds more tightly than or.
  # and is like arithmetic *, or is like arithmetic +
```

---

###[makes10](http://codingbat.com/prob/p124984)
Given 2 ints, a and b, return True if one if them is 10 or if their sum is 10.
* makes10(9, 10) → True
* makes10(9, 9) → False
* makes10(1, 9) → True

#### My solution
```r
def makes10(a, b):
  return(10 in (a, b, a+b))
```
#### Codingbat solution
```r
def makes10(a, b):
  return (a == 10 or b == 10 or a+b == 10)
```

---

###[near_hundred](http://codingbat.com/prob/p124676)
Given an int n, return True if it is within 10 of 100 or 200. Note: abs(num) computes the absolute value of a number.
* near_hundred(93) → True
* near_hundred(90) → True
* near_hundred(89) → False

#### My solution
```r
def near_hundred(n):
  return(abs(100-n) <= 10 or abs(200-n) <= 10)
```
#### Codingbat solution
```r
def near_hundred(n):
  return ((abs(100 - n) <= 10) or (abs(200 - n) <= 10))
```

---

###[pos_neg](http://codingbat.com/prob/p124676)
Given 2 int values, return True if one is negative and one is positive. Except if the parameter "negative" is True, then return True only if both are negative.
* pos_neg(1, -1, False) → True
* pos_neg(-1, 1, False) → True
* pos_neg(-4, -5, True) → True

#### My solution
```r
def pos_neg(a, b, negative):
  if negative:
    return(a<0 and b<0)
  else:
    return((a<0 and b>0) or  (a>0 and b<0))
```
#### Codingbat solution
```r
def pos_neg(a, b, negative):
  if negative:
    return (a < 0 and b < 0)
  else:
    return ((a < 0 and b > 0) or (a > 0 and b < 0))
```

---

###[not_string](http://codingbat.com/prob/p189441)
Given a string, return a new string where "not " has been added to the front. However, if the string already begins with "not", return the string unchanged.
* not_string('candy') → 'not candy'
* not_string('x') → 'not x'
* not_string('not bad') → 'not bad'

#### My solution
```r
def not_string(str):
  if len(str) >= 3 and str[:3] == "not":
    return(str)
  else:
    return("not "+str)
```
#### Codingbat solution
```r
def not_string(str):
  if len(str) >= 3 and str[:3] == "not":
    return str
  return "not " + str
  # str[:3] goes from the start of the string up to but not
  # including index 3
```

---

###[missing_char](http://codingbat.com/prob/p149524)
Given a non-empty string and an int n, return a new string where the char at index n has been removed. The value of n will be a valid index of a char in the original string (i.e. n will be in the range 0..len(str)-1 inclusive).
* missing_char('kitten', 1) → 'ktten'
* missing_char('kitten', 0) → 'itten'
* missing_char('kitten', 4) → 'kittn'

#### My solution
```r
def missing_char(str, n):
  front = str[0:n]
  back = str[n+1:len(str)]
  return(front+back)
```
#### Codingbat solution
```r
def missing_char(str, n):
  front = str[:n]   # up to but not including n
  back = str[n+1:]  # n+1 through end of string
  return front + back
```

---

###[front_back](http://codingbat.com/prob/p153599)
Given a string, return a new string where the first and last chars have been exchanged.
front_back('code') → 'eodc'
front_back('a') → 'a'
front_back('ab') → 'ba'

#### My solution
```r
def front_back(str):
  if len(str) <= 1:
    return str
  else:
    return(str[-1]+str[1:-1]+str[0])
```
#### Codingbat solution
```r
def front_back(str):
  if len(str) <= 1:
    return str

  mid = str[1:len(str)-1]  # can be written as str[1:-1]

  # last + mid + first
  return str[len(str)-1] + mid + str[0]
```

---

###[front3](http://codingbat.com/prob/p147920)
Given a string, we'll say that the front is the first 3 chars of the string. If the string length is less than 3, the front is whatever is there. Return a new string which is 3 copies of the front.
* front3('Java') → 'JavJavJav'
* front3('Chocolate') → 'ChoChoCho'
* front3('abc') → 'abcabcabc'

#### My solution
```r
def front3(str):
  if len(str)<3:
    return str*3
  else:
    return(str[0:3]*3)
```
#### Codingbat solution
```r
def front3(str):
  # Figure the end of the front
  front_end = 3
  if len(str) < front_end:
    front_end = len(str)
  front = str[:front_end]
  return front + front + front

  # Could omit the if logic, and write simply front = str[:3]
  # since the slice is silent about out-of-bounds conditions
```

---
