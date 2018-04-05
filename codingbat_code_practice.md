#Codingbat

*Code Practice*

[Link](http://codingbat.com/)

## [Python](http://codingbat.com/python)


### Logic-2
[Link](http://codingbat.com/python/Logic-2)

#### make_bricks
[Link](http://codingbat.com/prob/p118406)
##### Description
We want to make a row of bricks that is goal inches long. We have a number of small bricks (1 inch each) and big bricks (5 inches each). Return True if it is possible to make the goal by choosing from the given bricks. This is a little harder than it looks and can be done without any loops. See also: Introduction to MakeBricks

make_bricks(3, 1, 8) → True
make_bricks(3, 1, 9) → False
make_bricks(3, 2, 10) → True


##### My solution
```r
def make_bricks(small, big, goal):
    b = big * 5
    s = small * 1
    if goal > b + s: return False
    if goal % 5 > s: return False
    return True
```

##### Their solution
```r
def make_bricks(small, big, goal):
    if goal > big*5 + small: return False
    if goal % 5 > small: return False
    return True
```




#### round_sum
[link](http://codingbat.com/prob/p179960)


##### Description
For this problem, we'll round an int value up to the next multiple of 10 if its rightmost digit is 5 or more, so 15 rounds up to 20. Alternately, round down to the previous multiple of 10 if its rightmost digit is less than 5, so 12 rounds down to 10. Given 3 ints, a b c, return the sum of their rounded values. To avoid code repetition, write a separate helper "def round10(num):" and call it 3 times. Write the helper entirely below and at the same indent level as round_sum().

round_sum(16, 17, 18) → 60
round_sum(12, 13, 14) → 30
round_sum(6, 4, 4) → 10

##### My solution
```r
def round_sum(a, b, c):
    return(round10(a)+round10(b)+round10(c))

def round10(num):
    if num%10 <5: return(num-num%10)
    else: return(num+(10-num%10))
```

Or with a loop - better for longer input lists
```r
def round_sum(a, b, c):
    sums = 0
    nums = [a,b,c]
    for i in nums:
        sums = sums + round10(i)
    return sums

def round10(num):
    if num%10 <5: return(num-num%10)
    else: return(num+(10-num%10))
```

##### Codingbat solution
```r
def round_sum(a, b, c):
  return round10(a) + round10(b) + round10(c)

def round10(num):
  mod = num % 10
  num -= mod
  if mod >= 5: num += 10
  return num
  ```
