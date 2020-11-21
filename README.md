# Python_Tips_-_Tricks
Quick Guide to Useful Python Items




## debugger: vsCode

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
input_list = [1,2,3]
for index,item in enumerate(input_list):
  print(index,item)
```

counter dictionary

from collections import counter
	

~


one thing - ()
set - {}
list - []

zip:
iterates over two list

~x
-X 

-1

~ for 0 count offset index

list to string
''.join(["a","b"])

check for remainder:
number_variable.is_integer() == False
	
all()
# Runs on everything in a list
boolean_result = all(element > 3 for element in test_list)
