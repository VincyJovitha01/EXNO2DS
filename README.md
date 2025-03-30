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
### Developed by: Vincy Jovitha V
### Register no: 212223230242
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns  
df=pd.read_csv("titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/0a6919fd-24c7-4e3e-8bc9-20c2e6c850a0)

```
df.info()
```
![image](https://github.com/user-attachments/assets/84c60709-2ede-43ce-b089-246cda7f8418)

```
df.shape
```
![image](https://github.com/user-attachments/assets/c0dfa8d6-79f7-4597-9a12-e3c6e36f09d8)

```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/user-attachments/assets/68962cd3-54c9-49ea-b9e4-cb8a6d122194)

```
df.shape
```
![image](https://github.com/user-attachments/assets/1a87d127-2173-448f-829f-023b2d61816e)

### Categorical data analysis
```
df.nunique()
```
![image](https://github.com/user-attachments/assets/d5f6d51b-1396-4164-b784-0ee80675707a)


```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/3fedfc48-6e48-4589-9f59-cf7895c9189d)

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/1b04b9c6-266e-4406-8da8-c13abeea29d4)

```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/0587ba82-30fe-4ea7-b1f7-fcbd0cc6ac15)


```
df
```
![image](https://github.com/user-attachments/assets/8485c48c-2548-4950-8a14-09ecd0cfb89e)

```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/68e7e87f-cd47-449f-b215-10b210d0f141)

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/9634f01b-a334-4a3f-a3f7-a1e112300d3b)

### Bivariate Analysis
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/74935e66-3dc9-4e0b-9270-7cbbe1b9e9c2)

```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/db8144e3-21a8-47fc-a1d7-40deb7766e1f)

```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/50543f68-58a1-4f52-a432-71b698c0fe5c)

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/5123da08-5522-4d2e-9149-c1eb0e302fea)

```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/995a304b-70b7-45cc-8dd6-a441c55a940e)


### Multivariate Analysis
```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/3a7ac7a3-f59b-48e6-a757-7b9271887817)

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/f66b44e8-40d1-40de-b67c-a4f46c48703f)

# Co-relation
```
corr=df.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/a533f225-2b6e-4e51-812c-77cac0c2f56a)

```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/b0267798-d3d4-4fa2-a42e-041e26126e0b)

# RESULT
We have performed Exploratory Data Analysis on the given data set successfully.

