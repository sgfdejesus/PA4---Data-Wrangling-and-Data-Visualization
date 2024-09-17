# PA4 - Data Wrangling and Data Visualization
"This repository contains Python code to solve one programming problem titled: **ECE Board Exam Problem**. This problem involves the use of Data Wrangling and Data Visualization"

Below is a preview of the code, but there is also a Jupyter notebook uploaded in the files section.

---

## 1. ECE Board Exam Problem
### Overview

### Code Implementation
``` python
import pandas as pd

# Load data from the Excel file
data = pd.read_excel('board2.xlsx')

#Filter rows where 'Electronics' is greater than 70
filtered_data = data[data['Electronics'] > 70]

#Select only 'Name' and 'GEAS' columns
filtered_data = filtered_data[['Name', 'GEAS', 'Electronics']]

print(filtered_data)
 ```
