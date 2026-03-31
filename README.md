# PYTHON_Fundamentals
A guide and summary of my practice with PYTHON Fundamentals 

I best learn by practice and repetition thus i though, why not document it.
Below you will find a number of exercises regarding PYTHON fundamentals, basic code building and syntax
All the practice tasks were done using PyCharm IDE

_________

## Exploring `VARIABLES` and `IF` statements

- Saving name, last name, Date of Birth as well as current year as `variable`. Writing a short code that can `print` name and surname, calculate current age based on input.

```Python
name = "Vakaris"
surname = "Genutis"
dob = 1996
currdate = 2026

print(f"My name is {name} {surname}. I'm {currdate - dob} years old")
```  
- Creating two `variables` with random values from 0 to 4, dividing the larger by the smaller and print the result rounded to 2 decimal places.

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
- Creating 3 `variables` with random values from 0 to 25. Finding and printing smallest, biggest and middle value number.

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

- Creating 3 `variables` which are random values from 0 to 10. These `variables` are assigned as a triangle sides.
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
- Creating 4 `variables` and assigning random values from 0 to 2. Code below counts how many 0, 1s and 2s were generated.
Although such result can be reached using an `array`, i decided to do it without it, visiting and analyzing `arrays` at a later date.

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

- Assigning actor names to `variables` as a `string`. Printing the shorter `string`

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

- Using the same assigned actor name/surname as `strings`, assigning a `variable` as a combination of last 3 letters for name and surname.
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

- Replacing defined symbols in a `string`, lowercase and uppercase combined.

```PYTHON
str1 = "An American in Paris"
print(str1.replace("A", "*").replace("a", "*"))
```

- Assigning a `string` to a variable, checking if there is numbers in the `string`. Using `isdigit` for the easy solution.

```PYTHON
text = "I'm 24 years old"
result = any(char.isdigit() for char in text)
if result == True:
    print("Yes")
else:
    print("No")
```

___
## Exploring `FOR` Loops, `LISTS` and `ARRAYS`

- Simple `FOR` loop printing same `STR` defined amount of times. Listing numbers from 0 to 10 (with `list` and without)
- 
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

> WORK IN PROGRESS...
