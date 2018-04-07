## [String-1](http://codingbat.com/python/String-1)
Basic python string problems -- no loops. Use + to combine strings, len(str) is the number of chars in a String, str[i:j] extracts the substring starting at index i and running up to but not including index j.
* hello_name
* make_abba
* make_tags
* make_out_word
* extra_end
* first_two
* first_half
* without_end
* combo_string
* non_start
* left2

---

###[hello_name](http://codingbat.com/prob/p115413)
Given a string name, e.g. "Bob", return a greeting of the form "Hello Bob!".
* hello_name('Bob') → 'Hello Bob!'
* hello_name('Alice') → 'Hello Alice!'
* hello_name('X') → 'Hello X!'

#### My solution
```r
def hello_name(name):
  str = "Hello " + name + "!"
  return(str)
```
#### Codingbat solution
```r
def hello_name(name):
  return "Hello " + name + "!"
```

---

###[make_abba](http://codingbat.com/prob/p182144)
Given two strings, a and b, return the result of putting them together in the order abba, e.g. "Hi" and "Bye" returns "HiByeByeHi".
* make_abba('Hi', 'Bye') → 'HiByeByeHi'
* make_abba('Yo', 'Alice') → 'YoAliceAliceYo'
* make_abba('What', 'Up') → 'WhatUpUpWhat'

#### My solution
```r
def make_abba(a, b):
  return(a+b+b+a)
```
#### Codingbat solution
```r
def make_abba(a, b):
  return a + b + b + a
```

---

###[make_tags](http://codingbat.com/prob/p132290)
The web is built with HTML strings like "<i>Yay</i>" which draws Yay as italic text. In this example, the "i" tag makes <i> and </i> which surround the word "Yay". Given tag and word strings, create the HTML string with tags around the word, e.g. "<i>Yay</i>".
* make_tags('i', 'Yay') → '<i>Yay</i>'
* make_tags('i', 'Hello') → '<i>Hello</i>'
* make_tags('cite', 'Yay') → '<cite>Yay</cite>'

#### My solution
```r
def make_tags(tag, word):
  return("<" + tag + ">" + word + "</" + tag + ">")
```
#### Codingbat solution
```r
Non given
```

---

###[make_out_word](http://codingbat.com/prob/p129981)
Given an "out" string length 4, such as "<<>>", and a word, return a new string where the word is in the middle of the out string, e.g. "<<word>>".
make_out_word('<<>>', 'Yay') → '<<Yay>>'
make_out_word('<<>>', 'WooHoo') → '<<WooHoo>>'
make_out_word('[[]]', 'word') → '[[word]]'

#### My solution
```r
def make_out_word(out, word):
  return(out[:2] + word + out[2:])
```
#### Codingbat solution
```r
Non given
```

---

###[extra_end](http://codingbat.com/prob/p148853)
Given a string, return a new string made of 3 copies of the last 2 chars of the original string. The string length will be at least 2.
* extra_end('Hello') → 'lololo'
* extra_end('ab') → 'ababab'
* extra_end('Hi') → 'HiHiHi'

#### My solution
```r
def extra_end(str):
  return(str[-2:]*3)
```
#### Codingbat solution
```r
def extra_end(str):
  end = str[-2:]
  return end + end + end
```

---

###[first_two](http://codingbat.com/prob/p184816)
Given a string, return the string made of its first two chars, so the String "Hello" yields "He". If the string is shorter than length 2, return whatever there is, so "X" yields "X", and the empty string "" yields the empty string "".
* first_two('Hello') → 'He'
* first_two('abcdefg') → 'ab'
* first_two('ab') → 'ab'

#### My solution
```r
def first_two(str):
  if len(str) <= 2: return str
  else: return(str[:2])
```
#### Codingbat solution
```r
def first_two(str):
  if len(str) >= 2:
    return str[:2]
  else:
    return str
```

---

###[first_half](http://codingbat.com/prob/p107010)
Given a string of even length, return the first half. So the string "WooHoo" yields "Woo".
* first_half('WooHoo') → 'Woo'
* first_half('HelloThere') → 'Hello'
* first_half('abcdef') → 'abc'

#### My solution
```r
def first_half(str):
  return(str[:int(len(str)/2)])
```
#### Codingbat solution
```r
Non given
```

---

###[without_end](http://codingbat.com/prob/p138533)
Given a string, return a version without the first and last char, so "Hello" yields "ell". The string length will be at least 2.
* without_end('Hello') → 'ell'
* without_end('java') → 'av'
* without_end('coding') → 'odin'

#### My solution
```r
def without_end(str):
  return(str[1:-1])
```
#### Codingbat solution
```r
Non given
```

---

###[combo_string](http://codingbat.com/prob/p194053)
Given 2 strings, a and b, return a string of the form short+long+short, with the shorter string on the outside and the longer string on the inside. The strings will not be the same length, but they may be empty (length 0).
* combo_string('Hello', 'hi') → 'hiHellohi'
* combo_string('hi', 'Hello') → 'hiHellohi'
* combo_string('aaa', 'b') → 'baaab'

#### My solution
```r
def combo_string(a, b):

  if len(a) >= len(b):
    l = a
    s = b
  else:
    l = b
    s = a

  return(s+l+s)
```
#### Codingbat solution
```r
Non given
```

---

###[non_start](http://codingbat.com/prob/p127703)
Given 2 strings, return their concatenation, except omit the first char of each. The strings will be at least length 1.
* non_start('Hello', 'There') → 'ellohere'
* non_start('java', 'code') → 'avaode'
* non_start('shotl', 'java') → 'hotlava'

#### My solution
```r
def non_start(a, b):
  return(a[1:]+b[1:])
```
#### Codingbat solution
```r
Non given
```

---

###[left2](http://codingbat.com/prob/p160545)
Given a string, return a "rotated left 2" version where the first 2 chars are moved to the end. The string length will be at least 2.
* left2('Hello') → 'lloHe'
* left2('java') → 'vaja'
* left2('Hi') → 'Hi'

#### My solution
```r
def left2(str):
  return(str[2:]+str[:2])
```
#### Codingbat solution
```r
def left2(str):
  return str[2:] + str[:2]
```
