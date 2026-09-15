# python-for-data-anlaysis-lessons
my course for python
# 📊 Day 4: Missing Values Analysis

## 📌 Overview

Casharkan wuxuu diiradda saarayaa sida loo **ogaado, tiriyo, fahmo, iyo go'aan looga gaaro Missing Values** iyadoo la isticmaalayo Python Pandas.

Waxaan sidoo kale baranay sida loo helo **Mode iyo Count** ee columns-ka dataset-ka.

---

# 🎯 Learning Objectives

Casharkan waxaan ku baranay:

* Sida loo ogaado Missing Values.
* Farqiga u dhexeeya `isna()` iyo `isnull()`.
* Sida loo tiriyo Missing Values.
* Sida loo helo Total Missing Values.
* Sida loo xisaabiyo Missing Value Percentage.
* Sida loo helo Mode iyo Count.
* Sida Mode loogu sameeyo columns badan.
* Sida loo go'aamiyo in Missing Values la delete-gareeyo ama la fill-gareeyo.
* Sida loo isticmaalo `dropna()`.
* Sida loo isticmaalo `fillna()`.
* Sida loo isticmaalo Mean iyo Median.
* Sida categorical values loogu buuxiyo Mode ama `"Unknown"`.
* Sababta aan Missing Values si automatic ah loogu buuxin `0`.

---

# 1. 🔍 Detecting Missing Values

Missing Value waa value ka maqan dataset-ka.

### `isna()`

```python
data.isna()
```

Pandas wuxuu soo celinayaa:

* `True` → value-ku waa missing.
* `False` → value-ku ma aha missing.

Waxaa kale oo la isticmaali karaa:

```python
data.isnull()
```

`isna()` iyo `isnull()` labaduba waxay kaa caawinayaan inaad ogaato missing values.

---

# 2. 🔎 Checking Missing Values in One Column

Haddii aan rabno inaan eegno hal column:

```python
data["Age"].isna()
```

ama:

```python
data["Age"].isnull()
```

Tani waxay kuu sheegaysaa rows-ka `Age` ka maqan yahay.

---

# 3. 🔢 Counting Missing Values

Si aan u ogaano inta Missing Value ee column kasta:

```python
Missing_Data = data.isnull().sum()
```

Tani waxay soo saaraysaa tirada missing values ee **column kasta**.

Tusaale:

```text
Age       3
Gender    2
Score     5
```

---

# 4. 📊 Total Missing Values

Si aan u helno dhammaan Missing Values-ka dataset-ka:

```python
Missing_Data = data.isnull().sum().sum()
```

First `sum()` wuxuu tirinayaa missing values column kasta.

Second `sum()` wuxuu isku darayaa dhammaan missing values-ka.

---

# 5. 📈 Missing Value Percentage

Tirada Missing Values oo keliya mararka qaar kuma filna.

Waxaan sidoo kale xisaabin karnaa percentage-ka:

```python
data.isna().mean() * 100
```

Tani waxay muujinaysaa boqolkiiba Missing Values ee column kasta.

---

# 6. 🧠 Delete or Fill?

Marka Missing Values la ogaado, **ma ahan inaan si automatic ah u isticmaalno `dropna()` ama `fillna()`**.

Marka hore waxaan is weydiinaynaa:

* Immisa value ayaa missing ah?
* Column kee ayaa missing leh?
* Variable-kaasi muhiim ma yahay?
* Maxaa sababay missing-ka?
* Haddii rows la tirtiro, sample size-ku ma yaraadayaa?
* Ma jirtaa value macquul ah oo lagu beddeli karo?
* Filling-ku ma qalloocinayaa xogta?

Go'aanka waa inuu ku salaysnaadaa xogta iyo xaaladda dataset-ka.

---

# 7. 🗑️ Removing Missing Values with `dropna()`

### Specific Column

Haddii aan rabno inaan ka saarno rows-ka `Score` ka maqan:

```python
data = data.dropna(subset=["Score"])
```

### Multiple Columns

```python
data = data.dropna(subset=["Age", "Score"])
```

### Dataset-ka oo dhan

```python
data = data.dropna()
```

`dropna()` waxay tirtiraysaa rows-ka leh Missing Values.

---

# 8. 📝 Filling Missing Values

Mararka qaar ma rabno inaan rows tirtirno.

Waxaan isticmaali karnaa:

```python
fillna()
```

Filling waxaa la tixgelin karaa marka:

* Sample size-ka la ilaalinayo.
* Replacement macquul ah jiro.
* Variable-ku taageerayo habka la dooranayo.
* Filling-ku uusan abuureyn xog marin-habaabisa analysis-ka.

`fillna()` waa technical command; isticmaalkeedu macnaheedu ma aha in go'aanka statistical-ka uu sax yahay.

---

# 9. 📐 Filling Numerical Variables with Mean

Numerical variable waxaa lagu buuxin karaa Mean haddii ay ku habboon tahay.

```python
mean_score = data["Age"].mean()

data["Age"] = data["Age"].fillna(mean_score)
```

Mean = Average.

