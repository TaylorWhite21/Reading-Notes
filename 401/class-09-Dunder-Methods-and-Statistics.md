# Dunder Methods and Basic Statistics in Python — Probability


# Dunder Methods
  Dunder methods are special methods that let you emulate behaviors of built-in types of methods.

  e.g. to get the length of a string you can call len('string'). But an empty class definition doesn’t support this behavior out of the box:
  ```
  class NoLenSupport:
    pass

>>> obj = NoLenSupport()
>>> len(obj)
TypeError: "object of type 'NoLenSupport' has no len()"
```

To fix this you can use __len__:
```
class LenSupport:
    def __len__(self):
        return 42

>>> obj = LenSupport()
>>> len(obj)
42
```

## List of Dunder Methods:  
```
Object initilization: 
__init__
```

### Object Representation:
```
__str__: The “informal” or nicely printable string representation of an object. This is for the enduser.

__repr__: The “official” string representation of an object. This is how you would make an object of the class. The goal of __repr__ is to be unambiguous.
```
```
str(acc)  
'Account of bob with starting amount: 10'

print(acc)
"Account of bob with starting amount: 10"

repr(acc)
"Account('bob', 10)"
```

### Iteration:
Used to iterate through what is passed in.
```
 __len__, 
 __getitem__, 
 __reversed__
```

### Operator Overloading for Comparing Accounts:
Used to compare different data types
``` 
__eq__, 
__lt__
```

Operator Overloading for Merging Accounts:  
Can be used to add objects together
```
__add__

>>> acc3 = acc2 + acc
>>> acc3
Account('tim&bob', 110)

>>> acc3.amount
110
>>> acc3.balance
240
>>> acc3._transactions
[20, 40, 20, -10, 50, -20, 30]
```

Callable Python Objects: 
Used to make an object callable like a function:
```
__call__

class Account:
    # ... (see above)

    def __call__(self):
        print('Start amount: {}'.format(self.amount))
        print('Transactions: ')
        for transaction in self:
            print(transaction)
        print('\nBalance: {}'.format(self.balance))

>>> acc = Account('bob', 10)
>>> acc.add_transaction(20)
>>> acc.add_transaction(-10)
>>> acc.add_transaction(50)
>>> acc.add_transaction(-20)
>>> acc.add_transaction(30)

>>> acc()
Start amount: 10
Transactions:
20
-10
50
-20
30
Balance: 80
```  

Context Manager Support and the With Statement:   
A context manager is a simple “protocol” (or interface) that your object needs to follow so it can be used with the with statement. Basically all you need to do is add ```__enter__``` and ```__exit__``` methods to an object if you want it to function as a context manager.

```
__enter__, 
__exit__
```

# Basic Statistics in Python — Probability

### What is probability?
  -  To calculate the probability of an event occurring, we count how many times are event of interest can occur (say flipping heads) and dividing it by the sample space.  

  - Sample Space:  
    - Flipping a heads  
    - Flipping a tails

  - Probability will tell us that an ideal coin will have a 1-in-2 chance of being heads or tails.

### From statistics to probability
   - To calculating statistics we can call a set of 10 coins tosses a trial. Which will equal 1 data point and record the number of heads we observe.
   - Once more trials are done, we can start to see the average number of heads to approach 50%.

The code below simulates 10, 100, 1000, and 1000000 trials, and then calculates the average proportion of heads observed.
```
import random
def coin_trial():
heads = 0
for i in range(100):
    if random.random() <= 0.5:
        heads +=1
    return heads
def simulate(n):
    trials = []
    for i in range(n):
        trials.append(coin_trial())
    return(sum(trials)/n)
simulate(10)
>>> 5.4
simulate(100)
>>> 4.83
simulate(1000)
>>> 5.055
simulate(1000000)
>>> 4.999781
```

 The coin_trial function is what represents a simulation of 10 coin tosses. It uses the random() function to generate a float between 0 and 1, and increments our heads count if it’s within half of that range. Then, simulate repeats these trials depending on how many times you’d like, returning the average number of heads across all of the trials. The coin toss simulations give us some interesting results.
