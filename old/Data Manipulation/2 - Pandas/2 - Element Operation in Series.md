### Element Operation in Series


```python
import numpy as np
import pandas as pd
```


```python
x = np.random.randint(0, 100, 5, dtype = 'int')
seri = pd.Series(x)
seri
```




    0    20
    1    32
    2     4
    3    78
    4     2
    dtype: int32




```python
list(seri.items())
```




    [(0, 20), (1, 32), (2, 4), (3, 78), (4, 2)]




```python
0 in seri
```




    True




```python
5 in seri
```




    False




```python
seri[[0, 3]]
```




    0    20
    3    78
    dtype: int32




```python
seri[2] = 25
seri
```




    0    20
    1    32
    2    25
    3    78
    4     2
    dtype: int32




```python
seri[(seri > 20) & (seri < 50)]
```




    1    32
    2    25
    dtype: int32




```python
data = pd.Series(['a', 'b', 'c'], index = [1, 3, 5])
data
```




    1    a
    3    b
    5    c
    dtype: object




```python
data[0]
```


    ---------------------------------------------------------------------------

    KeyError                                  Traceback (most recent call last)

    <ipython-input-10-80a4aab09c73> in <module>
    ----> 1 data[0]
    

    ~\Anaconda3\lib\site-packages\pandas\core\series.py in __getitem__(self, key)
       1066         key = com.apply_if_callable(key, self)
       1067         try:
    -> 1068             result = self.index.get_value(self, key)
       1069 
       1070             if not is_scalar(result):
    

    ~\Anaconda3\lib\site-packages\pandas\core\indexes\base.py in get_value(self, series, key)
       4728         k = self._convert_scalar_indexer(k, kind="getitem")
       4729         try:
    -> 4730             return self._engine.get_value(s, k, tz=getattr(series.dtype, "tz", None))
       4731         except KeyError as e1:
       4732             if len(self) > 0 and (self.holds_integer() or self.is_boolean()):
    

    pandas\_libs\index.pyx in pandas._libs.index.IndexEngine.get_value()
    

    pandas\_libs\index.pyx in pandas._libs.index.IndexEngine.get_value()
    

    pandas\_libs\index.pyx in pandas._libs.index.IndexEngine.get_loc()
    

    pandas\_libs\hashtable_class_helper.pxi in pandas._libs.hashtable.Int64HashTable.get_item()
    

    pandas\_libs\hashtable_class_helper.pxi in pandas._libs.hashtable.Int64HashTable.get_item()
    

    KeyError: 0



```python
data[1]
```




    'a'




```python
data[1:3]
```




    3    b
    5    c
    dtype: object




```python
data[0:3]
```




    1    a
    3    b
    5    c
    dtype: object



### loc label based indexing


```python
data.loc[1]
```




    'a'