---

# 10. 📊 Filling Numerical Variables with Median

Waxaan sidoo kale isticmaali karnaa Median:

```python
data["Age"] = data["Age"].fillna(
    data["Age"].median()
)
```

Median badanaa wuxuu noqon karaa doorasho ka habboon marka data-du skewed tahay ama ay leedahay outliers.

---

# 11. 🏷️ Filling Categorical Variables

Categorical variables waxaa ka mid noqon kara:

* Gender
* Program
* Department
* Status

Mid ka mid ah hababka waa **Mode**.

### Find Mode

```python
mode = data["Gender"].mode()[0]
```

### Find Count of Mode

```python
count = data["Gender"].value_counts()[mode]
```

### Print Results

```python
print("Column:", "Gender")
print("Mode:", mode)
print("Count:", count)
```

Casharku wuxuu sidoo kale soo jeedinayaa in categorical missing values lagu buuxin karo `"Unknown"` haddii ay ku habboon tahay:

```python
data["Gender"] = data["Gender"].fillna("Unknown")
```

---

# 12. 📋 Mode and Count for All Columns

Hadda waxaan u gudbaynaa qaybta aan ku joojinay casharka.

Waxaan rabnaa inaan helno:

* Column name
* Mode
* Count of Mode

Marka hore waxaan sameynaynaa empty list:

```python
result = []
```

Kadib waxaan isticmaalaynaa loop:

```python
for column in data.columns:
```

Tani waxay maraysaa **column kasta** oo ku jira dataset-ka.

### Find Mode

```python
mode = data[column].mode()[0]
```

Waxay helaysaa value-ka ugu badan ee column-ka.

### Find Count

```python
count = data[column].value_counts()[mode]
```

Waxay tirinaysaa inta jeer ee Mode-ku ku soo noqday column-ka.

### Ku dar Result-ka

```python
result.append([column, mode, count])
```

Waxay ku kaydinaysaa saddexda xog:

```text
Column
Mode
Count
```

### Complete Code

```python
result = []

for column in data.columns:
    mode = data[column].mode()[0]
    count = data[column].value_counts()[mode]
    result.append([column, mode, count])

pd.DataFrame(
    result,
    columns=["Column", "Mode", "Count"]
)
```

Natiijadu waxay noqon kartaa table sida:

| Column  | Mode   | Count |
| ------- | ------ | ----: |
| Gender  | Female |   180 |
| Program | IT     |   120 |
| Status  | Active |   250 |

Tani waxay kuu oggolaanaysaa inaad hal mar aragto **Mode iyo Count-ka column kasta**.

---

# ⚠️ Important Rule: Do Not Automatically Fill with Zero

Ha samayn:

```python
data["Score"] = data["Score"].fillna(0)
```

adigoon sabab sax ah haysan.

Sababtoo ah:

```text
Score = 0
```

waxay ka dhigan tahay ardaygu dhab ahaan wuxuu helay **0**.

Laakiin:

```text
Score = NaN
```

waxay ka dhigan tahay score-ku **wuu maqan yahay**.

Labadaas xaaladood isku macne ma laha.

---

# 🧠 Key Commands

| Command                     | Purpose                         |
| --------------------------- | ------------------------------- |
| `data.isna()`               | Detect missing values           |
| `data.isnull()`             | Detect missing values           |
| `data.isnull().sum()`       | Count missing values per column |
| `data.isnull().sum().sum()` | Count total missing values      |
| `data.isna().mean() * 100`  | Missing percentage              |
| `data.dropna()`             | Remove rows with missing values |
| `data.fillna()`             | Fill missing values             |
| `.mean()`                   | Calculate mean                  |
| `.median()`                 | Calculate median                |
| `.mode()[0]`                | Find mode                       |
| `.value_counts()`           | Count values                    |
| `data.duplicated().sum()`   | Count duplicate rows            |
| `data.drop_duplicates()`    | Remove duplicate rows           |

---

# 🎯 Practice Task

Isticmaal dataset-kaaga oo samee:

### Task 1

```python
data.isnull().sum()
```

### Task 2

```python
data.isnull().sum().sum()
```

### Task 3

```python
data.isna().mean() * 100
```

### Task 4

Samee Mode + Count table:

```python
result = []

for column in data.columns:
    mode = data[column].mode()[0]
    count = data[column].value_counts()[mode]
    result.append([column, mode, count])

pd.DataFrame(
    result,
    columns=["Column", "Mode", "Count"]
)
```

### Task 5

Is weydii:

> Missing Values-ka dataset-kayga ma in la delete-gareeyaa mise la fill-gareeyaa? Maxay tahay sababtu?

---

# ✅ What I Learned

After completing this lesson, I can:

* Detect Missing Values using Pandas.
* Count Missing Values.
* Calculate Missing Value Percentage.
* Understand when to delete or fill Missing Values.
* Use `dropna()`.
* Use `fillna()`.
* Use Mean, Median, and Mode appropriately.
* Find Mode and Count for all columns using a loop.
* Understand why filling Missing Values with `0` can be incorrect.
