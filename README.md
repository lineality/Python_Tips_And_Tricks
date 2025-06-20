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




# Get list of all text files in the directory
list_of_files = glob.glob(os.path.join(dir_path, "*.txt"))


```

# glob file list in cwd
```python
# # for directory at path
# list_of_files = glob.glob(os.path.join(dir_path, "*.csv"))

list_of_files = glob("*.csv")
print(list_of_files)


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


# Readable Timestamp
# timer
```python




from datetime import datetime, UTC as datetime_UTC


# get time
sample_time = datetime.now(datetime_UTC)
# make readable string
readable_timesatamp = sample_time.strftime('%Y_%m_%d__%H_%M_%S%f')
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
# from datetime import datetime, UTC
date_time = datetime.now(UTC)


print("\nCurrent Time UTC")
print(date_time)
print(type(date_time))


# Posix UTC Seconds
# make readable time
# from datetime import datetime, UTC
date_time = datetime.now(UTC)
clean_timestamp = date_time.strftime('%Y%m%d%H%M%S%f')


Posix_UTC = calendar.timegm(date_time.utctimetuple())
print("\nPosix UTC")
print(Posix_UTC)
print(type(Posix_UTC))




# Posix UTC miliseconds
from datetime import datetime, UTC
date = datetime.now(UTC)
unix_time_miliseconds = datetime.timestamp(date)*1000
print("\nPosix UTC miliseconds")
print(unix_time_miliseconds)
print(type(unix_time_miliseconds))


Time_Stamp_Mili = unix_time_miliseconds


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
# from datetime import datetime, UTC
date_time = datetime.now(UTC)


date_time.strftime('%Y_%m_%d_%H_%M_%S')
```
## sample Readable-date-string 2
```
# from datetime import datetime, UTC
date_time = datetime.now(UTC)
clean_timestamp = date_time.strftime('%Y%m%d%H%M%S%f')
timestamp = date_time.strftime('%Y_%m_%d_%H_%M_%S_%f')

```

```
from datetime import datetime, UTC


# get time
from datetime import datetime, UTC
Sample_Time = datetime.now(UTC)




# make readable string
readable_string = Sample_Time.strftime('%Y-%m-%d %H:%M:%S')


print('type: ', type(readable_string))
print(readable_string)
```

## or
```
import datetime, calendar, time
from datetime import date, datetime, UTC


# get time
# from datetime import datetime, UTC
date_time = datetime.now(UTC)




# make readable string
readable_string = Sample_Time.strftime('%Y-%m')


print('type: ', type(readable_string))
print(readable_string)

```

# timestamp for file names readable
```python
# from datetime import datetime, UTC
date_time = datetime.now(UTC)
clean_timestamp = date_time.strftime('%Y%m%d%H%M%S%f')

timestamp = date_time.strftime('%Y_%m_%d__%Hh_%Mm_%Ss__%ffs')
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
# from datetime import datetime, UTC
date_time = datetime.now(UTC)
clean_timestamp = date_time.strftime('%Y%m%d%H%M%S%f')






# get time (stamp)
Sample_Time = datetime.now(UTC)


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


- function version:
```
import sys
import traceback




def get_traceback_info(input_exception):
   """Get formatted traceback information for the current exception."""




   traceback_message = ""
   final_output_message = ""


   e_type, e_value, e_traceback = sys.exc_info()
   traceback_message = traceback.format_exception(
       e_type,
       e_value,
       e_traceback,
   )
  
   traceback_message = "".join(traceback_message)


   final_output_message = f"""
   Exception in test_traceback():
   Error     -> {str(input_exception)}
   Traceback -> {traceback_message}
   """
   print(final_output_message)


   return final_output_message




def test_traceback():
   try:
       # make the oopsy
       a = 1/0
       return "hello whirld"
  
   except Exception as e:
       traceback_message = get_traceback_info(e)
       # print(traceback_message)
       return traceback_message




test_traceback()

```


- not in function version
```
import sys
import traceback




def test_traceback():
  try:
    
      # make the oopsy
      a = 1/0




      return "hello whirld"








  except Exception as e:




       # get manual traceback,
       # not relying on other forms of traceback that may fail:
       e_type, e_value, e_traceback = sys.exc_info()
       traceback_message = traceback.format_exception(
          e_type,
          e_value,
          e_traceback,
       )
       traceback_message = "".join(traceback_message)
       message = f"""
       Exception in test_traceback():
       Error     -> {str(e)}
       Traceback -> {traceback_message}
       """
       print( message )


       return message




test_traceback()

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





# remove indent-caused spaces from mutli-line python string
```
def remove_indentation(text):
    # Split the text into lines
    lines = text.split('\n')

    # Find the minimum number of leading spaces in non-empty lines
    min_indentation = float('inf')
    for line in lines:
        if line.strip():  # Check if the line is not empty after stripping
            leading_spaces = len(line) - len(line.lstrip())
            min_indentation = min(min_indentation, leading_spaces)

    # Remove the minimum number of spaces from the beginning of each line
    adjusted_lines = [line[min_indentation:] for line in lines]

    # Join the adjusted lines back into a single string
    adjusted_text = '\n'.join(adjusted_lines)

    return adjusted_text

```

# A cli one-liner to inspect a csv file row
```
python -c "import csv; print(repr([row for i, row in enumerate(csv.reader(open('YOUR_FILE_NAME'.csv', 'r'))) if i == 76][0]))"
```



