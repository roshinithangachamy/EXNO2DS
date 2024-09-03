
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
df=pd.read_csv('/content/titanic_dataset.csv')
df
```
![image](https://github.com/user-attachments/assets/dca98844-f9f2-44ea-a1f6-a8e616e4bf66)
```
df.isnull().sum()
```
![image](https://github.com/user-attachments/assets/9d17cf72-7d53-4a8f-a7ad-5f7fede9f1e7)
```
df.dropna(inplace=True)
```
![image](https://github.com/user-attachments/assets/a1523901-5c7d-4454-bdb1-b94bb82c25d9)
```
df.isnull().sum()
```
![image](https://github.com/user-attachments/assets/09185c6d-0ee0-4fba-bcfb-0cc09ba84dd5)
```
df.info()
```
![image](https://github.com/user-attachments/assets/1f913098-dc08-49b7-9dd2-5b0c9fe08e64)
```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/user-attachments/assets/117ecf76-d1e1-4f3f-96d7-373e810a03d0)
```
df
```
![image](https://github.com/user-attachments/assets/42212308-7aa2-478b-9ff9-26cc0dbc86e5)

```
df.nunique()
```
![image](https://github.com/user-attachments/assets/29d364f2-c334-4dd7-a1bc-7b9e08dd2f8f)
```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/659d3352-1693-491e-bb21-632ce5e78a3d)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/35a88679-3b44-4704-94c1-227946bfe408)
```
import matplotlib.pyplot as plt
import seaborn as sns

sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/3313c5e6-8efd-47e8-b953-5b3a4b8e6e4a)
```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/dd2373a7-3b42-49b5-a377-9d00327ebed7)
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/37b44ff6-cc2c-41b5-97e7-6f8823274bad)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/d2097903-f160-48ec-96b2-7e1205dac6e4)
```
sns.catplot(data=df,col = "Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/73ba5e1a-d117-4642-8915-1240814641d4)

# RESULT
The Exploratory Data Analysis on the given data set has been performed.
