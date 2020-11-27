# Python_Tips_And_Tricks
Quick Guide to Useful Python Items

## Example Sandbox Colab 
https://colab.research.google.com/drive/1t5oDF2qXfEYqmc2ssvep01Wa-1yOldHP?usp=sharing 


## Pipenv & IDE Configuration Guide
linux pipenv, linter, formatter, vsCode, atom, vim, jupyter notebook, configuration & setup
https://docs.google.com/document/d/1dZJI20D7uIknT1pdlTSmlHH1WPYdVhs2PSUyH1qdnUo/edit 

## Nifty General Python Courses
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
from collections import counter

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


## check for remainder:
number_variable.is_integer() == False
	

## all()
# Runs on everything in a list
boolean_result = all(element > 3 for element in test_list)


## sort vs. sorted (in place, reverse order)

## to get file extension:
use filename.split('.')[-1] to split on the period separating the extension and filename and select the extension

## select all files of one type:
you can use import glob and glob.glob(*.rds) to select all rds files from a dir (instead of listdir which is all files)