# check for non-ascii characters
```
# helper function to detect non-ascii characters
def detect_non_ascii(input_str):
    """
    Detects and reports the positions of non-ASCII characters in a string.

    Args:
        input_str (str): The string to be checked for non-ASCII characters.

    Returns:
        list: A list of tuples containing the index and the character that is non-ASCII.
    """
    non_ascii_list = []

    # Iterate through the input string to find non-ASCII characters
    for idx, char in enumerate(input_str):
        # ASCII characters have a code point between 0 and 127
        if ord(char) > 127:
            non_ascii_list.append((idx, char))


    # plain English
    if not non_ascii_list:
        print(f"OK! characters are all ascii-compatible: {non_ascii_list}")
    else:
        print(f'WARNING, contains these non-ascii characters: {non_ascii_list}')

    return non_ascii_list

# Sample input string

sample_str = """

"""

# RUN CODE: Detect non-ASCII characters
result = detect_non_ascii(sample_str)

result
```

# removing letters and numbers from a string
```python


import string


def strip_non_alphanumerics(text):
   """
   Strip all non-alphanumeric characters from a string.


   Args:
     text: The string to strip.


   Returns:
     The stripped string.
   """


   # Create a translation table that maps all non-alphanumeric characters to None.
   translation_table = str.maketrans('', '', string.punctuation + string.whitespace)


   # Use the translation table to strip the non-alphanumeric characters from the string.
   stripped_text = text.translate(translation_table)


   return stripped_text




text = "Hello, world!"
stripped_text = strip_non_alphanumerics(text)
print(stripped_text)  # Output: "Hello world"


import re


def strip_non_alphanumerics_regex(text):
   """
   Strip all non-alphanumeric characters from a string using regular expression.


   Args:
     text: The string to strip.


   Returns:
     The stripped string.
   """


   pattern = re.compile("[^a-zA-Z0-9]")
   stripped_text = pattern.sub('', text)
   return stripped_text






```


# check and make folder name
```python
# Check if the directory already exists, if not: make it
if not os.path.exists(path):
    # Create the directory
    os.makedirs(path)
    print(f"Directory '{spath}' created successfully!")
else:
    print(f"Directory '{path}' already exists.")

```


# Traceback in try except

```python
import traceback


def SAMPE_DUMMY_FUNCTION(x, y):
   # makes error by divide by zero
   try:
       result = x / y
       return result
   except Exception as e:
       # Print the traceback
       traceback_message = f"""
       Traceback for Error:
       Exception as e: {str(e)}
       Traceback_message: {traceback.format_exc()}
       """
       # # return traceback_message
       # # display formats may vary, alternate versions
       # return traceback_message
       return "Error/Exception Traceback Data: e, traceback -> ", e, traceback.format_exc()




print( SAMPE_DUMMY_FUNCTION(1,0) )

```


# timer
```python
import time
from datetime import datetime, timedelta




# helper function: start timer for python script
def start_timer():
   """
   requires:
       import time
       from datetime import datetime
   """
   # get time
   sample_time = datetime.utcnow()
   # make readable string
   readable_timesatamp = sample_time.strftime('%Y-%m-%d %H:%M:%S')


   # Calculate time in different time zones
   readable_timestamp_est = (sample_time - timedelta(hours=5)).strftime('%Y-%m-%d %H:%M:%S')
   readable_timestamp_edt = (sample_time - timedelta(hours=4)).strftime('%Y-%m-%d %H:%M:%S')


   readable_timestamp_mst = (sample_time - timedelta(hours=7)).strftime('%Y-%m-%d %H:%M:%S')
   readable_timestamp_mdt = (sample_time - timedelta(hours=6)).strftime('%Y-%m-%d %H:%M:%S')


   readable_timestamp_pst = (sample_time - timedelta(hours=8)).strftime('%Y-%m-%d %H:%M:%S')
   readable_timestamp_pdt = (sample_time - timedelta(hours=9)).strftime('%Y-%m-%d %H:%M:%S')


   time_message = f"""
   Starting Time:
       UTC {readable_timesatamp}


       EST {readable_timestamp_est}
       EDT {readable_timestamp_edt}


       MST {readable_timestamp_mst}
       MDT {readable_timestamp_mdt}


       PST {readable_timestamp_pst}
       PDT {readable_timestamp_pdt}


   """
   print(time_message)


   start_stamp = time.time()
   return start_stamp




# helper function: finish timer for python script
def end_timer(start_time):
   """
   requires:
       import time
       start_time = time.time()
   """
   # get time
   sample_time = datetime.utcnow()
   # make readable string
   readable_timesatamp = sample_time.strftime('%Y-%m-%d %H:%M:%S')


   # Calculate time in different time zones
   readable_timestamp_est = (sample_time - timedelta(hours=5)).strftime('%Y-%m-%d %H:%M:%S')
   readable_timestamp_edt = (sample_time - timedelta(hours=4)).strftime('%Y-%m-%d %H:%M:%S')


   readable_timestamp_mst = (sample_time - timedelta(hours=7)).strftime('%Y-%m-%d %H:%M:%S')
   readable_timestamp_mdt = (sample_time - timedelta(hours=6)).strftime('%Y-%m-%d %H:%M:%S')


   readable_timestamp_pst = (sample_time - timedelta(hours=8)).strftime('%Y-%m-%d %H:%M:%S')
   readable_timestamp_pdt = (sample_time - timedelta(hours=9)).strftime('%Y-%m-%d %H:%M:%S')


   time_message = f"""
   Finish Time:
       UTC {readable_timesatamp}


       EST {readable_timestamp_est}
       EDT {readable_timestamp_edt}


       MST {readable_timestamp_mst}
       MDT {readable_timestamp_mdt}


       PST {readable_timestamp_pst}
       PDT {readable_timestamp_pdt}
   """
   print(time_message)






   MARS_TO_EARTH = 1.02749125104


   # Record the end time
   end_time = time.time()
   # Calculate the elapsed time
   elapsed_time = end_time - start_time
   # Print the elapsed time in seconds




   count = elapsed_time
   total_mars_tenths = count * MARS_TO_EARTH
   total_mars_secs = total_mars_tenths // 10
   total_mars_mins = total_mars_secs // 60


   time_message = f"""
   Elapsed time:
       posix epoch time: {elapsed_time} seconds
       Earth Time Total: {count//600} min {count%600/10:.1f} sec, Mars Time Total: {total_mars_mins:.0f} min {total_mars_secs%60 + total_mars_tenths%10 / 10:.1f} sec


   """
   print(time_message)






# Timer: For Start of Script
start_the_timer = start_timer()


# ... Python script goes here...
time.sleep(2)  # This will pause the script for 5 seconds


# Timer: For End of Script
end_timer(start_the_timer)

```


