## Ex 01
## Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output
```
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
```
```
df
```
![image](https://github.com/user-attachments/assets/1851cba8-5668-46c5-b2a7-58f2f5acf9f7)

```
df.shape
```
(21, 12)

```
df.describe()
```
![image](https://github.com/user-attachments/assets/e9260436-813d-4fd9-bafc-16c99e1d0242)
```
df.info()
```
![image](https://github.com/user-attachments/assets/71c14613-8cfe-4d93-b8c7-332b357a84e6)
```
df.head(10)
```
![image](https://github.com/user-attachments/assets/c2da3024-d9dc-4a50-bb47-68d16ea49fcc)

```
df.tail(10)
```
![image](https://github.com/user-attachments/assets/bf98a7de-6771-4896-833b-b0cea0f4e271)

```
df.isna().sum()
```
![image](https://github.com/user-attachments/assets/6815d05d-9e0d-4d76-b306-a1150cb98d3d)

```
df.dropna(how='any').shape
```
(13, 12)

```
df.shape
```
(21, 12)

```
x=df.dropna(how='any')
x
```
![image](https://github.com/user-attachments/assets/6cf22cdd-9d7e-4adb-8e20-e59776d292d5)

```
mn=df.TOTAL.mean()
mn
```
![image](https://github.com/user-attachments/assets/528860cd-8b01-4687-9dc2-22d6c89a1c62)

```
df.TOTAL.fillna(mn,inplace=True)
df
```

![image](https://github.com/user-attachments/assets/57b388bf-3227-4815-8892-200cceaee871)

```
df.isnull().sum()
```
![image](https://github.com/user-attachments/assets/4060aa41-a1fd-4eb7-bec3-7f632eb795f2)
```
df.M1.fillna(method='ffill',inplace=True)
df
```
![image](https://github.com/user-attachments/assets/1553b527-25bd-460c-8d1b-881242609750)
```
df.isnull().sum()
```
![image](https://github.com/user-attachments/assets/b800bc63-dcc8-43a7-9cc8-d67c93b1baff)













# Result
Thus the program executed successfully          
