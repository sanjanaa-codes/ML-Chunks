# 📊 Retrieving Data from Multiple Data Sources using Pandas

This guide covers how to **read and write data** from various sources like **CSV, JSON, SQL, APIs**, and **Cloud** using Python’s `pandas` library.

---

## 📁 Reading CSV Files

**CSV (Comma-Separated Values)** files store tabular data with commas separating values.

### 🔹 Basic Syntax

```python
import pandas as pd

file_path = "data/iris_data.csv"
data = pd.read_csv(file_path)
print(data.head())  # Display first 5 rows
```

### ⚙️ Useful Arguments in `read_csv()`

| Argument                      | Description                                     |
| ----------------------------- | ----------------------------------------------- |
| `sep='\t'`                    | For tab-separated files                         |
| `delim_whitespace=True`       | Treat any whitespace as a separator             |
| `header=None` / `header=2`    | Skip or choose which row to use as column names |
| `names=['col1', 'col2', ...]` | Assign custom column names                      |
| `na_values=['NA', 99]`        | Treat given values as missing (NaN)             |

---

## 🧩 Reading JSON Files

**JSON (JavaScript Object Notation)** is a lightweight, structured format—commonly used in APIs and NoSQL databases.

### 🔹 Basic Syntax

```python
import pandas as pd

file_path = "data/sample.json"
data = pd.read_json(file_path)
```

### ⚙️ Common JSON Orientations

If loading fails, specify orientation with:

```python
pd.read_json(file_path, orient='records')
```

| Orient    | Description                                 |
| --------- | ------------------------------------------- |
| `split`   | Dictionary with keys {index, columns, data} |
| `records` | List of records (row-wise)                  |
| `index`   | Dict of dicts (index-based)                 |
| `columns` | Dict of lists (column-based)                |
| `values`  | Just values array                           |

---

## 💾 Writing Data

| Format | Function    | Example                                         |
| ------ | ----------- | ----------------------------------------------- |
| CSV    | `to_csv()`  | `data.to_csv("output.csv", index=False)`        |
| JSON   | `to_json()` | `data.to_json("output.json", orient='records')` |

---

## 🧠 Quick Tips

* Always inspect your data after loading using `data.info()` and `data.head()`.
* Handle missing or incorrect values immediately using `na_values` or `fillna()`.
* When in doubt about format errors, check the file structure and `orient` parameter.

---

✅ **Next Steps**

* Learn to retrieve data from **SQL** and **NoSQL databases**
* Explore APIs with `requests` and convert JSON response to DataFrame
* Work with cloud storage (AWS S3, GCS, Azure Blob) using `pandas` connectors

---
