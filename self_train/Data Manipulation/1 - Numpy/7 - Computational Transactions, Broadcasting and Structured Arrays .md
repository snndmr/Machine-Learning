## Computational Transactions


```python
import numpy as np

x = np.arange(5)
x
```




    array([0, 1, 2, 3, 4])




```python
x - 1
```




    array([-1,  0,  1,  2,  3])




```python
x / 23
```




    array([0.        , 0.04347826, 0.08695652, 0.13043478, 0.17391304])




```python
x * 5
```




    array([ 0,  5, 10, 15, 20])




```python
x ** 3
```




    array([ 0,  1,  8, 27, 64], dtype=int32)




```python
np.add(x, 2) # x + 2
```




    array([2, 3, 4, 5, 6])




```python
x = np.arange(1, 6)
x
```




    array([1, 2, 3, 4, 5])




```python
np.add.reduce(x)
```




    15




```python
np.add.accumulate(x)
```




    array([ 1,  3,  6, 10, 15], dtype=int32)




```python
x = np.random.normal(0, 1, 50)
x
```




    array([ 0.38871034, -0.65227137, -2.20006395,  0.21409646, -0.36420376,
            0.17833133, -0.38171615,  0.67711218,  0.42406157,  1.32177109,
            0.27094691, -0.46888351, -0.14370209,  0.95311898, -0.86574808,
           -0.23024543,  0.60185019, -0.90089588,  0.68609739, -1.23332236,
            1.07057532, -0.9213653 , -0.27688899, -0.8736859 ,  0.72372077,
            0.11066039,  1.3367022 ,  0.74644302, -0.26883184,  1.29205688,
           -1.25042412,  0.14972774,  0.67550127,  1.51354704,  0.87307852,
           -0.78160719, -0.24061265, -1.19814572, -2.60585753, -1.29106725,
           -0.6254006 ,  0.32366612, -1.82706763, -0.57959659,  0.79493369,
           -0.80997507, -0.6020245 ,  3.30843291, -0.27039445, -1.88125748])




```python
np.mean(x)
```




    -0.10220226210174221




```python
np.std(x)
```




    1.0613069902329768




```python
np.var(x)
```




    1.1263725275173797




```python
np.median(x)
```




    -0.23542904013585744




```python
sum(x)
```




    -5.110113105087111



#### For nan values

* np.nanmean(x)
* np.nanstd(x)
* np.nanvar(x)
* np.nanargmin(x)
* np.nanargmax(x)
* np.nanmedian(x)


```python
np.min(x)
```




    -2.6058575322704396




```python
x = np.random.normal(0, 1, (3, 3))
x
```




    array([[ 1.12103326,  1.53038736, -2.31718093],
           [-0.69783332, -1.20451187,  0.20031304],
           [ 1.40795053,  0.16908869,  0.52763821]])




```python
x.sum()
```




    0.7368849745218587




```python
x.sum(axis = 0)
```




    array([ 1.83115047,  0.49496418, -1.58922968])



## Broadcasting


```python
y = np.ones((3, 3))
y
```




    array([[1., 1., 1.],
           [1., 1., 1.],
           [1., 1., 1.]])




```python
a = np.array([[1., 2., 3.],
             [1., 2., 3.],
             [1., 2., 3.]])
a
```




    array([[1., 2., 3.],
           [1., 2., 3.],
           [1., 2., 3.]])




```python
a + y
```




    array([[2., 3., 4.],
           [2., 3., 4.],
           [2., 3., 4.]])




```python
X = np.ones((3, 3))
X
```




    array([[1., 1., 1.],
           [1., 1., 1.],
           [1., 1., 1.]])




```python
Y = np.ones(3)
Y
```




    array([1., 1., 1.])




```python
X + Y
```




    array([[2., 2., 2.],
           [2., 2., 2.],
           [2., 2., 2.]])



### Structured Arrays


```python
name = ["Sinan", "Ahmet", "Ayşe"]
age = [21, 23, 26]
num = [555, 666, 777]

data = np.zeros(3, dtype = {
    'names' : ('name', 'age', 'num'),
    'formats' : ('U10', 'i4', 'f8')
})
```


```python
data
```




    array([('', 0, 0.), ('', 0, 0.), ('', 0, 0.)],
          dtype=[('name', '<U10'), ('age', '<i4'), ('num', '<f8')])




```python
data['name'] = name
data['age'] = age
data['num'] = num
data
```




    array([('Sinan', 21, 555.), ('Ahmet', 23, 666.), ('Ayşe', 26, 777.)],
          dtype=[('name', '<U10'), ('age', '<i4'), ('num', '<f8')])




```python
data['name']
```




    array(['Sinan', 'Ahmet', 'Ayşe'], dtype='<U10')




```python
data[data['age'] < 25]['name']
```




    array(['Sinan', 'Ahmet'], dtype='<U10')


