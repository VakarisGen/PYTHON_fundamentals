# PYTHON_Fundamentals
A guide and summary of my practice with PYTHON Fundamentals 

I best learn by practice and repetition thus i though, why not document it.
Below you will find a number of exercises regarding PYTHON fundamentals, basic code building and syntax
All the practice tasks were done using PyCharm IDE

_________

## Exploring `VARIABLES` and `IF` statements

- Saving name, last name, Date of Birth as well as current year as `VAR`. Writing a short code that can `PRINT` name and surname, calculate current age based on input.

```Python
name = "Vakaris"
surname = "Genutis"
dob = 1996
currdate = 2026

print(f"My name is {name} {surname}. I'm {currdate - dob} years old")
```  
- Creating two `VAR` with random values from 0 to 4, dividing the larger by the smaller and print the result rounded to 2 decimal places.

```Python
import random

num1 = random.randint(0, 4)
num2 = random.randint(0, 4)
minnum = min(num1, num2)
maxnum = max(num1, num2)

if minnum == 0:
    print("Division by 0 is impossible")
else:
    print(round(maxnum / minnum, 2))
```
- Creating 3 `VAR` with random values from 0 to 25. Finding and printing smallest, biggest and middle value number.

```PYTHON
import random
from statistics import median

num1 = random.randint(0, 25)
num2 = random.randint(0, 25)
num3 = random.randint(0, 25)

list = num1, num2, num3
maxvar = max(list)
minvar = min(list)
medvar = median(list)

print(f" first: {num1}, second: {num2}, third: {num3}")
print(f"Middle number is {medvar}")
print(f"Lowest number is {minvar}")
print(f"Biggest number is {maxvar}")
```

- Creating 3 `VAR` which are random values from 0 to 10. These `VAR` are assigned as a triangle sides.
Code below generates the numbers and checks if triangle is possible with generated values.

```PYTHON
import random

a = random.randint(1, 10)
b = random.randint(1, 10)
c = random.randint(1, 10)

print(f"Sides: a = {a}, b = {b}, c = {c}")
if (a + b > c) and (b + c > a) and (c + a > b):
    print("Triangle is possible")
else:
    print("Triangle is impossible")
```
- Creating 4 `VAR` and assigning random values from 0 to 2. Code below counts how many 0, 1s and 2s were generated.
Although such result can be reached using an `ARRAY`, i decided to do it without it, visiting and analyzing `ARRAY` at a later date.

```PYTHON
import random

num1 = random.randint(0, 2)
num2 = random.randint(0, 2)
num3 = random.randint(0, 2)
num4 = random.randint(0, 2)

numblock = num1, num2, num3, num4
#print(f"num1 = {num1}, num2 = {num2}, num3 = {num3}, num4 = {num4}") #Checking generated numbers

res0 = numblock.count(0)
res1 = numblock.count(1)
res2 = numblock.count(2)

print(f" Total amount of zeroes: {res0}, {res1} ones {res2} twos")
```
- Task. Candles are being sold for 1 Eur/ea. If more than 1000 units are being sold - 3% discount is applied per unit, for more than 2000 units - 4% discount per unit
Code below generates a random amount of units sold (between 5 and 3000), calculates and prints finalized prices.

```PYTHON
import random

price1 = 1
price2 = 1 - (1 * 0.03)
price3 = 1 - (1 * 0.04)

candle = random.randint(5, 3000)
print(f"Buying amount {candle}")

#defining the calculation
if candle < 1000:
    finalprice = price1
elif candle > 1000 and candle < 2000:
    finalprice = price2
else:
    finalprice = price3

# Printing result
print(f"Single candle price {finalprice} eur")
result = candle * finalprice
print(f"Total price {result}")
```

___
## Exploring `STRINGS`

- Assigning actor names to `VAR` as a `STRING`. Printing the shorter `STRING`

```PYTHON
name = "Viggo"
surname = "Mortensen"

if len(name) < len(surname):
    print(name)
elif len(name) == len(surname):
    print("Lenght of each string is the same")
else:
    print(surname)
```

- Printing assigned strings - name in uppercase, surname in lowercase letters / printing Initials of the assigned names.

```PYTHON
name = "Viggo"
surname = "Mortensen"

initial = name[0] + surname[0]
print(str.upper(name), str.lower(surname))
print(f" Initials are {initial}")
```

- Using the same assigned actor name/surname as `STRING`, assigning a `VAR` as a combination of last 3 letters for name and surname.
Printing the result.

```PYTHON
name = "Viggo"
surname = "Mortensen"
n = 3

result = name[-n:] + surname[-n:]

if len(name) < n or len(surname) < n:
    print("Requested number of last symbols exceed the length of the name/surname")
else:
    print(result)
```

- Replacing defined symbols in a `STRING`, lowercase and uppercase combined.

