### First Look at the Data


```python
import seaborn as sns
planents = sns.load_dataset('planets')
planents.head()
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
      <th>method</th>
      <th>number</th>
      <th>orbital_period</th>
      <th>mass</th>
      <th>distance</th>
      <th>year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Radial Velocity</td>
      <td>1</td>
      <td>269.300</td>
      <td>7.10</td>
      <td>77.40</td>
      <td>2006</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Radial Velocity</td>
      <td>1</td>
      <td>874.774</td>
      <td>2.21</td>
      <td>56.95</td>
      <td>2008</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Radial Velocity</td>
      <td>1</td>
      <td>763.000</td>
      <td>2.60</td>
      <td>19.84</td>
      <td>2011</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Radial Velocity</td>
      <td>1</td>
      <td>326.030</td>
      <td>19.40</td>
      <td>110.62</td>
      <td>2007</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Radial Velocity</td>
      <td>1</td>
      <td>516.220</td>
      <td>10.50</td>
      <td>119.47</td>
      <td>2009</td>
    </tr>
  </tbody>
</table>
</div>




```python
df = planents.copy()
df.head()
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
      <th>method</th>
      <th>number</th>
      <th>orbital_period</th>
      <th>mass</th>
      <th>distance</th>
      <th>year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Radial Velocity</td>
      <td>1</td>
      <td>269.300</td>
      <td>7.10</td>
      <td>77.40</td>
      <td>2006</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Radial Velocity</td>
      <td>1</td>
      <td>874.774</td>
      <td>2.21</td>
      <td>56.95</td>
      <td>2008</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Radial Velocity</td>
      <td>1</td>
      <td>763.000</td>
      <td>2.60</td>
      <td>19.84</td>
      <td>2011</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Radial Velocity</td>
      <td>1</td>
      <td>326.030</td>
      <td>19.40</td>
      <td>110.62</td>
      <td>2007</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Radial Velocity</td>
      <td>1</td>
      <td>516.220</td>
      <td>10.50</td>
      <td>119.47</td>
      <td>2009</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 1035 entries, 0 to 1034
    Data columns (total 6 columns):
    method            1035 non-null object
    number            1035 non-null int64
    orbital_period    992 non-null float64
    mass              513 non-null float64
    distance          808 non-null float64
    year              1035 non-null int64
    dtypes: float64(3), int64(2), object(1)
    memory usage: 48.6+ KB
    


```python
df.dtypes
```




    method             object
    number              int64
    orbital_period    float64
    mass              float64
    distance          float64
    year                int64
    dtype: object




```python
import pandas as pd
df.method = pd.Categorical(df.method)
df.dtypes
```




    method            category
    number               int64
    orbital_period     float64
    mass               float64
    distance           float64
    year                 int64
    dtype: object




```python
df.head(100)
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
      <th>method</th>
      <th>number</th>
      <th>orbital_period</th>
      <th>mass</th>
      <th>distance</th>
      <th>year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Radial Velocity</td>
      <td>1</td>
      <td>269.300000</td>
      <td>7.10</td>
      <td>77.40</td>
      <td>2006</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Radial Velocity</td>
      <td>1</td>
      <td>874.774000</td>
      <td>2.21</td>
      <td>56.95</td>
      <td>2008</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Radial Velocity</td>
      <td>1</td>
      <td>763.000000</td>
      <td>2.60</td>
      <td>19.84</td>
      <td>2011</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Radial Velocity</td>
      <td>1</td>
      <td>326.030000</td>
      <td>19.40</td>
      <td>110.62</td>
      <td>2007</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Radial Velocity</td>
      <td>1</td>
      <td>516.220000</td>
      <td>10.50</td>
      <td>119.47</td>
      <td>2009</td>
    </tr>
    <tr>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <td>95</td>
      <td>Transit</td>
      <td>1</td>
      <td>4.037896</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2009</td>
    </tr>
    <tr>
      <td>96</td>
      <td>Transit</td>
      <td>1</td>
      <td>8.886593</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2009</td>
    </tr>
    <tr>
      <td>97</td>
      <td>Transit</td>
      <td>2</td>
      <td>0.853585</td>
      <td>NaN</td>
      <td>150.00</td>
      <td>2009</td>
    </tr>
    <tr>
      <td>98</td>
      <td>Radial Velocity</td>
      <td>2</td>
      <td>3.698000</td>
      <td>NaN</td>
      <td>150.00</td>
      <td>2009</td>
    </tr>
    <tr>
      <td>99</td>
      <td>Transit</td>
      <td>1</td>
      <td>6.212290</td>
      <td>NaN</td>
      <td>380.00</td>
      <td>2010</td>
    </tr>
  </tbody>
</table>
<p>100 rows × 6 columns</p>
</div>




```python
df.tail(10)
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
      <th>method</th>
      <th>number</th>
      <th>orbital_period</th>
      <th>mass</th>
      <th>distance</th>
      <th>year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1025</td>
      <td>Transit</td>
      <td>1</td>
      <td>3.067850</td>
      <td>NaN</td>
      <td>60.0</td>
      <td>2012</td>
    </tr>
    <tr>
      <td>1026</td>
      <td>Transit</td>
      <td>1</td>
      <td>0.925542</td>
      <td>NaN</td>
      <td>470.0</td>
      <td>2014</td>
    </tr>
    <tr>
      <td>1027</td>
      <td>Imaging</td>
      <td>1</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>19.2</td>
      <td>2011</td>
    </tr>
    <tr>
      <td>1028</td>
      <td>Transit</td>
      <td>1</td>
      <td>3.352057</td>
      <td>NaN</td>
      <td>3200.0</td>
      <td>2012</td>
    </tr>
    <tr>
      <td>1029</td>
      <td>Imaging</td>
      <td>1</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>10.1</td>
      <td>2012</td>
    </tr>
    <tr>
      <td>1030</td>
      <td>Transit</td>
      <td>1</td>
      <td>3.941507</td>
      <td>NaN</td>
      <td>172.0</td>
      <td>2006</td>
    </tr>
    <tr>
      <td>1031</td>
      <td>Transit</td>
      <td>1</td>
      <td>2.615864</td>
      <td>NaN</td>
      <td>148.0</td>
      <td>2007</td>
    </tr>
    <tr>
      <td>1032</td>
      <td>Transit</td>
      <td>1</td>
      <td>3.191524</td>
      <td>NaN</td>
      <td>174.0</td>
      <td>2007</td>
    </tr>
    <tr>
      <td>1033</td>
      <td>Transit</td>
      <td>1</td>
      <td>4.125083</td>
      <td>NaN</td>
      <td>293.0</td>
      <td>2008</td>
    </tr>
    <tr>
      <td>1034</td>
      <td>Transit</td>
      <td>1</td>
      <td>4.187757</td>
      <td>NaN</td>
      <td>260.0</td>
      <td>2008</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.shape
