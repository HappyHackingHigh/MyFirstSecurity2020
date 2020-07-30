#
```
https://github.com/MyDearGreatTeacher/uTaipei2019
```
```
import pandas as pd
print("pandas version: %s" % pd.__version__)


import matplotlib
print("matplotlib version: %s" % matplotlib.__version__)


import numpy as np
print("numpy version: %s" % np.__version__)


import sklearn
print("scikit-learn version: %s" % sklearn.__version__)
```
# NUMPY
```
import numpy as np


ar2=np.array([[0,3,5],[2,8,7]]) 
ar2.shape
```
```



```

```



```
```



```
```



```
```



```
```



```

# 類神經網路
```
# coding: utf-8
import numpy as np


def AND(x1, x2):
    x = np.array([x1, x2])
    w = np.array([0.5, 0.5])
    b = -0.7
    tmp = np.sum(w*x) + b
    if tmp <= 0:
        return 0
    else:
        return 1

if __name__ == '__main__':
    for xs in [(0, 0), (1, 0), (0, 1), (1, 1)]:
        y = AND(xs[0], xs[1])
        print(str(xs) + " -> " + str(y))

```

# MATplotlib
```
import numpy as np
import pylab as pl


# 產生資料
x = np.arange(0.0, 2.0*np.pi, 0.01)	
y = np.sin(t)			

#畫圖

pl.plot(x,y)		
pl.xlabel('x')			
pl.ylabel('y')
pl.title('sin')		
pl.show()
```
```



```
```



```
```



```
```



```
```



```
```



```


