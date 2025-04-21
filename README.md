# EX  01
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
         REG NO : 212224230141
         NAME : LOGU R
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
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
```
df.M2.fillna(method='ffill',inplace=True)
df
```
![image](https://github.com/user-attachments/assets/62d89f13-619b-4e08-aa3b-f2267e0fccc7)

```
df.isna().sum()
```
![image](https://github.com/user-attachments/assets/29aa195e-e6f9-444c-9a2a-f97fc5276446)
```
df.M3.fillna(method='ffill',inplace=True)
df
```
![image](https://github.com/user-attachments/assets/2fa0ceb9-3678-413f-a537-2b0cd3f75746)
```
df.isnull().sum()
```
![image](https://github.com/user-attachments/assets/556bfd82-caea-45b5-a2f0-2da681f754f5)
```
df.duplicated()
```
![image](https://github.com/user-attachments/assets/c64f84e4-e6d3-4b1d-a38f-589198ad4288)
```
df.drop_duplicates(inplace=True)
df
```

![image](https://github.com/user-attachments/assets/071b9d75-6cf6-4fc4-8f31-ef3cdef84b99)
```
df.duplicated()
```
![image](https://github.com/user-attachments/assets/17e73991-18f5-49d7-8206-ca7f475c02f0)
```
df['DOB']
```
![image](https://github.com/user-attachments/assets/2c0883bf-3e20-4479-80ce-7a6b455131c9)
```
import seaborn as sns
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
```
![image](https://github.com/user-attachments/assets/6a44d724-6bfb-43fe-b7d0-3b3a1e2e0131)
```
df.dropna(inplace=True)
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
```
![image](https://github.com/user-attachments/assets/256f685b-47cd-4e0c-b678-92b8ab963ce3)
```
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
df=pd.DataFrame(age)
df
```
![image](https://github.com/user-attachments/assets/b7133cbf-3ab5-48ef-9c7a-50a8001ab2dd)
```
sns.boxplot(data=df)
```
![image](https://github.com/user-attachments/assets/c4938f63-b3ae-4d14-a556-548f010efc72)
```
sns.scatterplot(data=df)
```
![image](https://github.com/user-attachments/assets/caca0cb3-41c3-4481-983d-ec781a53b5dd)
```
q1=df.quantile(0.25)
q2=df.quantile(0.5)
q3=df.quantile(0.75)
iqr=q3-q1
iqr
```

![image](https://github.com/user-attachments/assets/51bd3e9c-8a4e-42cb-82e5-27f86fdb113f)
























# Result
Thus the program executed successfully          
