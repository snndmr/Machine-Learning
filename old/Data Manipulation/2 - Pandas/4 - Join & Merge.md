### Join Operation


```python
import numpy as np
import pandas as pd

dfOne = pd.DataFrame({'X' : np.random.randint(10, 20, size = 10), 
                      'Y' : np.random.randint(20, 30, size = 10),
                      'Z' : np.random.randint(30, 40, size = 10)})
dfTwo = dfOne + 20 
```


```python
dfOne
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
      <td>18</td>
      <td>22</td>
      <td>37</td>
    </tr>
    <tr>
      <td>1</td>
      <td>18</td>
      <td>27</td>
      <td>38</td>
    </tr>
    <tr>
      <td>2</td>
      <td>10</td>
      <td>23</td>
      <td>34</td>
    </tr>
    <tr>
      <td>3</td>
      <td>16</td>
      <td>25</td>
      <td>35</td>
    </tr>
    <tr>
      <td>4</td>
      <td>13</td>
      <td>22</td>
      <td>31</td>
    </tr>
    <tr>
      <td>5</td>
      <td>16</td>
      <td>20</td>
      <td>35</td>
    </tr>
    <tr>
      <td>6</td>
      <td>15</td>
      <td>26</td>
      <td>30</td>
    </tr>
    <tr>
      <td>7</td>
      <td>18</td>
      <td>25</td>
      <td>33</td>
    </tr>
    <tr>
      <td>8</td>
      <td>15</td>
      <td>29</td>
      <td>39</td>
    </tr>
    <tr>
      <td>9</td>
      <td>17</td>
      <td>20</td>
      <td>34</td>
    </tr>
  </tbody>
</table>
</div>




```python
dfTwo
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
      <td>38</td>
      <td>42</td>
      <td>57</td>
    </tr>
    <tr>
      <td>1</td>
      <td>38</td>
      <td>47</td>
      <td>58</td>
    </tr>
    <tr>
      <td>2</td>
      <td>30</td>
      <td>43</td>
      <td>54</td>
    </tr>
    <tr>
      <td>3</td>
      <td>36</td>
      <td>45</td>
      <td>55</td>
    </tr>
    <tr>
      <td>4</td>
      <td>33</td>
      <td>42</td>
      <td>51</td>
    </tr>
    <tr>
      <td>5</td>
      <td>36</td>
      <td>40</td>
      <td>55</td>
    </tr>
    <tr>
      <td>6</td>
      <td>35</td>
      <td>46</td>
      <td>50</td>
    </tr>
    <tr>
      <td>7</td>
      <td>38</td>
      <td>45</td>
      <td>53</td>
    </tr>
    <tr>
      <td>8</td>
      <td>35</td>
      <td>49</td>
      <td>59</td>
    </tr>
    <tr>
      <td>9</td>
      <td>37</td>
      <td>40</td>
      <td>54</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.concat([dfOne, dfTwo])
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
      <td>18</td>
      <td>22</td>
      <td>37</td>
    </tr>
    <tr>
      <td>1</td>
      <td>18</td>
      <td>27</td>
      <td>38</td>
    </tr>
    <tr>
      <td>2</td>
      <td>10</td>
      <td>23</td>
      <td>34</td>
    </tr>
    <tr>
      <td>3</td>
      <td>16</td>
      <td>25</td>
      <td>35</td>
    </tr>
    <tr>
      <td>4</td>
      <td>13</td>
      <td>22</td>
      <td>31</td>
    </tr>
    <tr>
      <td>5</td>
      <td>16</td>
      <td>20</td>
      <td>35</td>
    </tr>
    <tr>
      <td>6</td>
      <td>15</td>
      <td>26</td>
      <td>30</td>
    </tr>
    <tr>
      <td>7</td>
      <td>18</td>
      <td>25</td>
      <td>33</td>
    </tr>
    <tr>
      <td>8</td>
      <td>15</td>
      <td>29</td>
      <td>39</td>
    </tr>
    <tr>
      <td>9</td>
      <td>17</td>
      <td>20</td>
      <td>34</td>
    </tr>
    <tr>
      <td>0</td>
      <td>38</td>
      <td>42</td>
      <td>57</td>
    </tr>
    <tr>
      <td>1</td>
      <td>38</td>
      <td>47</td>
      <td>58</td>
    </tr>
    <tr>
      <td>2</td>
      <td>30</td>
      <td>43</td>
      <td>54</td>
    </tr>
    <tr>
      <td>3</td>
      <td>36</td>
      <td>45</td>
      <td>55</td>
    </tr>
    <tr>
      <td>4</td>
      <td>33</td>
      <td>42</td>
      <td>51</td>
    </tr>
    <tr>
      <td>5</td>
      <td>36</td>
      <td>40</td>
      <td>55</td>
    </tr>
    <tr>
      <td>6</td>
      <td>35</td>
      <td>46</td>
      <td>50</td>
    </tr>
    <tr>
      <td>7</td>
      <td>38</td>
      <td>45</td>
      <td>53</td>
    </tr>
    <tr>
      <td>8</td>
      <td>35</td>
      <td>49</td>
      <td>59</td>
    </tr>
    <tr>
      <td>9</td>
      <td>37</td>
      <td>40</td>
      <td>54</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.concat([dfOne, dfTwo], axis = 1)
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
      <th>X</th>
      <th>Y</th>
      <th>Z</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>18</td>
      <td>22</td>
      <td>37</td>
      <td>38</td>
      <td>42</td>
      <td>57</td>
    </tr>
    <tr>
      <td>1</td>
      <td>18</td>
      <td>27</td>
      <td>38</td>
      <td>38</td>
      <td>47</td>
      <td>58</td>
    </tr>
    <tr>
      <td>2</td>
      <td>10</td>
      <td>23</td>
      <td>34</td>
      <td>30</td>
      <td>43</td>
      <td>54</td>
    </tr>
    <tr>
      <td>3</td>
      <td>16</td>
      <td>25</td>
      <td>35</td>
      <td>36</td>
      <td>45</td>
      <td>55</td>
    </tr>
    <tr>
      <td>4</td>
      <td>13</td>
      <td>22</td>
      <td>31</td>
      <td>33</td>
      <td>42</td>
      <td>51</td>
    </tr>
    <tr>
      <td>5</td>
      <td>16</td>
      <td>20</td>
      <td>35</td>
      <td>36</td>
      <td>40</td>
      <td>55</td>
    </tr>
    <tr>
      <td>6</td>
      <td>15</td>
      <td>26</td>
      <td>30</td>
      <td>35</td>
      <td>46</td>
      <td>50</td>
    </tr>
    <tr>
      <td>7</td>
      <td>18</td>
      <td>25</td>
      <td>33</td>
      <td>38</td>
      <td>45</td>
      <td>53</td>
    </tr>
    <tr>
      <td>8</td>
      <td>15</td>
      <td>29</td>
      <td>39</td>
      <td>35</td>
      <td>49</td>
      <td>59</td>
    </tr>
    <tr>
      <td>9</td>
      <td>17</td>
      <td>20</td>
      <td>34</td>
      <td>37</td>
      <td>40</td>
      <td>54</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.concat([dfOne, dfTwo], ignore_index = True)
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
      <td>18</td>
      <td>22</td>
      <td>37</td>
    </tr>
    <tr>
      <td>1</td>
      <td>18</td>
      <td>27</td>
      <td>38</td>
    </tr>
    <tr>
      <td>2</td>
      <td>10</td>
      <td>23</td>
      <td>34</td>
    </tr>
    <tr>
      <td>3</td>
      <td>16</td>
      <td>25</td>
      <td>35</td>
    </tr>
    <tr>
      <td>4</td>
      <td>13</td>
      <td>22</td>
      <td>31</td>
    </tr>
    <tr>
      <td>5</td>
      <td>16</td>
      <td>20</td>
      <td>35</td>
    </tr>
    <tr>
      <td>6</td>
      <td>15</td>
      <td>26</td>
      <td>30</td>
    </tr>
    <tr>
      <td>7</td>
      <td>18</td>
      <td>25</td>
      <td>33</td>
    </tr>
    <tr>
      <td>8</td>
      <td>15</td>
      <td>29</td>
      <td>39</td>
    </tr>
    <tr>
      <td>9</td>
      <td>17</td>
      <td>20</td>
      <td>34</td>
    </tr>
    <tr>
      <td>10</td>
      <td>38</td>
      <td>42</td>
      <td>57</td>
    </tr>
    <tr>
      <td>11</td>
      <td>38</td>
      <td>47</td>
      <td>58</td>
    </tr>
    <tr>
      <td>12</td>
      <td>30</td>
      <td>43</td>
      <td>54</td>
    </tr>
    <tr>
      <td>13</td>
      <td>36</td>
      <td>45</td>
      <td>55</td>
    </tr>
    <tr>
      <td>14</td>
      <td>33</td>
      <td>42</td>
      <td>51</td>
    </tr>
    <tr>
      <td>15</td>
      <td>36</td>
      <td>40</td>
      <td>55</td>
    </tr>
    <tr>
      <td>16</td>
      <td>35</td>
      <td>46</td>
      <td>50</td>
    </tr>
    <tr>
      <td>17</td>
      <td>38</td>
      <td>45</td>
      <td>53</td>
    </tr>
    <tr>
      <td>18</td>
      <td>35</td>
      <td>49</td>
      <td>59</td>
    </tr>
    <tr>
      <td>19</td>
      <td>37</td>
      <td>40</td>
      <td>54</td>
    </tr>
  </tbody>
