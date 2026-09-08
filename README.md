# python-for-data-anlaysis-lessons
my course for python
# 📊 Student Performance Data Analysis with Pandas

This project demonstrates how to use **Pandas**, one of the most popular Python libraries for data analysis, to explore, select, filter, and work with a **Student Performance Dataset**.

The project focuses on fundamental Pandas operations that are essential for anyone learning **Data Analysis with Python**.

---

## 📌 Project Overview

In this project, I practiced different techniques for working with data using Pandas, including:

* Selecting a single column
* Selecting multiple columns
* Selecting rows using `loc`
* Selecting rows using `iloc`
* Filtering data using a single condition
* Filtering data using multiple conditions

---

## 🛠️ Technologies Used

* 🐍 **Python 3.x**
* 🐼 **Pandas**
* 📓 **Jupyter Notebook**
* ☁️ **Google Colab**

---

## 📂 Dataset

The project uses a **Student Performance Dataset** containing information about students and their academic performance.

### Example Columns

| Column               | Description                     |
| -------------------- | ------------------------------- |
| `Student_ID`         | Unique student identifier       |
| `Program`            | Student's academic program      |
| `Academic_Status`    | Student's academic status       |
| `Final_Score`        | Student's final score           |
| `Attendance_Percent` | Student's attendance percentage |

---

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

### Common Pandas operators

| Operator | Meaning                  |    |
| -------- | ------------------------ | -- |
| `>`      | Greater than             |    |
| `<`      | Less than                |    |
| `>=`     | Greater than or equal to |    |
| `<=`     | Less than or equal to    |    |
| `==`     | Equal to                 |    |
| `!=`     | Not equal to             |    |
| `&`      | AND                      |    |
| `        | `                        | OR |

---

# 📦 Installation

First, make sure Python is installed on your computer.

Then install Pandas:

```bash
pip install pandas
```

To verify the installation:

```python
import pandas as pd

print(pd.__version__)
```

---

# 🚀 How to Run the Project

### Step 1 — Install Pandas

```bash
pip install pandas
```

### Step 2 — Open the Notebook

You can use either:

* Jupyter Notebook
* Google Colab
* VS Code

### Step 3 — Import Pandas

```python
import pandas as pd
```

### Step 4 — Load the Dataset

For example:

```python
data = pd.read_excel('Student_Performance.xlsx')
```

Or, if your dataset is a CSV file:

```python
data = pd.read_csv('Student_Performance.csv')
```

### Step 5 — Explore the Data

```python
data.head()
```

You can then practice the Pandas operations demonstrated in this project.

---

# 🎯 Learning Objectives

Through this project, I practiced how to:

* Work with Pandas DataFrames
* Select specific columns
* Select multiple columns
* Select rows using `loc`
* Select rows using `iloc`
* Filter data using conditions
* Combine multiple filtering conditions
* Analyze student performance data

---

# 📈 Project Skills

This project helped develop foundational skills in:

**Python • Pandas • Data Manipulation • Data Filtering • Data Selection • Data Analysis**

---

# 👩‍💻 Author

**Deeqo Abdulkadir**

Information Technology Student | Aspiring Data Analyst

---

⭐ **If you find this project useful, feel free to explore the repository and follow my learning journey in Data Analytics.**

