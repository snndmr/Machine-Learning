## Aggregation and Grouping


```python
import seaborn as sns

sns.get_dataset_names()
```

    C:\Users\SNN\Anaconda3\lib\site-packages\seaborn\utils.py:376: UserWarning: No parser was explicitly specified, so I'm using the best available HTML parser for this system ("lxml"). This usually isn't a problem, but if you run this code on another system, or in a different virtual environment, it may use a different parser and behave differently.
    
    The code that caused this warning is on line 376 of the file C:\Users\SNN\Anaconda3\lib\site-packages\seaborn\utils.py. To get rid of this warning, pass the additional argument 'features="lxml"' to the BeautifulSoup constructor.
    
      gh_list = BeautifulSoup(http)
    




    ['anscombe',
     'attention',
     'brain_networks',
     'car_crashes',
     'diamonds',
     'dots',
     'exercise',
     'flights',
     'fmri',
     'gammas',
     'iris',
     'mpg',
     'planets',
     'tips',
     'titanic']




```python
df = sns.load_dataset('planets')
df
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
      <td>1030</td>
      <td>Transit</td>
      <td>1</td>
      <td>3.941507</td>
      <td>NaN</td>
      <td>172.00</td>
      <td>2006</td>
    </tr>
    <tr>
      <td>1031</td>
      <td>Transit</td>
      <td>1</td>
      <td>2.615864</td>
      <td>NaN</td>
      <td>148.00</td>
      <td>2007</td>
    </tr>
    <tr>
      <td>1032</td>
      <td>Transit</td>
      <td>1</td>
      <td>3.191524</td>
      <td>NaN</td>
      <td>174.00</td>
      <td>2007</td>
    </tr>
    <tr>
      <td>1033</td>
      <td>Transit</td>
      <td>1</td>
      <td>4.125083</td>
      <td>NaN</td>
      <td>293.00</td>
      <td>2008</td>
    </tr>
    <tr>
      <td>1034</td>
      <td>Transit</td>
      <td>1</td>
      <td>4.187757</td>
      <td>NaN</td>
      <td>260.00</td>
      <td>2008</td>
    </tr>
  </tbody>
</table>
<p>1035 rows × 6 columns</p>
</div>




```python
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
df.shape
```




    (1035, 6)




```python
df.count()
```




    method            1035
    number            1035
    orbital_period     992
    mass               513
    distance           808
    year              1035
    dtype: int64




```python
df['mass'].count()
```




    513




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
df['mass'].describe()
```




    count    513.000000
    mean       2.638161
    std        3.818617
    min        0.003600
    25%        0.229000
    50%        1.260000
    75%        3.040000
    max       25.000000
    Name: mass, dtype: float64




```python
import pandas as pd

df = pd.DataFrame({
    'Groups' : ['A', 'B', 'C', 'A', 'B', 'C'],
    'Data'   : [10, 11, 12, 13, 14, 15]
})
df
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
      <th>Groups</th>
      <th>Data</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>A</td>
      <td>10</td>
    </tr>
    <tr>
      <td>1</td>
      <td>B</td>
      <td>11</td>
    </tr>
    <tr>
      <td>2</td>
      <td>C</td>
      <td>12</td>
    </tr>
    <tr>
      <td>3</td>
      <td>A</td>
      <td>13</td>
    </tr>
    <tr>
      <td>4</td>
      <td>B</td>
      <td>14</td>
    </tr>
    <tr>
      <td>5</td>
      <td>C</td>
      <td>15</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.groupby('Groups')
```




    <pandas.core.groupby.generic.DataFrameGroupBy object at 0x000001B3F93F0B48>




