# Python_Tips_And_Tricks
Quick Guide to Useful Python Items

###:
Python can be in some ways combined with R and with C:
- https://github.com/lineality/run_R_in_Python
- 


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


for index, list_item in enumerate(input_list):
   print(index,list_item)


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
# Not Mod

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
   # write file content
   file_object.write("write to file\n")


# read it
with open('sample.txt', "r") as file_object:
   # read file content
   data = file_object.read()
   # print file contents
   print(data)


# add to it (append)
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
# This sets the default number of decimals to 2
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
```
# Convert a datetime.date object to a datetime.datetime object
from datetime import date, datetime


just_a_date = date.today()


# inspection
print(just_a_date)


converted_to_datetime = datetime.combine( just_a_date, datetime.min.time())
# inspection
print(converted_to_datetime)
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

## sample Readable-date-string
```
from datetime import datetime
date_time = datetime.utcnow()
date_time.strftime('%Y_%m_%d_%H_%M_%S')
```


```
from datetime import datetime


# get time
Sample_Time = datetime.utcnow()


# make readable string
readable_string = Sample_Time.strftime('%Y-%m-%d %H:%M:%S')


print('type: ', type(readable_string))
print(readable_string)
```

## or
```
import datetime, calendar, time
from datetime import date, datetime


# get time
Sample_Time = datetime.utcnow()


# make readable string
readable_string = Sample_Time.strftime('%Y-%m')


print('type: ', type(readable_string))
print(readable_string)

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


## Deal with Standard "Unicode Error"
```
import pandas as pd
df = pd.read_csv("YOUR_FILE_NAME_HERE.csv", encoding = "ISO-8859-1" )
```


## Formatting: Decimals
http://cis.bentley.edu/sandbox/wp-content/uploads/Documentation-on-f-strings.pdf
'''
x = 4.5 print(f'This will print out the variable x: {x:.3f}') 
'''


## Transform Pandas: Carry out a function on each item in a pandas dataframe column
```
# e.g. feature engineer a new column which is the length of a string in another column
# https://towardsdatascience.com/when-to-use-pandas-transform-function-df8861aa0dcf

# Step 1: Make a Function
def name_len(name):
    return len(name)

# Step 2: df.transform(name_of_function)
df["name_len"] = df["Contractors"].transform(name_len)
```

## Unspecified number of multiple function inputs: "Variable Argument Lists"
```
## Unspecified number of multiple function inputs: "Variable Argument Lists"

def add_these(*input_numbers_to_add):

        total_for_output = 0

        for this_number in input_numbers_to_add:
            total_for_output += this_number

        return total_for_output

# Run Program
add_these(2,3,4)

```


## Unzip in Python
```
import zipfile

# # Extract whole zip file to your current working directory: 
with zipfile.ZipFile("TARGET_FILE_NAME.zip","r") as zf:
    zf.extractall()
```


## Iter-items: example: use pandas iteritems to iterate through a df column to feature-engineer values in a new column from two dataframes to transform zipcodes into geocodes:


```

!wget https://gist.githubusercontent.com/erichurst/7882666/raw/5bdc46db47d9515269ab12ed6fb2850377fd869e/US%2520Zip%2520Codes%2520from%25202013%2520Government%2520Data

zip_df = pd.read_csv("US Zip Codes from 2013 Government Data")


# make new columns
df["geo_lat"] = 0.0
df["geo_long"] = 0.0


# test where your data are going
index = 1
# geolat
print(df.iloc[index, 29])
# geolong
print(df.iloc[index, 30])



# script for making geocodes for zipcodes from list
for index, value in df["zip_code"].iteritems():


   if (value in zip_df["ZIP"].values) != False:


       # geolat
       df.iloc[index, 29] = zip_df[zip_df["ZIP"] == value]["LAT"].values[0]


       # geolong
       df.iloc[index, 30] = zip_df[zip_df["ZIP"] == value]["LNG"].values[0]


   #else: print("0")


print("Done!")


```

## Google Colab auto make and auto download a timestamp-named .csv file

```

# # make and download a time-stamped saved copy of .csv


import datetime, calendar, time
from datetime import date, datetime
from google.colab import files


# get time (stamp)
Sample_Time = datetime.utcnow()


# make timestamp text (string)
timestamp_string = str( Sample_Time.strftime('v_%Y_%m_%d__%H%M_%S') )


# make file name
file_name = f'save_csv_{timestamp_string}.csv'


# make .csv from your dataframe (df)
df.to_csv( file_name, index = True )


# download .csv
files.download( file_name )


```



