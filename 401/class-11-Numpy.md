# Data Analysis

## JupyterLab
  JupyterLab enables you to work with documents and activities such as Jupyter notebooks, text editors, terminals, and custom components in a flexible, integrated, and extensible manner.  

### Code Consoles:  
  - Provides transient scratchpads for running code interactively, with full support for rich output. A code console can be linked to a notebook kernel as a computation log from the notebook

### Kernel Backed documents:
  - Enable code in any text file (Markdown, Python, R, LaTeX, etc.) to be run interactively in any Jupyter kernel.  


# Numpy

Numpy is a Python data analysis package that is used to speed up workflow and interface with other packeages.

## Creating a Numpy array

 - Import the numpy package.
 - Pass the list of lists wines into the array function, which converts it into a NumPy array.
    - Exclude the header row with list slicing.
    - Specify the keyword argument dtype to make sure each element is converted to a float.

```
import csv
with open("winequality-red.csv", 'r') as f:
    wines = list(csv.reader(f, delimiter=";"))
import numpy as np
wines = np.array(wines[1:], dtype=np.float)
```

Output:
```
array([[ 7.4 , 0.7 , 0. , ..., 0.56 , 9.4 , 5. ],
[ 7.8 , 0.88 , 0. , ..., 0.68 , 9.8 , 5. ],
[ 7.8 , 0.76 , 0.04 , ..., 0.65 , 9.8 , 5. ],
...,
[ 6.3 , 0.51 , 0.13 , ..., 0.75 , 11. , 6. ],
[ 5.9 , 0.645, 0.12 , ..., 0.71 , 10.2 , 5. ],
[ 6. , 0.31 , 0.47 , ..., 0.66 , 11. , 6. ]])
```

## NumPy to read files

 - Use the genfromtxt function to read in the winequality-red.csv file.
 - Specify the keyword argument delimiter=";" so that the fields are parsed properly.
 - Specify the keyword argument skip_header=1 so that the header row is skipped.
```
wines = np.genfromtxt("winequality-red.csv", delimiter=";", skip_header=1)
```

Several NumPy methods:  

numpy.ndarray.sum - Adds values in an array together.  
numpy.ndarray.mean — finds the mean of an array.  
numpy.ndarray.std — finds the standard deviation of an array.  
numpy.ndarray.min — finds the minimum value in an array.  
numpy.ndarray.max — finds the maximum value in an array.  