```python
df.groupby('Groups').sum()
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
      <th>Data</th>
    </tr>
    <tr>
      <th>Groups</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>A</td>
      <td>23</td>
    </tr>
    <tr>
      <td>B</td>
      <td>25</td>
    </tr>
    <tr>
      <td>C</td>
      <td>27</td>
    </tr>
  </tbody>
</table>
</div>




```python
df = sns.load_dataset('planets')
```


```python
df.groupby('mass').sum()
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
      <th>distance</th>
      <th>year</th>
    </tr>
    <tr>
      <th>mass</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0.00360</td>
      <td>1</td>
      <td>3.23570</td>
      <td>1.35</td>
      <td>2012</td>
    </tr>
    <tr>
      <td>0.00600</td>
      <td>4</td>
      <td>3.14942</td>
      <td>6.27</td>
      <td>2005</td>
    </tr>
    <tr>
      <td>0.00755</td>
      <td>3</td>
      <td>40.11400</td>
      <td>6.06</td>
      <td>2011</td>
    </tr>
    <tr>
      <td>0.00800</td>
      <td>12</td>
      <td>101.26600</td>
      <td>13.60</td>
      <td>4026</td>
    </tr>
    <tr>
      <td>0.00850</td>
      <td>3</td>
      <td>18.31500</td>
      <td>6.06</td>
      <td>2011</td>
    </tr>
    <tr>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <td>19.40000</td>
      <td>1</td>
      <td>326.03000</td>
      <td>110.62</td>
      <td>2007</td>
    </tr>
    <tr>
      <td>19.80000</td>
      <td>1</td>
      <td>677.80000</td>
      <td>0.00</td>
      <td>2007</td>
    </tr>
    <tr>
      <td>20.60000</td>
      <td>1</td>
      <td>305.50000</td>
      <td>92.51</td>
      <td>2013</td>
    </tr>
    <tr>
      <td>21.42000</td>
      <td>2</td>
      <td>379.63000</td>
      <td>0.00</td>
      <td>2009</td>
    </tr>
    <tr>
      <td>25.00000</td>
      <td>1</td>
      <td>2371.00000</td>
      <td>37.05</td>
      <td>2008</td>
    </tr>
  </tbody>
</table>
<p>381 rows × 4 columns</p>
</div>




```python
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
df.groupby('method')['orbital_period']
```




    <pandas.core.groupby.generic.SeriesGroupBy object at 0x000001B3F942FF08>




```python
df.groupby('method')['orbital_period'].sum()
```




    method
    Astrometry                       1.262360e+03
    Eclipse Timing Variations        4.276480e+04
    Imaging                          1.418973e+06
    Microlensing                     2.207500e+04
    Orbital Brightness Modulation    2.127920e+00
    Pulsar Timing                    3.671511e+04
    Pulsation Timing Variations      1.170000e+03
    Radial Velocity                  4.553151e+05
    Transit                          8.377523e+03
    Transit Timing Variations        2.393505e+02
    Name: orbital_period, dtype: float64




