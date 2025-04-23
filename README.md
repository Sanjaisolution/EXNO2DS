# EXNO2DS-Exploratory Data Analysis
## AIM:
  To perform Exploratory Data Analysis on the given data set.
      
## EXPLANATION:
 The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
## ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
### Developed by: SANJAI.R 
### Register no: 212223040180
```py
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns  
df=pd.read_csv("titanic_dataset.csv")
df
```
![Screenshot 2025-03-26 152839](https://github.com/user-attachments/assets/660f628a-37a9-4ed3-a07a-31a1dbbeec1b)


```py
df.info()
```

![Screenshot 2025-03-26 152859](https://github.com/user-attachments/assets/b0376f90-88a7-4a34-b203-e0fc7de77805)

```py
df.shape
```
![Screenshot 2025-03-26 153625](https://github.com/user-attachments/assets/a3692ec6-4e07-4e97-98c0-db28b2f09faf)


```py
df.set_index("PassengerId",inplace=True)
df.describe()
```
![Screenshot 2025-03-26 152910](https://github.com/user-attachments/assets/97817493-9d3b-4f8a-b4f8-12b2c48aff2d)


```py
df.shape
```
![Screenshot 2025-03-26 152922](https://github.com/user-attachments/assets/561d9269-fc49-40c6-a937-4e466ed531f0)


### Categorical data analysis
```py
df.nunique()
```
![Screenshot 2025-03-26 152932](https://github.com/user-attachments/assets/d9e85e78-2876-4a6a-8f8d-4f6aa8a2187e)


```py
df["Survived"].value_counts()
```
![Screenshot 2025-03-26 152944](https://github.com/user-attachments/assets/2f9a4066-0d21-42e7-bff4-db2e33c9ac01)


```py
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![Screenshot 2025-03-26 152953](https://github.com/user-attachments/assets/37d3d984-e3bb-46b3-bc97-db7b9797899c)


```py
sns.countplot(data=df,x="Survived")
```
![Screenshot 2025-03-26 153004](https://github.com/user-attachments/assets/0df8fa63-d6c2-45a7-be64-1485d1a55f71)


```py
df
```
![Screenshot 2025-03-26 153022](https://github.com/user-attachments/assets/3f6cdde6-3895-41ee-a201-6d8b34f12e4f)


```py
df.Pclass.unique()
```
![Screenshot 2025-03-26 153036](https://github.com/user-attachments/assets/b11ba621-8b9e-4fd3-b4d2-f19acbb743ce)


```py
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![Screenshot 2025-03-26 153057](https://github.com/user-attachments/assets/de80326b-d37d-4b7e-ae5a-d239ce84e57f)


### Bivariate Analysis
```py
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![Screenshot 2025-03-26 153112](https://github.com/user-attachments/assets/090b3d62-a759-4303-9851-041cd5d1a619)


```py
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![Screenshot 2025-03-26 153125](https://github.com/user-attachments/assets/bfe4c5cb-bca1-46a3-841c-8134e1b3f770)


```py
df.boxplot(column="Age",by="Survived")
```
![Screenshot 2025-03-26 153142](https://github.com/user-attachments/assets/952ff0f1-9e60-4403-9da3-4629be6c6a9a)


```py
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![Screenshot 2025-03-26 153220](https://github.com/user-attachments/assets/eaf7eead-f2c1-4958-b0bd-f3f78f77cbf6)


```py
sns.jointplot(x="Age",y="Fare",data=df)
```
![Screenshot 2025-03-26 153353](https://github.com/user-attachments/assets/83bfc138-50d9-40b1-9293-845f8aad4947)


### Multivariate Analysis
```py
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![Screenshot 2025-03-26 153410](https://github.com/user-attachments/assets/db0e0041-519b-45ab-98cc-5d5015d82b7a)


```py
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![Screenshot 2025-03-26 153422](https://github.com/user-attachments/assets/134c287b-7d09-488f-9404-e4ee6be6a560)


# Co-relation
```py
corr=df.corr()
sns.heatmap(corr,annot=True)
```
![Screenshot 2025-03-26 153432](https://github.com/user-attachments/assets/b77b0b24-9656-4abf-88fe-f920d2d8726c)


```py
sns.pairplot(df)
```
![Screenshot 2025-03-26 153456](https://github.com/user-attachments/assets/8b68060c-1ca5-4e78-ae60-1578580a7c76)


## RESULT
We have performed Exploratory Data Analysis on the given data set successfully.