</table>
</div>




```python
dfTwo.columns = ['A', 'B', 'C']
dfTwo
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
      <th>A</th>
      <th>B</th>
      <th>C</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>38</td>
      <td>42</td>
      <td>57</td>
    </tr>
    <tr>
      <td>1</td>
      <td>38</td>
      <td>47</td>
      <td>58</td>
    </tr>
    <tr>
      <td>2</td>
      <td>30</td>
      <td>43</td>
      <td>54</td>
    </tr>
    <tr>
      <td>3</td>
      <td>36</td>
      <td>45</td>
      <td>55</td>
    </tr>
    <tr>
      <td>4</td>
      <td>33</td>
      <td>42</td>
      <td>51</td>
    </tr>
    <tr>
      <td>5</td>
      <td>36</td>
      <td>40</td>
      <td>55</td>
    </tr>
    <tr>
      <td>6</td>
      <td>35</td>
      <td>46</td>
      <td>50</td>
    </tr>
    <tr>
      <td>7</td>
      <td>38</td>
      <td>45</td>
      <td>53</td>
    </tr>
    <tr>
      <td>8</td>
      <td>35</td>
      <td>49</td>
      <td>59</td>
    </tr>
    <tr>
      <td>9</td>
      <td>37</td>
      <td>40</td>
      <td>54</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.concat([dfOne, dfTwo])
```

    C:\Users\SNN\Anaconda3\lib\site-packages\ipykernel_launcher.py:1: FutureWarning: Sorting because non-concatenation axis is not aligned. A future version
    of pandas will change to not sort by default.
    
    To accept the future behavior, pass 'sort=False'.
    
    To retain the current behavior and silence the warning, pass 'sort=True'.
    
      """Entry point for launching an IPython kernel.
    




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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>X</th>
      <th>Y</th>
      <th>Z</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>18.0</td>
      <td>22.0</td>
      <td>37.0</td>
    </tr>
    <tr>
      <td>1</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>18.0</td>
      <td>27.0</td>
      <td>38.0</td>
    </tr>
    <tr>
      <td>2</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>10.0</td>
      <td>23.0</td>
      <td>34.0</td>
    </tr>
    <tr>
      <td>3</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>16.0</td>
      <td>25.0</td>
      <td>35.0</td>
    </tr>
    <tr>
      <td>4</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>13.0</td>
      <td>22.0</td>
      <td>31.0</td>
    </tr>
    <tr>
      <td>5</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>16.0</td>
      <td>20.0</td>
      <td>35.0</td>
    </tr>
    <tr>
      <td>6</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>15.0</td>
      <td>26.0</td>
      <td>30.0</td>
    </tr>
    <tr>
      <td>7</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>18.0</td>
      <td>25.0</td>
      <td>33.0</td>
    </tr>
    <tr>
      <td>8</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>15.0</td>
      <td>29.0</td>
      <td>39.0</td>
    </tr>
    <tr>
      <td>9</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>17.0</td>
      <td>20.0</td>
      <td>34.0</td>
    </tr>
    <tr>
      <td>0</td>
      <td>38.0</td>
      <td>42.0</td>
      <td>57.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <td>1</td>
      <td>38.0</td>
      <td>47.0</td>
      <td>58.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <td>2</td>
      <td>30.0</td>
      <td>43.0</td>
      <td>54.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <td>3</td>
      <td>36.0</td>
      <td>45.0</td>
      <td>55.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <td>4</td>
      <td>33.0</td>
      <td>42.0</td>
      <td>51.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <td>5</td>
      <td>36.0</td>
      <td>40.0</td>
      <td>55.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <td>6</td>
      <td>35.0</td>
      <td>46.0</td>
      <td>50.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <td>7</td>
      <td>38.0</td>
      <td>45.0</td>
      <td>53.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <td>8</td>
      <td>35.0</td>
      <td>49.0</td>
      <td>59.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <td>9</td>
      <td>37.0</td>
      <td>40.0</td>
      <td>54.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.concat([dfOne, dfTwo], join = 'inner')
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
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
    </tr>
    <tr>
      <td>1</td>
    </tr>
    <tr>
      <td>2</td>
    </tr>
    <tr>
      <td>3</td>
    </tr>
    <tr>
      <td>4</td>
    </tr>
    <tr>
      <td>5</td>
    </tr>
    <tr>
      <td>6</td>
    </tr>
    <tr>
      <td>7</td>
    </tr>
    <tr>
      <td>8</td>
    </tr>
    <tr>
      <td>9</td>
    </tr>
    <tr>
      <td>0</td>
    </tr>
    <tr>
      <td>1</td>
    </tr>
    <tr>
      <td>2</td>
    </tr>
    <tr>
      <td>3</td>
    </tr>
    <tr>
      <td>4</td>
    </tr>
    <tr>
      <td>5</td>
    </tr>
    <tr>
      <td>6</td>
    </tr>
    <tr>
      <td>7</td>
    </tr>
    <tr>
      <td>8</td>
    </tr>
    <tr>
      <td>9</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.concat([dfOne, dfTwo], join_axes = [dfOne.columns])
```

    C:\Users\SNN\Anaconda3\lib\site-packages\ipykernel_launcher.py:1: FutureWarning: The join_axes-keyword is deprecated. Use .reindex or .reindex_like on the result to achieve the same functionality.
      """Entry point for launching an IPython kernel.
    




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
      <td>18.0</td>
      <td>22.0</td>
      <td>37.0</td>
    </tr>
    <tr>
      <td>1</td>
      <td>18.0</td>
      <td>27.0</td>
      <td>38.0</td>
    </tr>
    <tr>
      <td>2</td>
      <td>10.0</td>
      <td>23.0</td>
      <td>34.0</td>
    </tr>
    <tr>
      <td>3</td>
      <td>16.0</td>
      <td>25.0</td>
      <td>35.0</td>
    </tr>
    <tr>
      <td>4</td>
      <td>13.0</td>
      <td>22.0</td>
      <td>31.0</td>
    </tr>
    <tr>
      <td>5</td>
      <td>16.0</td>
      <td>20.0</td>
      <td>35.0</td>
    </tr>
    <tr>
      <td>6</td>
      <td>15.0</td>
      <td>26.0</td>
      <td>30.0</td>
    </tr>
    <tr>
      <td>7</td>
      <td>18.0</td>
      <td>25.0</td>
      <td>33.0</td>
    </tr>
    <tr>
      <td>8</td>
      <td>15.0</td>
      <td>29.0</td>
      <td>39.0</td>
    </tr>
    <tr>
      <td>9</td>
      <td>17.0</td>
      <td>20.0</td>
      <td>34.0</td>
    </tr>
    <tr>
      <td>0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <td>1</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <td>2</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <td>3</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <td>4</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <td>5</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <td>6</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <td>7</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <td>8</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <td>9</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>