```python
df.groupby('method')['orbital_period'].describe()
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
    <tr>
      <th>method</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Astrometry</td>
      <td>2.0</td>
      <td>631.180000</td>
      <td>544.217663</td>
      <td>246.360000</td>
      <td>438.770000</td>
      <td>631.180000</td>
      <td>823.590000</td>
      <td>1016.000000</td>
    </tr>
    <tr>
      <td>Eclipse Timing Variations</td>
      <td>9.0</td>
      <td>4751.644444</td>
      <td>2499.130945</td>
      <td>1916.250000</td>
      <td>2900.000000</td>
      <td>4343.500000</td>
      <td>5767.000000</td>
      <td>10220.000000</td>
    </tr>
    <tr>
      <td>Imaging</td>
      <td>12.0</td>
      <td>118247.737500</td>
      <td>213978.177277</td>
      <td>4639.150000</td>
      <td>8343.900000</td>
      <td>27500.000000</td>
      <td>94250.000000</td>
      <td>730000.000000</td>
    </tr>
    <tr>
      <td>Microlensing</td>
      <td>7.0</td>
      <td>3153.571429</td>
      <td>1113.166333</td>
      <td>1825.000000</td>
      <td>2375.000000</td>
      <td>3300.000000</td>
      <td>3550.000000</td>
      <td>5100.000000</td>
    </tr>
    <tr>
      <td>Orbital Brightness Modulation</td>
      <td>3.0</td>
      <td>0.709307</td>
      <td>0.725493</td>
      <td>0.240104</td>
      <td>0.291496</td>
      <td>0.342887</td>
      <td>0.943908</td>
      <td>1.544929</td>
    </tr>
    <tr>
      <td>Pulsar Timing</td>
      <td>5.0</td>
      <td>7343.021201</td>
      <td>16313.265573</td>
      <td>0.090706</td>
      <td>25.262000</td>
      <td>66.541900</td>
      <td>98.211400</td>
      <td>36525.000000</td>
    </tr>
    <tr>
      <td>Pulsation Timing Variations</td>
      <td>1.0</td>
      <td>1170.000000</td>
      <td>NaN</td>
      <td>1170.000000</td>
      <td>1170.000000</td>
      <td>1170.000000</td>
      <td>1170.000000</td>
      <td>1170.000000</td>
    </tr>
    <tr>
      <td>Radial Velocity</td>
      <td>553.0</td>
      <td>823.354680</td>
      <td>1454.926210</td>
      <td>0.736540</td>
      <td>38.021000</td>
      <td>360.200000</td>
      <td>982.000000</td>
      <td>17337.500000</td>
    </tr>
    <tr>
      <td>Transit</td>
      <td>397.0</td>
      <td>21.102073</td>
      <td>46.185893</td>
      <td>0.355000</td>
      <td>3.160630</td>
      <td>5.714932</td>
      <td>16.145700</td>
      <td>331.600590</td>
    </tr>
    <tr>
      <td>Transit Timing Variations</td>
      <td>3.0</td>
      <td>79.783500</td>
      <td>71.599884</td>
      <td>22.339500</td>
      <td>39.675250</td>
      <td>57.011000</td>
      <td>108.505500</td>
      <td>160.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
import numpy as np

df = pd.DataFrame({
    'Groups' : ['A', 'B', 'C', 'A', 'B', 'C'],
    'Var X'   : np.random.randint(0, 100, 6),
    'Var Y'   : np.random.randint(100, 1000, 6)
})
df
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
      <th>Groups</th>
      <th>Var X</th>
      <th>Var Y</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>A</td>
      <td>55</td>
      <td>598</td>
    </tr>
    <tr>
      <td>1</td>
      <td>B</td>
      <td>48</td>
      <td>605</td>
    </tr>
    <tr>
      <td>2</td>
      <td>C</td>
      <td>18</td>
      <td>721</td>
    </tr>
    <tr>
      <td>3</td>
      <td>A</td>
      <td>92</td>
      <td>503</td>
    </tr>
    <tr>
      <td>4</td>
      <td>B</td>
      <td>9</td>
      <td>657</td>
    </tr>
    <tr>
      <td>5</td>
      <td>C</td>
      <td>87</td>
      <td>987</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.groupby('Groups').aggregate(['min', np.median, max])
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead tr th {
        text-align: left;
    }

    .dataframe thead tr:last-of-type th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr>
      <th></th>
      <th colspan="3" halign="left">Var X</th>
      <th colspan="3" halign="left">Var Y</th>
    </tr>
    <tr>
      <th></th>
      <th>min</th>
      <th>median</th>
      <th>max</th>
      <th>min</th>
      <th>median</th>
      <th>max</th>
    </tr>
    <tr>
      <th>Groups</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>A</td>
      <td>55</td>
      <td>73.5</td>
      <td>92</td>
      <td>503</td>
      <td>550.5</td>
      <td>598</td>
    </tr>
    <tr>
      <td>B</td>
      <td>9</td>
      <td>28.5</td>
      <td>48</td>
      <td>605</td>
      <td>631.0</td>
      <td>657</td>
    </tr>
    <tr>
      <td>C</td>
      <td>18</td>
      <td>52.5</td>
      <td>87</td>
      <td>721</td>
      <td>854.0</td>
      <td>987</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.groupby('Groups').aggregate({'Var X' : 'min', 'Var Y' : 'max'})
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
      <th>Var X</th>
      <th>Var Y</th>
    </tr>
    <tr>
      <th>Groups</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>A</td>
      <td>55</td>
      <td>598</td>
    </tr>
    <tr>
      <td>B</td>
      <td>9</td>
      <td>657</td>
    </tr>
    <tr>
      <td>C</td>
      <td>18</td>
      <td>987</td>
    </tr>
  </tbody>
</table>
</div>




```python
def filter_func(x):
    return x['Var X'].std() > 4
