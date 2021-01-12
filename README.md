# Python_Tips_And_Tricks
Quick Guide to Useful Python Items

## Example Sandbox Colab 
https://colab.research.google.com/drive/1t5oDF2qXfEYqmc2ssvep01Wa-1yOldHP?usp=sharing 

## Runtime Comparison: Compare Two Solutions
https://colab.research.google.com/drive/1jvkSq9Bsh83X4amgHLN6CJj5vtlhSbNO#scrollTo=54qBU7WHI2zU

## Pipenv & IDE Configuration Guide
linux pipenv, linter, formatter, vsCode, atom, vim, jupyter notebook, configuration & setup
https://docs.google.com/document/d/1dZJI20D7uIknT1pdlTSmlHH1WPYdVhs2PSUyH1qdnUo/edit 

## Recommended General Python Courses
- https://www.udemy.com/course/python-for-data-science-and-machine-learning-bootcamp/ 
- https://www.udemy.com/course/ultimate-python-tutorial/ Derek Banas


## Debugger: vsCode

#### vsCode Debugger in Python, 4-Lesson-Course:
https://www.youtube.com/watch?v=KEdq7gC_RTA&list=PLQzZ4krxwT9Yay3kz8ly4wXiYJHzMtsWi

#### Content Map Skills for Debugging:
- breakpoints
- traversing
- "current scope"
- step into vs. step out
- call stack
- variables: local vs. global
- the debugger-console
- inspecting 'state'

#so more head displays
#override display option
pd.set_option('display.max_rows', 500)
pd.set_option('display.max_columns', 500)
pd.set_option('display.width', 1000)


## enumerate: cleanly separate and use both indices and list-items
```
# list / array
input_list = [1,2,3]
 
for index,item in enumerate(input_list):
   print(index,item)
 
# dictionary (just keys)
input_dict = {1:"a", 2:"b", 3:"c"}
 
for index, key in enumerate(input_dict):
   print(index, key)
 
# dictionary (keys and values!)
input_dict = {1:"a", 2:"b", 3:"c"}
 
for index, (key, value) in enumerate(input_dict.items()):
   print(index, key, value)
```

## collections counter (dictionary of item counts)
```
import collections
from collections import Counter
 
# 4 'a's & 2 'b's
input_list = ['a', 'a', 'a', 'a', 'b', 'b']
 
counter_dict = collections.Counter(input_list)
 
print(counter_dict)
 
print(type(counter_dict))
 
print(counter_dict['a'])
 
print('a' in counter_dict)
https://colab.research.google.com/drive/1jvkSq9Bsh83X4amgHLN6CJj5vtlhSbNO#scrollTo=54qBU7WHI2zU

```

## sort vs. sorted (in place, reverse order)

#### item.sort() vs. sorted(item)
#### sort --> in place
#### sorted --> not 'in place'
#### sorted --> has reverse-order feature
```
# sorted(item)
numbers = [1, 3, 5, 9, 0]
 
print(numbers)
 
print(sorted(numbers))
 
print(numbers)
```
 
```
# item.sort
 
numbers = [1, 3, 5, 9, 0]
 
print(numbers)
 
print(numbers.sort())
 
print(numbers)
 
```
 
```
# reverse order
# reverse sorted(item)
numbers = [1, 3, 5, 9, 0]
 
print(numbers)
 
print(sorted(numbers, reverse = True))
 
print(numbers)
 
```
 
 
## Large .csv with non-utf8 encoding
 
```
import pandas as pd
df = pd.read_csv("FY2018_archived_opportunities.csv", encoding = "ISO-8859-1")
```


## ~ The tilde operator
~ for 0 count offset index
~x
-X 
-1

one thing - ()
set - {}
list - []


## zip:
#### iterates over two list


## list to string
''.join(["a","b"])




# Check (For) Remainder & Check (For) Integer

```
# set a value
check_this = 5
 
# Boolean return for checking divisibility
not check_this % 2

# look at the outcome of a computation
check_this = 5/2
 
# Boolean return for checking if result is an integer
check_this.is_integer()
```

	

## all()
## Check everything in a list

#### boolean_result = all(element > 3 for element in test_list)
```
test_list = [1, 3, 5, 9, 0]
 
boolean_result = all(element > 3 for element in test_list)
boolean_result
```

```
test_list = [1, 3, 5, 9, 0]
 
# check if items are less than 10
boolean_result = all(element < 10 for element in test_list)
boolean_result
```

```
test_list = ["a", "b", "c"]
 
# check if all items are strings
boolean_result = all(type(element) == str for element in test_list)
boolean_result

```

Term Note: Ternary operation: "In computer science, a ternary operator is an operator that takes three arguments."

## if-else ternary:

```
apple = "red"
red_fruit = True if apple == "red" else False
 
# inspection
print(red_fruit)
```


## to get file extension:
use filename.split('.')[-1] to split on the period separating the extension and filename and select the extension


## glob:
#### glob is an optimized, built-in, unix related, pattern matcher for file names
#### glob can use regeX-like wildcard searches: *, ?, [ranges]
 
https://www.geeksforgeeks.org/how-to-use-glob-function-to-find-files-recursively-in-python/ 
 
```
# find and print name of .txt files in the Current Working Directory
import glob
 
print(glob.glob("*.txt")
 
```




...

# slice reversing
#### return the reverse order of a list
list1[::-1]


try-except block