### Merge - Join


```python
dfOne = pd.DataFrame({'Worker' : ['Ali', 'Veli', 'Ayşe', 'Mehmet', 'Ahmet'], 
                      'Group' : ['Engineer', 'Lawyer', 'Accounting', 'HR', 'Engineer']})
dfTwo = pd.DataFrame({'Worker' : ['Ali', 'Veli', 'Ayşe', 'Mehmet', 'Ahmet'], 
                      'Start' : ['2010', '1998', '2005', '2008', '2000']})
```


```python
dfOne
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
      <th>Worker</th>
      <th>Group</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Ali</td>
      <td>Engineer</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Veli</td>
      <td>Lawyer</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Ayşe</td>
      <td>Accounting</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Mehmet</td>
      <td>HR</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Ahmet</td>
      <td>Engineer</td>
    </tr>
  </tbody>
</table>
</div>




```python
dfTwo
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
      <th>Worker</th>
      <th>Start</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Ali</td>
      <td>2010</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Veli</td>
      <td>1998</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Ayşe</td>
      <td>2005</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Mehmet</td>
      <td>2008</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Ahmet</td>
      <td>2000</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.merge(dfOne, dfTwo)
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
      <th>Worker</th>
      <th>Group</th>
      <th>Start</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Ali</td>
      <td>Engineer</td>
      <td>2010</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Veli</td>
      <td>Lawyer</td>
      <td>1998</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Ayşe</td>
      <td>Accounting</td>
      <td>2005</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Mehmet</td>
      <td>HR</td>
      <td>2008</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Ahmet</td>
      <td>Engineer</td>
      <td>2000</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.merge(dfOne, dfTwo, on = 'Worker')
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
      <th>Worker</th>
      <th>Group</th>
      <th>Start</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Ali</td>
      <td>Engineer</td>
      <td>2010</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Veli</td>
      <td>Lawyer</td>
      <td>1998</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Ayşe</td>
      <td>Accounting</td>
      <td>2005</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Mehmet</td>
      <td>HR</td>
      <td>2008</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Ahmet</td>
      <td>Engineer</td>
      <td>2000</td>
    </tr>
  </tbody>
