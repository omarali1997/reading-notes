# Read 08 Data Analysis with Pandas

># Pandas
* ## What is pandas in Python?

### pandas (all lowercase) is a popular Python-based data analysis toolkit which can be imported using `import pandas as pd`. It presents a diverse range of utilities, ranging from parsing multiple file formats to converting an entire data table into a `NumPy` matrix array. This makes pandas a trusted ally in data science and machine learning.

>## Series
### In pandas, 1-D arrays are referred to a series. A series is created through the `pd.Series` constructor, which has a lot of optional arguments. The most common argument is `data`, which specifies the elements of the series.

### Similar to the NumPy arrays, a pandas series also uses the dtype keyword for manual casting.

```python
import pandas as pd
import numpy as np

ser = pd.Series()
print('{}\n'.format(ser))

ser = pd.Series(10)
print('{}\n'.format(ser))

ser = pd.Series([0, 10, 20, 30, 40, 50, 60, 70, 80, 90])
print('{}\n'.format(ser))

ser = pd.Series([20, 15.7, '10'])
print('{}\n'.format(ser))

# A series from a numpy array
arr = np.array([0, 10, 20, 30, 40, 50])
ser = pd.Series(arr, dtype = np.double)
print('{}\n'.format(ser))

ser = pd.Series([[15, 4], [89, 23.5], [21, 22]])
print('{}\n'.format(ser))

```

### In the code above, there are integers on the left side of the Series elements. These integers are collectively known as the index of the series.

>## Indexing
### A custom index can be defined as long as the index has the same length as the Series.

```python
import pandas as pd

ser = pd.Series([1, 2, 3], index = ['first', 'second', 'third'])
print('{}\n'.format(ser))

ser = pd.Series([50.45, 71, 90], index = [-7, 'second', 18.7])
print('{}\n'.format(ser))
```


>## DataFrame
### A DataFrame is simply a 2-D array. It can be created through the `pd.DataFrame`constructor, which takes in essentially the same arguments as `pd.Series`. However, while a series could be constructed from a scalar (representing a single value Series), a DataFrame cannot.

### The index (row) and column labels of a DataFrame can be defined in the constructor.

```python
import pandas as pd

df = pd.DataFrame()
print('{}\n'.format(df))

df = pd.DataFrame([20, 100, -30])
print('{}\n'.format(df))

df = pd.DataFrame([18, -12], [54, 72])
print('{}\n'.format(df))

df = pd.DataFrame([[18, -12], [54, 72]],
                  index=['row1', 'row2'],
                  columns=['column1', 'column2'])
print('{}\n'.format(df))

df = pd.DataFrame({'a': [18, -12], 'b': [54, 72]},
                  index=['x', 'y'])
print('{}\n'.format(df))
```

>## Addition and deletion

### Rows can be added to a DataFrame using the `append` function, which takes in either a series or another DataFrame. In the case of a series, we either need to specify the `index` for the series or use the `ignore_index` keyword. Setting `ignore_index`=True will change the row labels to integer indexes.

### The `append` method does not alter the original DataFrame. Instead, a new DataFrame with the appended row is created.


>## The drop method

### The drop method allows us to remove columns and rows in a DataFrame. This can be done one of two ways:

1. By using the labels argument to specify the labels of the rows/columns to be dropped. labels works alongside the axis keyword argument (which has a default value of 0) to drop from the rows or columns axis.

2. By directly using the index or columns keyword arguments to specify the labels of the rows or columns directly, without needing to use axis.

```python
import pandas as pd

df = pd.DataFrame([[10, 20, 30], [40, 50, 60]])
ser = pd.Series([70, 80, 90], name='new row')
print('{}\n'.format(df))

df2 = df.append(ser)
print('{}\n'.format(df2))

df3 = df.append(ser, ignore_index = True)
print('{}\n'.format(df3))

df3 = pd.DataFrame([[100, 110, 120],[120, 120, 130]])
df4 = df.append(df3)
print('{}\n'.format(df4))
```

### Similar to `append`, `drop` returns a new DataFrame.

### DataFrames can be concatenated using the `concat` function. `merge` joins two DataFrames using all their common column labels.

>## Further utilities

### pandas has an extensive library of data analysis utilities which allow us to group, sort, filter or describe a dataset. DataFrames can also be represented visually using the `pyplot` API.
