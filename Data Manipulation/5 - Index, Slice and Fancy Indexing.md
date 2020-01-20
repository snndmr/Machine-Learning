## INDEX


```python
import numpy as np

x = np.random.randint(10, size = 10)
x
```




    array([1, 2, 1, 4, 4, 0, 7, 5, 1, 1])




```python
x[5]
```




    0




```python
y = np.random.randint(10, size = [5, 5])
y
```




    array([[1, 2, 4, 2, 3],
           [6, 6, 7, 4, 9],
           [9, 8, 4, 1, 8],
           [2, 4, 2, 4, 3],
           [6, 1, 3, 3, 6]])




```python
y[3, 2]
```




    2




```python
x[5] = 3
x[5]
```




    3




```python
y[3, 2] = 5
y[3, 2]
```




    5




```python
y[3, 2] = 7.83
y[3, 2]
```




    7



## Slice


```python
a = np.arange(20, 40)
a
```




    array([20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36,
           37, 38, 39])




```python
a[0:3]
```




    array([20, 21, 22])




```python
a[:3]
```




    array([20, 21, 22])




```python
a[3:]
```




    array([23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39])




```python
a[::2]
```




    array([20, 22, 24, 26, 28, 30, 32, 34, 36, 38])




```python
a = np.random.randint(20, size = (5, 5))
a = np.random.randint(20, size = (5, 5))
a
```




    array([[ 0, 18, 10, 19, 11],
           [ 2, 18,  9,  7, 19],
           [19,  0,  7,  2,  1],
           [ 2,  0,  9, 16,  0],
           [ 3, 16, 13,  0,  0]])




```python
a[:,0]
```




    array([ 0,  2, 19,  2,  3])




```python
a[0,:]
```




    array([ 0, 18, 10, 19, 11])




```python
a[:2, :3]
```




    array([[ 0, 18, 10],
           [ 2, 18,  9]])




```python
a[1:4, 1:4]
```




    array([[18,  9,  7],
           [ 0,  7,  2],
           [ 0,  9, 16]])




```python
subset = a[1:4, 1:4]
subset[0, 0] = 99999
subset[1, 1] = 99999
subset
```




    array([[99999,     9,     7],
           [    0, 99999,     2],
           [    0,     9,    16]])




```python
a
```




    array([[    0,    18,    10,    19,    11],
           [    2, 99999,     9,     7,    19],
           [   19,     0, 99999,     2,     1],
           [    2,     0,     9,    16,     0],
           [    3,    16,    13,     0,     0]])



### When we change any value in a subset of the parent set, the parent set will also change.

_Making independent subsets with copy()_


```python
a = np.random.randint(20, size = (5, 5))
a
```




    array([[ 4, 17,  6, 19,  8],
           [ 5,  3,  9, 18,  3],
           [ 5, 14,  1,  7, 15],
           [11, 19, 11, 15,  5],
           [14, 13, 17, 13, 17]])




```python
subset = a[1:4, 1:4].copy()
subset[0, 0] = 99999
subset[1, 1] = 99999
subset
```




    array([[99999,     9,    18],
           [   14, 99999,     7],
           [   19,    11,    15]])




```python
a
```




    array([[ 4, 17,  6, 19,  8],
           [ 5,  3,  9, 18,  3],
           [ 5, 14,  1,  7, 15],
           [11, 19, 11, 15,  5],
           [14, 13, 17, 13, 17]])



### FANCY INDEX


```python
a = np.random.randint(100, size = 10)
a.size
```




    10




```python
indexes = np.random.randint(a.size, size = 3)
indexes
```




    array([9, 1, 8])




```python
a[indexes]
```




    array([93, 47, 84])