# min sec duration 

```python[
from datetime import datetime

def duration_min_sec(start_time, end_time):


   duration = end_time - start_time


   duration_seconds = duration.total_seconds()


   minutes = int(duration_seconds // 60)
   seconds = duration_seconds % 60
   time_message = f"{minutes}_min__{seconds:.2f}_sec"


   return time_message


start_time_whole_single_task = datetime.now()
end_time_whole_single_task = datetime.now()


time_taken = duration_min_sec(start_time_whole_single_task, end_time_whole_single_task)
print(time_taken)


```



#  make sure directory exists, if not, make it

```python
    # Split the file path into directory and filename
    directory, filename = os.path.split(file_path)

    # Check if the directory exists, and create it if it doesn't
    if not os.path.exists(directory):
        os.makedirs(directory)
```


# Minimal Function Timer
```python
import time
from datetime import datetime, timedelta




# helper function: start timer for python script
def start_timer():
  """
  # do
  start_time = start_timer()


  requires:
      import time
      from datetime import datetime
  """
  # get time
  sample_time = datetime.utcnow()
  # make readable string
  readable_timesatamp = sample_time.strftime('%Y-%m-%d %H:%M:%S')


  time_message = f"""
  Starting Time:
      UTC {readable_timesatamp}
  """
  # print(time_message)




  start_stamp = time.time()
  return start_stamp




# helper function: finish timer for python script
def end_timer(start_time):
  """
  requires:
      import time
      start_time = time.time()
  """
  # get time
  sample_time = datetime.utcnow()
  # make readable string
  readable_timesatamp = sample_time.strftime('%Y-%m-%d %H:%M:%S')




  time_message = f"""
  Finish Time:
      UTC {readable_timesatamp}
  """
  print(time_message)


  MARS_TO_EARTH = 1.02749125104




  # Record the end time
  end_time = time.time()
  # Calculate the elapsed time
  elapsed_time = end_time - start_time
  # Print the elapsed time in seconds


  count = elapsed_time
  total_mars_tenths = count * MARS_TO_EARTH
  total_mars_secs = total_mars_tenths
  total_mars_mins = total_mars_secs // 60




  time_message = f"""
  Elapsed time:
      posix epoch time: {elapsed_time} seconds
      Earth Time Total: {count//600} min {count%600:.1f} sec, Mars Time Total: {total_mars_mins:.0f} min {total_mars_secs%60 + total_mars_tenths%10 / 10:.1f} sec




  """
  print(time_message)












# Timer: For Start of Script
start_the_timer = start_timer()




# ... Python script goes here...
time.sleep(2)  # This will pause the script for 5 seconds




# Timer: For End of Script
end_timer(start_the_timer)
```



# check if valid as object-id (bson)
```python
# helper function
def is_valid_object_id(input_string):
   """
   uses from bson import ObjectId
   """
   try:
       if ObjectId.is_valid(input_string):
           print(f"{input_string} is a valid ObjectId")
           return True
       else:
           print(f"{input_string} is not a valid ObjectId")
           return False
   except Exception as e:
       # inspection
       print(str(e))
       return False
```

# Remove fields from a dictionary
```python
# helper function
def remove_fields_from_dict_list(dict_list, field_list):
    """
    removes each of a list of keys
    from each of a list of dictionaries
    """
    try:
        for this_field in field_list:
            for this_dict in dict_list:
                if this_field in this_dict:
                    del this_dict[this_field]
        return dict_list
    except Exception as e:
        raise e

```




#####################
# Print & Log (prep)
#####################
def print_and_log(input_string):
   if DEBUG_PRINT is True:
       print(str(input_string))


       # log(input_string)




def check_if_user_in_organization(user_id_from_jwt, organization_id):
   """
   The user_organiziations collection has a key that is the user_id
   and organization_id values in an array of organization_id values.


   check if this user (based on jwt) has the stated organization_id in their list.
   """
   """Standard use:
               ################################
               # Check Organization Membership
               ################################
               # by default, the parent-owner of the role is the user
               # unless specified within a larger organization
               if (organization_id is None) or (str(organization_id) == str(user_id_from_jwt)):
                   print_and_log(f"organization_id is None -> {organization_id} {type(organization_id)}")
                   organization_id = user_id_from_jwt


               else:  # if there is an org id, check if the current user really has that:
                   memebership_status = check_if_user_in_organization(user_id_from_jwt, organization_id)
                   print_and_log(f"memebership_status = {memebership_status} {type(memebership_status)}")


                   if memebership_status is not True:
                       print_and_log(f"memebership_status is not True; memebership_status -> {memebership_status}")
                       message_text = {
                           'stdout': {
                               'message': "",
                           },


                           "stderr": {
                               "error_message": f"Failed: memebership_status",
                               "error_details": f"Failed: current user does not have membership in that organization (hiring)",
                           }
                       }
                       status_code = 500
                       return message_text, status_code
               ######################################
               # Check Organization Membership Block
               ######################################


   """
   try:


       # lookup target_user_id in lookup table, to get their array of organizations of which they are a member:
       current_organizations = mongo_db.get_all_values_if_key_found_or_none_from_db('hiring_accelerator', 'user_organizations', str(user_id_from_jwt))


       # if there are any:
       if current_organizations:
           """
           If there is data, see if organization_id is in the array
           which would indicate that this jwt-user is a member of that organization
           """


           print_and_log(f"check_if_user_in_organization() current_organizations {current_organizations} {type(current_organizations)}")
           print_and_log(f"current_organizations[0] {current_organizations[0]} {type(current_organizations[0])}")


           if str(organization_id) in current_organizations:
               print_and_log(f"{organization_id} found: Member OK!")
               # if in list
               return True


           else:
               print_and_log(f"NOT {organization_id} found: NOT member")
               # if not in list
               return False


       else:
           print_and_log("current_organizations is None")


           """
           If that user has no organization array, exit
           """
           return False


   except Exception as e:
       print_and_log(f"Exception failed dict_list_obj_to_string() {str(e)}")
       raise e




