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

## CODING AND OUTPUT:
```
import pandas as pd
df=pd.read_csv('titanic_dataset.csv')
df
```
<img width="1418" height="543" alt="image" src="https://github.com/user-attachments/assets/24974f6e-da55-466a-8c07-d917f0187ef7" />

```
df.shape
```
<img width="179" height="52" alt="image" src="https://github.com/user-attachments/assets/76996262-28b3-41ad-8823-cb567ca14846" />

```
df.set_index("PassengerId",inplace=True)
df
```
<img width="1436" height="572" alt="Screenshot 2025-10-07 150306" src="https://github.com/user-attachments/assets/da7d7e7c-516b-45f5-a2af-a9487c431f6b" />

```
df.nunique()
```
<img width="927" height="281" alt="image" src="https://github.com/user-attachments/assets/2a30548d-b249-4761-9884-c31d2a521e91" />

```
df['Sex'].value_counts()

```
<img width="706" height="106" alt="image" src="https://github.com/user-attachments/assets/c6f5b791-7961-46e0-9803-97981c4a648e" />
```
df.Survived.unique()
```
<img width="332" height="52" alt="image" src="https://github.com/user-attachments/assets/7b51838b-6d26-4732-bf1f-3b059b0ead66" />
```
df.rename(columns={"Sex":"Gender"},inplace=True)
df
```
<img width="1446" height="553" alt="image" src="https://github.com/user-attachments/assets/b5d3190d-3f6f-420f-8a21-3928d95649eb" />
```
import seaborn as sns
sns.countplot(data=df)
df
```
<img width="856" height="525" alt="image" src="https://github.com/user-attachments/assets/68a3920d-35e0-4ca5-a519-a8a4bee51b77" />
```
sns.countplot(x="Survived",hue="Gender",data=df)
```
<img width="987" height="591" alt="image" src="https://github.com/user-attachments/assets/92842f0f-8a04-4af1-9efb-aaeec5d106b7" />
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="violin")
```
<img width="1077" height="657" alt="image" src="https://github.com/user-attachments/assets/2fb8b9ab-dfcc-40d1-91f5-ba3f701105d4" />
```
sns.boxplot(data=df)
```
<img width="888" height="546" alt="image" src="https://github.com/user-attachments/assets/4b1bda89-2867-47f1-894a-5c7e5db48659" />
```
sns.boxplot(column="Survived",by="Gender")
```
<img width="1216" height="825" alt="image" src="https://github.com/user-attachments/assets/1860d998-1bf7-4e00-95aa-4272682374eb" />
```
sns.scatterplot(data=df)
```
<img width="1100" height="572" alt="image" src="https://github.com/user-attachments/assets/cd75b869-9856-4d9b-a212-1950bd340dad" />
```
sns.scatterplot(x=df['Age'],y=df['Fare'])
```
<img width="1191" height="581" alt="image" src="https://github.com/user-attachments/assets/4f5c1344-d7cd-4911-9c0c-368214c7af3f" />
```
sns.jointplot(x='Age',y='Fare',data=df)
```
<img width="1078" height="776" alt="image" src="https://github.com/user-attachments/assets/3f4fc816-a5fb-4371-9afe-9a08dc108419" />
```
sns.jointplot(x='Age',y='Fare',data=df,kind="kde")
```
<img width="973" height="750" alt="image" src="https://github.com/user-attachments/assets/72937ab0-c630-4a24-bcae-f5ee6ea602e6" />
```
sns.jointplot(x='Age',y='Fare',data=df,kind="hist")
```
<img width="1055" height="771" alt="image" src="https://github.com/user-attachments/assets/9df19fa4-cb02-4f38-b5f1-9387f9886c7f" />
```
sns.pairplot(data=df)
```
<img width="1487" height="898" alt="image" src="https://github.com/user-attachments/assets/2c15b5b2-370a-46ce-a6b6-e0aaa60d87c4" />
```
corr1=df.select_dtypes(include=['number']).corr()
sns.heatmap(corr1,annot=True)
```
<img width="913" height="554" alt="image" src="https://github.com/user-attachments/assets/b3203e9b-dcec-4710-bd3c-e730e4945947" />
```
sns.catplot(x="Gender",col='Survived',data=df,kind='count',color='green')
```
<img width="1448" height="661" alt="image" src="https://github.com/user-attachments/assets/925bdd66-679b-4767-a5e1-0b11a793bb1b" />

# RESULT
        <<INCLUDE YOUR RESULT HERE>>
