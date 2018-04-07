## [String-1](http://codingbat.com/python/String-1)
Medium warmup string/list problems with loops (solutions available)
 * string_times
 * front_times
 * string_bits
 * string_splosion
 * last2
 * array_count9
 * array_front9
 * array123string_match

---

###[string_times](http://codingbat.com/prob/p193507)
Given a string and a non-negative int n, return a larger string that is n copies of the original string.
* string_times('Hi', 2) → 'HiHi'
* string_times('Hi', 3) → 'HiHiHi'
* string_times('Hi', 1) → 'Hi'

#### My solution
```r
def string_times(str, n):
  return(str*n)
```
#### Codingbat solution
```r
def string_times(str, n):
  result = ""
  for i in range(n):  # range(n) is [0, 1, 2, .... n-1]
    result = result + str  # could use += here
  return result
```

---

###[front_times](http://codingbat.com/prob/p165097)
Given a string and a non-negative int n, we'll say that the front of the string is the first 3 chars, or whatever is there if the string is less than length 3. Return n copies of the front;
* front_times('Chocolate', 2) → 'ChoCho'
* front_times('Chocolate', 3) → 'ChoChoCho'
* front_times('Abc', 3) → 'AbcAbcAbc'

#### My solution
```r
def front_times(str, n):
  if len(str) < 3:
    front = str
  else:
    front = str[:3]
  return front*n
```
#### Codingbat solution
```r
def front_times(str, n):
  front_len = 3
  if front_len > len(str):
    front_len = len(str)
  front = str[:front_len]

  result = ""
  for i in range(n):
    result = result + front
  return result
```

---

###[string_bits](http://codingbat.com/prob/p113152)
Given a string, return a new string made of every other char starting with the first, so "Hello" yields "Hlo".
* string_bits('Hello') → 'Hlo'
* string_bits('Hi') → 'H'
* string_bits('Heeololeo') → 'Hello'

#### My solution
```r
def string_bits(str):
  my_str = ''
  for i in range(len(str)):
    if i % 2 == 0:
      my_str = my_str+str[i]
  return my_str
```
#### Codingbat solution
```r
def string_bits(str):
  result = ""
  # Many ways to do this. This uses the standard loop of i on every char,
  # and inside the loop skips the odd index values.
  for i in range(len(str)):
    if i % 2 == 0:
      result = result + str[i]
  return result
```

---

###[string_splosion](http://codingbat.com/prob/p118366)
Given a non-empty string like "Code" return a string like "CCoCodCode".
* string_splosion('Code') → 'CCoCodCode'
* string_splosion('abc') → 'aababc'
* string_splosion('ab') → 'aab'

#### My solution
```r
def string_splosion(str):
  res = ''
  for i in range(len(str)):
    res = res+str[0:i+1]
  return res
```
#### Codingbat solution
```r
def string_splosion(str):
  result = ""
  # On each iteration, add the substring of the chars 0..i
  for i in range(len(str)):
    result = result + str[:i+1]
  return result
```

---

###[last2](http://codingbat.com/prob/p145834)
Given a string, return the count of the number of times that a substring length 2 appears in the string and also as the last 2 chars of the string, so "hixxxhi" yields 1 (we won't count the end substring).
* last2('hixxhi') → 1
* last2('xaxxaxaxx') → 1
* last2('axxxaaxx') → 2

#### My solution
```r
def last2(str):
  count = 0
  last2 = str[-2:]

  if len(str) < 2:
    return 0

  for i in range(len(str)-2):
    if str[i:i+2] == last2:
      count += 1
  return count
```
#### Codingbat solution
```r
def last2(str):
  # Screen out too-short string case.
  if len(str) < 2:
    return 0

  # last 2 chars, can be written as str[-2:]
  last2 = str[len(str)-2:]
  count = 0

  # Check each substring length 2 starting at i
  for i in range(len(str)-2):
    sub = str[i:i+2]
    if sub == last2:
      count = count + 1

  return count
```

---

###[array_count9](http://codingbat.com/prob/p166170)
Given an array of ints, return the number of 9's in the array.
* array_count9([1, 2, 9]) → 1
* array_count9([1, 9, 9]) → 2
* array_count9([1, 9, 9, 3, 9]) → 3

#### My solution
```r
def array_count9(nums):
  count = 0

  for i in range(len(nums)):
    if nums[i] == 9:
      count += 1
  return count
```
#### Codingbat solution
```r
def array_count9(nums):
  count = 0
  # Standard loop to look at each value
  for num in nums:
    if num == 9:
      count = count + 1

  return count
```

---

###[array_front9](http://codingbat.com/prob/p110166)
Given an array of ints, return True if one of the first 4 elements in the array is a 9. The array length may be less than 4.
* array_front9([1, 2, 9, 3, 4]) → True
* array_front9([1, 2, 3, 4, 9]) → False
* array_front9([1, 2, 3, 4, 5]) → False

#### My solution
```r
def array_front9(nums):

  if len(nums) <= 4:
    my_len = len(nums)
  else:
    my_len = 4

  for i in range(my_len):
    if nums[i] == 9:
      return True

  return False
```
#### Codingbat solution
```r
def array_front9(nums):
  # First figure the end for the loop
  end = len(nums)
  if end > 4:
    end = 4

  for i in range(end):  # loop over index [0, 1, 2, 3]
    if nums[i] == 9:
      return True
  return False
```

---

###[array123](http://codingbat.com/prob/p193604)
Given an array of ints, return True if the sequence of numbers 1, 2, 3 appears in the array somewhere.
* array123([1, 1, 2, 3, 1]) → True
* array123([1, 1, 2, 4, 1]) → False
* array123([1, 1, 2, 1, 2, 3]) → True

#### My solution
```r
def array123(nums):

  my_len = len(nums)

  for i in range(my_len-2):
    if nums[i] == 1 and nums[i+1] == 2 and nums[i+2] == 3: return True

  else: return False
```
#### Codingbat solution
```r
def array123(nums):
  # Note: iterate with length-2, so can use i+1 and i+2 in the loop
  for i in range(len(nums)-2):
    if nums[i]==1 and nums[i+1]==2 and nums[i+2]==3:
      return True
  return False
```

---

###[string_match](http://codingbat.com/prob/p182414)
Given an array of ints, return True if the sequence of numbers 1, 2, 3 appears in the array somewhere.
* array123([1, 1, 2, 3, 1]) → True
* array123([1, 1, 2, 4, 1]) → False
* array123([1, 1, 2, 1, 2, 3]) → True

#### My solution
```r
def string_match(a, b):

    c = 0
    my_min = min(len(a), len(b))

    for i in range(my_min-1):
        a1 = a[i:i+2]
        b1 = b[i:i+2]
        if a1 == b1:
            c = c + 1

  return c
```
#### Codingbat solution
```r
def string_match(a, b):
  # Figure which string is shorter.
  shorter = min(len(a), len(b))
  count = 0

  # Loop i over every substring starting spot.
  # Use length-1 here, so can use char str[i+1] in the loop
  for i in range(shorter-1):
    a_sub = a[i:i+2]
    b_sub = b[i:i+2]
    if a_sub == b_sub:
      count = count + 1

  return count
```