def dict_obj_to_string(this_dict):
   """
   requires from bson import ObjectId


   Converts ObjectId values in a dictionary to strings
   and manages lists.
   Converts ObjectId values in a dictionary to strings.
   """
   if not isinstance(this_dict, dict):
       raise Exception("input is not  a dictionary")


   try:
       if this_dict:
           for key, value in this_dict.items():
               if isinstance(value, dict):
                   this_dict[key] = dict_obj_to_string(value)
               elif isinstance(value, list):
                   for i, item in enumerate(value):
                       if isinstance(item, ObjectId):
                           value[i] = str(item)
               elif isinstance(value, ObjectId):
                   this_dict[key] = str(value)
           return this_dict
       else:
           print_and_log("dict_list_obj_to_string(), None entered as dict")
           return None
   except Exception as e:
       print_and_log(f"Exception failed dict_list_obj_to_string() {str(e)}")
       raise e




def enforce_value_is_list(input_dict):
   try:
       # Iterate over each key-value pair in the dictionary
       for key, value in input_dict.items():
           # Check if the value is not a list
           if not isinstance(value, list):
               # If the value is not a list, convert it into a list with a single element
               input_dict[key] = [value]
       # Return the modified dictionary
       return input_dict
   except Exception as e:
       print_and_log(f"Exception enforce_value_is_list() {str(e)}")
       raise e




# helper function
def read_after_tag(input_string, tag):
   """
   read document/string until the specified tag
   then return the text up to but not after that tag
   """
   try:
       get_this_string = ''
       tag_found_flag = False


       # iterate through list of lines in string
       list_of_lines = input_string.split('\n')
       for this_line in list_of_lines:


           if tag_found_flag:
               # add line to record: get_this_string
               get_this_string += this_line
               get_this_string += '\n'


           # get tag after storing it
           if tag in this_line:
               tag_found_flag = True


       return get_this_string
   except Exception as e:


       if DEBUG_PRINT:
           raise e


       print_and_log(f"Exception read_until_tag {str(e)}")
       return input_string




def check_keys(input_dictionary, required_keys):
   """
   return False by default if exception thrown
   """
   try:
       print_and_log(input_dictionary.keys())
       return set(input_dictionary.keys()) == set(required_keys)


   except Exception as e:
       e = str(e)
       return False




def merge_remove_duplicates_listdict(dict_of_lists, add_to_this_list, list_to_add):
   try:
       # Add the list to the dictionary's list
       dict_of_lists[add_to_this_list] += dict_of_lists[list_to_add]


       # Remove duplicates by converting the list to a set and then back to a list
       dict_of_lists[add_to_this_list] = list(set(dict_of_lists[add_to_this_list]))


       return dict_of_lists
   except Exception as e:
       raise e




def merge_dict_lists(d1, d2):
   """
   merges two versions of dictionary
   keeping all unique values
   but no duplicates
   """
   try:
       # Create a new dictionary to store the merged result
       new_d = {}


       # Iterate over the keys in the first dictionary
       for key in d1.keys():
           # If the key is also in the second dictionary
           if key in d2:
               # If the values are lists, remove duplicates and merge them
               if isinstance(d1[key], list) and isinstance(d2[key], list):
                   new_d[key] = list(set(d1[key] + d2[key]))
               # If the values are strings, keep them as is (no duplicates to remove)
               elif isinstance(d1[key], str) and isinstance(d2[key], str):
                   new_d[key] = d1[key]
               # If the values are of different types, raise an error
               else:
                   raise ValueError(f"Values for key '{key}' are of different types in the input dictionaries.")
           # If the key is only in the first dictionary, add it to the new dictionary
           else:
               new_d[key] = d1[key]


       # Iterate over the keys in the second dictionary
       for key in d2.keys():
           # If the key is not already in the new dictionary, add it
           if key not in new_d:
               new_d[key] = d2[key]


       # Return the merged dictionary
       return new_d
   except Exception as e:
       # If any error occurs, raise it
       raise e




# remove indent-caused spaces from mutli-line python string
def remove_indentation(text):
   try:
       # Split the text into lines
       lines = text.split('\n')


       # Find the minimum number of leading spaces in non-empty lines
       min_indentation = float('inf')
       for line in lines:
           if line.strip():  # Check if the line is not empty after stripping
               leading_spaces = len(line) - len(line.lstrip())
               min_indentation = min(min_indentation, leading_spaces)


       # Remove the minimum number of spaces from the beginning of each line
       adjusted_lines = [line[min_indentation:] for line in lines]


       # Join the adjusted lines back into a single string
       adjusted_text = '\n'.join(adjusted_lines)


       return adjusted_text


   except Exception as e:
       raise e




def try_jsonify_to_dict(input_text):
   import json
   try:
       # Remove the leading and trailing "```json\n" and "\n```"
       input_text = input_text.strip("```json\n")


       # Parse the JSON string into a Python dictionary
       dict_data = json.loads(input_text)


       # Convert the Python dictionary back into a JSON string
       json_string = json.dumps(dict_data)


       print_and_log(json_string)


       return dict_data


   except Exception as e:
       e = str(e)
       return None




