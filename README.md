## DATA CLEANING PROCESS
```
Date: 27/02/2025
Register number: 212223040240
Name:Vimala Rani A
```
# AIM:
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation:
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm:
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

Coding and Output:

# ACTIVITY 1:
1)Write a Python program to select the 'name' and 'score' columns from the following DataFrame. Sample DataFrame:

exam_data = {'name': ['Anastasia', 'Dima', 'Katherine', 'James', 'Emily', 'Michael', 'Matthew', 'Laura', 'Kevin', 'Jonas'],

'score': [12.5, 9, 16.5, np.nan, 9, 20, 14.5, np.nan, 8, 19],

'attempts': [1, 3, 4, 3, 5, 3, 6, 1, 7, 1] }
```
import pandas as pd
import numpy as np
exam_data = {'name': ['Anastasia', 'Dima', 'Katherine', 'James', 'Emily', 'Michael', 'Matthew', 'Laura', 'Kevin', 'Jonas'],

'score': [12.5, 9, 16.5, np.nan, 9, 20, 14.5, np.nan, 8, 19],

'attempts': [1, 3, 4, 3, 5, 3, 6, 1, 7, 1] }
df=pd.DataFrame(exam_data)
df
```
![1](https://github.com/user-attachments/assets/2f323b6c-7a11-4f30-bec1-923655f382df)

```
selected_columns=df[['name','score']]
selected_columns
```
![2](https://github.com/user-attachments/assets/fe9668a4-b5ff-4d1e-aad6-7ddef4521b6c)

2)For the above dataframe, Write a program to select the data who's attempt is greater than 3
```
filtered_data=df[df['attempts']>3]
filtered_data
```
![3](https://github.com/user-attachments/assets/c14a466e-f6c5-4643-81b7-b35e341acb33)

3)Write python code for indexing rows and columns based on the following conditions: Assume we have the following dataframe:

data = {'name': ['Alice', 'Bob', 'Charlie', 'Dave'],

'age': [25, 35, 40, 28],

'gender': ['F', 'M', 'M', 'M'],

'salary': [50000, 70000, 60000, 80000]}

df = pd.DataFrame(data)
```
data = {'name': ['Alice', 'Bob', 'Charlie', 'Dave'],

'age': [25, 35, 40, 28],

'gender': ['F', 'M', 'M', 'M'],

'salary': [50000, 70000, 60000, 80000]}

df = pd.DataFrame(data)
```
![3](https://github.com/user-attachments/assets/48ec7b03-99ba-4422-8dad-612a8a1fc3e2)

a. Select rows where age is greater than 30:
```
age=df[df['age']>30]
age
```

![5](https://github.com/user-attachments/assets/f6e7e8cb-c598-4fc4-86e9-8a0b720bda76)



b. Select rows where name contains 'e':
```
name=df[df['name'].str.contains('e')]
name
```

![6](https://github.com/user-attachments/assets/397e5fb3-2c44-449a-b33e-a3fb56dbca68)

c. Select rows where gender is 'M' and salary is greater than 65000:
```
A=df[(df['gender']=='M') & (df['salary']>65000)]
A
```
![7](https://github.com/user-attachments/assets/97278b58-8425-47a4-b5d7-27edb0582d60)


d. Select columns 'name' and 'age'
```
B=df[['name','age']]
B
```
![8](https://github.com/user-attachments/assets/cf941b2d-5a23-4830-b794-111e5b8676b9)

# ACTIVITY 2:
Write python code for indexing rows and columns using iloc or loc method based on the following conditions:
```
path='/content/drive/My Drive/Bank_train.csv'
df=pd.read_csv(path)
df
```
![9](https://github.com/user-attachments/assets/86e30463-82ec-4679-88c3-c78e3e5d7010)


a. select the rows where clients with primary education have subscribed to a deposit?
```
rows= df.loc[(df['education'] == 'primary') & (df['deposit']=='yes')]
rows
```
![10](https://github.com/user-attachments/assets/9c6f1807-7500-4a60-8e72-a8c2f5eeba73)


b. select the rows where clients who have not subscribed to a deposit?
```
rows= df.loc[(df['deposit']=='no')]
rows
```
![11](https://github.com/user-attachments/assets/8e17ce76-5de2-481b-bc97-56f56dfc58cf)


c. select the rows where clients who have subscribed to a deposit either have a housing or a personal loan?
```
A= df.loc[(df['deposit']=='yes') & ((df['housing']=='yes') | (df['loan']=='yes'))]
A
```
![12](https://github.com/user-attachments/assets/ca0b211e-e8fd-413c-944f-71889330367f)


d. select the rows where clients with secondary education who have not subscribed to a deposit?
```
rows= df.loc[(df['education'] == 'secondary') & (df['deposit']=='no')]
rows
```

![13](https://github.com/user-attachments/assets/65b98db6-6800-41c1-b5ee-650e9854dbb6)


e. select the rows where clients who have subscribed to a term deposit as an outcome of the successful marketing campaign?
```
B= df.loc[(df['poutcome'] == 'success') & (df['deposit']=='yes')]
B
```
![14](https://github.com/user-attachments/assets/5849c0a8-ccbe-4fe9-bf72-8c189abfc04c)


f. select the rows where unemployed clients who have not subscribed to deposit?
```
J= df.loc[(df['job'] == 'unemployed') & (df['deposit']=='no')]
J
```
![15](https://github.com/user-attachments/assets/aae94c3c-448d-4ae4-a17e-b62d912a1dc3)


g. Select columns 'name' and 'salary' where age is less than or equal to 30:
```
H = df.loc[df['age'] <= 30, ['age', 'balance']]
H
```
![16](https://github.com/user-attachments/assets/92030f1a-9d81-4b25-a421-1f6465dde806)


h.select coloumns ‘education’ and ‘balance’ where age is less than or equal to 30.
```
H = df.loc[df['age'] <= 30, ['education', 'balance']]
H
```
![17](https://github.com/user-attachments/assets/4cce8370-1269-4617-bed0-d0ef864401df)


Result:
Thus the program for the given question has been run and executed successfully