```




    (1035, 6)




```python
df.columns
```




    Index(['method', 'number', 'orbital_period', 'mass', 'distance', 'year'], dtype='object')




```python
df.describe()
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
      <th>number</th>
      <th>orbital_period</th>
      <th>mass</th>
      <th>distance</th>
      <th>year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>count</td>
      <td>1035.000000</td>
      <td>992.000000</td>
      <td>513.000000</td>
      <td>808.000000</td>
      <td>1035.000000</td>
    </tr>
    <tr>
      <td>mean</td>
      <td>1.785507</td>
      <td>2002.917596</td>
      <td>2.638161</td>
      <td>264.069282</td>
      <td>2009.070531</td>
    </tr>
    <tr>
      <td>std</td>
      <td>1.240976</td>
      <td>26014.728304</td>
      <td>3.818617</td>
      <td>733.116493</td>
      <td>3.972567</td>
    </tr>
    <tr>
      <td>min</td>
      <td>1.000000</td>
      <td>0.090706</td>
      <td>0.003600</td>
      <td>1.350000</td>
      <td>1989.000000</td>
    </tr>
    <tr>
      <td>25%</td>
      <td>1.000000</td>
      <td>5.442540</td>
      <td>0.229000</td>
      <td>32.560000</td>
      <td>2007.000000</td>
    </tr>
    <tr>
      <td>50%</td>
      <td>1.000000</td>
      <td>39.979500</td>
      <td>1.260000</td>
      <td>55.250000</td>
      <td>2010.000000</td>
    </tr>
    <tr>
      <td>75%</td>
      <td>2.000000</td>
      <td>526.005000</td>
      <td>3.040000</td>
      <td>178.500000</td>
      <td>2012.000000</td>
    </tr>
    <tr>
      <td>max</td>
      <td>7.000000</td>
      <td>730000.000000</td>
      <td>25.000000</td>
      <td>8500.000000</td>
      <td>2014.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.describe().T
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
      <th>count</th>
      <th>mean</th>
      <th>std</th>
      <th>min</th>
      <th>25%</th>
      <th>50%</th>
      <th>75%</th>
      <th>max</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>number</td>
      <td>1035.0</td>
      <td>1.785507</td>
      <td>1.240976</td>
      <td>1.000000</td>
      <td>1.00000</td>
      <td>1.0000</td>
      <td>2.000</td>
      <td>7.0</td>
    </tr>
    <tr>
      <td>orbital_period</td>
      <td>992.0</td>
      <td>2002.917596</td>
      <td>26014.728304</td>
      <td>0.090706</td>
      <td>5.44254</td>
      <td>39.9795</td>
      <td>526.005</td>
      <td>730000.0</td>
    </tr>
    <tr>
      <td>mass</td>
      <td>513.0</td>
      <td>2.638161</td>
      <td>3.818617</td>
      <td>0.003600</td>
      <td>0.22900</td>
      <td>1.2600</td>
      <td>3.040</td>
      <td>25.0</td>
    </tr>
    <tr>
      <td>distance</td>
      <td>808.0</td>
      <td>264.069282</td>
      <td>733.116493</td>
      <td>1.350000</td>
      <td>32.56000</td>
      <td>55.2500</td>
      <td>178.500</td>
      <td>8500.0</td>
    </tr>
    <tr>
      <td>year</td>
      <td>1035.0</td>
      <td>2009.070531</td>
      <td>3.972567</td>
      <td>1989.000000</td>
      <td>2007.00000</td>
      <td>2010.0000</td>
      <td>2012.000</td>
      <td>2014.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.describe(include='all')
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
      <th>method</th>
      <th>number</th>
      <th>orbital_period</th>
      <th>mass</th>
      <th>distance</th>
      <th>year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>count</td>
      <td>1035</td>
      <td>1035.000000</td>
      <td>992.000000</td>
      <td>513.000000</td>
      <td>808.000000</td>
      <td>1035.000000</td>
    </tr>
    <tr>
      <td>unique</td>
      <td>10</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <td>top</td>
      <td>Radial Velocity</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <td>freq</td>
      <td>553</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <td>mean</td>
      <td>NaN</td>
      <td>1.785507</td>
      <td>2002.917596</td>
      <td>2.638161</td>
      <td>264.069282</td>
      <td>2009.070531</td>
    </tr>
    <tr>
      <td>std</td>
      <td>NaN</td>
      <td>1.240976</td>
      <td>26014.728304</td>
      <td>3.818617</td>
      <td>733.116493</td>
      <td>3.972567</td>
    </tr>
    <tr>
      <td>min</td>
      <td>NaN</td>
      <td>1.000000</td>
      <td>0.090706</td>
      <td>0.003600</td>
      <td>1.350000</td>
      <td>1989.000000</td>
    </tr>
    <tr>
      <td>25%</td>
      <td>NaN</td>
      <td>1.000000</td>
      <td>5.442540</td>
      <td>0.229000</td>
      <td>32.560000</td>
      <td>2007.000000</td>
    </tr>
    <tr>
      <td>50%</td>
      <td>NaN</td>
      <td>1.000000</td>
      <td>39.979500</td>
      <td>1.260000</td>
      <td>55.250000</td>
      <td>2010.000000</td>
    </tr>
    <tr>
      <td>75%</td>
      <td>NaN</td>
      <td>2.000000</td>
      <td>526.005000</td>
      <td>3.040000</td>
      <td>178.500000</td>
      <td>2012.000000</td>
    </tr>
    <tr>
      <td>max</td>
      <td>NaN</td>
      <td>7.000000</td>
      <td>730000.000000</td>
      <td>25.000000</td>
      <td>8500.000000</td>
      <td>2014.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.nunique()