# Helper function for cleaning
def convert_dict_to_lower(dictionary):
   """
   """
   try:
       return {k.lower(): [v.lower() for v in value] if isinstance(value, list) else value.lower() for k, value in dictionary.items()}
   except Exception as e:
       raise e




# Helper function for cleaning
def replace_apostrophe_s(dictionary):
   """
   This function takes a dictionary as input and returns a new dictionary
   where all keys and values have "'s" replaced with "s".
   If a value is a list, each item in the list has "'s" replaced with "s".
   If a value is None, it is left as None.
   """
   try:
       return {k.replace("'s", "s"): [v.replace("'s", "s") for v in value] if isinstance(value, list) else value.replace("'s", "s") if value is not None else None for k, value in dictionary.items()}
   except Exception as e:
       raise e




# Helper function
def extract_unique_field_values(dict_list, key):
   """
   Extract unique values for a specific key from a list of dictionaries.


   :param dict_list: List of dictionaries
   :param key: The key to extract values for
   :return: A list of unique values for the specified key
   """
   unique_values = set()


   for d in dict_list:
       value = d.get(key)
       if value is not None:
           unique_values.add(value)


   return list(unique_values)




# helper function
def remove_fields_from_dict_list(dict_list, field_list):
   """
   removes each of a list of keys
   from each of a list of dictionaries
   """
   try:
       for this_field in field_list:
           for this_dict in dict_list:
               if this_field in this_dict:
                   del this_dict[this_field]
       return dict_list
   except Exception as e:
       raise e





# import traceback

```python
import traceback
DEBUG_PRINT = True
def print_and_log(input_string):
    if DEBUG_PRINT is True:
        print(str(input_string))


try:

except Exception as e:
    print_and_log(f"EXCEPTION: {str(e)}")
    print_and_log(traceback.format_exc())  # This will print the stack trace
    raise e
```

# check for any 2nn status code: 200, 201 etc.
```python
# check for any 2nn status code
if status_code // 100 == 2:
    pass  # code here
```


# XOR OTP Encrypt or Decrypt
```python
import random
import string






def xor_otp_encrypt_decrypt(text, key=None, seed=None):
   """
   Encrypts or decrypts a given text
   using a one-time pad (OTP) with either a provided key or seed.


   Args:
   text (str): The input text to be encrypted or decrypted.


   key (str, optional): The key to be used for encryption or decryption.
                        Must be at least as long as the text.


   seed (int, optional): The seed to be used for random key generation.
                         If key is not provided, a key will be generated using this seed.


   Returns: three items:
   str: 1. The encrypted or decrypted text
        2. key
        3. exit code


   Raises:
   ValueError: If neither key nor seed is provided,
               or if the key is shorter than the text.
   """
   def generate_key(length, seed):
       """
       Generates a random key of a given length using a seed.


       Args:
       length (int): The length of the key to be generated.
       seed (int): The seed to be used for random number generation.


       Returns:
       str: The generated key.
       """
       random.seed(seed)
       key = ''.join(random.choice(string.ascii_letters) for i in range(length))
       return key




   # If key is not provided, generate a key using the seed
   if key is None:
       if seed is None:
           return "Failed: Either key or seed must be provided.", None, 1
       key = generate_key(len(text), seed)


   # Check if the key is long enough
   if len(key) < len(text):
       return "Failed: Key must be at least as long as the text.", None, 1


   # Convert text and key to ASCII values
   text_ascii = [ord(c) for c in text]
   key_ascii = [ord(c) for c in key]


   # Encrypt/Decrypt by XORing text and key
   encrypted_decrypted_ascii = [t ^ k for t, k in zip(text_ascii, key_ascii)]


   # Convert back to characters
   encrypted_decrypted_text = ''.join(chr(c) for c in encrypted_decrypted_ascii)


   return encrypted_decrypted_text, key, 0


# Example usage
text = "Hello, World!"
seed = 12345
key = "abcdefghijklmn!"


# # too short key test
# key = "1"


# key
encrypted_text, key, code = xor_otp_encrypt_decrypt(text, key=key)
print("Encrypted text:", encrypted_text)
print("Key:", key)
print("code:", code)


decrypted_text, key, code = xor_otp_encrypt_decrypt(encrypted_text, key=key)
print("Decrypted text:", decrypted_text)
print("Key:", key)
print("code:", code)


# seed
encrypted_text, key, code = xor_otp_encrypt_decrypt(text, seed=seed)
print("Encrypted text:", encrypted_text)
print("Key:", key)
print("code:", code)


decrypted_text, key, code = xor_otp_encrypt_decrypt(encrypted_text, seed=seed)
print("Decrypted text:", decrypted_text)
print("Key:", key)
print("code:", code)




```







