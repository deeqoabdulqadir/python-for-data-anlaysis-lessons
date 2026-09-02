# 🐍 4. Python Data Analysis with Google Colab

## 📥 Importing Libraries

The analysis was performed using **Python in Google Colab**. The Pandas library was imported to read, explore, and analyze the dataset.

```python
import pandas as pd
```

## 📂 Loading the Dataset

The Excel dataset was loaded from Google Drive using Pandas.

```python
date = pd.read_excel("/content/drive/MyDrive/Colab Notebooks/python/Book1211.xlsx")
```

## 🔍 Understanding the Dataset

Several Pandas functions were used to explore and understand the dataset before performing further analysis.

### First 5 Rows

The `head()` function was used to display the first five rows.

```python
date.head()
```

### Last 5 Rows

The `tail()` function was used to display the last five rows of the dataset.

```python
date.tail()
```

### Random Sample

The `sample()` function was used to display a random row from the dataset.

```python
date.sample()
```

### Dataset Shape

The `shape` attribute was used to identify the number of rows and columns.

```python
date.shape
```

**Result:** `300 rows × 7 columns`

### Dataset Columns

The column names were displayed using `columns.tolist()`.

```python
date.columns.tolist()
```

The dataset contains:

* `Student_ID`
* `Program`
* `Attendance_Percent`
* `Assignment_Score`
* `Midterm_Score`
* `Final_Score`
* `Academic_Status`

### Dataset Index

The dataset index was checked using:

```python
date.index
```

The dataset contains a `RangeIndex` from **0 to 299**.

## 📊 Dataset Information

The `info()` function was used to examine the dataset structure, number of non-null values, data types, and memory usage.

```python
date.info()
```

The initial dataset contains **300 records and 7 columns**. The output also shows that some columns contain missing values.

## 🔢 Data Types

The `dtypes` attribute was used to identify the data type of each column.

```python
date.dtypes
```

This step helped identify numeric and text-based columns before performing **data cleaning and further analysis**.

## 📝 Summary

Google Colab and Pandas were used to:

* Import the dataset from Google Drive.
* Inspect the first and last records.
* View random records.
* Check the dataset size.
* Identify column names.
* Examine the dataset index.
* Check missing values.
* Identify column data types.
* Prepare the dataset for further cleaning and analysis.
