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

### DEVELOPED BY : swarhi.s
### REG NO : 212223040219.


```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/da11e46d-1fa9-4206-a096-7ca38ca93138)
```
df.head(10)
```
![image](https://github.com/user-attachments/assets/c5bdf8ac-bf0d-4dd5-a9c3-594564348ff6)
```
df.tail(10)
```
![image](https://github.com/user-attachments/assets/5a1102e2-cc2b-4715-8db8-835347ab67db)
```
df.info()
```
![image](https://github.com/user-attachments/assets/19b25e01-b764-4b6f-89e6-8fa2692a25fa)
```
df.describe()
```
![image](https://github.com/user-attachments/assets/0374a6bd-4ac4-4179-9cf5-e7ba10521154)
```
df.shape
```
![image](https://github.com/user-attachments/assets/ffa2cbde-65f4-43b4-93a2-2b59cfba58a4)
```
df.set_index("PassengerId",inplace=True)
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/f7d5e877-dd40-4d5e-be50-066c9c0032bd)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/c06bafaa-d0fe-4d8d-824b-a70831bc82dd)
```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/249d6127-dce2-4d0f-80b3-3ec6cd2aefdb)
```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/90183f2f-c6a0-4892-bdc7-9cce2dc479dc)

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/c21866e5-b2cc-4557-aed7-dafb6b224edc)
```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/b06eb160-3887-4b8c-9563-88cfd870c05a)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5)
```
![image](https://github.com/user-attachments/assets/30d21430-55f4-42cb-924c-a13909fd8027)
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/c70f3e59-263d-4dd5-808c-549ff511ae3c)
```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/b958388f-a96e-4993-ad68-b4131cb83bcf)
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/e74dcf08-fe27-41b5-9438-5d78bb711cbb)
```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/04bd92ad-d0e5-4be8-a904-d935589d5b9b)

```
fig,ax1 = plt.subplots(figsize=(8,5))
sns.boxplot(ax=ax1, x="Pclass",y="Age",hue="Gender",data=df)
```
![image](https://github.com/user-attachments/assets/03485e50-90ac-4a38-a3f9-02a01be83c78)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/e57e79ae-65c3-410c-8c77-62dfba5b9af3)
```
## Co-relation
corr=df.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/4ff74237-9ee9-4c65-98ea-4751db167a76)
```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/9ae10350-e571-4c05-b270-afafd56c3200)

![image](https://github.com/user-attachments/assets/49e671af-9496-473d-83b3-b48a433c23a9)

# RESULT
Thus, the Exploratory Data Analysis on the given data set was performed successfully.