```




    method             10
    number              7
    orbital_period    988
    mass              381
    distance          552
    year               23
    dtype: int64




```python
df.isnull().values.any()
```




    True




```python
df.isnull().sum()
```




    method              0
    number              0
    orbital_period     43
    mass              522
    distance          227
    year                0
    dtype: int64




```python
df['orbital_period'].fillna(0, inplace=True)
df.isnull().sum()
```




    method              0
    number              0
    orbital_period      0
    mass              522
    distance          227
    year                0
    dtype: int64




```python
import numpy as np
df['mass'].fillna(np.mean(df.mass), inplace=True)
df.isnull().sum()
```




    method              0
    number              0
    orbital_period      0
    mass                0
    distance          227
    year                0
    dtype: int64



### Properties of categorical Variables


```python
catDF = df.select_dtypes(include=['category'])
catDF.head(5)
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
      <th>method</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Radial Velocity</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Radial Velocity</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Radial Velocity</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Radial Velocity</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Radial Velocity</td>
    </tr>
  </tbody>
</table>
</div>




```python
catDF.method.unique()
```




    [Radial Velocity, Imaging, Eclipse Timing Variations, Transit, Astrometry, Transit Timing Variations, Orbital Brightness Modulation, Microlensing, Pulsar Timing, Pulsation Timing Variations]
    Categories (10, object): [Radial Velocity, Imaging, Eclipse Timing Variations, Transit, ..., Orbital Brightness Modulation, Microlensing, Pulsar Timing, Pulsation Timing Variations]




```python
catDF['method'].value_counts().count()
```




    10




```python
catDF['method'].value_counts()
```




    Radial Velocity                  553
    Transit                          397
    Imaging                           38
    Microlensing                      23
    Eclipse Timing Variations          9
    Pulsar Timing                      5
    Transit Timing Variations          4
    Orbital Brightness Modulation      3
    Astrometry                         2
    Pulsation Timing Variations        1
    Name: method, dtype: int64




```python
catDF['method'].value_counts().plot.barh()
```




    <matplotlib.axes._subplots.AxesSubplot at 0x290cbcc9448>




![png](output_23_1.png)



```python
from pandas.api.types import CategoricalDtype
catDF = catDF.astype(CategoricalDtype(ordered = True))
catDF.method.head()
```




    0    Radial Velocity
    1    Radial Velocity
    2    Radial Velocity
    3    Radial Velocity
    4    Radial Velocity
    Name: method, dtype: category
    Categories (10, object): [Astrometry < Eclipse Timing Variations < Imaging < Microlensing ... Pulsation Timing Variations < Radial Velocity < Transit < Transit Timing Variations]


