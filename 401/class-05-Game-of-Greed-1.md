# Game of Greed 1 Reading Notes

## Random Module

### Randint
- The command ```Randint``` will return a number between two parameters, a lowest and highest number.

The code below will print a number between 1 and 23.:
```
import random
print random.randint(1, 23)
```

### Random
- This method returns a random floating number between 0 and 1.
```
import random
random.random() * 100
```

### Choice
- Generates a random value from a sequence
e.g. Choosing a random element from a list
```
import random
myList = [2, 109, False, 10, "Lorem", 482, "Ipsum"]
random.choice(myList)
```

### Shuffle
- Shuffles the elements in a list, so that they are in a random order.
```
from random import shuffle
x = [[i] for i in range(10)]
shuffle(x)
Output:
# print x  gives  [[9], [2], [7], [0], [4], [5], [3], [1], [8], [6]]
# of course your results will vary
```

### Randrange
- Generates a random element from a range(start, stop, step)
e.g. random.randrange(start, stop[, step])
```
import random
for i in range(3):
    print random.randrange(0, 101, 5)
```


## Risk Analysis

Risk Analysis is used at the beginning of a project to highlight potential problems that may arise when creating software.

A list of possible risks are:
1. Use of new hardware
2. Use of new technology
3. Use of new automation tool
4. The sequence of code
5. Availability of test resources for the application

Some unavoidable risks are:
1. The time that you allocated for testing
2. A defect leakage due to the complexity or size of the application
3. Urgency from the clients to deliver the project
4. Incomplete requirements

### Risk Magnitude Indicators
- High: means the effect of the risk would be very high and non-tolerable. The company might face loss.

- Medium: it is tolerable but not desirable. The company may suffer financially but there is a limited risk.

- Low: it is tolerable. There lies little or no external exposure or no financial loss.

### Risk Assessment
There are 3 perspectives to a Risk Assesment:

- Effect – To assess risk by Effect. In case you identify a condition, event or action and try to determine its impact.

- Cause – To assess risk by Cause is opposite of by Effect. Initialize scanning the problem and reach to the point that could be the most probable reason behind that.

- Likelihood – To assess risk by Likelihood is to say that there is a probability that a requirement won’t be satisfied.