```python
data.loc[2]
```


    ---------------------------------------------------------------------------

    KeyError                                  Traceback (most recent call last)

    ~\Anaconda3\lib\site-packages\pandas\core\indexes\base.py in get_loc(self, key, method, tolerance)
       2896             try:
    -> 2897                 return self._engine.get_loc(key)
       2898             except KeyError:
    

    pandas\_libs\index.pyx in pandas._libs.index.IndexEngine.get_loc()
    

    pandas\_libs\index.pyx in pandas._libs.index.IndexEngine.get_loc()
    

    pandas\_libs\hashtable_class_helper.pxi in pandas._libs.hashtable.Int64HashTable.get_item()
    

    pandas\_libs\hashtable_class_helper.pxi in pandas._libs.hashtable.Int64HashTable.get_item()
    

    KeyError: 2

    
    During handling of the above exception, another exception occurred:
    

    KeyError                                  Traceback (most recent call last)

    <ipython-input-15-870ecc20c9fe> in <module>
    ----> 1 data.loc[2]
    

    ~\Anaconda3\lib\site-packages\pandas\core\indexing.py in __getitem__(self, key)
       1422 
       1423             maybe_callable = com.apply_if_callable(key, self.obj)
    -> 1424             return self._getitem_axis(maybe_callable, axis=axis)
       1425 
       1426     def _is_scalar_access(self, key: Tuple):
    

    ~\Anaconda3\lib\site-packages\pandas\core\indexing.py in _getitem_axis(self, key, axis)
       1848         # fall thru to straight lookup
       1849         self._validate_key(key, axis)
    -> 1850         return self._get_label(key, axis=axis)
       1851 
       1852 
    

    ~\Anaconda3\lib\site-packages\pandas\core\indexing.py in _get_label(self, label, axis)
        154             # but will fail when the index is not present
        155             # see GH5667
    --> 156             return self.obj._xs(label, axis=axis)
        157         elif isinstance(label, tuple) and isinstance(label[axis], slice):
        158             raise IndexingError("no slices here, handle elsewhere")
    

    ~\Anaconda3\lib\site-packages\pandas\core\generic.py in xs(self, key, axis, level, drop_level)
       3735             loc, new_index = self.index.get_loc_level(key, drop_level=drop_level)
       3736         else:
    -> 3737             loc = self.index.get_loc(key)
       3738 
       3739             if isinstance(loc, np.ndarray):
    

    ~\Anaconda3\lib\site-packages\pandas\core\indexes\base.py in get_loc(self, key, method, tolerance)
       2897                 return self._engine.get_loc(key)
       2898             except KeyError:
    -> 2899                 return self._engine.get_loc(self._maybe_cast_indexer(key))
       2900         indexer = self.get_indexer([key], method=method, tolerance=tolerance)
       2901         if indexer.ndim > 1 or indexer.size > 1:
    

    pandas\_libs\index.pyx in pandas._libs.index.IndexEngine.get_loc()
    

    pandas\_libs\index.pyx in pandas._libs.index.IndexEngine.get_loc()
    

    pandas\_libs\hashtable_class_helper.pxi in pandas._libs.hashtable.Int64HashTable.get_item()
    

    pandas\_libs\hashtable_class_helper.pxi in pandas._libs.hashtable.Int64HashTable.get_item()
    

    KeyError: 2



```python
data.loc[0:2]
```




    1    a
    dtype: object



### iloc label based indexing


```python
data.iloc[2] # data[0:2]
```




    'c'




```python
data.iloc[0:3]
```




    1    a
    3    b
    5    c
    dtype: object



## Pandas DataFrame Attributes & Creating


```python
mList = [1, 5, 14, 29, 150]
mList
```




    [1, 5, 14, 29, 150]




```python
pd.DataFrame(mList, columns = ['varName'])
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>varName</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <td>1</td>
      <td>5</td>
    </tr>
    <tr>
      <td>2</td>
      <td>14</td>
    </tr>
    <tr>
      <td>3</td>
      <td>29</td>
    </tr>
    <tr>
      <td>4</td>
      <td>150</td>
    </tr>
  </tbody>
</table>
</div>




```python
dataFrame = pd.DataFrame(mList, columns = ['varName'])
```


```python
type(dataFrame)
```




    pandas.core.frame.DataFrame




```python
dataFrame.axes
```




    [RangeIndex(start=0, stop=5, step=1), Index(['varName'], dtype='object')]




```python
dataFrame.shape
```




    (5, 1)




```python
dataFrame.ndim
```




    2




```python
dataFrame.size
```




    5




```python
dataFrame.values
```




    array([[  1],
           [  5],
           [ 14],
           [ 29],
           [150]], dtype=int64)




```python
dataFrame.head(3)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>varName</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <td>1</td>
      <td>5</td>
    </tr>
    <tr>
      <td>2</td>
      <td>14</td>
    </tr>
  </tbody>
</table>
</div>




```python
dataFrame.tail(2)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>varName</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>3</td>
      <td>29</td>
    </tr>
    <tr>
      <td>4</td>
      <td>150</td>
    </tr>
  </tbody>
</table>
</div>




```python
x = np.random.randint(0 , 100, 10)
pd.DataFrame(x, columns = ['Random Numbers'])
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Random Numbers</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>13</td>
    </tr>
    <tr>
      <td>1</td>
      <td>90</td>
    </tr>
    <tr>
      <td>2</td>
      <td>19</td>
    </tr>
    <tr>
      <td>3</td>
      <td>83</td>
    </tr>
    <tr>
      <td>4</td>
      <td>99</td>
    </tr>
    <tr>
      <td>5</td>
      <td>44</td>
    </tr>
    <tr>
      <td>6</td>
      <td>93</td>
    </tr>
    <tr>
      <td>7</td>
      <td>67</td>
    </tr>
    <tr>
      <td>8</td>
      <td>93</td>
    </tr>
    <tr>
      <td>9</td>
      <td>37</td>
    </tr>
  </tbody>
