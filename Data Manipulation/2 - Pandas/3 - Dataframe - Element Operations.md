## Dataframe - Element Operation


```python
import numpy as np
import pandas as pd

x = np.random.randint(10, size = 5)
y = np.random.randint(10, size = 5)
z = np.random.randint(10, size = 5)

dataframe = pd.DataFrame({"X" : x, "Y" : y, "Z" : z})
dataframe
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
      <th>X</th>
      <th>Y</th>
      <th>Z</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>1</td>
      <td>2</td>
      <td>1</td>
    </tr>
    <tr>
      <td>1</td>
      <td>0</td>
      <td>3</td>
      <td>5</td>
    </tr>
    <tr>
      <td>2</td>
      <td>0</td>
      <td>5</td>
      <td>8</td>
    </tr>
    <tr>
      <td>3</td>
      <td>7</td>
      <td>4</td>
      <td>5</td>
    </tr>
    <tr>
      <td>4</td>
      <td>3</td>
      <td>1</td>
      <td>8</td>
    </tr>
  </tbody>
</table>
</div>




```python
dataframe[0:1]
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
      <th>X</th>
      <th>Y</th>
      <th>Z</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>1</td>
      <td>2</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
dataframe.index = ['a', 'b', 'c', 'd', 'e']
dataframe
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
      <th>X</th>
      <th>Y</th>
      <th>Z</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>a</td>
      <td>1</td>
      <td>2</td>
      <td>1</td>
    </tr>
    <tr>
      <td>b</td>
      <td>0</td>
      <td>3</td>
      <td>5</td>
    </tr>
    <tr>
      <td>c</td>
      <td>0</td>
      <td>5</td>
      <td>8</td>
    </tr>
    <tr>
      <td>d</td>
      <td>7</td>
      <td>4</td>
      <td>5</td>
    </tr>
    <tr>
      <td>e</td>
      <td>3</td>
      <td>1</td>
      <td>8</td>
    </tr>
  </tbody>
</table>
</div>




```python
dataframe['c':'e']
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
      <th>X</th>
      <th>Y</th>
      <th>Z</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>c</td>
      <td>0</td>
      <td>5</td>
      <td>8</td>
    </tr>
    <tr>
      <td>d</td>
      <td>7</td>
      <td>4</td>
      <td>5</td>
    </tr>
    <tr>
      <td>e</td>
      <td>3</td>
      <td>1</td>
      <td>8</td>
    </tr>
  </tbody>
</table>
</div>




```python
dataframe.drop('a', axis=0) #it will not drop.
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
      <th>X</th>
      <th>Y</th>
      <th>Z</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>b</td>
      <td>0</td>
      <td>3</td>
      <td>5</td>
    </tr>
    <tr>
      <td>c</td>
      <td>0</td>
      <td>5</td>
      <td>8</td>
    </tr>
    <tr>
      <td>d</td>
      <td>7</td>
      <td>4</td>
      <td>5</td>
    </tr>
    <tr>
      <td>e</td>
      <td>3</td>
      <td>1</td>
      <td>8</td>
    </tr>
  </tbody>
</table>
</div>




```python
dataframe
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
      <th>X</th>
      <th>Y</th>
      <th>Z</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>a</td>
      <td>1</td>
      <td>2</td>
      <td>1</td>
    </tr>
    <tr>
      <td>b</td>
      <td>0</td>
      <td>3</td>
      <td>5</td>
    </tr>
    <tr>
      <td>c</td>
      <td>0</td>
      <td>5</td>
      <td>8</td>
    </tr>
    <tr>
      <td>d</td>
      <td>7</td>
      <td>4</td>
      <td>5</td>
    </tr>
    <tr>
      <td>e</td>
      <td>3</td>
      <td>1</td>
      <td>8</td>
    </tr>
  </tbody>
</table>
</div>




```python
dataframe.drop('a', axis=0, inplace=True) #it will drop.
```


```python
dataframe
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
      <th>X</th>
      <th>Y</th>
      <th>Z</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>b</td>
      <td>0</td>
      <td>3</td>
      <td>5</td>
    </tr>
    <tr>
      <td>c</td>
      <td>0</td>
      <td>5</td>
      <td>8</td>
    </tr>
    <tr>
      <td>d</td>
      <td>7</td>
      <td>4</td>
      <td>5</td>
    </tr>
    <tr>
      <td>e</td>
      <td>3</td>
      <td>1</td>
      <td>8</td>
    </tr>
  </tbody>
</table>
</div>




```python
dropList = ['b', 'd']
dataframe.drop(dropList, axis=0, inplace=True)
```


```python
dataframe
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
      <th>X</th>
      <th>Y</th>
      <th>Z</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>c</td>
      <td>0</td>
      <td>5</td>
      <td>8</td>
    </tr>
    <tr>
      <td>e</td>
      <td>3</td>
      <td>1</td>
      <td>8</td>
    </tr>
  </tbody>
</table>
</div>




```python
'X' in dataframe
```




    True




```python
searchList = ['X', 'Y', 'W']
for i in searchList:
    print(i in dataframe)
