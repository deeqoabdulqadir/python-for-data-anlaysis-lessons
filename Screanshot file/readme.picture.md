# 💻 Pandas Operations

## 1. Selecting a Single Column

A single column can be selected using its column name.

```python
data['Program']
```

This returns the `Program` column from the DataFrame.

---

## 2. Selecting Multiple Columns

Multiple columns can be selected by providing their names inside a list.

```python
data[['Program', 'Academic_Status']]
```

Another example:

```python
data[['Student_ID', 'Program', 'Final_Score']]
```

This allows us to work with only the columns that are relevant to our analysis.

---

## 3. Selecting Rows with `loc`

The `loc` method is used to select rows based on their **index labels**.

### Select one row

```python
data.loc[0]
```

This selects the row with index label `0`.

### Select multiple rows

```python
data.loc[0:5]
```

This selects rows from index `0` through `5`.

> **Note:** `loc` includes the ending label when selecting a range.

---

## 4. Selecting Rows with `iloc`

The `iloc` method selects rows based on their **integer position**.

```python
data.iloc[0:3]
```

This selects the first three rows:

```text
0
1
2
```

Unlike `loc`, the ending position `3` is not included.

---

# 🔎 Filtering Data

Filtering allows us to select only the rows that meet specific conditions.

## 5. Single Condition

To find students whose final score is greater than `70`:

```python
data[data['Final_Score'] > 70]
```

This returns only students whose `Final_Score` is greater than 70.

---

## 6. Multiple Conditions

We can combine multiple conditions using Pandas operators.

For example, to find students whose:

* Final Score is greater than `70`
* Attendance is greater than `80%`

Use:

```python
data[
    (data['Final_Score'] > 70) &
    (data['Attendance_Percent'] > 80)
]
```
