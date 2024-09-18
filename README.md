# PA4 - Data Wrangling and Data Visualization
"This repository contains Python code to solve one programming problem titled: **ECE Board Exam Problem**. This problem involves the use of Data Wrangling and Data Visualization"

Below is a preview of the code, but there is also a Jupyter notebook uploaded in the files section.

---

## 1. ECE Board Exam Problem
### Overview
This project is centered on analyzing and visualizing educational data to extract meaningful insights about student performance. The problem involves two main tasks: creating specific data frames and generating visualizations to understand the factors influencing student average grades. 

---

### Data Frame Creation
### Code Implementation and its Output

``` python
import pandas as pd

#Load data from the Excel file
board = pd.read_excel('board2.xlsx')
board
```

<img width="485" alt="Screenshot 2024-09-18 at 8 39 54 PM" src="https://github.com/user-attachments/assets/1c4b3580-4e86-48a8-bc10-c4b60ac6c741">



``` python
#Filter rows where 'Track' is 'Instrumentation', 'Hometown' is 'Luzon', and 'Electronics' score is above 70
Instru = board[(board['Track'] == 'Instrumentation') & (board['Hometown'] == 'Luzon') & (board['Electronics'] > 70)]

#Select and display the relevant columns: 'Name', 'GEAS', and 'Electronics'
Instru[['Name', 'GEAS', 'Electronics']]
 ```

<img width="168" alt="Screenshot 2024-09-18 at 8 40 27 PM" src="https://github.com/user-attachments/assets/05182a39-bbe1-40f4-bd32-340dfbda40d7">

``` python
#Filter the DataFrame to include only rows where 'Hometown' is 'Mindanao' and 'Gender' is 'Female'
Mindy = board[(board['Hometown'] == 'Mindanao') & (board['Gender'] == 'Female')].copy()

#Calculate the average of 'Math', 'Electronics', 'GEAS', and 'Communication' for each row
Mindy['Average'] = Mindy[['Math', 'Electronics', 'GEAS', 'Communication']].mean(axis=1)

#Keep only the rows where the calculated average is 55 or above
Mindy = Mindy[Mindy['Average'] >= 55]

# Select and print the relevant columns: 'Name', 'Track', 'Electronics', and 'Average'
Mindy[['Name', 'Track', 'Electronics', 'Average']]
 ```

<img width="266" alt="Screenshot 2024-09-18 at 8 40 55 PM" src="https://github.com/user-attachments/assets/f662044e-260d-487e-a46d-05b8c1696eb1">

---

### Data Visualization
### Code Implementation and its Output

``` python
#Use matplotlib.pyplot library as it will be required for making different graphs
import matplotlib.pyplot as plt
```



``` python
#Create a bar plot for Average Score by Gender
plt.figure(figsize=(10, 4))  #Set figure size
plt.bar(board['Gender'], board['Average'])  #Plot average scores with Gender on x-axis
plt.title('Average Score by Gender')  #Add title
plt.xlabel('Gender')  #Label x-axis
plt.ylabel('Average Score')  #Label y-axis
plt.tight_layout()  #Adjust layout to prevent clipping
plt.show()  #Display the plot
```

<img width="745" alt="Screenshot 2024-09-18 at 8 45 23 PM" src="https://github.com/user-attachments/assets/dd9ea052-53da-4bb1-a76c-caa769521b92">


``` python
#Create a bar plot for Average Score by Track
plt.figure(figsize=(10, 4))  #Set figure size
plt.bar(board['Track'], board['Average'])  #Plot average scores with Track on x-axis
plt.title('Average Score by Track')  #Add title
plt.xlabel('Track')  #Label x-axis
plt.ylabel('Average Score')  #Label y-axis
plt.tight_layout()  #Adjust layout to prevent clipping
plt.show()  #Display the plot
```

<img width="745" alt="Screenshot 2024-09-18 at 8 45 41 PM" src="https://github.com/user-attachments/assets/544c6687-c82e-4bfe-a94c-9abb2ba24c60">

``` python
#Create a bar plot for Average Score by Hometown
plt.figure(figsize=(10, 4))  #Set figure size
plt.bar(board['Hometown'], board['Average'])  #Plot average scores with Hometown on x-axis
plt.title('Average Score by Hometown')  #Add title
plt.xlabel('Hometown')  #Label x-axis
plt.ylabel('Average Score')  #Label y-axis
plt.tight_layout()  #Adjust layout to prevent clipping
plt.show()  #Display the plot
```

<img width="745" alt="Screenshot 2024-09-18 at 8 45 59 PM" src="https://github.com/user-attachments/assets/cd074dc0-e44d-47cb-b4ed-f280fdea111d">

### Data Observation
- Female students generally achieve higher average grades compared to their male counterparts.
- Microelectronics has the highest average grade, followed by Communication, with Instrumentation recording the lowest average grade.
- Luzon shows the highest average grade, followed by Visayas, while Mindanao has the lowest average grade.


