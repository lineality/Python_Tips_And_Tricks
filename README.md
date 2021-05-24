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

# ~Unix Terminal 
#### print text file in terminal
```
$ cat file_name
```

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
 
## Slicing with intervals (and reversing)

In addition to from and to, you can also slice at an interval
e.g. from items 1-20, but only every 5th item.
AND
If you pick an interval of -1...it reverses your list. 
 
```
list1 = [1,2,3,4,5,6,7,8]
 
# whole list
print( list1 )
 
# from and to
print( list1[0:3] )
 
# add an interval!
print( list1[1:7:2] )
 
# reverses list
print( list1[::-1] )
 
 
 
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
 
print(glob.glob("*.txt"))
 
```




...

# slice reversing
#### return the reverse order of a list
list1[::-1]


try-except block


...

Zip

$zip myfile.zip filename.txt


# open a file with "with open"
To avoid issues with not-closing files, some say this is the default best practice for python

```
with open(file.txt', "r") as file_object:
# read file content
data = file_object.read()
# print file contents
print(data)

# using "with statement" with open() function
 
# make it
with open('sample.txt', "w") as file_object:
   # read file content
   file_object.write("write to file\n")
 
# read it
with open('sample.txt', "r") as file_object:
   # read file content
   data = file_object.read()
   # print file contents
   print(data)
 
# add to it
with open('sample.txt', "a") as file_object:
   # read file content
   file_object.write("write more to file\n")
 
# read it
with open('sample.txt', "r") as file_object:
   # read file content
   data = file_object.read()
   # print file contents
   print(data)
 
# Check if file is closed
if file_object.closed == False:
   print('File is not closed')
else:
   print('File is closed')
```

## Truncating and Rounding
Truncating and rounding to a given decimal place (without extra libraries etc.) can be oddly not straight forward considering how easy so many things are in vanilla python. Here is one function from: https://realpython.com/python-rounding/

```
def truncate(n, decimals=2):
   multiplier = 10 ** decimals
   return int(n * multiplier) / multiplier
```


## Decimal Type vs. Float Type
(e.g. for AWS)

```
from decimal import Decimal
 
def decimal_type_truncated(n, decimals=2):
  multiplier = 10 ** decimals
  return Decimal(n * multiplier) / multiplier

decimal_type_truncated(0.6, 2)

```

# Date Time & Posix Time!

https://colab.research.google.com/drive/1VHk7J2yU2s8zX7fO7VU7pZyfbogKxQlt#scrollTo=UbEzt--NLs-7

Datetime functions in Python make dealing with times and time ranges manageable. Here are some useful snippets for dealing with dates and time ranges.

```
# There and Back Again: Normal -> Posix -> Normal
 
import datetime, calendar, time
from datetime import date, datetime
 
year = 2021
month = 12
day = 14
 
Sample_Time = datetime(year,month,day)
 
print("Staring with Normal Time")
print(Sample_Time)
print(type(Sample_Time))
 
# Current Time UTC
 
date_time = datetime.utcnow()
print("\nCurrent Time UTC")
print(date_time)
print(type(date_time))
 
# Posix UTC Seconds
date_time = datetime.utcnow()
Posix_UTC = calendar.timegm(date_time.utctimetuple())
print("\nPosix UTC")
print(Posix_UTC)
print(type(Posix_UTC))
 
 
# Posix UTC miliseconds
date = datetime.utcnow()
unix_time_miliseconds = datetime.timestamp(date)*1000
print("\nPosix UTC miliseconds")
print(unix_time_miliseconds)
print(type(unix_time_miliseconds))
 
Time_Stamp = Posix_UTC
 
try:
   # if you encounter a "year is out of range" error
   # the timestamp may be in milliseconds, try
   # `Time_Stamp /= 1000` in that case
   date_time = datetime.utcfromtimestamp(Time_Stamp).strftime('%Y-%m-%d %H:%M:%S')
   print("\nCurrent Time UTC")
   print(date_time)
   print(type(date_time))
 
except:
   Time_Stamp /= 1000
   date_time = datetime.utcfromtimestamp(Time_Stamp).strftime('%Y-%m-%d %H:%M:%S')
   print("\nCurrent Time UTC")
   print(date_time)
   print(type(date_time))
 
Time_Stamp_Mili = unix_time_miliseconds
 
 
try:
   # if you encounter a "year is out of range" error
   # the timestamp may be in milliseconds, try
   # `Time_Stamp /= 1000` in that case
   date_time = datetime.utcfromtimestamp(Time_Stamp).strftime('%Y-%m-%d %H:%M:%S')
   print("\nCurrent Time UTC")
   print(date_time)
   print(type(date_time))
 
except:
   Time_Stamp_Mili /= 1000
   date_time = datetime.utcfromtimestamp(Time_Stamp).strftime('%Y-%m-%d %H:%M:%S')
   print("\nCurrent Time UTC")
   print(date_time)
   print(type(date_time))

```

## Recreate a pipenv from a pipenv-lock file

```
pipenv install restore
```


## Merge a List of Lists into a One List


```
list_of_lists = [[9, 2, 9, 4], [5, 9, 7], [8, 9]]
merged_list = [i for sublist in list_of_lists for i in sublist]
merged_list

```
