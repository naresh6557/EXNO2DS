## NAME : NARESH KUMAR R 
## REGISTER NUMBER : 212224040213
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
 import seaborn as sns
 df=pd.read_csv("C:/Users/admin/Downloads/titanic_dataset.csv")
 print(df)
 ```
<img width="1002" height="680" alt="image" src="https://github.com/user-attachments/assets/4bd1bf34-c5bf-41ba-b510-4510cf56928d" />

```
df.info()
```
<img width="411" height="409" alt="image" src="https://github.com/user-attachments/assets/e3a98245-4759-4944-bb75-22ca356de77a" />

```
df.describe()
```
<img width="739" height="308" alt="image" src="https://github.com/user-attachments/assets/b825b231-1b51-482b-99a2-748f6a8495f6" />

```
df.dtypes
```
<img width="235" height="285" alt="image" src="https://github.com/user-attachments/assets/08101d3d-ea0e-45d0-9cf6-70598f3ed7d2" />

```
df.shape
```
<img width="109" height="40" alt="image" src="https://github.com/user-attachments/assets/b1b5cb62-2558-4958-ac82-340765577322" />

```
df.value_counts()
```
<img width="751" height="595" alt="image" src="https://github.com/user-attachments/assets/fe49641b-919e-40ce-aea1-3d91f31c5029" />

```
df['Age'].value_counts()
```
<img width="415" height="272" alt="image" src="https://github.com/user-attachments/assets/8e2b32ed-9cdc-4ae1-b6c1-ab73ebc87c3d" />

```
df.set_index("PassengerId",inplace=True)
print(df)
```
<img width="788" height="637" alt="image" src="https://github.com/user-attachments/assets/f8b36297-a21d-4386-97ab-87e92bc819ee" />

```
df.nunique()
```
<img width="256" height="265" alt="image" src="https://github.com/user-attachments/assets/468308f9-f5f7-441d-90a6-d2469e4e5271" />

```
sns.countplot(data=df,x='Age')
```
<img width="755" height="581" alt="image" src="https://github.com/user-attachments/assets/5bb84e98-84fa-409d-ba0c-fccbc79cda76" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
print(df)
```
<img width="803" height="643" alt="image" src="https://github.com/user-attachments/assets/66300236-88b7-48be-80b2-3b2616be3bd1" />

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
<img width="763" height="589" alt="image" src="https://github.com/user-attachments/assets/24147edb-76fe-434c-ab8a-53d8fb78e2da" />

```
df.boxplot(column='Age',by="Survived")
```
<img width="762" height="630" alt="image" src="https://github.com/user-attachments/assets/bff2c2fa-a140-4021-99f4-096e82d91212" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
<img width="758" height="594" alt="image" src="https://github.com/user-attachments/assets/53a68408-7ea6-4b60-bb07-ac64a8ee78f1" />

```
plt=sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```
<img width="737" height="548" alt="image" src="https://github.com/user-attachments/assets/e7ec5ce0-b678-4368-894c-27151d7d94a3" />

```
sns.catplot(x="Pclass",y="Age",hue="Gender",col="Survived",kind="box",data=df)
```
<img width="757" height="390" alt="image" src="https://github.com/user-attachments/assets/e60e18d6-5f71-4f3b-b5a7-0a12739d8e36" />

```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```
<img width="723" height="573" alt="image" src="https://github.com/user-attachments/assets/286b06a0-5c73-4e1a-968a-4dbb69e6cfbb" /> 

# RESULT
Thus, To perform Exploratory Data Analysis on the given data set is implemented successfully.