</table>
</div>




```python
x = np.random.randint(0 , 100, 16).reshape(4, 4)
x
```




    array([[89, 12, 58, 88],
           [24, 68, 61, 69],
           [37, 99, 83, 31],
           [45, 17, 19, 33]])




```python
dataFrame = pd.DataFrame(x, columns = ['VAR 1', 'VAR 2', 'VAR 3', 'VAR 4'])
dataFrame
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>VAR 1</th>
      <th>VAR 2</th>
      <th>VAR 3</th>
      <th>VAR 4</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>89</td>
      <td>12</td>
      <td>58</td>
      <td>88</td>
    </tr>
    <tr>
      <td>1</td>
      <td>24</td>
      <td>68</td>
      <td>61</td>
      <td>69</td>
    </tr>
    <tr>
      <td>2</td>
      <td>37</td>
      <td>99</td>
      <td>83</td>
      <td>31</td>
    </tr>
    <tr>
      <td>3</td>
      <td>45</td>
      <td>17</td>
      <td>19</td>
      <td>33</td>
    </tr>
  </tbody>
</table>
</div>




```python
dataFrame.columns = ('VAR A', 'VAR B', 'VAR C', 'VAR D')
dataFrame
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>VAR A</th>
      <th>VAR B</th>
      <th>VAR C</th>
      <th>VAR D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>89</td>
      <td>12</td>
      <td>58</td>
      <td>88</td>
    </tr>
    <tr>
      <td>1</td>
      <td>24</td>
      <td>68</td>
      <td>61</td>
      <td>69</td>
    </tr>
    <tr>
      <td>2</td>
      <td>37</td>
      <td>99</td>
      <td>83</td>
      <td>31</td>
    </tr>
    <tr>
      <td>3</td>
      <td>45</td>
      <td>17</td>
      <td>19</td>
      <td>33</td>
    </tr>
  </tbody>
</table>
</div>




```python
dataFrame.index = ('INDEX A', 'INDEX B', 'INDEX C', 'INDEX D')
dataFrame
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>VAR A</th>
      <th>VAR B</th>
      <th>VAR C</th>
      <th>VAR D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>INDEX A</td>
      <td>89</td>
      <td>12</td>
      <td>58</td>
      <td>88</td>
    </tr>
    <tr>
      <td>INDEX B</td>
      <td>24</td>
      <td>68</td>
      <td>61</td>
      <td>69</td>
    </tr>
    <tr>
      <td>INDEX C</td>
      <td>37</td>
      <td>99</td>
      <td>83</td>
      <td>31</td>
    </tr>
    <tr>
      <td>INDEX D</td>
      <td>45</td>
      <td>17</td>
      <td>19</td>
      <td>33</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.DataFrame(pd.Series([1, 2, 3, 4]), columns= ['Var'])
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Var</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <td>1</td>
      <td>2</td>
    </tr>
    <tr>
      <td>2</td>
      <td>3</td>
    </tr>
    <tr>
      <td>3</td>
      <td>4</td>
    </tr>
  </tbody>
</table>
</div>




```python
first = pd.Series([1, 2, 3, 4])
second = pd.Series([6, 7, 8, 9])

pd.DataFrame({'Var A' : first,
             'Var B' : second})
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Var A</th>
      <th>Var B</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>1</td>
      <td>6</td>
    </tr>
    <tr>
      <td>1</td>
      <td>2</td>
      <td>7</td>
    </tr>
    <tr>
      <td>2</td>
      <td>3</td>
      <td>8</td>
    </tr>
    <tr>
      <td>3</td>
      <td>4</td>
      <td>9</td>
    </tr>
  </tbody>
</table>
</div>




```python

```
