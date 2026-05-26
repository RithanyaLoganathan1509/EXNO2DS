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
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("titanic_dataset.csv")
df
```
<img width="1226" height="441" alt="image" src="https://github.com/user-attachments/assets/f29e0d4f-29ba-4c6b-84fb-c769e887405d" />

```
df.info()
```
<img width="409" height="413" alt="image" src="https://github.com/user-attachments/assets/f0faaee5-308f-4ab7-8f09-be40eeeb032e" />

```
df.describe()
```
<img width="731" height="296" alt="image" src="https://github.com/user-attachments/assets/1237cf4d-2625-4e69-b509-63bc1b401853" />

```
df.dtypes
```
<img width="316" height="289" alt="image" src="https://github.com/user-attachments/assets/34cb9e27-919b-4a9c-972d-0233dc61cc31" />

```
df.value_counts()
```
<img width="1250" height="546" alt="image" src="https://github.com/user-attachments/assets/c638d27c-b129-4cfb-b2f9-1c7c3dc6b8f3" />

```
df['Age'].value_counts()
```
<img width="369" height="269" alt="image" src="https://github.com/user-attachments/assets/051ee230-46eb-4738-9164-4a8c17464cf1" />

```
df.set_index("PassengerId",inplace=True)
df.describe()
```
<img width="636" height="298" alt="image" src="https://github.com/user-attachments/assets/34a862fb-d200-4fb1-9a72-541b2c9586f6" />

```
df.shape
```
<img width="139" height="37" alt="image" src="https://github.com/user-attachments/assets/5c9df46c-c1b4-4524-9174-8f0535be0a35" />

```
df.nunique()
```
<img width="240" height="268" alt="image" src="https://github.com/user-attachments/assets/3b780c4d-26ed-4e42-acc1-7d62ffcca4f8" />

```
sns.countplot(data=df,x='Survived')
```
<img width="757" height="579" alt="image" src="https://github.com/user-attachments/assets/0fbfa906-3430-4606-8680-0c20778066ad" />

```
df.Pclass.unique()
```
<img width="302" height="35" alt="image" src="https://github.com/user-attachments/assets/6e05eaa4-d88b-42e3-80e8-667399ba7719" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
<img width="1227" height="472" alt="image" src="https://github.com/user-attachments/assets/48e503e8-3c9c-4b8d-9fcf-b71ae3bfb94e" />

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=7,aspect=.7)
```
<img width="1010" height="728" alt="image" src="https://github.com/user-attachments/assets/d6de9f6c-9df9-4536-8656-eaad60947229" />

```
df.boxplot(column="Age",by="Survived")
```
<img width="754" height="611" alt="image" src="https://github.com/user-attachments/assets/1d7b292e-b71b-45c8-a312-54751ef4eb56" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
<img width="768" height="579" alt="image" src="https://github.com/user-attachments/assets/e762f1ca-3cf5-4b1e-9eb7-5b94bc1abd70" />

```
fig,ax1=plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
<img width="897" height="569" alt="image" src="https://github.com/user-attachments/assets/27adff05-e203-4d14-a984-f1ca6761aa69" />

```
plt = sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```
<img width="715" height="540" alt="image" src="https://github.com/user-attachments/assets/99775db7-4ccc-4348-8443-61d1a5c07b79" />

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
<img width="1242" height="621" alt="image" src="https://github.com/user-attachments/assets/b4bd2c76-bcaa-42ea-b6a5-eebcd7323b40" />

```
sns.pairplot(data=df)
```
<img width="848" height="815" alt="image" src="https://github.com/user-attachments/assets/240f2c29-43fa-4ff8-931c-103410ea0138" />

```
corr1 = df.select_dtypes(include=['number']).corr()
sns.heatmap(corr1, annot=True)
```
<img width="657" height="528" alt="image" src="https://github.com/user-attachments/assets/a58c7978-4dbb-46f6-97e0-800a68876084" />

# RESULT
Thus, To perform Exploratory Data Analysis on the given data set is implemented successfully.