# always ascii caesar_otp_encrypt or caesar_otp_decrypt
```python






def caesar_otp_encrypt(text, key=None, seed=None):
   """
   Encrypts a given text using a Caesar cipher
   with a one-time pad (OTP) generated from a key or seed.




   This implementation utilizes a Caesar cipher, where each character in the
   plaintext is shifted forward in the ASCII table by a value determined by
   the corresponding character in the key. The key is either provided directly
   or generated randomly using a seed.


   To guarantee that the encrypted output contains only printable ASCII
   characters (characters with ASCII codes between 32 and 126, inclusive),
   the following steps are taken:


   1. Both the plaintext character and the corresponding key character are
      converted to their ASCII ordinal values.
   2. The value 32 (representing the space character, the first printable
      ASCII character) is subtracted from both ordinal values.
   3. The adjusted ordinal values are added together, and the result is
      taken modulo 95 (the number of printable ASCII characters).
   4. The value 32 is added back to the result to bring it back into the
      printable ASCII range.
   5. The final value is converted back to a character and appended to the
      encrypted text.


   This process ensures that the encrypted text will always consist of
   printable ASCII characters, making it safe for display and transmission
   without concerns about control characters or non-printable characters.


   Args:
   text (str): The input text to be encrypted.
   key (str, optional): The key to be used for encryption.
                        Must be at least as long as the text.
   seed (str or int, optional): The seed to be used for random key generation.
                         If key is not provided, a key will be generated using this seed.


   Returns:
   tuple: (encrypted_text, key, exit_code)
          encrypted_text (str): The encrypted text.
          key (str): The key used for encryption.
          exit_code (int): 0 for success, 1 for failure.


   Raises:
   ValueError: If neither key nor seed is provided,
               or if the key is shorter than the text.
   """
   try:
       def generate_key(length, seed):
           """
           Generates a random key of a given length using a seed.


           Args:
           length (int): The length of the key to be generated.
           seed (int): The seed to be used for random number generation.


           Returns:
           str: The generated key.
           """
           random.seed(seed)
           key = ''.join(random.choice(string.printable) for i in range(length))
           return key


       if key is None:
           if seed is None:
               return "Failed: Either key or seed must be provided.", None, 1
           key = generate_key(len(text), seed)


       if len(key) < len(text):
           return "Failed: Key must be at least as long as the text.", None, 1


       encrypted_text = ""
       for i in range(len(text)):
           text_ord = ord(text[i])
           key_ord = ord(key[i])
           shifted_ord = 32 + (text_ord + key_ord - 32) % 95  # Ensure it stays within printable ASCII range (32-126)
           encrypted_text += chr(shifted_ord)


       return encrypted_text, key, 0


   except Exception as e:
       if DEBUG_PRINT:
           raise e
       return 'Exception', 'Exception', 1




def caesar_otp_decrypt(text, key=None, seed=None):
   """
   Decrypts a given text that was encrypted using the caesar_otp_encrypt function.




   This implementation utilizes a Caesar cipher, where each character in the
   plaintext is shifted forward in the ASCII table by a value determined by
   the corresponding character in the key. The key is either provided directly
   or generated randomly using a seed.


   To guarantee that the encrypted output contains only printable ASCII
   characters (characters with ASCII codes between 32 and 126, inclusive),
   the following steps are taken:


   1. Both the plaintext character and the corresponding key character are
      converted to their ASCII ordinal values.
   2. The value 32 (representing the space character, the first printable
      ASCII character) is subtracted from both ordinal values.
   3. The adjusted ordinal values are added together, and the result is
      taken modulo 95 (the number of printable ASCII characters).
   4. The value 32 is added back to the result to bring it back into the
      printable ASCII range.
   5. The final value is converted back to a character and appended to the
      encrypted text.


   This process ensures that the encrypted text will always consist of
   printable ASCII characters, making it safe for display and transmission
   without concerns about control characters or non-printable characters.


   Args:
   text (str): The encrypted text to be decrypted.
   key (str): The key that was used for encryption.


   Returns:
   tuple: (decrypted_text, exit_code)
          decrypted_text (str): The decrypted text.
          exit_code (int): 0 for success, 1 for failure.


   Raises:
   ValueError: If the key is shorter than the text.
   """
   try:
       def generate_key(length, seed):
           """
           Generates a random key of a given length using a seed.


           Args:
           length (int): The length of the key to be generated.
           seed (int): The seed to be used for random number generation.


           Returns:
           str: The generated key.
           """
           random.seed(seed)
           key = ''.join(random.choice(string.printable) for i in range(length))
           return key


       if key is None:
           if seed is None:
               return "Failed: Either key or seed must be provided.", None, 1
           key = generate_key(len(text), seed)


       if len(key) < len(text):
           return "Failed: Key must be at least as long as the text.", None, 1


       decrypted_text = ""
       for i in range(len(text)):
           text_ord = ord(text[i])
           key_ord = ord(key[i])
           shifted_ord = 32 + (text_ord - key_ord - 32) % 95  # Reverse the shift, staying within printable ASCII
           decrypted_text += chr(shifted_ord)


       return decrypted_text, key, 0


   except Exception as e:
       if DEBUG_PRINT:
           raise e
       return 'Exception', 'Exception', 1


# Example Usage
text = "Hello, World! This is a test with all printable ASCII characters!@#$%^&*()"
seed = "MySecretSeed"


# Encryption with seed
encrypted_text, key, code = caesar_otp_encrypt(text, seed=seed)
print("Encrypted text:", encrypted_text)
print("Key:", key)
print("Encryption exit code:", code)


# Decryption
decrypted_text, key, code  = caesar_otp_decrypt(encrypted_text, key=key)
print("Decrypted text:", decrypted_text)
print("Decryption exit code:", code)




```

# extract dict list from dirty json markdown string
```python
import json
import re


def extract_dict_list_from_dirty_json_md_str(text):
   """
   Extracts and parses valid JSON dictionaries from markdown-formatted text.
  
   Args:
       text (str): Input text containing markdown-formatted JSON
      
   Returns:
       list: List of parsed JSON dictionaries
  
   Returns Empty list by default, in case of errors.
   """


   try:
       # Find all content between ```json and ``` markers
       json_pattern = r'```json\s*(.*?)\s*```'
       json_matches = re.findall(json_pattern, text, re.DOTALL)
   except Exception as e:
       print(
           #extract_clean_json_dict_list_from_dirty_markdown_string",
           str(e),
       )
       # If parsing fails, skip this one and continue
       return []




   valid_jsons = []


  
   for json_str in json_matches:
       try:
           # Try to parse the JSON string
           json_obj = json.loads(json_str)
           # Only append if it's a dictionary
           if isinstance(json_obj, dict):
               valid_jsons.append(json_obj)
       except Exception as e:
           print(
               #extract_clean_json_dict_list_from_dirty_markdown_string",
               str(e),
           )
           # If parsing fails, skip this one and continue
           continue
          
   return valid_jsons


```



