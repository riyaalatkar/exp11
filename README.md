## Lab Report: Dataset Creation and Exploratory Data Analysis (EDA)
**Student Name:** Riya Latkar  
**PRN:** 25070123092 
**Experiment No:** 11 (Dataset Management)

### 1. Aim
To demonstrate the process of creating a custom dataset, exporting it to a CSV format, and performing basic Exploratory Data Analysis (EDA) on an imported dataset using the `pandas` library.

### 2. Theory
Data handling in Python primarily revolves around the **DataFrame**, a 2D labeled data structure. 
* **Dataset Creation:** Data can be manually structured using Python dictionaries and converted into a DataFrame.
* **Persistence:** Using `.to_csv()`, we can save our digital data into a physical file on the hard drive.
* **Exploratory Data Analysis (EDA):** This is the initial investigation of data to discover patterns, spot anomalies, and check assumptions with the help of summary statistics and graphical representations.
* **Data Metadata:** Attributes like `.shape` and `.size` provide the "dimensions" of the data, while `.info()` provides the "health" (data types and null counts).

### 3. Logic
The code logic is split into two distinct phases:
1.  **The Creator Phase:** A dictionary is mapped to a DataFrame. The logic here ensures that every list in the dictionary has the same length to maintain tabular integrity. The data is then written to a permanent file.
2.  **The Inspector Phase:** An external dataset is loaded. The logic follows a "General-to-Specific" inspection:
    * **Volume Check:** How big is the data? (`shape`, `size`)
    * **Structure Check:** What are the columns? (`info`, `head`)
    * **Quality Check:** Is data missing or repeated? (`isnull`, `duplicated`)
    * **Statistical Check:** What are the averages and ranges? (`describe`)

### 4. One-Liner Code Explanations
* `pd.DataFrame(data)`: Converts a Python dictionary into a structured tabular DataFrame.
* `df.to_csv("name.csv", index=False)`: Saves the DataFrame as a CSV file without including the row index numbers.
* `df.shape`: Returns a tuple representing the number of rows and columns (e.g., 93 rows, 10 columns).
* `df.size`: Returns the total number of elements (cells) in the DataFrame (Rows $\times$ Columns).
* `df.info()`: Displays the data type of each column and identifies how many non-null values exist.
* `df.describe()`: Generates a summary of descriptive statistics (mean, std, min, max) for numerical columns.
* `df.head()` / `df.tail()`: Retrieves the first five or last five rows of the dataset for a quick preview.
* `df.sample(5)`: Randomly selects five rows to give an unbiased view of the data distribution.
* `df.isnull().sum()`: Counts and displays the number of missing values in each column.
* `df.nunique()`: Returns the number of unique entries in each column to identify categorical variety.

### 5. Algorithm
1.  **Import** the `pandas` and `numpy` libraries.
2.  **Manually Define** data using a dictionary and convert it to a DataFrame (`df`).
3.  **Export** the created DataFrame to a `.csv` file for external use.
4.  **Load** an existing dataset (`Cars93.csv`) using `pd.read_csv()`.
5.  **Audit the Dataset:**
    * Check dimensions using `shape` and `size`.
    * Preview data using `head()`, `tail()`, and `sample()`.
6.  **Analyze Metadata:** Run `info()` to check memory usage and column data types.
7.  **Check Data Integrity:** Identify missing values with `isnull().sum()` and check for duplicates with `duplicated().sum()`.
8.  **Summarize Statistics:** Run `describe()` to understand the mathematical spread of the data.

### 6. Conclusion
In this experiment, I learned the full lifecycle of data management in Python, from manual creation to professional auditing. I observed that the `Cars93` dataset contains missing values in columns like `AirBags` and `Luggage.room`, which highlights the necessity of data cleaning before analysis. Mastering these EDA commands allows for a comprehensive understanding of any dataset's strengths and flaws before building models.

---