</table>
</div>




```python
dfThr = pd.merge(dfOne, dfTwo)
dfThr
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
      <th>Worker</th>
      <th>Group</th>
      <th>Start</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Ali</td>
      <td>Engineer</td>
      <td>2010</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Veli</td>
      <td>Lawyer</td>
      <td>1998</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Ayşe</td>
      <td>Accounting</td>
      <td>2005</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Mehmet</td>
      <td>HR</td>
      <td>2008</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Ahmet</td>
      <td>Engineer</td>
      <td>2000</td>
    </tr>
  </tbody>
</table>
</div>




```python
dfFou = pd.DataFrame({'Group' : ['Engineer', 'Lawyer', 'Accounting', 'HR'], 
                      'Manager' : ['Hakan', 'Aydın', 'Filiz', 'Can']})
dfFou
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
      <th>Group</th>
      <th>Manager</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Engineer</td>
      <td>Hakan</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Lawyer</td>
      <td>Aydın</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Accounting</td>
      <td>Filiz</td>
    </tr>
    <tr>
      <td>3</td>
      <td>HR</td>
      <td>Can</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.merge(dfThr, dfFou)
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
      <th>Worker</th>
      <th>Group</th>
      <th>Start</th>
      <th>Manager</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Ali</td>
      <td>Engineer</td>
      <td>2010</td>
      <td>Hakan</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Ahmet</td>
      <td>Engineer</td>
      <td>2000</td>
      <td>Hakan</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Veli</td>
      <td>Lawyer</td>
      <td>1998</td>
      <td>Aydın</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Ayşe</td>
      <td>Accounting</td>
      <td>2005</td>
      <td>Filiz</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Mehmet</td>
      <td>HR</td>
      <td>2008</td>
      <td>Can</td>
    </tr>
  </tbody>
