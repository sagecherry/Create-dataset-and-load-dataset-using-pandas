# Create and Load Datasets

## THEORY:

This experiment introduces core Pandas operations for creating, manipulating, inspecting, and analyzing tabular data in Python. Pandas is the standard library used for data wrangling and exploratory data analysis in data science and machine learning projects.


1. Importing Pandas and creating a DataFrame from a dictionary  
   ```python
   import pandas as pd

   data = {
       'Roll No.': ['1','2','3','4','5'],
       'grender': ['female','male','female','male','female'],
       'department': ['entc','cse','it','mech','civil'],
       'cgpa': [8.2,9.0,7.8,9.3,7.7]
   }

   df = pd.DataFrame(data)
   ```

2. Saving the DataFrame to a CSV file  
   ```python
   df.to_csv('student.csv', index=False)
   ```
   `index=False` prevents writing the default row index numbers into the CSV file.

3. Adding new columns to the DataFrame  
   ```python
   df['age'] = [17, 18, 19, 18, 19]
   ```
   You assign a list (or Series) that has the same length as the number of rows.

4. Removing a column  
   ```python
   df = df.drop('grender', axis=1)
   ```
   `axis=1` tells Pandas to drop a column (axis=0 would drop rows).

5. Basic inspection and summary methods  
   ```python
   df.shape       # returns tuple (number of rows, number of columns)
   df.size        # total number of elements (rows × columns)
   df.info()      # shows column names, data types, non-null counts, memory usage
   df.describe()  # statistical summary for numeric columns: count, mean, std, min, quartiles, max
   df.head()      # first 5 rows by default
   df.tail()      # last 5 rows by default
   ```

6. Calculating basic statistics on a numeric column  
   ```python
   df['cgpa'].mean()     # arithmetic mean / average
   df['cgpa'].median()   # middle value after sorting
   df['cgpa'].mode()     # most frequent value(s)
   df['cgpa'].max()      # highest value in the column
   ```

7. Accessing specific columns and rows  
   ```python
   df['department']       # returns the whole column as a Series
   df.loc[2]              # returns all columns for the row with index 2
   df['department'][0]    # first value in the department column
   ```

8. Loading and inspecting external CSV files  
   ```python
   # Example 1: Cars93 dataset
   cars = pd.read_csv('Cars93.csv')
   cars.shape
   cars.info()
   cars.describe()
   cars.head()

   # Example 2: Library records (500 rows)
   library = pd.read_csv('library_records_500 - Sheet1.csv')
   library.shape
   library.info()
   library.describe()
   library.head()
   library.tail()
   ```
   
## Conclusion
The experiment successfully demonstrated how to manually create a Pandas DataFrame and export it to CSV, add and remove columns, use the most important inspection functions (shape, info(), describe(), head(), tail()), perform simple statistical operations (mean, median, mode, max), and load and quickly explore external CSV files. These are the basic building blocks needed for almost every data-related task in Python (data cleaning, exploration, preprocessing, etc.).
