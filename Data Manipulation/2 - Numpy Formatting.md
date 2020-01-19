# Numpy Formatting

* ndim
* shape
* size
* dtype


```python
import numpy as np

npArr = np.random.randint(10, size = 10)
npArr.ndim # 1
npArr.shape # 10, 1
npArr.size # 10
npArr.dtype # int32
```




    dtype('int32')



## Reshape


```python
np.arange(1, 10)
```




    array([1, 2, 3, 4, 5, 6, 7, 8, 9])




```python
np.arange(1, 10).reshape(3, 3)
```




    array([[1, 2, 3],
           [4, 5, 6],
           [7, 8, 9]])



## One dim to Two dim


```python
a = np.array([i for i in range(10)])
a
```




    array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])




```python
a.reshape(1, 10)
```




    array([[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]])




```python
a[np.newaxis, :]
```




    array([[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]])




```python
a[:, np.newaxis]
```




    array([[0],
           [1],
           [2],
           [3],
           [4],
           [5],
           [6],
           [7],
           [8],
           [9]])


