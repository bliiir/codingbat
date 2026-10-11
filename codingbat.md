### [cigar_party](http://codingbat.com/prob/p195669)
When squirrels get together for a party, they like to have cigars. A squirrel party is successful when the number of cigars is between 40 and 60, inclusive. Unless it is the weekend, in which case there is no upper bound on the number of cigars. Return True if the party with the given values is successful, or False otherwise.
* cigar_party(30, False) → False
* cigar_party(50, False) → True
* cigar_party(70, True) → True

#### My solution
```r
def cigar_party(cigars, is_weekend):
return((not is_weekend and cigars >= 40 and cigars <= 60) or (is_weekend and cigars >= 40))
```
#### Codingbat solution
```r
None given
```

---

### [date_fashion](http://codingbat.com/prob/p129125)
You and your date are trying to get a table at a restaurant. The parameter "you" is the stylishness of your clothes, in the range 0..10, and "date" is the stylishness of your date's clothes. The result getting the table is encoded as an int value with 0=no, 1=maybe, 2=yes. If either of you is very stylish, 8 or more, then the result is 2 (yes). With the exception that if either of you has style of 2 or less, then the result is 0 (no). Otherwise the result is 1 (maybe).
* date_fashion(5, 10) → 2
* date_fashion(5, 2) → 0
* date_fashion(5, 5) → 1

#### My solution
```r
def date_fashion(you, date):
  if you <= 2 or date <=2: return 0
  elif you >= 8 or date >= 8: return 2
  else: return 1
```
#### Codingbat solution
```r
None given
```

---

### [squirrel_play](http://codingbat.com/prob/p135815)
The squirrels in Palo Alto spend most of the day playing. In particular, they play if the temperature is between 60 and 90 (inclusive). Unless it is summer, then the upper limit is 100 instead of 90. Given an int temperature and a boolean is_summer, return True if the squirrels play and False otherwise.
* squirrel_play(70, False) → True
* squirrel_play(95, False) → False
* squirrel_play(95, True) → True

#### My solution
```r
def squirrel_play(temp, is_summer):
  i = 0
  if is_summer: i = 10
  return(temp >= 60 and temp <= (90 + i))
```
#### Codingbat solution
```r
None given
```
---

### [caught_speeding](http://codingbat.com/prob/p137202)
You are driving a little too fast, and a police officer stops you. Write code to compute the result, encoded as an int value: 0=no ticket, 1=small ticket, 2=big ticket. If speed is 60 or less, the result is 0. If speed is between 61 and 80 inclusive, the result is 1. If speed is 81 or more, the result is 2. Unless it is your birthday -- on that day, your speed can be 5 higher in all cases.
* caught_speeding(60, False) → 0
* caught_speeding(65, False) → 1
* caught_speeding(65, True) → 0

#### My solution
```r
def caught_speeding(speed, is_birthday):
    speed = int(speed)
    lr = 0
    if is_birthday: lr = 5
    if speed <= 60 + lr: return 0
    elif speed >= 61 + lr and speed <= 80+lr: return 1
    elif speed >= 81 + lr: return 2
```
#### Codingbat solution
```r
None given
```

---

### [sorta_sum](http://codingbat.com/prob/p116620)
Given 2 ints, a and b, return their sum. However, sums in the range 10..19 inclusive, are forbidden, so in that case just return 20.
* sorta_sum(3, 4) → 7
* sorta_sum(9, 4) → 20
* sorta_sum(10, 11) → 21

#### My solution
```r
def sorta_sum(a, b):
  my_sum = a+b
  if my_sum in range(10, 20): return 20
  else: return my_sum
```
#### Codingbat solution
```r
None given
```
