
# Pandas Basics in Python

Pandas is a Python library used for data manipulation and analysis. It provides powerful data structures like **DataFrame** and **Series** for handling structured data effectively.

---

## **Key Features of Pandas**

1. **Data Structures:**
   - **Series:** A one-dimensional labeled array.
   - **DataFrame:** A two-dimensional table with labeled rows and columns.

2. **Data Manipulation:**
   - Add, remove, and modify data.

3. **Data Analysis:**
   - Grouping, aggregation, and descriptive statistics.

4. **File Handling:**
   - Read/write operations for CSV, Excel, SQL, JSON, and more.

5. **Integration with Visualization and Machine Learning:**
   - Integration with Matplotlib, Seaborn, and machine learning libraries like scikit-learn.

---

## **Getting Started with Pandas**

### **Installation**
To install Pandas:
```bash
pip install pandas
```

---

### **Creating a DataFrame**
```python
import pandas as pd

# Create a dummy DataFrame
data = {
    'Name': ['Alice', 'Bob', 'Charlie', 'David'],
    'Age': [25, 30, 35, 40],
    'Salary': [50000, 60000, 55000, 70000]
}

df = pd.DataFrame(data)
print("DataFrame:")
print(df)
```

---

### **Viewing Data**
```python
# View the first few rows
print(df.head())

# Display column names
print(df.columns)

# Shape of the DataFrame
print(df.shape)
```

---

### **Basic Data Manipulation**

#### Adding a New Column:
```python
df['Bonus'] = df['Salary'] * 0.1
print("
DataFrame with Bonus:")
print(df)
```

#### Filtering Data:
```python
high_salary = df[df['Salary'] > 55000]
print("
Employees with Salary > 55000:")
print(high_salary)
```

#### Grouping and Aggregation:
```python
print("
Average Salary by Age:")
print(df.groupby('Age')['Salary'].mean())
```

---

### **File Input/Output**

#### Save to CSV:
```python
df.to_csv("dummy_data.csv", index=False)
```

#### Load from CSV:
```python
new_df = pd.read_csv("dummy_data.csv")
print("
Loaded DataFrame:")
print(new_df)
```

---

### **Advanced Applications**

#### Handling Missing Data:
```python
data = {
    'Name': ['Alice', 'Bob', 'Charlie', 'David'],
    'Age': [25, None, 35, 40],
    'Salary': [50000, 60000, None, 70000]
}

df = pd.DataFrame(data)

# Fill missing values
df['Age'].fillna(df['Age'].mean(), inplace=True)

# Drop rows with missing values
df.dropna(inplace=True)

print("
DataFrame after handling missing values:")
print(df)
```

#### Merging DataFrames:
```python
df1 = pd.DataFrame({'ID': [1, 2], 'Name': ['Alice', 'Bob']})
df2 = pd.DataFrame({'ID': [1, 2], 'Salary': [50000, 60000]})

merged_df = pd.merge(df1, df2, on='ID')
print("
Merged DataFrame:")
print(merged_df)
```

---

### **Visualization with Pandas**
```python
import matplotlib.pyplot as plt

# Line plot
df.plot(x='Age', y='Salary', kind='line')
plt.show()

# Bar plot
df['Salary'].plot(kind='bar')
plt.show()
```

---

### **Applications of Pandas**

1. **Data Cleaning and Preprocessing:**
   - Handle missing values, duplicates, and type conversions.
2. **Exploratory Data Analysis (EDA):**
   - Analyze datasets to find patterns and trends.
3. **Feature Engineering:**
   - Prepare data for machine learning workflows.
4. **Time-Series Analysis:**
   - Analyze temporal data for trends and patterns.
5. **Input/Output:**
   - Read/write data from various file formats (CSV, Excel, JSON, SQL).
6. **Integration with Machine Learning Libraries:**
   - Prepare datasets for scikit-learn, TensorFlow, or PyTorch models.

---

Pandas is an essential tool for data analysis and manipulation in Python. Let me know if you need further details or specific examples! 😊
