# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
```import pandas as pd
df=pd.read_csv('/content/titanic_dataset.csv')
df
```
![image](https://github.com/user-attachments/assets/46ba2f85-fe6b-4083-9d43-707bddf48f61)
```
df.isna().sum()
```
![image](https://github.com/user-attachments/assets/1902ba40-6427-4a0d-8f4e-75223eddcba2)

```
df.dropna(inplace=True)
df
```
![image](https://github.com/user-attachments/assets/05f83b9c-31f8-4b1b-a11f-d6d8e21f2b6c)
```
df.isnull().sum()
```
![image](https://github.com/user-attachments/assets/1d170c22-3959-4f47-a5fd-e744c2c25690)

```
df.info()
```
![image](https://github.com/user-attachments/assets/87f00135-45bd-48fa-8894-8e7c2537584b)

```
df.shape
```
![image](https://github.com/user-attachments/assets/fd6361bb-f2a9-43f7-8157-e31421a54f67)
```
df.set_index("PassengerId",inplace=True)
df
```
![image](https://github.com/user-attachments/assets/189a306a-da3b-499b-b4c5-a1c7f2e22975)

```
df.nunique()
```
![image](https://github.com/user-attachments/assets/b14de8a0-7b68-46ef-b30b-c39e915e0fe3)
```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/5cde5852-9c4b-4917-8381-892181370568)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/024ec984-c785-42f5-8f58-51624b05b999)
```
import matplotlib.pyplot as plt
import seaborn as sns
sns.countplot(data=df,x="Survived")
```

![image](https://github.com/user-attachments/assets/b20b3fcc-5fe1-410b-90f1-2b7bb0688038)
```
df
```
![image](https://github.com/user-attachments/assets/0973a390-5e43-49c3-bee3-777db2eefe18)
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/96c6bd86-67ad-46e5-a168-a0ded1a23e59)

```
sns.catplot(x='Survived',hue='Gender',data=df,kind='count')
```
![image](https://github.com/user-attachments/assets/22fd2dcd-605d-4c63-a039-09b2c360c541)
```
sns.catplot(data=df,col='Survived',x='Gender',hue='Pclass',kind='count')
```
![image](https://github.com/user-attachments/assets/a71cf316-8e95-45d6-8551-009e6227ce7e)


# RESULT
   This process helps in effective data cleaning, outlier detection, and exploratory data analysis (EDA).        
