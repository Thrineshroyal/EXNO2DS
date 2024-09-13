# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
## Developed by: T Thrinesh Royal
## Reg.No: 212223230226

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
1)Step1:
```Python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
dt=pd.read_csv("titanic_dataset.csv")
dt
```
<br>
<br>

## Output:
![image](https://github.com/user-attachments/assets/086d4b26-2cac-4384-820d-734f676ba3f8)

## Step2:
```Python
dt.info()
```
## Output:
![image](https://github.com/user-attachments/assets/9ded7311-5069-4a93-a12b-df562a86362c)

## Step3:
```Python
dt.shape
```
## Output:
![image](https://github.com/user-attachments/assets/55fe48cd-964f-47b6-bdf8-545897623b2d)

## Step4:
```Python
dt.describe()
```
## Output:
![image](https://github.com/user-attachments/assets/0543a4a6-5f3c-4617-97f5-7983428fef9e)

## Step5:
```Python
dt.nunique()
```

## Output:
![image](https://github.com/user-attachments/assets/4a178921-ec11-4d49-8b30-3bc9470d9b53)

## Step6:
```Python
dt["Survived"].value_counts()
```
## Output:
![image](https://github.com/user-attachments/assets/1cab5dff-6c0a-4059-b45d-91f9022a5e03)

## Step7:
```Python
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
## Output:
![image](https://github.com/user-attachments/assets/f79eddd0-0835-4aa0-8a0f-3485dd7f40a7)

## Step8:
```Python
sns.countplot(data=dt,x="Survived")
```
## Output:
![image](https://github.com/user-attachments/assets/9a361d93-bf8a-4ce4-8c56-313473e3e174)

## Step9:
```Python
dt.Pclass.unique()
```
## Output:
![image](https://github.com/user-attachments/assets/c51f7d0f-a39b-4a4b-a572-3606e5a76407)

## Step10:
```Python
dt.rename(columns={"Sex":"Gender"},inplace=True)
dt
```
## Output:
![image](https://github.com/user-attachments/assets/034f2630-0828-4466-8105-9b4822346ac0)

## Step11:
```Python
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```
## Output:
![image](https://github.com/user-attachments/assets/7245aeed-0d45-4697-9b92-6500c1e0669a)

## Step12:
```Python
sns.catplot(x="Survived",hue='Gender',data=dt,kind='count')
```
## Output:
![image](https://github.com/user-attachments/assets/d0ab5312-5ae6-4e53-a9b0-4ad79db29b50)

## Step13:
```Python
dt.boxplot(column="Age",by="Survived")
```
## Output:
![image](https://github.com/user-attachments/assets/df30afc0-ea09-4c45-ba8b-4534ee05f323)

## Step14:
```Python
sns.scatterplot(data=dt,x="Age",y="Fare",hue="Survived")
```
## Output:
![image](https://github.com/user-attachments/assets/3a4a8ef3-12c3-4f29-af45-394dedc076ec)

## Step15:
```Python
sns.jointplot(data=dt,x="Age",y="Fare",hue="Survived")
```
## Output:
![image](https://github.com/user-attachments/assets/118f0373-6119-4c75-b66f-9b9193579dc8)

## Step16:
```Python
sns.catplot(x="Gender",col="Survived",hue="Pclass",kind="count",data=dt)
```
## Output:
![image](https://github.com/user-attachments/assets/552d7bfd-91c1-49d0-b66f-6ac25a3ee07a)

## Step17:
```Python
numeric_dt=dt.select_dtypes(exclude=[object])
corr=numeric_dt.corr()
sns.heatmap(corr,annot=True)
```
## Output:
![image](https://github.com/user-attachments/assets/49d138dc-4615-4534-a74d-4d24ab0b3932)


## Step18:
```Python
sns.pairplot(dt)
```
## Output:
![image](https://github.com/user-attachments/assets/376cddfd-696c-4c5c-9692-ee4ba73eedc7)
![image](https://github.com/user-attachments/assets/00cd70fa-81b3-4aca-acea-2ee83f913adb)
