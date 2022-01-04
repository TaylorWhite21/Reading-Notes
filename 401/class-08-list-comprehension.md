# List Comprehension

## Syntax
```
my_new_list = [expression for item in list]
```
The example above shows 3 ingredeints needed for python list comprehension to work.

  1. First is the expression we’d like to carry out. expression inside the square brackets.
  2. Second is the object that the expression will work on. item inside the square brackets.
  3. Finally, we need an iterable list of objects to build our new list from. list inside the square brackets.

A better way to understand this is to  imagine that for each item in a list, you are goingf to perform an expression which will determine the output that is stored in the list.

## Create a list with range()

### Example 1:
```
# construct a basic list using range() and list comprehensions
# syntax
# [ expression for item in list ]
digits = [x for x in range(10)]

print(digits)
```

Output:
```
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

 - The first x is simply recording the number
 - The second x is every item in the list created by the range method

 ## Create a List Using Loops and List Comprehension in Python

 ### Example 2:
 The code below is a for loop to create a list to the power of 2.
 ```
 # create a list using a for loop
squares = []

for x in range(10):
    # raise x to the power of 2
    squares.append(x**2)

print(squares)
```

Output:
```
[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```

This can be refactored using list comprehension
```
# create a list using list comprehension
squares = [x**2 for x in range(10)]

print(squares)
```

## Multiplying Parts of a List

### Example 3: Multiplication with list comprehensions
The example below is multiplying each item in the list by 3.
```
# create a list with list comprehensions
multiples_of_three = [ x*3 for x in range(10) ]

print(multiples_of_three)
```

Output:
```
[0, 3, 6, 9, 12, 15, 18, 21, 24, 27]
```

A filter can be added gives even greater flexibility.
This example is only multiplying the even numbers
```
even_numbers = [ x for x in range(1,20) if x % 2 == 0]
```

Output:
```
[2, 4, 6, 8, 10, 12, 14, 16, 18]
```

## Show the first letter of each word using Python

### Example 4: Using list comprehensions with strings

The example below is iterating through the list of strings and only taking the first letter then creating a list of those letters

```
# a list of the names of popular authors
authors = ["Ernest Hemingway","Langston Hughes","Frank Herbert","Toni Morrison",
    "Emily Dickson","Stephen King"]

# create an acronym from the first letter of the author's names
letters = [ name[0] for name in authors ]
print(letters)
```

Output:
```
['E', 'L', 'F', 'T', 'E', 'S']
```

### Example 5: Separating the characters in a string

```
# use list comprehension to print the letters in a string
letters = [ letter for letter in "20,000 Leagues Under The Sea"]

print(letters)
```

Output:
```
['2', '0', ',', '0', '0', '0', ' ', 'L', 'e', 'a', 'g', 'u', 'e', 's', ' ', 'U', 'n', 'd', 'e', 'r', ' ', 'T', 'h', 'e', ' ', 'S', 'e', 'a']
```

## Lower/Upper case converter using Python
With list comprehension, you can loop through a string and convert them to either lower case or upper case

### Example 6: Changing a letter’s case
```
lower_case = [ letter.lower() for letter in ['A','B','C'] ]
upper_case = [ letter.upper() for letter in ['a','b','c'] ]

print(lower_case, upper_case)
```

Output:
```
['a', 'b', 'c'] ['A', 'B', 'C']
```

## Print numbers only from a given string
Using the isdigit method, we can extract numbers from a string and return them in a list. This works well for a database with names and phone numbers.

### Example 7: Identify numbers in a string using the isdigit() method

```
# user data entered as name and phone number
user_data = "Elvis Presley 987-654-3210"
phone_number = [ x for x in user_data if x.isdigit()]

print(phone_number)
```

Output:
```
['9', '8', '7', '6', '5', '4', '3', '2', '1', '0']
```


## Parsing a file using list comprehension

It's also possible to read files using list comprehension. You can iterate through the lines of text in the file and store their contents in a new list. The 'r' means it opens in read-only mode.

### Example 8: Reading a poem with list comprehensions
```
# open the file in read-only mode
file = open("dreams.txt", 'r')
poem = [ line for line in file ]

for line in poem:
    print(line)
```

Output:
```
Hold fast to dreams

For if dreams die

Life is a broken-winged bird

That cannot fly.

-Langston Hughs
```

## Using functions in list comprehensions

You can also use functions in list comprehension.
### Example 9: Adding arguments to list comprehension

```
# list comprehension with functions
# create a function that returns a number doubled
def double(x):
    return x*2

nums = [double(x) for x in range(1,10)]
print(nums)
```

Output:
```
[2, 4, 6, 8, 10, 12, 14, 16, 18]
```

You can also filter the items. In the example below, only the even numbers are used.

```
# add a filter so we only double even numbers
even_nums = [double(x) for x in range(1,10) if x%2 == 0]
print(even_nums)
```

Output:
```
[4, 8, 12, 16]
```

You can even use to for loops to add the items in a list together.

```
nums = [x+y for x in [1,2,3] for y in [10,20,30]]
print(nums)
```

Output:
```
[11, 21, 31, 12, 22, 32, 13, 23, 33]
```