# timer
```python
# Function-Timer Functions

import time
from datetime import datetime

# helper function: start timer for python script
def start_timer():
   """
   # do
   start_time = start_timer()

   requires:
       import time
       from datetime import datetime
   """
   # get time
   sample_time = datetime.now()
   # make readable string
   readable_timesatamp = sample_time.strftime('%Y-%m-%d %H:%M:%S')

   time_message = f"""
   Starting Time:
       UTC {readable_timesatamp}
   """
   # debug_log(time_message)


   start_stamp = time.time()
   return start_stamp


# helper function: finish timer for python script
def end_timer(start_time):
    """
    requires:
       import time
       start_time = time.time()
    """
    # get time
    sample_time = datetime.now()
    # make readable string
    readable_timesatamp = sample_time.strftime('%Y-%m-%d %H:%M:%S')
    
    
    time_message = f"""
    Finish Time:
       UTC {readable_timesatamp}
    """
    debug_log(time_message)
    
    # Record the end time
    end_time = time.time()
    # Calculate the elapsed time
    elapsed_time = end_time - start_time
    # Print the elapsed time in seconds

    # Calculate hours, minutes, and seconds
    hours = int(elapsed_time // 3600)
    minutes = int((elapsed_time % 3600) // 60)
    seconds = elapsed_time % 60
    
    # Format the message
    time_message = f"""Elapsed time: total posix time: {elapsed_time} s -> {hours} hr : {minutes} min : {seconds:.6f} sec"""
        
    debug_log(time_message)
    # print(time_message)
    return time_message

#######
# Test
#######
# Timer: For Start of Section
start_the_timer = start_timer()

# ... Python script goes here...
time.sleep(2)  

# Timer: For End of Section
end_timer(start_the_timer)
```


# native python bash ls
```python
import os


def py_ls(directory="./"):
   """
   List files and directories in the specified directory.


   Args:
       directory (str): The directory to list files and directories from. Default is the current directory.


   Returns:
       list: A list of files and directories in the specified directory.
   """
   try:
       list_to_return = []


       # Print the current working directory
       this_cwd = os.getcwd()


       # add cwd to output
       list_to_return.append((this_cwd, "cwd"))


       print(f"Current working directory -> {this_cwd}")


       # Check if the specified directory exists
       if os.path.exists(directory):
           # Print the number of items in the directory
           print(f"Number of items -> {len(os.listdir(directory))}")


           # Iterate through the items in the directory
           for item in os.listdir(directory):
               item_path = os.path.join(directory, item)


               # Check if the item is a file or a directory
               if os.path.isfile(item_path):
                   list_to_return.append((item, "file"))
               elif os.path.isdir(item_path):
                   list_to_return.append((item, "directory"))




           for item in list_to_return:
               print(f"{item[0]} - {item[1]}")


           return list_to_return


       else:
           return f"Error: The specified directory '{directory}' does not exist."


   except Exception as e:
       return f"Error, failed: error message, e -> {str(e)}"


###########
# test use
###########
# Call the function and print the results
files_and_dirs = py_ls()
print(files_and_dirs)
print(type(files_and_dirs))


```











# simple config.ini (vanilla python)

### sample file format
```text
# config.ini file
[settings]
DEBUG_AND_PRINT_MODE = true
```

```python
import configparser  # standard library

###########################
# vanilla config file read
###########################
"""
use: import configparser  # standard library

# sample file format
'''config.ini file
# config.ini file
[settings]
DEBUG_AND_PRINT_MODE = true
'''
"""

# Specify the path to the config file
config_file_path = 'config.ini'

# Create ConfigParser object
config = configparser.ConfigParser()

# Read config file
config.read(config_file_path)

###########################################################
# Access values from loaded config.ini directly or by type
###########################################################
# Read String Directly (can convert later)
X_PATH = config['settings']['X_PATH']

# .get(): Retrieves a string value.
string_value = config.get('settings', 'option', fallback='default_value')

# .getboolean(): Retrieves a boolean value.
boolean_value = config.getboolean('settings', 'option', fallback=False)

# .getint(): Retrieves an integer value.
int_value = config.getint('settings', 'option', fallback=0)

# .getfloat(): Retrieves a floating-point value.
float_value = config.getfloat('settings', 'option', fallback=0.0)
```



# Modular pandas df filter mask
```python
# Initialize mask with first 'condition'
mask = (df['A'] > 3)

# Add 'conditions' via "&"
mask = mask & (df['B'] == 'd')
mask = mask & (df['C'] < 10)
# etc.

# Apply mask
filtered_df = df[mask]
```


# Make HTML (and then .pdf) 
- Go into your venv env
- in bash terminal:

```bash
jupyter nbconvert --to pdf --TemplateExporter.exclude_input=True  PATH_TO_YOUR_NOTEBOOK_HERE.ipynb
```

