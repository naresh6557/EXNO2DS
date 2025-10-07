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
df=pd.read_csv("Encoding Data.csv")
df
```
<img width="770" height="616" alt="image" src="https://github.com/user-attachments/assets/81d721f3-531d-4303-9ea2-16a6fa0d8c5e" />

```
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
pm=['Hot','Warm','Cold']
e1=OrdinalEncoder(categories=[pm])
e1.fit_transform(df[["ord_2"]])
```
<img width="732" height="373" alt="image" src="https://github.com/user-attachments/assets/3afd533e-c780-4b61-895d-6a7701b482d9" />

```
df['bo2']=e1.fit_transform(df[["ord_2"]])
df
```
<img width="688" height="532" alt="image" src="https://github.com/user-attachments/assets/4e8f1a77-da1e-4529-b250-160f64b72ff8" />

```
le=LabelEncoder()
dfc=df.copy()
dfc['ord_2']=le.fit_transform(dfc['ord_2'])
dfc
```
<img width="685" height="571" alt="image" src="https://github.com/user-attachments/assets/994adfad-cbcf-4f9c-aa68-37f140c88644" />

```
from sklearn.preprocessing import OneHotEncoder
ohe=OneHotEncoder()
df2=df.copy()
enc=pd.DataFrame(ohe.fit_transform(df2[["nom_0"]]))
df2=pd.concat([df2,enc],axis=1)
df2
```
<img width="1117" height="631" alt="image" src="https://github.com/user-attachments/assets/0a544c0a-9712-4896-a582-775236d82776" />

```
pd.get_dummies(df2,columns=["nom_0"])
```
<img width="872" height="343" alt="image" src="https://github.com/user-attachments/assets/4c693520-7b5e-417f-b3c9-a2e3573f5da9" />

```
pip install --upgrade category_encoders
```
<img width="908" height="268" alt="image" src="https://github.com/user-attachments/assets/1270bb9a-4a1b-4d68-90bd-e06eefb8cb29" />

```
from category_encoders import BinaryEncoder
df=pd.read_csv("data.csv")
df
```
<img width="623" height="416" alt="image" src="https://github.com/user-attachments/assets/061eee53-47ce-411d-9f61-80265fe1cd2e" />

```
be=BinaryEncoder()
nd=be.fit_transform(df['Ord_2'])
df
```
<img width="585" height="403" alt="image" src="https://github.com/user-attachments/assets/4209d94d-e8e0-4843-a909-1df597a78d58" />

```
dfb=pd.concat([df,nd],axis=1)
dfb
```
<img width="706" height="392" alt="image" src="https://github.com/user-attachments/assets/77e8b845-b0d6-4bb5-98d2-e1ce471c8507" />

```
from category_encoders import TargetEncoder
te=TargetEncoder()
CC=df.copy()
new=te.fit_transform(X=CC["City"],y=CC["Target"])
CC=pd.concat([CC,new],axis=1)
CC
```
<img width="657" height="448" alt="image" src="https://github.com/user-attachments/assets/8b140f54-03d7-48a1-b49a-ab7774be7212" />

```
import pandas as pd
from scipy import stats
import numpy as np
df=pd.read_csv("Data_to_Transform.csv")
df
```
<img width="756" height="472" alt="image" src="https://github.com/user-attachments/assets/f348785e-9299-48a7-90f8-957f7abb8515" />

```
df.skew()
```
<img width="500" height="320" alt="image" src="https://github.com/user-attachments/assets/4e895803-1e39-410c-a23c-71fae487e25c" />

```
np.log(df["Highly Positive Skew"])
```
<img width="493" height="413" alt="image" src="https://github.com/user-attachments/assets/21402e29-9582-417a-a9a8-31f21f3f5111" />

```
np.reciprocal(df["Moderate Positive Skew"])
```
<img width="442" height="408" alt="image" src="https://github.com/user-attachments/assets/9581ffd4-b291-458d-a484-270b79f35d7b" />

```
np.sqrt(df["Highly Positive Skew"])
```
<img width="423" height="423" alt="image" src="https://github.com/user-attachments/assets/a7aab671-4399-4201-a70a-a7c6e3a54a8e" />

```
np.square(df["Highly Positive Skew"])
```
<img width="442" height="413" alt="image" src="https://github.com/user-attachments/assets/d7244d3c-7d11-441e-9328-9297e6125733" />

```
df["Highly Positive Skew_boxcox"], parameters=stats.boxcox(df["Highly Positive Skew"])
df
```
<img width="878" height="423" alt="image" src="https://github.com/user-attachments/assets/1e0925f7-9fdf-4ee2-89f7-a3042d95ec62" />

```
df.skew()
```
<img width="341" height="232" alt="image" src="https://github.com/user-attachments/assets/c05648fe-0472-4a3b-8dc0-e34d1087c1ab" />

```
df["Highly Negative Skew_yeojohnson"],parameters=stats.yeojohnson(df["Highly Negative Skew"])
df.skew()
```
<img width="696" height="277" alt="image" src="https://github.com/user-attachments/assets/a1d1b8c1-b019-4185-8310-d023c17e3cfd" />

```
from sklearn.preprocessing import QuantileTransformer
qt=QuantileTransformer(output_distribution='normal')
df["Moderate Negative Skew_1"]=qt.fit_transform(df[["Moderate Negative Skew"]])
df
```
<img width="881" height="462" alt="image" src="https://github.com/user-attachments/assets/9aa58aa6-988c-403a-8b0d-787b7576d335" />

```
import seaborn as sns
import statsmodels.api as sm
import matplotlib.pyplot as plt
sm.qqplot(df["Moderate Negative Skew"],line='45')
plt.show()
```
<img width="627" height="385" alt="image" src="https://github.com/user-attachments/assets/1eb419b4-863a-4568-8df0-0f3b44d905e8" />

```
sm.qqplot(np.reciprocal(df["Moderate Negative Skew"]),line='45')
plt.show()
```
<img width="807" height="399" alt="image" src="https://github.com/user-attachments/assets/ec5254cf-7f5b-4d06-b1e6-4bb0a056227c" />

```
from sklearn.preprocessing import QuantileTransformer
qt=QuantileTransformer(output_distribution='normal',n_quantiles=891)
df["Moderate Negative Skew"]=qt.fit_transform(df[["Moderate Negative Skew"]])
sm.qqplot(df["Moderate Negative Skew"],line='45')
plt.show()
```
<img width="642" height="470" alt="image" src="https://github.com/user-attachments/assets/71978dc1-fb42-4a78-b0a4-3b245ce1e1fb" />

```
df["Highly Negative Skew_1"]=qt.fit_transform(df[["Highly Negative Skew"]])
sm.qqplot(df["Highly Negative Skew"],line='45')
plt.show()
```
<img width="672" height="443" alt="image" src="https://github.com/user-attachments/assets/7c323b0a-513c-4211-a54a-a9df9ac3135b" />

```
dt=pd.read_csv("titanic_dataset.csv")
dt
```
<img width="857" height="488" alt="image" src="https://github.com/user-attachments/assets/bc8a55b3-d498-4640-8cd0-00d3ce3435bd" />

```
from sklearn.preprocessing import QuantileTransformer
qt=QuantileTransformer(output_distribution='normal',n_quantiles=891)
dt["Age_1"]=qt.fit_transform(dt[["Age"]])
sm.qqplot(dt['Age'],line='45')
plt.show()
```
<img width="676" height="470" alt="image" src="https://github.com/user-attachments/assets/564dcfd2-bcb7-49ad-83f7-4d40ad85171c" />

```
sm.qqplot(df["Highly Negative Skew_1"],line='45')
plt.show()
```
<img width="717" height="446" alt="image" src="https://github.com/user-attachments/assets/317240ec-1160-42f7-a2bf-fbac9cf38229" />

# RESULT

Hence,exploratory data analysis on the given data set has been executed successfully.
