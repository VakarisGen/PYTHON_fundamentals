# PYTHON_Fundamentals
A guide and summary of my practice with PYTHON Fundamentals 

I best learn by practice and repetition thus i though, why not document it.
Below you will find a number of exercises regarding PYTHON fundamentals, basic code building and syntax
All the practice tasks were done using PyCharm IDE

_________

## Exploring `VARIABLES` and `IF` statements

- Saving name, last name, Date of Birth as well as current year as Var. Writing a short code that can `print` name and surname, calculate current age based on input.  
```Python
name = "Vakaris"
surname = "Genutis"
dob = 1996
currdate = 2026

print(f"My name is {name} {surname}. I'm {currdate - dob} years old")
```  
- Creating two variables with random values from 0 to 4, dividing the larger by the smaller and print the result rounded to 2 decimal places.  
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
- Creating 3 variables with random values from 0 to 25. Finding and printing smallest, biggest and middle value number.

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
> WORK IN PROGRESS...