</table>
</div>




```python
dfFiv = pd.DataFrame({'Group' : ['Engineer', 'Engineer', 'Accounting', 'Engineer', 'HK', 'HK'], 
                      'Abilities' : ['Math', 'Excel', 'Coding', 'Linux', 'Excel', 'Managemant']})
dfFiv
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
      <th>Group</th>
      <th>Abilities</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Engineer</td>
      <td>Math</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Engineer</td>
      <td>Excel</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Accounting</td>
      <td>Coding</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Engineer</td>
      <td>Linux</td>
    </tr>
    <tr>
      <td>4</td>
      <td>HK</td>
      <td>Excel</td>
    </tr>
    <tr>
      <td>5</td>
      <td>HK</td>
      <td>Managemant</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.merge(dfOne, dfFiv)
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
      <th>Worker</th>
      <th>Group</th>
      <th>Abilities</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Ali</td>
      <td>Engineer</td>
      <td>Math</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Ali</td>
      <td>Engineer</td>
      <td>Excel</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Ali</td>
      <td>Engineer</td>
      <td>Linux</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Ahmet</td>
      <td>Engineer</td>
      <td>Math</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Ahmet</td>
      <td>Engineer</td>
      <td>Excel</td>
    </tr>
    <tr>
      <td>5</td>
      <td>Ahmet</td>
      <td>Engineer</td>
      <td>Linux</td>
    </tr>
    <tr>
      <td>6</td>
      <td>Ayşe</td>
      <td>Accounting</td>
      <td>Coding</td>
    </tr>
  </tbody>
</table>
</div>




```python
dfSix = pd.DataFrame({'Name' : ['Ali', 'Veli', 'Ayşe', 'Mehmet', 'Ahmet'], 
                      'Slary' : ['10000', '5000', '2500', '3000', '6500']})
