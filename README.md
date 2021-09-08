# py-lower-bound-bai
Python utilities to compute a lower bound of the expected sample complexity to identify the best arm in a bandit model


## Requirements
Python 3 and the following libraries
- Numpy
- Scipy
- Cython

`pip install cython numpy scipy`

## Usage
Check the example files

```python 
import numpy as np
import os
import math

import pyximport
_ = pyximport.install()
from math_func_cython import solveFBern

mu = [0.6, 0.5]

w, Tinv = solveFBern(np.sort(mu)[::-1])

print("T^(-1): {}".format(Tinv))
print("Sample complexity: {}".format(1/Tinv))
print("Optimal weights: {}".format(w))
```
