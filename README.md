# EX NO 2 : EDA ANALYSIS USING PYTHON

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
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![WhatsApp Image 2025-09-15 at 11 43 30_82980fd0](https://github.com/user-attachments/assets/6bed2bb1-b856-4cc9-938e-b68290bc3436)

```
df.info()
```
![WhatsApp Image 2025-09-15 at 11 43 31_f84b200a](https://github.com/user-attachments/assets/26b7cd3c-fe61-4a7f-9b8f-f4230894fffd)

```
df.describe()
```
![WhatsApp Image 2025-09-15 at 11 43 31_e78aafeb](https://github.com/user-attachments/assets/8c97795a-d900-4072-83e6-9690d3726c48)

```
df.dtypes
```
![WhatsApp Image 2025-09-15 at 11 43 31_5cc3ac11](https://github.com/user-attachments/assets/3e2a1b2b-0340-4dec-8018-2ba90b94554f)

```
df.shape
```
(891, 12)

```
df.value_counts()
```
![WhatsApp Image 2025-09-15 at 11 43 31_ec2b39a7](https://github.com/user-attachments/assets/951155e3-b060-465e-9064-8428a3e95e79)

```
df['Age'].value_counts()
```
![WhatsApp Image 2025-09-15 at 11 43 32_c409ae9d](https://github.com/user-attachments/assets/b89be5e8-e285-4bef-bc6b-cedf64bb6979)

```
df.set_index("PassengerId", inplace=True)
df
```
![WhatsApp Image 2025-09-15 at 11 43 32_7a3daa24](https://github.com/user-attachments/assets/e835abb7-9f53-4756-b579-574a1d674122)

```
df.nunique()
```
![WhatsApp Image 2025-09-15 at 11 43 32_b2363800](https://github.com/user-attachments/assets/221f87d3-8658-4ff1-a4d2-eece853ebaed)

```
sns.countplot(data=df,x='Age')
```
![WhatsApp Image 2025-09-15 at 11 43 33_f7d43e07](https://github.com/user-attachments/assets/29aa82ab-2f50-4771-975b-8d0180cbad0f)

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![WhatsApp Image 2025-09-15 at 11 43 33_cfd0ad74](https://github.com/user-attachments/assets/50191f0d-3757-4656-be68-d0eb3fce6558)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![WhatsApp Image 2025-09-15 at 11 43 34_6e4f337b](https://github.com/user-attachments/assets/b5966af1-fc70-4f36-8a24-a13ad904538e)

```
df.boxplot(column="Age",by="Survived")
```
![WhatsApp Image 2025-09-15 at 11 43 34_71fd169a](https://github.com/user-attachments/assets/27faf7b4-d63a-492e-ac30-0a38524789ce)

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![WhatsApp Image 2025-09-15 at 11 43 34_52695263](https://github.com/user-attachments/assets/6521ce61-57e4-4b40-bacb-7efafc7c11af)

```
plt=sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```
<img width="562" height="432" alt="image" src="https://github.com/user-attachments/assets/59da7cab-ee18-4a93-9c98-70c6ab8e6a62" />

```
import seaborn as sns
sns.catplot(x='Pclass',y="Age",hue="Gender",col="Survived",kind="box",data=df)
```
<img width="1089" height="490" alt="image" src="https://github.com/user-attachments/assets/18d1279d-9fc0-47ab-9df7-bee51beb0134" />

```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```

<img width="527" height="418" alt="image" src="https://github.com/user-attachments/assets/71ca7d4a-580e-426c-9cc4-5b4b4df3d49c" />

# RESULT

Thus exploratory data analysis on the given data set has been executed successfully.      
