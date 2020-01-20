## COMBINING ARRAYS


```python
import numpy as np

x = np.random.randint(10, 20, size = 10, dtype = 'int')
y = np.random.randint(20, 30, size = 10, dtype = 'int')
```


```python
x
```




    array([12, 12, 19, 14, 15, 19, 16, 18, 17, 11])




```python
y
```




    array([25, 28, 27, 28, 21, 23, 29, 26, 20, 27])




```python
np.concatenate([x, y])
```




    array([12, 12, 19, 14, 15, 19, 16, 18, 17, 11, 25, 28, 27, 28, 21, 23, 29,
           26, 20, 27])



### Two Dim Array Combining


```python
x = np.random.randint(10, 20, size = 16, dtype = 'int').reshape(4, 4)
y = np.random.randint(20, 30, size = 16, dtype = 'int').reshape(4, 4)
```


```python
x
```




    array([[19, 19, 16, 10],
           [14, 18, 18, 10],
           [13, 14, 18, 13],
           [14, 13, 11, 13]])




```python
y
```




    array([[23, 29, 24, 24],
           [29, 29, 29, 21],
           [25, 29, 24, 26],
           [20, 20, 21, 29]])




```python
np.concatenate([x, y])
```




    array([[19, 19, 16, 10],
           [14, 18, 18, 10],
           [13, 14, 18, 13],
           [14, 13, 11, 13],
           [23, 29, 24, 24],
           [29, 29, 29, 21],
           [25, 29, 24, 26],
           [20, 20, 21, 29]])




```python
np.concatenate([x, y], axis = 1)
```




    array([[19, 19, 16, 10, 23, 29, 24, 24],
           [14, 18, 18, 10, 29, 29, 29, 21],
           [13, 14, 18, 13, 25, 29, 24, 26],
           [14, 13, 11, 13, 20, 20, 21, 29]])




```python

```




    array([[19, 19, 16, 10],
           [14, 18, 18, 10],
           [13, 14, 18, 13],
           [14, 13, 11, 13],
           [23, 29, 24, 24],
           [29, 29, 29, 21],
           [25, 29, 24, 26],
           [20, 20, 21, 29]])



### Different Dim Array Combining


```python
x = np.random.randint(10, 20, size = 4, dtype = 'int')
y = np.random.randint(20, 30, size = 16, dtype = 'int').reshape(4, 4)
z = np.random.randint(10, 20, size = 4, dtype = 'int').reshape(4, 1)
```


```python
x
```




    array([18, 11, 11, 19])




```python
y
```




    array([[23, 21, 26, 21],
           [22, 20, 28, 25],
           [26, 29, 29, 28],
           [26, 26, 25, 22]])




```python
z
```




    array([[16],
           [14],
           [12],
           [13]])




```python
np.vstack([x, y])
```




    array([[18, 11, 11, 19],
           [23, 21, 26, 21],
           [22, 20, 28, 25],
           [26, 29, 29, 28],
           [26, 26, 25, 22]])




```python
np.hstack([z, y])
```




    array([[16, 23, 21, 26, 21],
           [14, 22, 20, 28, 25],
           [12, 26, 29, 29, 28],
           [13, 26, 26, 25, 22]])




```python

```