## JSON and nested-Dictionary string search in python:
If you have a nested dictionary as a string (e.g. from an AWS result), you can dig into that nested dictionary BUT you may need to convert that string into a json object first.

```
import json
dict_string = """{"body":{"item":12}, "key":3}"""


dict1 = json.loads(dict_string)
dict1["body"]["item"]

```


## Regex in Python: Regular Expressions
Here is a real example where you will need to extract data that you want.
This is a bit of a cludge using a combination of string 'slicing'[#:#] with Regex.

```
import re


# object from AWS directory query
text = "s3.ObjectSummary(bucket_name='YOUR_BUCKET_NAME', key='YOUR_FOLDER_NAME/YOUR_FILE_NAME.csv')"


# after this
after_this = 'key='


# get item after your choice of characters:
pattern = f'(?<={after_this}).*$'
# use regex
target = re.findall(pattern,text)


# strip out extra characters
target = str(target[0][1:-2])
# inspection of results
print(target)


```



# Sum List of Numbers

```
total = sum(item for item in NAME_OF_YOUR_LIST)
```


# Create a Row-Number Column (as the first column)
```
import pandas as pd
import numpy as np

# Create a new row containing row numbers:
df['Row_Number'] = np.arange(df.shape[0]) + 1

# Select new row to be moved to the front (made the first column)
new_first_column = df.pop('Row_Number')
  
# Move new row to the front (make it the first column)
df.insert(0, 'Row_Number', new_first_column)
```






```
# function to turn a string into a list for pandas


def string_to_list(string_input):


   # print( type( string_input ) )
   # print("1", string_input  )


   string_input = string_input.replace("[", "")
   # print("2", string_input  )


   string_input = string_input.replace("]", "")
   # print("3", string_input  )


   string_input = string_input.replace('"', "")
   # print("4", string_input  )


   string_input = string_input.replace("'", "")
   # print("5", string_input  )


   string_input = list(string_input.split(','))
   # print("6",  string_input  )


   return string_input


# Testing The Function
string_input1 = '["1","2","3"]'
print( type( string_input1) )


string_input2 = '["Abc","bbb","ccc"]'
print( type( string_input2) )


print( string_to_list(string_input1) )
print( type( string_to_list(string_input1) ) )


print( string_to_list(string_input2) )
print( type( string_to_list(string_input2) ) )

```





# Script to make a dictionary/display of column iloc index values

```
########################################################
# Make and Print Dictionary of Column Names and Indices
########################################################

import pandas as pd

df = pd.read_csv("xyz.csv")

# make a dictionary to store the values
index_dict = {}

# iterate through each item in the list of df columns
for index, item in enumerate(df.columns):
    # # inspection
    # print( index, item )

    # add index as the key, and item as the value in the dictionary
    index_dict[index] = item

#print( index_dict )
index_dict
```


# To then drop a list of rows by index number:

```
# # Example List
# list_of_indices_to_drop = [26,25,24,23,22,21,20,17,16,14,12,11,10,9,7,6,5,4,3,2]


for i in list_of_indices_to_drop:
   this_column = index_dict[i]


   df = df.drop([this_column], axis = 1)


# # inspection
# df.head(1)   

```

# infer data types of columns:
```
for column in df.columns:
   print(pd.api.types.infer_dtype(df[column]))
```

# infer data types of columns:

```
def sort_dict_by_values(input_dict):
  
   output = dict( sorted( input_dict.items(),key= lambda x:x[1] ) )


   return output


# Test it!
this_dic = {4:70, 6: 550, 8: 5, 5: 64, 2: 3}
print(sort_dict_by_values(this_dic))


```


# slice dictionary keys (e.g. get a list of the top 5 items)
```
def get_top_five_keys(this_dict):


   return list(dict.keys(this_dict))[:5]


# Test it
this_dic = {4:70, 6: 550, 8: 5, 5: 64, 2: 3}
print( get_top_five_keys(this_dic) )



```


# turn list-as-string into a list
```
################
# Format .......
################
# TODO: fix this
raw_string_list = raw_string_list.split(',')


new_list = []


for i in raw_string_list:
   new_list.append( int(i) )


# inspection
print(type(new_list), new_list)
```

# Get Random Item From List
```
import random


list_of_items = [1,2,3]


random_item_01 = random.choice(list_of_items)


print (random_item_01)
```

# Expand Pandas Display for Long Text etc
```
# show more df.head() displays
# override display size defaults
pd.set_option('display.max_rows', 500)
pd.set_option('display.max_columns', 500)
pd.set_option('display.width', 1000)
# show long strings inside cells
pd.options.display.max_colwidth = 500
```


# append the name of the directory to each file name
(no python installs needed, just vanilla imports)

```
"""
Code to rename all files in a directory
with the name of the directory appended 
to the file name
with a period between:

e.g.
folder_name.original_name.suffix

e.g.
whalepics.231.jpg
"""

# import your vanilla libraries (no pip installs needed)
import os 
import glob

# get the folder name (whole current working directory path)
full_path = os.getcwd()

"""
reduce full name to just the name of this directory
split the name on "/" and slice off just the last name [-1]
"""
this_directory = full_path.split("/")[-1]

"""
iterate through a list of folder contents obtained with glob
'*' is a wildcard to get all files, but you can substitute
in a specific suffix for a file type
e.g. glob.glob('*.jpg')
"""
for this_file_name in glob.glob('*.*'):

    # optional print old name
    print("old = ", this_file_name)
    
    # make the new name string	
    new_name = this_directory + "." + this_file_name 
    
    # change old name to new neame
    os.rename(this_file_name, new_name)
    
    # optional print the new name
    print("new = ", new_name, "\n")

```


# make df row values are row numbers, unique row primary key
```
# helper function
def make_new_primary_key_first_column(df):


   # Create a new row containing row numbers:
   df['Row_Number'] = np.arange(df.shape[0]) + 1


   # Select new row to be moved to the front (made the first column)
   new_first_column = df.pop('Row_Number')
    
   # Move new row to the front (make it the first column)
   df.insert(0, 'Row_Number', new_first_column)


   return df
```


# generate random names
```
# create the dict and save it to a file
def make_random_name_string():


   import random


   random_name_part_1 = [
       'texas_',
       'new_york_',
       'washington_',
       'LAX_',
       'D.C._',
       'london_'
   ]
   random_name_part_2 = [
       'lunar_',
       'smart_',
       'carbon_free_',
       'ESG_',
       'self_driving_'
       ]
   random_name_part_3 = [
       'city',
       'base',
       'event_center',
       'platform',
   ]


   super_name = f"{random.choice(random_name_part_1)}{random.choice(random_name_part_2)}{random.choice(random_name_part_3)}"
    return super_name


make_random_name_string()

```

# Item Count in Pandas (via make new df)

```
"""
item count -> Totals by type:
Sometime you will have a dataframe where each row is some item,
but you need a dataset where each category is a row with totals as columns
in that category.


Here is working code to do that (on the fly) in python.


Create a new dataframe in which the rows are states
and there is a column for total values.


e.g. total number of EV charging stations per state


"""


import pandas as pd


# open original df
df = pd.read_csv("NAME.csv")


# make a list_of_catagorical_items
list_of_catagorical_items = df["XXX"].unique()


# create new blank df_item_counts
df_item_counts = pd.DataFrame()


# iterate through list_of_catagorical_items
for i in list_of_catagorical_items:
   # get name (initials) of catagorical_item
   count_by_this = i


   # get number of items in the column
   # conditions will vary case by case...
   count_of_items = df[ (df["XXX"] == count_by_this) & (df["XXX Code"] == "XXX") ].shape[0]


   # make new row
   df_item_counts = df_item_counts.append({'XXX':i}, ignore_index=True)


   # update/ change row label to be the same a certain
   df.loc[len(df)] = df_item_counts["XXX"]


   # save those data
   df_item_counts.loc[count_by_this, "count"] = count_of_items




# save csv
df_item_counts.to_csv('NAME.csv', index=False)


# print header)
print( df_item_counts.head(5) )

```


# get just python version 

```
import platform


# Retrieve Python version
python_version = platform.python_version()
python_version = python_version[:4]

```

# manual error traceback

```
import sys
import traceback


try:
	print("hello whirld")


except Exception as e:
e = str(e)


# get manual traceback, not relying on other forms of traceback that may fail:
e_type, e_value, e_traceback = sys.exc_info()
traceback_message = traceback.format_exception(e_type, e_value, e_traceback)
traceback_message = "".join(traceback_message)


message = f"ERROR during pip install: {e} + {traceback_message}"
print( message )
return message

```


# remove one list from another
```
from_this = [8, 2, 4, 3]
remove_this = [2, 4]
clean_list = []


def remove_this_list_from_this_list(remove_this, from_this):
    try:
        clean_list = []
        for i in from_this:
            if i in remove_this:
                pass
            else:
                clean_list.append(i)
        print("list cleaned ok!")
        return clean_list
    except Exception as e:
        message = """remove_this_list_from_this_list(), 
        error, nothing done, 
        original list returned"""
        
        print(message, str(e))
        return from_this


clean_list = remove_this_list_from_this_list(remove_this, from_this)
clean_list
```
