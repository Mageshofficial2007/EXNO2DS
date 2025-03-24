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
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
dt=pd.read_csv("titanic_dataset.csv")
print(dt)
```
![Screenshot 2025-03-24 102511](https://github.com/user-attachments/assets/d63ec427-8ae1-498f-9672-8525ae21f824)
```python
dt.info()
```
![Screenshot 2025-03-24 102527](https://github.com/user-attachments/assets/dd4b9d4b-feb2-49dc-a192-2ce919c70c87)
```python
dt.set_index("PassengerId",inplace=True)
dt.describe()
```
![Screenshot 2025-03-24 102536](https://github.com/user-attachments/assets/4213e17e-3ab9-4b32-a948-b64b2110357c)
CATEGORICAL DATA ANALYSIS
```python
dt.nunique()
```
![Screenshot 2025-03-24 102553](https://github.com/user-attachments/assets/d90998ae-d082-4890-b968-c779b3957196)
```python
dt["Survived"].value_counts()
```
![Screenshot 2025-03-24 102620](https://github.com/user-attachments/assets/ab7d0361-1c7f-4bf3-9ab3-0b6c53ebd15c)
```python
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
print(per)
```
![Screenshot 2025-03-24 102628](https://github.com/user-attachments/assets/f9ebb11a-7889-4e14-83dd-27bafe9abf5b)

UNIVARIATE ANALYSIS
```python
sns.countplot(data=dt,x="Survived")
```
![Screenshot 2025-03-24 102651](https://github.com/user-attachments/assets/65f17878-2bec-4cc5-97fe-f45be442da74)
```python
dt
```
![Screenshot 2025-03-24 102937](https://github.com/user-attachments/assets/983a1f96-f457-4bee-b042-ea1260eade42)
```python
dt.Pclass.unique()
```
![Screenshot 2025-03-24 102955](https://github.com/user-attachments/assets/a5ddc774-0151-49a6-a5f1-b17df6feaacc)
```python
dt=pd.read_csv("titanic_dataset.csv")
dt.rename(columns={'Sex':'Gender'}, inplace=True)
print(dt)
```
![Screenshot 2025-03-24 103028](https://github.com/user-attachments/assets/1a29c9ef-712b-4289-8327-7ccee807a0c3)
```python
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5, aspect=.7)
```
![Screenshot 2025-03-24 103043](https://github.com/user-attachments/assets/827983a8-28f9-4c64-b4eb-4152510c6180)
```pyhton
sns.catplot(x='Survived',hue="Gender",data=dt,kind="count")
```
![Screenshot 2025-03-24 103307](https://github.com/user-attachments/assets/e0c06f73-b0dc-4135-9161-a15bea3116e8)
```python
dt.boxplot(column="Age",by="Survived")
```
![Screenshot 2025-03-24 103406](https://github.com/user-attachments/assets/a6797153-d161-4831-8ebd-b1ba2359f53d)
```python
sns.catplot(x=dt["Age"],y=dt["Fare"])
```
![Screenshot 2025-03-24 103414](https://github.com/user-attachments/assets/ae7ab1ed-b651-4057-a6c6-dec20637d4c1)
```python
sns.jointplot(x="Age",y="Fare",data=dt)
```
![Screenshot 2025-03-24 103422](https://github.com/user-attachments/assets/4f895fbf-3f16-45c4-870d-7be5f3e42a28)

MULTIVARIATE ANALYSIS
```python
fig, ax1 = plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)
```
![Screenshot 2025-03-24 103431](https://github.com/user-attachments/assets/072349cb-3fff-43cc-8e7e-f07d6a062025)
```python
sns.catplot(data=dt,col="Survived",x='Gender',hue="Pclass",kind="count")
```
![Screenshot 2025-03-24 103448](https://github.com/user-attachments/assets/805d9006-fc9e-45de-af35-bb05474669fd)
```python
corr=dt.corr()
sns.heatmap(corr,annot=True)
```
![Screenshot 2025-03-24 103520](https://github.com/user-attachments/assets/327d917a-e2f9-48d0-b125-587df72c4879)
```python
sns.pairplot(dt)
```
![Screenshot 2025-03-24 103549](https://github.com/user-attachments/assets/2f0ced28-47e8-4dfa-ab4d-7330496ab9f6)

# RESULT
 To perfrom Exploratory Data Analysis on the given data set is successully completed.    
