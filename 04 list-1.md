

## [List-2](http://codingbat.com/python/List-1)
Basic python list problems -- no loops.. Use a[0], a[1], ... to access elements in a list, len(a) is the length.

* first_last6
* same_first_last	 
* make_pi
* common_end	 
* sum3	 
* rotate_left3
* reverse3	 
* max_end3	 
* sum2
* middle_way	 
* make_ends	 
* has23

---

###[first_last6](http://codingbat.com/prob/p181624)
Given an array of ints, return True if 6 appears as either the first or last element in the array. The array will be length 1 or more.
* first_last6([1, 2, 6]) → True
* first_last6([6, 1, 2, 3]) → True
* first_last6([13, 6, 1, 2, 3]) → False

#### My solution
```r
def first_last6(nums):
  return(nums[0] == 6 or nums[len(nums)-1] == 6)
```
#### Codingbat solution
```r
def first_last6(nums):
  return (nums[0]==6 or nums[-1]== 6)
```

---

###[same_first_last](http://codingbat.com/prob/p179078)
Given an array of ints, return True if the array is length 1 or more, and the first element and the last element are equal.
* same_first_last([1, 2, 3]) → False
* same_first_last([1, 2, 3, 1]) → True
* same_first_last([1, 2, 1]) → True

#### My solution
```r
def same_first_last(nums):
  return(len(nums) > 0 and nums[0] == nums[len(nums)-1])
```
#### Codingbat solution
```r
def same_first_last(nums):
  return (len(nums) >= 1 and nums[0] == nums[-1])
```

---

###[make_pi](http://codingbat.com/prob/p113659)
Return an int array length 3 containing the first 3 digits of pi, {3, 1, 4}.
* make_pi() → [3, 1, 4]

#### My solution
```r
def make_pi():
  return([3, 1, 4])
```
#### Codingbat solution
```r
None given
```

---

###[common_end](http://codingbat.com/prob/p147755)
Given 2 arrays of ints, a and b, return True if they have the same first element or they have the same last element. Both arrays will be length 1 or more.
* common_end([1, 2, 3], [7, 3]) → True
* common_end([1, 2, 3], [7, 3, 2]) → False
* common_end([1, 2, 3], [1, 3]) → True

#### My solution
```r
def common_end(a, b):
  return(a[0] == b[0] or a[len(a)-1] == b[len(b)-1])
```
#### Codingbat solution
```r
None given
```

---

###[sum3](http://codingbat.com/prob/p191645)
Given 2 arrays of ints, a and b, return True if they have the same first element or they have the same last element. Both arrays will be length 1 or more.
* common_end([1, 2, 3], [7, 3]) → True
* common_end([1, 2, 3], [7, 3, 2]) → False
* common_end([1, 2, 3], [1, 3]) → True

#### My solution
```r
def sum3(nums):
  return(sum(nums[0:3]))
```
#### Codingbat solution
```r
None given
```

---

###[rotate_left3](http://codingbat.com/prob/p148661)
Given an array of ints length 3, return an array with the elements "rotated left" so {1, 2, 3} yields {2, 3, 1}.
* rotate_left3([1, 2, 3]) → [2, 3, 1]
* rotate_left3([5, 11, 9]) → [11, 9, 5]
* rotate_left3([7, 0, 0]) → [0, 0, 7]

#### My solution
```r
def rotate_left3(nums):
  return([nums[1], nums[2], nums[0]])
```
#### Codingbat solution
```r
None given
```

---

###[reverse3](http://codingbat.com/prob/p192962)
Given an array of ints length 3, return a new array with the elements in reverse order, so {1, 2, 3} becomes {3, 2, 1}.
* reverse3([1, 2, 3]) → [3, 2, 1]
* reverse3([5, 11, 9]) → [9, 11, 5]
* reverse3([7, 0, 0]) → [0, 0, 7]

#### My solution
```r
def reverse3(nums):
  return([nums[2], nums[1], nums[0]])
```
#### Codingbat solution
```r
None given
```

---

###[max_end3](http://codingbat.com/prob/p135290)
Given an array of ints length 3, return a new array with the elements in reverse order, so {1, 2, 3} becomes {3, 2, 1}.
* reverse3([1, 2, 3]) → [3, 2, 1]
* reverse3([5, 11, 9]) → [9, 11, 5]
* reverse3([7, 0, 0]) → [0, 0, 7]

#### My solution
```r
def max_end3(nums):
  return([max(nums[0],nums[2])]*3)
```
#### Codingbat solution
```r
def max_end3(nums):
  big = max(nums[0], nums[2])
  nums[0] = big
  nums[1] = big
  nums[2] = big
  return nums
```

---

###[sum2](http://codingbat.com/prob/p192589)
Given an array of ints, return the sum of the first 2 elements in the array. If the array length is less than 2, just sum up the elements that exist, returning 0 if the array is length 0.
* sum2([1, 2, 3]) → 3
* sum2([1, 1]) → 2
* sum2([1, 1, 1, 1]) → 2

#### My solution
```r
def sum2(nums):
  if len(nums) == 0: return 0
  elif len(nums) < 2: return (nums[0])
  else: return(nums[0] + nums[1])
```
#### Codingbat solution
```r
None given
```

---

###[middle_way](http://codingbat.com/prob/p171011)
Given 2 int arrays, a and b, each length 3, return a new array length 2 containing their middle elements.
* middle_way([1, 2, 3], [4, 5, 6]) → [2, 5]
* middle_way([7, 7, 7], [3, 8, 0]) → [7, 8]
* middle_way([5, 2, 9], [1, 4, 5]) → [2, 4]

#### My solution
```r
def middle_way(a, b):
  return([a[1],b[1]])
```
#### Codingbat solution
```r
None given
```

---

###[make_ends](http://codingbat.com/prob/p124806)

Given an array of ints, return a new array length 2 containing the first and last elements from the original array. The original array will be length 1 or more.
* make_ends([1, 2, 3]) → [1, 3]
* make_ends([1, 2, 3, 4]) → [1, 4]
* make_ends([7, 4, 6, 2]) → [7, 2]

#### My solution
```r
def make_ends(nums):
  return([nums[0], nums[len(nums)-1]])
```
#### Codingbat solution
```r
None given
```

---

###[has23](http://codingbat.com/prob/p177892)
Given an int array length 2, return True if it contains a 2 or a 3.
* has23([2, 5]) → True
* has23([4, 3]) → True
* has23([4, 5]) → False

#### My solution
```r
def has23(nums):
  return(2 in nums or 3 in nums)
```
#### Codingbat solution
```r
None given
```
