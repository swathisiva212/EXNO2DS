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

### Developed by:swathi.s
### Register No.:212223040219

~~~
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns 
df=pd.read_csv("titanic_dataset.csv")
df
~~~

![Screenshot 2024-09-03 082203](https://github.com/user-attachments/assets/ec2099a5-cc87-45ac-914e-1fa9d28b413e)

~~~
df.info()
~~~

![Screenshot 2024-09-03 082339](https://github.com/user-attachments/assets/701ae975-c450-4950-9c37-a3d063018b60)

~~~
df.shape
~~~

(891, 12)

~~~
df.set_index("PassengerId",inplace=True)
df.describe()
~~~

![Screenshot 2024-09-03 082625](https://github.com/user-attachments/assets/8ffd8586-fbc8-449e-b863-866ca9d5ee82)

~~~
df.shape
~~~

(891, 11)


### Categorical data analysis
       
~~~
df.nunique()
~~~

![Screenshot 2024-09-03 082814](https://github.com/user-attachments/assets/e8435a22-a168-4650-8347-1cbaa42971bd)

~~~
df["Survived"].value_counts()
~~~

![Screenshot 2024-09-03 082930](https://github.com/user-attachments/assets/501eedff-179a-41f2-9edc-48ef4a2e0ddb)

~~~
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
~~~

![Screenshot 2024-09-03 083017](https://github.com/user-attachments/assets/14c60dca-d087-49f5-a1c0-f00f3e49666f)

~~~
sns.countplot(data=df,x="Survived")
~~~

![Screenshot 2024-09-03 083111](https://github.com/user-attachments/assets/6081d94c-ca7b-442f-81dc-f63185cab764)

~~~
df
~~~

![Screenshot 2024-09-03 083209](https://github.com/user-attachments/assets/88d1d036-9854-4a95-a9b2-7a3ea71cf585)

~~~
df.Pclass.unique()
~~~

array([3, 1, 2], dtype=int64)

~~~
df.rename(columns={'Sex':'Gender'},inplace=True)
df
~~~

![Screenshot 2024-09-03 083337](https://github.com/user-attachments/assets/8b6e46f2-0568-4b8f-bed5-557ada936974)


### Bivariate Analysis

~~~
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
~~~

![Screenshot 2024-09-03 083436](https://github.com/user-attachments/assets/0b5c353a-a86a-4e4c-b85b-bc7577938116)

~~~
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
~~~

![Screenshot 2024-09-03 083540](https://github.com/user-attachments/assets/47d021f2-1b1d-4e24-a5c4-b51795d20ec2)

~~~
df.boxplot(column="Age",by="Survived")
~~~

![Screenshot 2024-09-03 083619](https://github.com/user-attachments/assets/f60e5924-9587-4c12-8f27-272807ed8e3e)

~~~
sns.scatterplot(x=df["Age"],y=df["Fare"])
~~~

![Screenshot 2024-09-03 083735](https://github.com/user-attachments/assets/c4dd4085-99c6-4ddd-98d8-4d6d90fb05aa)

~~~
sns.jointplot(x="Age",y="Fare",data=df)
~~~

![Screenshot 2024-09-03 083831](https://github.com/user-attachments/assets/a748af80-2ef4-48e2-b6ee-0b94eac18c69)



### Multivariate Analysis

~~~
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
~~~

![Screenshot 2024-09-03 083912](https://github.com/user-attachments/assets/7c6d01b2-cdc9-49fa-9599-8a6f9db25912)

~~~
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
~~~

![Screenshot 2024-09-03 084012](https://github.com/user-attachments/assets/7836d240-4977-4149-a314-17253648818c)



### Co-relation

~~~
corr=df.corr()
sns.heatmap(corr,annot=True)
~~~

![Screenshot 2024-09-03 084138](https://github.com/user-attachments/assets/59c83d73-b80b-4d8f-bc8f-18bfd31c02a8)

~~~
sns.pairplot(df)
~~~

![Screenshot 2024-09-03 084352](https://github.com/user-attachments/assets/899c16f0-c9cb-46c8-bd7b-568e74de9390)



# RESULT
        We have performed Exploratory Data Analysis on the given data set successfully.
