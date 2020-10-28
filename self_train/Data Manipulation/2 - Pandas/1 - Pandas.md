## Pandas (Panel Data)

### Pandas Series


```python
import numpy as np
import pandas as pd
```


```python
pd.Series(range(1, 10))
```




    0    1
    1    2
    2    3
    3    4
    4    5
    5    6
    6    7
    7    8
    8    9
    dtype: int64




```python
seri = pd.Series(range(1, 10))
type(seri)
```




    pandas.core.series.Series




```python
seri.axes
```




    [RangeIndex(start=0, stop=9, step=1)]




```python
seri.dtype
```




    dtype('int64')




```python
seri.empty
```




    False




```python
seri.ndim
```




    1




```python
seri.size
```




    9




```python
seri.values
```




    array([1, 2, 3, 4, 5, 6, 7, 8, 9], dtype=int64)




```python
seri.head(3)
```




    0    1
    1    2
    2    3
    dtype: int64




```python
seri[0:4]
```




    0    1
    1    2
    2    3
    3    4
    dtype: int64




```python
seri.tail(3)
```




    6    7
    7    8
    8    9
    dtype: int64



### Numpy to Series


```python
a = np.array([1, 2, 3, 4, 5])
a
```




    array([1, 2, 3, 4, 5])




```python
type(a)
```




    numpy.ndarray




```python
seri = pd.Series(a)
seri
```




    0    1
    1    2
    2    3
    3    4
    4    5
    dtype: int32




```python
seri.index
```




    RangeIndex(start=0, stop=5, step=1)




```python
seri[0]
```




    1




```python
pd.Series([1, 5, .9, 34], index = [1, 3, 5, 7])
```




    1     1.0
    3     5.0
    5     0.9
    7    34.0
    dtype: float64




```python
seri = pd.Series([1, 5, .9, 34], index = [1, 'Ahmet', 5, 7])
```


```python
seri['Ahmet']
```




    5.0



### Dict to Series


```python
dic = {"reg" : 10, "loj" : 11, "cart" : 12}
dic
```




    {'reg': 10, 'loj': 11, 'cart': 12}




```python
pd.Series(dic)
```




    reg     10
    loj     11
    cart    12
    dtype: int64




```python
seri = pd.Series(dic)
seri["reg"]
```




    10




```python
seri["reg":"cart"]
```




    reg     10
    loj     11
    cart    12
    dtype: int64



### Multiple Series


```python
pd.concat([seri, seri])
```




    reg     10
    loj     11
    cart    12
    reg     10
    loj     11
    cart    12
    dtype: int64




```python
seri.append(seri)
```




    reg     10
    loj     11
    cart    12
    reg     10
    loj     11
    cart    12
    dtype: int64




```python
seri
```




    reg     10
    loj     11
    cart    12
    dtype: int64