```PYTHON
str1 = "An American in Paris"
print(str1.replace("A", "*").replace("a", "*"))
```

- Assigning a `STRING` to a variable, checking if there is numbers in the `STRING`. Using `ISDIGIT` for the easy solution.

```PYTHON
text = "I'm 24 years old"
result = any(char.isdigit() for char in text)
if result == True:
    print("Yes")
else:
    print("No")
```

___
## Exploring `FOR` and `WHILE` Loops, `LISTS` and `ARRAYS`

- Simple `FOR` loop printing same `STR` defined amount of times. Listing numbers from 0 to 10 (with `LIST` and without)

```PYTHON
word = 'Hello'
for i in range(10):
    print(word)

lst = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
for i in lst:
    print(i)

for i in range(0, 11):
    print(i)
```

- Printing even numbers in range from 10 to 50. Repeat but skip numbers divisible by 10 without a remainder. using `CONTINUE` where possible.

```PYTHON
for i in range(10,51):
    if i % 2 == 0:
        print(i)

for i in range(10,51):
    if i % 2 == 0 and i % 10 != 0:
        print(i)

for i in range(10,51):
    if i % 10 == 0:
        continue
    if i % 2 == 0:
        print(i)
```

- Counting certain cycle iterrations, ex. when `VAR` is an even number.

```PYTHON
count = 0
for i in range(0, 21):
    if i % 2 == 0:
        count += 1
print(count)
```

- Counting `ARRAY` elements based on the symbol lenght. One cycle for counting elements that are shorter than 5 symbols, another cycle for elements longer than 7 symbols. 

```PYTHON
forest = ['Birch', 'Evergreen', 'Oak', 'Spruce', 'Willow', 'Yew', 'Redwood','Hazelnut', 'Ebony', 'Ash', 'Chestnut', 'Maple', 'Cedar', 'Pine']

count = 0
for i in forest:
    if len(i) < 5:
        count += 1
print(f'Shorter than 5 symbols = {count}')

count = 0
for i in forest:
    if len(i) > 7:
        count += 1
print(f'Longer than 7 symbols = {count}')
```

- Using the same array from a previous exercise, counting elements that are longer than 5 but shorter than 10 symbols.

```PYTHON
count = 0
for i in plants:
    if len(i) > 5 and len(i) < 10:
        count += 1
print(f'Plants that are longer than 5, but shorter than 10 symbols = {count}')
```

- Creating and filling in an `ARRAY` with random numbers.

```PYTHON
import random

arr1 = []
for i in range(30):
    i = random.randint(5, 25)
    arr1.append(i)
print(arr1)
```

- Counting previously filled `ARRAY` values that are larger than 10.

```PYTHON
count = 0
for i in arr1:
    if i > 10:
        count += 1
print(f'{count} values larger than 10')
```

- Looking for largest value. Counting a total sum of all `ARRAY` values.

```PYTHON
max_value = max(arr1)
print(f'Largest value in array is: {max_value}')

sumtotal = 0
for i in arr1:
    sumtotal += i
print(f'Bendra visu skaiciu suma yra: {sumtotal}')
```

- Sorting the `ARRAY` values into even and uneven values.

```PYTHON
even_arr = []
uneven_arr = []
for i in arr2:
    if i % 2 == 0:
        even_arr.append(i)
    else:
        uneven_arr.append(i)
print(f'Even values: {even_arr}, Uneven values: {uneven_arr}')
```
- Generating a random `ARRAY` with letters assigned as values. Counting each letter.

```PYTHON
import random

arr = []
for i in range(200):
     arr.append(random.randint(1, 4))

for i in range(len(arr)):
    if arr[i] == 1:
        arr[i] = 'A'
    elif arr[i] == 2:
        arr[i] = 'B'
    elif arr[i] == 3:
        arr[i] = 'C'
    elif arr[i] == 4:
        arr[i] = 'D'
# print(arr) #print for checking

countA = 0
countB = 0
countC = 0
countD = 0

for i in arr:
    if i == 'A':
        countA += 1
    elif i == 'B':
        countB += 1
    elif i == 'C':
        countC += 1
    elif i == 'D':
        countD +=1

print(f'A: {countA}, B: {countB}, C: {countC}, D: {countD}')
```

- Taking the code from the previous exercise and creating 3 `ARRAYS` on the same parameters. Merging them into 1 `ARRAY`, checking, separating and counting duplicate values. Of course my provided solution is not the most optimal, would be cleaner and easier to read using `FUNCTIONS` however as I'm currently exploring `ARRAYS`, leaning towards the more fundamentaly simple solution.