# Make it Hot! 
- add one-hot encoded columns for a categorical column in a pandas dataframe
```python
import pandas as pd


def make_it_one_hot(input_dataframe, target_column_name):
    """
    Creates one-hot encoded columns for a categorical column in a pandas dataframe.

    Parameters:
    -----------
    input_dataframe : pandas.DataFrame
        The input dataframe containing the categorical column to be one-hot encoded.
        This dataframe will not be modified.
    target_column_name : str
        The name of the categorical column to be one-hot encoded.

    Returns:
    --------
    tuple
        A tuple containing:
        - pandas.DataFrame: A new dataframe with one-hot encoded columns.
        - int: The number of new one-hot encoded columns created.
        - list: The names of the new one-hot encoded columns.

    Raises:
    -------
    TypeError
        If input_dataframe is not a pandas DataFrame.
        If target_column_name is not a string.
    ValueError
        If the target column is not found in the dataframe.
        If the dataframe is empty.
        If any of the new column names would conflict with existing columns.

    Note:
    This could potentially create column names with decimal points
    (like name_1.0 instead of name_1) in the following scenario:
    If the categorical column contains numeric values that are stored as floats
    rather than integers or strings, pandas will preserve the
    float format in the column names.

    Example:
    --------
    >>> import pandas as pd
    >>> df = pd.DataFrame({
    ...     'cats_videos': ['funny', 'cute', 'funny', 'scary']
    ... })
    >>> df_hot, num_new_cols, new_cols = make_it_one_hot(df, 'cats_videos')
    >>> print(f"Number of new columns: {num_new_cols}")
    Number of new columns: 3
    >>> print(f"New column names: {new_cols}")
    New column names: ['cats_videos_funny', 'cats_videos_cute', 'cats_videos_scary']
    """
    # Validate input types
    if not isinstance(input_dataframe, pd.DataFrame):
        raise TypeError("input_dataframe must be a pandas DataFrame")

    if not isinstance(target_column_name, str):
        raise TypeError("target_column_name must be a string")

    # Validate dataframe and column existence
    if input_dataframe.empty:
        raise ValueError("input_dataframe cannot be empty")

    if target_column_name not in input_dataframe.columns:
        raise ValueError(f"Target column '{target_column_name}' not found in the dataframe")

    # Create a copy of the input dataframe to avoid modifying the original
    modified_dataframe = input_dataframe.copy()

    # Generate one-hot encoded columns with prefixed column names
    one_hot_columns = pd.get_dummies(modified_dataframe[target_column_name],
                                     prefix=target_column_name)

    # Replace spaces with underscores in column names
    one_hot_columns.columns = [col.replace(' ', '_') for col in one_hot_columns.columns]

    # Get the list of new column names
    new_column_names = list(one_hot_columns.columns)

    # Check if any of the new column names already exist in the input dataframe
    existing_columns = set(input_dataframe.columns)
    conflicting_columns = [col for col in new_column_names if col in existing_columns]

    if conflicting_columns:
        raise ValueError(
            f"One-hot encoding would create columns that already exist: {conflicting_columns}. "
            f"Please rename these columns in your original dataframe first."
        )

    # Count the number of new one-hot columns created
    number_of_one_hot_columns = len(new_column_names)

    # Combine original dataframe with the new one-hot columns
    result_dataframe = pd.concat([modified_dataframe, one_hot_columns], axis=1)

    return result_dataframe, number_of_one_hot_columns, new_column_names




```

# Use/Get Latest File Version
```python
import os
import re

def get_highest_version_file(base_name="cats_data_v", extension=".csv"):
    """
    Find the file with the highest version number in the current directory.
    
    Args:
        base_name: Base part of the filename before the version number
        extension: File extension including the dot
        
    Returns:
        String with the name of the file with highest version number or None if no files found
    """
    files = os.listdir('.')
    version_pattern = re.compile(f"{re.escape(base_name)}(\\d+){re.escape(extension)}$")
    
    highest_version = -1
    highest_file = None
    
    for file in files:
        match = version_pattern.match(file)
        if match:
            version = int(match.group(1))
            if version > highest_version:
                highest_version = version
                highest_file = file
                
    return highest_file

# Example usage:
if __name__ == "__main__":
    highest_file = get_highest_version_file("cats_data_v", ".csv")
    print(f"Highest version file: {highest_file}")

```


# time filters (pandas)

```python
#################
# Start a 'mask'
#################
mask = pd.Series([True] * len(df), index=df.index)                # ALL rows
# mask = (df['groups'] == True)                                    

###################################
# Add 'conditions' to mask via "&"
###################################

# Filter by POSIX timestamp range
# mask = mask & (df['posix_time'] >= 1609459200)                  # From 2021-01-01 00:00:00 UTC
# mask = mask & (df['posix_time'] <= 1640995199)                  # To 2021-12-31 23:59:59 UTC

# Filter by datetime range
# mask = mask & (df['datetime'] >= pd.to_datetime('2021-01-01 00:00:00'))
# mask = mask & (df['datetime'] <= pd.to_datetime('2021-12-31 23:59:59'))

# Filter for specific date
# specific_date = pd.to_datetime('2021-07-01').date()
# mask = mask & (df['datetime'].dt.date == specific_date)

# Filter for specific month
# mask = mask & (df['datetime'].dt.year == 2021)
# mask = mask & (df['datetime'].dt.month == 7)

# Filter for specific day of week (Monday = 0, Sunday = 6)
# mask = mask & (df['datetime'].dt.dayofweek == 0)                # All Mondays

# Filter for time of day
# mask = mask & (df['datetime'].dt.hour >= 9)                     # 9 AM or later
# mask = mask & (df['datetime'].dt.hour < 17)                     # Before 5 PM

# Filter for last X days from reference date
# reference_date = pd.to_datetime('2021-12-31')
# days_ago = reference_date - pd.Timedelta(days=7)
# mask = mask & (df['datetime'] > days_ago)
# mask = mask & (df['datetime'] <= reference_date)

# Filter for last X hours
# last_x_hours = pd.Timestamp.now() - pd.Timedelta(hours=24)
# mask = mask & (df['datetime'] >= last_x_hours)

# Filter for business days only (Monday through Friday)
# mask = mask & (df['datetime'].dt.dayofweek < 5)                 # 0-4 = Mon-Fri

# Filter for specific quarter of the year
# mask = mask & (df['datetime'].dt.quarter == 2)                  # Q2

# Filter for date ranges relative to current date
# mask = mask & (df['datetime'] >= pd.Timestamp.now().normalize() - pd.Timedelta(days=30))  # Last 30 days

# Filter for specific week of year
# mask = mask & (df['datetime'].dt.isocalendar().week == 25)       # Week 25

# Filter for weekends
# mask = mask & (df['datetime'].dt.dayofweek >= 5)                # 5-6 = Sat-Sun

#############
# Apply Mask
#############
filtered_df = df[mask]

```
