## Comparison Operators


```python
import numpy as np

x = np.arange(5)
x
```




    array([0, 1, 2, 3, 4])




```python
x > 3
```




    array([False, False, False, False,  True])




```python
x < 3
```




    array([ True,  True,  True, False, False])




```python
x == 3
```




    array([False, False, False,  True, False])




```python
x != 3
```




    array([ True,  True,  True, False,  True])




```python
2 * x
```




    array([0, 2, 4, 6, 8])




```python
x ** 2
```




    array([ 0,  1,  4,  9, 16], dtype=int32)




```python
2 * x == x ** 2
```




    array([ True, False,  True, False, False])



### ufunc

* np.equal
* np.not_equal
* np.less
* np.less_equal
* np.greater
* np.greater_equal


```python
np.equal(3, x) # x == 3
```




    array([False, False, False,  True, False])




```python
y = np.random.randint(50, size = (5, 5))
y
```




    array([[46,  2, 35,  8, 44],
           [ 8,  4, 42,  1, 46],
           [11, 43, 18, 16, 22],
           [13, 44, 14,  8, 18],
           [ 5, 42,  0, 11, 11]])




```python
y > 25
```




    array([[ True, False,  True, False,  True],
           [False, False,  True, False,  True],
           [False,  True, False, False, False],
           [False,  True, False, False, False],
           [False,  True, False, False, False]])




```python
np.sum(y > 25)
```




    8




```python
np.sum((y > 25) & (y < 40))
```




    1




```python
(y > 25) & (y < 40)
```




    array([[False, False,  True, False, False],
           [False, False, False, False, False],
           [False, False, False, False, False],
           [False, False, False, False, False],
           [False, False, False, False, False]])




```python
np.sum(y > 25, axis = 1) # row
```




    array([3, 2, 1, 1, 1])




```python
np.sum(y > 25, axis = 0) # col
```




    array([1, 3, 2, 0, 2])




```python
np.all(y > 25)
```




    False




```python
np.any(y > 25)
```




    True




```python
y[y > 25]
```




    array([46, 35, 44, 42, 46, 43, 44, 42])




```python
y[(y > 25) & (y < 40)]
```




    array([35])