```PYTHON
import random

arr1 = []
for i in range(200):
     arr1.append(random.randint(1, 4))

for i in range(len(arr1)):
    if arr1[i] == 1:
        arr1[i] = 'A'
    elif arr1[i] == 2:
        arr1[i] = 'B'
    elif arr1[i] == 3:
        arr1[i] = 'C'
    elif arr1[i] == 4:
        arr1[i] = 'D'
# print(f'First array: {arr1}')

arr2 = []
for i in range(200):
     arr2.append(random.randint(1, 4))

for i in range(len(arr2)):
    if arr2[i] == 1:
        arr2[i] = 'A'
    elif arr2[i] == 2:
        arr2[i] = 'B'
    elif arr2[i] == 3:
        arr2[i] = 'C'
    elif arr2[i] == 4:
        arr2[i] = 'D'
# print(f' Second array: {arr2}')

arr3 = []
for i in range(200):
     arr3.append(random.randint(1, 4))

for i in range(len(arr3)):
    if arr3[i] == 1:
        arr3[i] = 'A'
    elif arr3[i] == 2:
        arr3[i] = 'B'
    elif arr3[i] == 3:
        arr3[i] = 'C'
    elif arr3[i] == 4:
        arr3[i] = 'D'
# print(f' Third array: {arr3}')

merged_array = []
for i in range(200):
    merged_array.append(arr1[i] + arr2[i] + arr3[i])
    # print(merged_array, end= ' ')               #    print(arr1[i] + arr2[i] + arr3[i], end= ' ')
print(merged_array)

unique_array = []
combcount = 0
for combination in merged_array:
    if combination not in unique_array:
        combcount += 1
        unique_array.append(combination)
print(f'Unique combinations: {unique_array}, total number of unique combinations: {combcount}')
``` 
- Generating a 101 value length random `ARRAY`. Checking and replacing all duplicate values untill all the `ARRAY` values are unique.

```PYTHON
import random

array1 = []
count = 0

while len(array1) < 101:
    count += 1
    i = random.randint(0, 300)
    if i not in array1:
        array1.append(i)

# check if there are any dublicates
array1.sort()
print(array1)
print(count)
```
___

- Creating a simple Heads/Tails simulator. 3 instances are made that stops the game in 3 different scenarios:
1. When heads are flipped: 
```PYTHON
import random

Hcount = 0
Scount = 0
while True:
    result = random.randint(0,1)
    if result == 1:
        Scount += 1
    else:
        Hcount += 1
    print(f'Heads count: {Hcount}')
    print(f'Tails count: {Scount}')
    print('-----------')
    if Hcount == 1:
        break
```
2. When Heads are flipped 3 times:
```PY
import random

Hcount = 0
Tcount = 0
while True:
    result = random.randint(0,1)
    if result == 1:
        Tcount += 1
    else:
        Hcount += 1
    print(f'Heads count: {Hcount}')
    print(f'Tails count: {Tcount}')
    print('-----------')
    if Hcount == 3:
        break
```
3. Heads are flipped 3 times in a row:
```PY
import random

Hcount = 0
Tcount = 0
while True:
    result = random.randint(0,1)
    if result == 0:
        Hcount += 1
        print(f'Heads count: {Hcount}')
        print(f'Tails count: {Tcount}')
        print('-----------')
    else:
        Tcount += 1
        print(f'Heads count: {Hcount}')
        print(f'Tails count: {Tcount}, tails dropped, reseting')
        print('-----------')
        Hcount = 0
        Tcount = 0

    if Hcount == 3:
        break
```

- Creating a simple nail hammering calculator. Each nail is 8.5cm in lenght.
Hammering 5 nails with small hits, 1 small hit moves the nail 5-20mm in the plank.
Hammering 5 nails with big hits, 1 big hit moves the nail 20-30mm in the plank.
in addition, there is a 50% chance that the hammer swing misses. 
Below code counts how many times would you need to swing the hammer in each scenario to drive the nail fully into the plank.

```PY
import random

# smallhit = random.randint(5,20)
# bighit = random.randint(20, 30)

depth = 0
hitcount = 0

for nail_nr in range(5):
    while depth < 850:
        hitcount += 1
        if random.randint(1, 100) <= 50:
            depth += random.randint(5, 20)
print(f'All 5 nails needed {hitcount} small hits')

depth = 0
hitcount = 0

for nail_nr in range(5):
    while depth < 850:
        hitcount += 1
        if random.randint(1, 100) <= 50: #taikom 50% tikimybe
            depth += random.randint(20, 30)
print(f'All 5 nails needed {hitcount} big hits')
```
___

## Exploring `FUNCTIONS`

- Creating a `FUNCTION` for `ARRAY` generation of defined length and defined random number value ranges.

```PY
import random

def f_random_array_gen(a, b, c):
    array_1 = []
    for i in range(c):
        rnd_num = random.randint(a, b)
        array_1.append(rnd_num)
    print(array_1)
    return array_1
```

- 



 
> WORK IN PROGRESS...