```

    True
    True
    False
    


```python
dataframe['X'] is dataframe['Y']
```




    False




```python
dataframe['X'] #Dict Type
```




    c    0
    e    3
    Name: X, dtype: int32




```python
dataframe.X #Attr Type
```




    c    0
    e    3
    Name: X, dtype: int32




```python
dataframe[['X', 'Y']]
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
      <th>X</th>
      <th>Y</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>c</td>
      <td>0</td>
      <td>5</td>
    </tr>
    <tr>
      <td>e</td>
      <td>3</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
selectList = ['X', 'Y']
dataframe[selectList]
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
      <th>X</th>
      <th>Y</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>c</td>
      <td>0</td>
      <td>5</td>
    </tr>
    <tr>
      <td>e</td>
      <td>3</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
dataframe['W'] = dataframe['X'] * dataframe['Y'] * dataframe['Z']
dataframe
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
      <th>X</th>
      <th>Y</th>
      <th>Z</th>
      <th>W</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>c</td>
      <td>0</td>
      <td>5</td>
      <td>8</td>
      <td>0</td>
    </tr>
    <tr>
      <td>e</td>
      <td>3</td>
      <td>1</td>
      <td>8</td>
      <td>24</td>
    </tr>
  </tbody>
</table>
</div>




```python
dataframe.drop('W', axis=1)
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
      <th>X</th>
      <th>Y</th>
      <th>Z</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>c</td>
      <td>0</td>
      <td>5</td>
      <td>8</td>
    </tr>
    <tr>
      <td>e</td>
      <td>3</td>
      <td>1</td>
      <td>8</td>
    </tr>
  </tbody>
</table>
</div>



### Multiple Operations


```python
x = np.random.randint(10, size = 5)
y = np.random.randint(10, size = 5)
z = np.random.randint(10, size = 5)

dataframe = pd.DataFrame({"X" : x, "Y" : y, "Z" : z})
dataframe
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
      <th>X</th>
      <th>Y</th>
      <th>Z</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>1</td>
      <td>8</td>
      <td>9</td>
    </tr>
    <tr>
      <td>1</td>
      <td>1</td>
      <td>3</td>
      <td>5</td>
    </tr>
    <tr>
      <td>2</td>
      <td>7</td>
      <td>3</td>
      <td>7</td>
    </tr>
    <tr>
      <td>3</td>
      <td>9</td>
      <td>2</td>
      <td>7</td>
    </tr>
    <tr>
      <td>4</td>
      <td>8</td>
      <td>4</td>
      <td>4</td>
    </tr>
  </tbody>
</table>
</div>




```python
dataframe.loc[0:3]
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
      <th>X</th>
      <th>Y</th>
      <th>Z</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>1</td>
      <td>8</td>
      <td>9</td>
    </tr>
    <tr>
      <td>1</td>
      <td>1</td>
      <td>3</td>
      <td>5</td>
    </tr>
    <tr>
      <td>2</td>
      <td>7</td>
      <td>3</td>
      <td>7</td>
    </tr>
    <tr>
      <td>3</td>
      <td>9</td>
      <td>2</td>
      <td>7</td>
    </tr>
  </tbody>
</table>
</div>




```python
dataframe.iloc[0:3]
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
      <th>X</th>
      <th>Y</th>
      <th>Z</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>1</td>
      <td>8</td>
      <td>9</td>
    </tr>
    <tr>
      <td>1</td>
      <td>1</td>
      <td>3</td>
      <td>5</td>
    </tr>
    <tr>
      <td>2</td>
      <td>7</td>
      <td>3</td>
      <td>7</td>
    </tr>
  </tbody>
</table>
</div>




```python
dataframe.iloc[0,0]
```




    1




```python
dataframe.iloc[:3, :2] 
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
      <th>X</th>
      <th>Y</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>1</td>
      <td>8</td>
    </tr>
    <tr>
      <td>1</td>
      <td>1</td>
      <td>3</td>
    </tr>
    <tr>
      <td>2</td>
      <td>7</td>
      <td>3</td>
    </tr>
  </tbody>
</table>
</div>




```python
dataframe.loc[1:3, 'X':'Y']
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
      <th>X</th>
      <th>Y</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td>1</td>
      <td>3</td>
    </tr>
    <tr>
      <td>2</td>
      <td>7</td>
      <td>3</td>
    </tr>
    <tr>
      <td>3</td>
      <td>9</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
</div>




```python
dataframe[(dataframe.X > 1) & (dataframe.X < 5)].loc[:, 'X']
```




    Series([], Name: X, dtype: int32)




```python
dataframe.loc[(dataframe.X > 1) & (dataframe.X < 5), ['X']]
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
      <th>X</th>
    </tr>
  </thead>
  <tbody>
  </tbody>
</table>
</div>