dfSix
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
      <th>Name</th>
      <th>Slary</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Ali</td>
      <td>10000</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Veli</td>
      <td>5000</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Ayşe</td>
      <td>2500</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Mehmet</td>
      <td>3000</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Ahmet</td>
      <td>6500</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.merge(dfOne, dfSix, left_on='Worker', right_on='Name')
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
      <th>Worker</th>
      <th>Group</th>
      <th>Name</th>
      <th>Slary</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Ali</td>
      <td>Engineer</td>
      <td>Ali</td>
      <td>10000</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Veli</td>
      <td>Lawyer</td>
      <td>Veli</td>
      <td>5000</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Ayşe</td>
      <td>Accounting</td>
      <td>Ayşe</td>
      <td>2500</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Mehmet</td>
      <td>HR</td>
      <td>Mehmet</td>
      <td>3000</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Ahmet</td>
      <td>Engineer</td>
      <td>Ahmet</td>
      <td>6500</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.merge(dfOne, dfSix, left_on='Worker', right_on='Name').drop('Name', axis = 1)
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
      <th>Worker</th>
      <th>Group</th>
      <th>Slary</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Ali</td>
      <td>Engineer</td>
      <td>10000</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Veli</td>
      <td>Lawyer</td>
      <td>5000</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Ayşe</td>
      <td>Accounting</td>
      <td>2500</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Mehmet</td>
      <td>HR</td>
      <td>3000</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Ahmet</td>
      <td>Engineer</td>
      <td>6500</td>
    </tr>
  </tbody>
