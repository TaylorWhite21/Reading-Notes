# FileIO & Exceptions

## Exceptions

### Syntax Errors
- Occur when the parser detects an incorrect statement. It has an arrow that indicates where the error is.

<!-- Code pulled from reading -->
```
>>> print( 0 / 0 ))
  File "<stdin>", line 1
    print( 0 / 0 ))
                  ^
SyntaxError: invalid syntax
```

### Raising an Exception
- Used when you want to throw an error when a certain condition is met.

```
x = 10
if x > 5:
    raise Exception('x should not exceed 5. The value of x was: {}'.format(x))
```

When you run this code, the output will be the following:
```
Traceback (most recent call last):
  File "<input>", line 4, in <module>
Exception: x should not exceed 5. The value of x was: 10
```

### Try and Except
- Used to catch and handle exceptions.
- Try statements will run as a normal part of the code
- Except statements is the programs response to any exceptions

```
def linux_interaction():
    assert ('linux' in sys.platform), "Function can only run on Linux systems."
    print('Doing something.')

try:
    linux_interaction()
except:
    print('Linux function was not executed')
```

### Else clause

 - Can be used when you want to execute code only if there are no exceptions

 ```
 try:
    linux_interaction()
except AssertionError as error:
    print(error)
else:
    print('Executing the else clause.')
```

```
try:
    linux_interaction()
except AssertionError as error:
    print(error)
else:
    try:
        with open('file.log') as file:
            read_data = file.read()
    except FileNotFoundError as fnf_error:
        print(fnf_error)
```

### Finally
- Used to clean and always run after the try and except

```
try:
    linux_interaction()
except AssertionError as error:
    print(error)
else:
    try:
        with open('file.log') as file:
            read_data = file.read()
    except FileNotFoundError as fnf_error:
        print(fnf_error)
finally:
    print('Cleaning up, irrespective of any exceptions.')
```

## FileI/O

### Open()

- Used to open a file
```
file = open('dog_breeds.txt')
```

### You should always make sure that an open file is properly closed.

### Close
```
reader = open('dog_breeds.txt')
try:
    # Further file processing goes here
finally:
    reader.close()
```

### With - Can also be used to close a file after use
```
with open('dog_breeds.txt') as reader:
    # Further file processing goes here
```
