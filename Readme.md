DATA CLEANING PROCESS
Date: 27/02/2025
Register number: 212223040240
Name:Vimala Rani A
AIM:
To read the given data and perform data cleaning and save the cleaned data to a file.

Explanation:
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

Algorithm:
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

Coding and Output:
ACTIVITY 1:
1)Write a Python program to select the 'name' and 'score' columns from the following DataFrame. Sample DataFrame:

exam_data = {'name': ['Anastasia', 'Dima', 'Katherine', 'James', 'Emily', 'Michael', 'Matthew', 'Laura', 'Kevin', 'Jonas'],

'score': [12.5, 9, 16.5, np.nan, 9, 20, 14.5, np.nan, 8, 19],

'attempts': [1, 3, 4, 3, 5, 3, 6, 1, 7, 1] }

import pandas as pd
import numpy as np
exam_data = {'name': ['Anastasia', 'Dima', 'Katherine', 'James', 'Emily', 'Michael', 'Matthew', 'Laura', 'Kevin', 'Jonas'],

'score': [12.5, 9, 16.5, np.nan, 9, 20, 14.5, np.nan, 8, 19],

'attempts': [1, 3, 4, 3, 5, 3, 6, 1, 7, 1] }
df=pd.DataFrame(exam_data)
df
Screenshot 2025-02-27 191602 Write a Python program to select the 'name' and 'score' columns from the following DataFrame

selected_columns=df[['name','score']]
selected_columns
Screenshot 2025-02-27 191831 2)For the above dataframe, Write a program to select the data who's attempt is greater than 3

filtered_data=df[df['attempts']>3]
filtered_data

Screenshot 2025-02-27 212148

3)Write python code for indexing rows and columns based on the following conditions: Assume we have the following dataframe:

data = {'name': ['Alice', 'Bob', 'Charlie', 'Dave'],

'age': [25, 35, 40, 28],

'gender': ['F', 'M', 'M', 'M'],

'salary': [50000, 70000, 60000, 80000]}

df = pd.DataFrame(data)

data = {'name': ['Alice', 'Bob', 'Charlie', 'Dave'],

'age': [25, 35, 40, 28],

'gender': ['F', 'M', 'M', 'M'],

'salary': [50000, 70000, 60000, 80000]}

df = pd.DataFrame(data)
Screenshot 2025-02-27 212243

a. Select rows where age is greater than 30:

age=df[df['age']>30]
age
Screenshot 2025-02-27 212320

b. Select rows where name contains 'e':

name=df[df['name'].str.contains('e')]
name

Screenshot 2025-02-27 212405

c. Select rows where gender is 'M' and salary is greater than 65000:

A=df[(df['gender']=='M') & (df['salary']>65000)]
A
Screenshot 2025-02-27 212439

d. Select columns 'name' and 'age'

B=df[['name','age']]
B
Screenshot 2025-02-27 212509

ACTIVITY 2:
Write python code for indexing rows and columns using iloc or loc method based on the following conditions:
path='/content/drive/My Drive/Bank_train.csv'
df=pd.read_csv(path)
df
Screenshot 2025-02-27 212555

a. select the rows where clients with primary education have subscribed to a deposit?

rows= df.loc[(df['education'] == 'primary') & (df['deposit']=='yes')]
rows
Screenshot 2025-02-27 212639

b. select the rows where clients who have not subscribed to a deposit?

rows= df.loc[(df['deposit']=='no')]
rows
Screenshot 2025-02-27 212713

c. select the rows where clients who have subscribed to a deposit either have a housing or a personal loan?

A= df.loc[(df['deposit']=='yes') & ((df['housing']=='yes') | (df['loan']=='yes'))]
A
Screenshot 2025-02-27 212806

d. select the rows where clients with secondary education who have not subscribed to a deposit?

rows= df.loc[(df['education'] == 'secondary') & (df['deposit']=='no')]
rows

Screenshot 2025-02-27 212853

e. select the rows where clients who have subscribed to a term deposit as an outcome of the successful marketing campaign?

B= df.loc[(df['poutcome'] == 'success') & (df['deposit']=='yes')]
B

image

f. select the rows where unemployed clients who have not subscribed to deposit?

J= df.loc[(df['job'] == 'unemployed') & (df['deposit']=='no')]
J
Screenshot 2025-02-27 213004

g. Select columns 'name' and 'salary' where age is less than or equal to 30:

H = df.loc[df['age'] <= 30, ['age', 'balance']]
H
Screenshot 2025-02-27 213035

h.select coloumns ‘education’ and ‘balance’ where age is less than or equal to 30.

H = df.loc[df['age'] <= 30, ['education', 'balance']]
H
Screenshot 2025-02-27 213122

Result:
Thus the program for the given question has been run and executed successfully