</table>
</div>




```python
dfAOne = dfOne.set_index('Worker')
```


```python
dfATwo = dfTwo.set_index('Worker')
```


```python
pd.merge(dfAOne, dfATwo, left_index=True, right_index=True)
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
      <th>Group</th>
      <th>Start</th>
    </tr>
    <tr>
      <th>Worker</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Ali</td>
      <td>Engineer</td>
      <td>2010</td>
    </tr>
    <tr>
      <td>Veli</td>
      <td>Lawyer</td>
      <td>1998</td>
    </tr>
    <tr>
      <td>Ayşe</td>
      <td>Accounting</td>
      <td>2005</td>
    </tr>
    <tr>
      <td>Mehmet</td>
      <td>HR</td>
      <td>2008</td>
    </tr>
    <tr>
      <td>Ahmet</td>
      <td>Engineer</td>
      <td>2000</td>
    </tr>
  </tbody>
</table>
</div>




```python
dfAOne.join(dfATwo)
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
      <th>Group</th>
      <th>Start</th>
    </tr>
    <tr>
      <th>Worker</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Ali</td>
      <td>Engineer</td>
      <td>2010</td>
    </tr>
    <tr>
      <td>Veli</td>
      <td>Lawyer</td>
      <td>1998</td>
    </tr>
    <tr>
      <td>Ayşe</td>
      <td>Accounting</td>
      <td>2005</td>
    </tr>
    <tr>
      <td>Mehmet</td>
      <td>HR</td>
      <td>2008</td>
    </tr>
    <tr>
      <td>Ahmet</td>
      <td>Engineer</td>
      <td>2000</td>
    </tr>
  </tbody>
</table>
</div>



#### Overlapping


```python
dfOne = pd.DataFrame({'Name' : ['Ali', 'Veli', 'Ayşe', 'Mehmet', 'Ahmet'], 
                      'Salary' : ['10000', '5000', '2500', '3000', '6500']})
dfTwo = pd.DataFrame({'Name' : ['Ali', 'Veli', 'Ayşe', 'Mehmet', 'Ahmet'], 
                      'Salary' : ['1000', '500', '250', '300', '650']})
pd.merge(dfOne, dfTwo, on = 'Name')
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
      <th>Name</th>
      <th>Salary_x</th>
      <th>Salary_y</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Ali</td>
      <td>10000</td>
      <td>1000</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Veli</td>
      <td>5000</td>
      <td>500</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Ayşe</td>
      <td>2500</td>
      <td>250</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Mehmet</td>
      <td>3000</td>
      <td>300</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Ahmet</td>
      <td>6500</td>
      <td>650</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.merge(dfOne, dfTwo, on = 'Name', suffixes = ['_SALARY', '_EXTRA'])
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
      <th>Name</th>
      <th>Salary_SALARY</th>
      <th>Salary_EXTRA</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Ali</td>
      <td>10000</td>
      <td>1000</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Veli</td>
      <td>5000</td>
      <td>500</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Ayşe</td>
      <td>2500</td>
      <td>250</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Mehmet</td>
      <td>3000</td>
      <td>300</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Ahmet</td>
      <td>6500</td>
      <td>650</td>
    </tr>
  </tbody>
</table>
</div>


