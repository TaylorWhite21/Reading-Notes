# Linear Regression

Regression analysis explores the relationship between a quantitative response variable and one or more explanotory variables

## How to implement Linear Regression

1. Import packages and classes
```
import numpy as np
from sklearn.linear_model import LinearRegression
```

2. Provide Data
```
x = np.array([5, 15, 25, 35, 45, 55]).reshape((-1, 1))
y = np.array([5, 20, 14, 32, 22, 38])
```
3. Create a model and fit it
```
model = LinearRegression()
```
4. Get Results
```
r_sq = model.score(x, y)
```

5. Predict Response
```
y_pred = model.predict(x)
```