df.groupby('Groups').filter(filter_func)
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
      <th>Groups</th>
      <th>Var X</th>
      <th>Var Y</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>A</td>
      <td>55</td>
      <td>598</td>
    </tr>
    <tr>
      <td>1</td>
      <td>B</td>
      <td>48</td>
      <td>605</td>
    </tr>
    <tr>
      <td>2</td>
      <td>C</td>
      <td>18</td>
      <td>721</td>
    </tr>
    <tr>
      <td>3</td>
      <td>A</td>
      <td>92</td>
      <td>503</td>
    </tr>
    <tr>
      <td>4</td>
      <td>B</td>
      <td>9</td>
      <td>657</td>
    </tr>
    <tr>
      <td>5</td>
      <td>C</td>
      <td>87</td>
      <td>987</td>
    </tr>
  </tbody>
</table>
</div>




```python
def filter_func(x):
    return x['Var Y'].std() > 200
df.groupby('Groups').filter(filter_func)
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
      <th>Groups</th>
      <th>Var X</th>
      <th>Var Y</th>
    </tr>
  </thead>
  <tbody>
  </tbody>
</table>
</div>




```python
df.groupby('Groups').transform(lambda x: (x - x.mean()) / x.std())
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
      <th>Var X</th>
      <th>Var Y</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>-0.707107</td>
      <td>0.707107</td>
    </tr>
    <tr>
      <td>1</td>
      <td>0.707107</td>
      <td>-0.707107</td>
    </tr>
    <tr>
      <td>2</td>
      <td>-0.707107</td>
      <td>-0.707107</td>
    </tr>
    <tr>
      <td>3</td>
      <td>0.707107</td>
      <td>-0.707107</td>
    </tr>
    <tr>
      <td>4</td>
      <td>-0.707107</td>
      <td>0.707107</td>
    </tr>
    <tr>
      <td>5</td>
      <td>0.707107</td>
      <td>0.707107</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.groupby('Groups').apply(np.sum)
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
      <th>Groups</th>
      <th>Var X</th>
      <th>Var Y</th>
    </tr>
    <tr>
      <th>Groups</th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>A</td>
      <td>AA</td>
      <td>147</td>
      <td>1101</td>
    </tr>
    <tr>
      <td>B</td>
      <td>BB</td>
      <td>57</td>
      <td>1262</td>
    </tr>
    <tr>
      <td>C</td>
      <td>CC</td>
      <td>105</td>
      <td>1708</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.groupby('Groups').apply(np.mean)
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
      <th>Var X</th>
      <th>Var Y</th>
    </tr>
    <tr>
      <th>Groups</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>A</td>
      <td>73.5</td>
      <td>550.5</td>
    </tr>
    <tr>
      <td>B</td>
      <td>28.5</td>
      <td>631.0</td>
    </tr>
    <tr>
      <td>C</td>
      <td>52.5</td>
      <td>854.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
L = [0, 1, 0, 1, 2, 0]
df.groupby(L).sum()
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
      <th>Var X</th>
      <th>Var Y</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>160</td>
      <td>2306</td>
    </tr>
    <tr>
      <td>1</td>
      <td>140</td>
      <td>1108</td>
    </tr>
    <tr>
      <td>2</td>
      <td>9</td>
      <td>657</td>
    </tr>
  </tbody>
</table>
</div>


