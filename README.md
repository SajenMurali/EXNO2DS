# EX.NO: 2 DS
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
 ```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
<img width="1019" height="337" alt="image" src="https://github.com/user-attachments/assets/0ddb267b-4e3c-4dd3-aa94-138eb95a2a88" />


```
df.info()
```
<img width="541" height="321" alt="image" src="https://github.com/user-attachments/assets/4f9d4639-2c3b-4517-aba2-17d0d12d5fc5" />


```
df.describe()
```
<img width="654" height="222" alt="image" src="https://github.com/user-attachments/assets/45790f18-14ba-4d96-8a28-06bfa3f6e53e" />

```
df.dtypes
```
<img width="274" height="218" alt="image" src="https://github.com/user-attachments/assets/cdf09a16-9302-416a-8cd3-78e21145c954" />


```
df.shape
```
<img width="233" height="61" alt="image" src="https://github.com/user-attachments/assets/657a466f-66db-491e-8963-f4dd20fd440f" />

```
df['Age'].value_counts()
```
<img width="379" height="208" alt="image" src="https://github.com/user-attachments/assets/038f712a-83a8-4809-a751-d066964a836b" />

```
df.nunique()
```
<img width="580" height="606" alt="image" src="https://github.com/user-attachments/assets/1e3a0a41-20ce-4c45-b99a-e3b6629d9648" />

```
sns.countplot(data=df,x='Survived')
```
<img width="738" height="442" alt="image" src="https://github.com/user-attachments/assets/5abc8f2d-e1e6-4af6-9fa2-1b23af5e7e0a" />


```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
<img width="1028" height="348" alt="image" src="https://github.com/user-attachments/assets/2cde9875-bad7-4a7b-aa96-5590b39859b7" />


```
sns.catplot(x="Gender",col="Survived",kind="count",data=df)
```
<img width="1013" height="495" alt="image" src="https://github.com/user-attachments/assets/3e7fd049-b465-4fbd-b5e9-3f03f8781330" />


```
df.boxplot(column="Age",by="Survived")
```
<img width="673" height="457" alt="image" src="https://github.com/user-attachments/assets/7cf9942a-9d77-47e7-af09-6ea89a6df544" />


```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
<img width="741" height="439" alt="image" src="https://github.com/user-attachments/assets/5f2cdda0-9e54-4116-a10a-eae884e956de" />


```
sns.boxplot(x="Pclass",y="Age",hue="Gender",data=df)
```
<img width="729" height="434" alt="image" src="https://github.com/user-attachments/assets/29d4fffb-ccf0-4dcd-9bb1-27a065c18a3b" />


```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
<img width="1016" height="473" alt="image" src="https://github.com/user-attachments/assets/f00d8b3b-1be5-4cae-bc0a-17e2b74b2c54" />


```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```
<img width="580" height="424" alt="image" src="https://github.com/user-attachments/assets/ddb96655-0804-4275-b8b4-96c461231c56" />



## RESULT
Thus, the outputs verifies that the data set has been applied the EDA process and methods.
