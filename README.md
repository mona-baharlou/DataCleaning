# DataCleaning
The initial phase of a crime data analysis project, focusing on cleaning and structuring raw data for downstream tasks.

---

### **Code Workflow Description**:
1. **Import Libraries**:
   ```python
   import pandas as pd
   ```
   - Imports the `pandas` library for data manipulation.

2. **Load Dataset**:
   ```python
   crime = pd.read_csv('crime.csv', encoding='latin1') 
   ```
   - Reads the CSV file `crime.csv` into a DataFrame. The encoding argument is `'latin1'`.

3. **Initial Data Inspection**:
   ```python
   crime.isnull()
   ```
   - Checks for missing values in the dataset.

4. **Identify Rows with Missing Values**:
   ```python
   rows_with_missing_values = crime.isnull().any(axis=1)
   crime[rows_with_missing_values]
   ```
   - Filters and displays rows containing missing values.

5. **Drop Unnecessary Columns**:
   ```python
   clean_crime = crime.drop(columns=['YEAR', 'MONTH', 'HOUR'])
   ```
   - Removes the columns `YEAR`, `MONTH`, and `HOUR` from the DataFrame, likely due to redundancy or irrelevance to the analysis.

6. **Explore Unique Values**:
   ```python
   clean_crime['OFFENSE_CODE_GROUP'].unique()
   clean_crime['OFFENSE_DESCRIPTION'].unique()
   ```
   - Checks unique values in the `OFFENSE_CODE_GROUP` and `OFFENSE_DESCRIPTION` columns to understand crime categories.

---

### **Purpose**:
- This script prepares the crime dataset for analysis by:
  - Removing irrelevant or redundant columns.
  - Identifying missing values for potential imputation or exclusion.
  - Exploring categorical features like offense types.
