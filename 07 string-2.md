### [String-2](http://codingbat.com/python/String-2)
Medium python string problems -- 1 loop.. Use + to combine strings, len(str) is the number of chars in a String, str[i:j] extracts the substring starting at index i and running up to but not including index j.

---

### [double_char](http://codingbat.com/prob/p170842)
Given a string, return a string where for every char in the original, there are two chars.
double_char('The') → 'TThhee'
double_char('AAbb') → 'AAAAbbbb'
double_char('Hi-There') → 'HHii--TThheerree'

#### My solution
```r
def double_char(str):
  str2 = ""
  for i in str:
    str2 = str2+i+i
  return str2
```
#### Codingbat solution
```r
def double_char(str):
  result = ""
  for i in range(len(str)):
    result += str[i] + str[i]
  return result
```

---

### [count_hi](http://codingbat.com/prob/p167246)
Return the number of times that the string "hi" appears anywhere in the given string.
* count_hi('abc hi ho') → 1
* count_hi('ABChi hi') → 2
* count_hi('hihi') → 2

#### My solution
```r
def count_hi(str):
    count = 0
    for i in range(len(str)):
        cursor = str[i:i+2]
        if cursor == "hi": count +=1
    return count
```
#### Codingbat solution
```r
def count_hi(str):
  sum = 0
  ## Loop to length-1 and access index i and i+1
  ## in the loop.
  for i in range(len(str)-1):
    if str[i:i+2] == 'hi':
      sum = sum + 1
  return sum
```

---

### [cat_dog](http://codingbat.com/prob/p164876)
Return True if the string "cat" and "dog" appear the same number of times in the given string.
* cat_dog('catdog') → True
* cat_dog('catcat') → False
* cat_dog('1cat1cadodog') → True

#### My solution
```r
def cat_dog(str):
  count_cat = 0
  count_dog = 0
  for i in range(len(str)):
    cur = str[i:i+3]
    if cur == "cat": count_cat += 1
    if cur == "dog": count_dog += 1
  return(count_cat == count_dog)
```
#### Codingbat solution
```r
Non given
```

---

### [count_code](http://codingbat.com/prob/p186048)
Return the number of times that the string "code" appears anywhere in the given string, except we'll accept any letter for the 'd', so "cope" and "cooe" count.
* count_code('aaacodebbb') → 1
* count_code('codexxcode') → 2
* count_code('cozexxcope') → 2

#### My solution
```r
def count_code(str):
    count = 0
    for i in range(len(str)-3):
        cur = str[i:i+4]
        if cur[0:2] == "co" and cur[3] == "e": count += 1
    return count
```
#### Codingbat solution
```r
Non given
```

---

### [end_other](http://codingbat.com/prob/p174314)
Given two strings, return True if either of the strings appears at the very end of the other string, ignoring upper/lower case differences (in other words, the computation should not be "case sensitive"). Note: s.lower() returns the lowercase version of a string.
* end_other('Hiabc', 'abc') → True
* end_other('AbC', 'HiaBc') → True
* end_other('abc', 'abXabc') → True

#### My solution
```r
def end_other(a, b):

  a = a.lower()
  b = b.lower()

  lena = len(a)
  lenb = len(b)

  enda = a[-lenb:].lower()
  endb = b[-lena:].lower()

  return(enda == b or endb == a)
```
#### Codingbat solution
```r
def end_other(a, b):
  a = a.lower()
  b = b.lower()
  return (b.endswith(a) or a.endswith(b))
```

---

### [xyz_there](http://codingbat.com/prob/p149391)
Return True if the given string contains an appearance of "xyz" where the xyz is not directly preceeded by a period (.). So "xxyz" counts but "x.xyz" does not.
* xyz_there('abcxyz') → True
* xyz_there('abc.xyz') → False
* xyz_there('xyz.abc') → True

#### My solution
```r
def xyz_there(str):
    for i in range(len(str)):
        cur1 = str[i:i+4]
        cur2 = str[i+1:i+4]
        cur3 = str[i:i+3]
        #print(cur1, cur2, cur3)
        if (i == 0 and cur3 == "xyz") or (cur1 != ".xyz" and cur2 == "xyz"): return True    
    return False
```
#### Codingbat solution
```r
None given
```
