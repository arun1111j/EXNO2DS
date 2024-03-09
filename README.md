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
```
```
dt=pd.read_csv("/content/titanic_dataset.csv")
dt
```
![Screenshot 2024-03-09 154054](https://github.com/arun1111j/EXNO2DS/assets/128461833/b85acb95-ae64-4106-9f6c-bdaf1d2510b7)
```
dt.info()
```
![image](https://github.com/arun1111j/EXNO2DS/assets/128461833/340b3dbf-ec52-4f75-b324-394ec96de86d)
```
dt.shape
```
![Screenshot 2024-03-09 154321](https://github.com/arun1111j/EXNO2DS/assets/128461833/29b0f854-38f1-4374-8f6b-9085468c4b43)
```
dt.set_index("PassengerId",inplace=True
```
```
dt.nunique()
```
![Screenshot 2024-03-09 154522](https://github.com/arun1111j/EXNO2DS/assets/128461833/4c795450-6c82-4127-bd9a-df0f88414e32)
```
dt["Survived"].value_counts()
```
![Screenshot 2024-03-09 154559](https://github.com/arun1111j/EXNO2DS/assets/128461833/144bbd3e-61c0-4fcc-8eb0-41ab4729d6fc)
```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![Screenshot 2024-03-09 154627](https://github.com/arun1111j/EXNO2DS/assets/128461833/8036292c-2b2f-484c-b780-6bfed8639716)
```
sns.countplot(data=dt,x="Survived")
```
![Screenshot 2024-03-09 154659](https://github.com/arun1111j/EXNO2DS/assets/128461833/235ebbfe-0fe6-4ddf-b076-8a3135eec12d)
```
dt
```
![Screenshot 2024-03-09 154725](https://github.com/arun1111j/EXNO2DS/assets/128461833/8585cce1-eb9a-4c51-929e-56a79e89024d)
```
dt.Pclass.unique()
```
![Screenshot 2024-03-09 154751](https://github.com/arun1111j/EXNO2DS/assets/128461833/2e9b7036-cc4f-42e7-b1bf-69766e5550d3)
```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```
![Screenshot 2024-03-09 154820](https://github.com/arun1111j/EXNO2DS/assets/128461833/332974fa-a537-4aaf-9b09-b10a2584d62c)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5, aspect=.7)
```
![Screenshot 2024-03-09 154848](https://github.com/arun1111j/EXNO2DS/assets/128461833/8f76334e-c99a-4a04-9566-ecd0f9d85c7e)
```
sns.catplot(x='Survived',hue="Gender",data=dt,kind="count")
```
![image](https://github.com/arun1111j/EXNO2DS/assets/128461833/1390caf1-aa67-4a33-ab4a-5ddf8fe83890)
```
dt.boxplot(column="Age",by="Survived")
```
![Screenshot 2024-03-09 154943](https://github.com/arun1111j/EXNO2DS/assets/128461833/c6cec8eb-fcfa-4da4-9315-79496eab5668)

```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
![Screenshot 2024-03-09 155006](https://github.com/arun1111j/EXNO2DS/assets/128461833/97f5451d-a547-4909-998e-d85b53a3050a)
```
sns.jointplot(x="Age",y="Fare",data=dt)
```
![image](https://github.com/arun1111j/EXNO2DS/assets/128461833/454d5f4c-b23e-4c9e-8394-320a2f3bd387)
```
import matplotlib.pyplot as plt
fig, ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)
```
![image](https://github.com/arun1111j/EXNO2DS/assets/128461833/24a7623a-1603-465f-9bf8-671f843bae62)
```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```










# RESULT
        <<INCLUDE YOUR RESULT HERE>>
