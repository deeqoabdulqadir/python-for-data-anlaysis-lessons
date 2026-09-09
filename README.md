# python-for-data-anlaysis-lessons
my course for python
# 🐍 Python for Data Analysis

## 📚 Lesson 03: Data Cleaning and Data Preparation

Casharkan waxaan ku baranay sida loo isticmaalo **Pandas** si loo akhriyo, loo nadiifiyo, loona diyaariyo data analysis.

---

## 🎯 Topics Covered

* Importing Pandas
* Reading Excel Files
* Renaming Columns
* Checking Column Values
* Replacing Inconsistent Values
* Removing Unnecessary Columns
* Checking Data Types
* Converting Columns to Numeric Data
* Converting Columns to Datetime
* Handling Invalid Values using `errors="coerce"`

---

# 1. 📦 Importing Pandas

Pandas waa Python library loo isticmaalo Data Analysis.

```python
import pandas as pd
```

`pd` waa magaca gaaban ee Pandas.

---

# 2. 📂 Reading Excel Files

Excel file waxaa lagu akhrin karaa `pd.read_excel()`.

```python
df = pd.read_excel('students.xlsx')
```

Si aad u aragto 5-ta row ee ugu horreeya:

```python
df.head()
```

---

# 3. ✏️ Renaming Columns

Column names waxaa lagu beddeli karaa `rename()`.

```python
df.rename(columns={
    'Student ID': 'Student_ID',
    'Final Score': 'Final_Score'
}, inplace=True)
```

Si aad u hubiso column names-ka:

```python
df.columns
```

---

# 4. 🔍 Checking Column Values

Si aad u aragto values-ka kala duwan ee column:

```python
df['Program'].unique()
```

Si aad u aragto tirada value kasta:

```python
df['Program'].value_counts()
```

---

# 5. 🔄 Replacing Inconsistent Values

Mararka qaar xogta waxaa ku jiri kara values isku macne ah laakiin siyaabo kala duwan loo qoray.

Tusaale:

```python
df['Program'] = df['Program'].replace({
    'CS': 'Computer Science',
    'computer science': 'Computer Science',
    'COMPUTER SCIENCE': 'Computer Science'
})
```

Kadib hubi:

```python
df['Program'].unique()
```

---

# 6. 🗑️ Removing Unnecessary Columns

Column aan loo baahnayn waxaa lagu tirtiri karaa `drop()`.

```python
df = df.drop(columns=['Student_ID'])
```

Columns badan:

```python
df = df.drop(columns=[
    'Student_ID',
    'Academic_Status'
])
```

---

# 7. 📊 Checking Data Types

Si aad u hubiso data types-ka:

```python
df.dtypes
```

Dataset-kayga wuxuu lahaa data types-kan:

| Column             | Data Type |
| ------------------ | --------- |
| Student_ID         | object    |
| Program            | object    |
| Attendance_Percent | float64   |
| Assignment_Score   | float64   |
| Midterm_Score      | float64   |
| Final_Score        | object    |
| Academic_Status    | object    |

---

# 8. 🔢 Converting Columns to Numeric Data

`Assignment_Score` hore ayuu u ahaa `float64`, sidaas darteed conversion uma baahnayn.

Laakiin `Final_Score` wuxuu ahaa `object`, sidaas darteed waxaan u beddelnay numeric:

```python
df['Final_Score'] = pd.to_numeric(
    df['Final_Score'],
    errors='coerce'
)
```

Kadib waxaan hubinay data types-ka:

```python
df.dtypes
```

---

# 9. 📅 Converting Columns to Datetime

Column ka kooban taariikho waxaa loo beddeli karaa datetime:

```python
df['Date'] = pd.to_datetime(
    df['Date'],
    errors='coerce'
)
```

Datetime wuxuu muhiim u yahay data analysis-ka ku saabsan:

* Dates
* Months
* Years
* Time-based analysis

---

# 10. ⚠️ Handling Invalid Values

`errors='coerce'` waxaa loo isticmaalaa marka column uu leeyahay values aan sax ahayn.

```python
df['Final_Score'] = pd.to_numeric(
    df['Final_Score'],
    errors='coerce'
)
```

Values aan loo beddeli karin numeric waxaa loo beddelayaa:

```text
NaN
```

Tusaale:

| Original Value | Converted Value |
| -------------- | --------------- |
| 80             | 80              |
| 90             | 90              |
| Unknown        | NaN             |
| N/A            | NaN             |
| 75             | 75              |

---

# 🛠️ Key Skills Learned

Casharkan kadib waxaan bartay:

* Sida loo import-gareeyo Pandas
* Sida loo akhriyo Excel files
* Sida loo hubiyo columns
* Sida loo beddelo column names
* Sida loo hubiyo values-ka column
* Sida loo nadiifiyo inconsistent values
* Sida loo tirtiro columns aan muhiim ahayn
* Sida loo hubiyo data types
* Sida text loogu beddelo numeric data
* Sida loo isticmaalo datetime
* Sida loo isticmaalo `errors='coerce'`

---

# 💻 Tools Used

* Python
* Pandas
* Google Colab
* Microsoft Excel

---

## 👨‍💻 Author

**Deeqo Abdulkadir**

🎓 Python for Data Analysis Student

