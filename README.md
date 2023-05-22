# Ex-04-Multivariate-Analysis
# AIM
To perform Multivariate EDA on the given data set.

# Explanation:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

# ALGORITHM:
STEP 1 Import the built libraries required to perform EDA and outlier removal.

STEP 2 Read the given csv file

STEP 3 Convert the file into a dataframe and get information of the data.

STEP 4 Return the objects containing counts of unique values using (value_counts()).

STEP 5 Plot the counts in the form of Histogram or Bar Graph.

STEP 6 Use seaborn the bar graph comparison of data can be viewed.

STEP 7 Find the pairwise correlation of all columns in the dataframe.corr()

STEP 8 Save the final data set into the file

# PROGRAM
Name : Sachin.EA
Register Number : 212221040139
```
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("SuperStore.csv")
df
df.info()
df.describe()
df.isnull().sum()
df['Postal Code'] = df["Postal Code"].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()
df.dtypes
sns.scatterplot(df['Row ID'],df['Sales'])
states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()
states=df.loc[:,["State","Row ID"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Row ID")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("ROW ID")
plt.show()
states=df.loc[:,["Segment","Row ID"]]
states=states.groupby(by=["Segment"]).sum().sort_values(by="Row ID")
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SEGMENT")
plt.ylabel=("ROW ID")
plt.show()
sns.barplot(df['Sales'],df['Ship Mode'],hue=df['Region'])
df.corr()
sns.heatmap(df.corr(),annot=True)
```
# OUTPUT
# DATA
![image](https://github.com/sachinezhilmaran/Ex-04-Multivariate-Analysis/assets/128135351/d233d09c-48c6-4823-962d-8abc47e11fa1)
# Data.info
![image](https://github.com/sachinezhilmaran/Ex-04-Multivariate-Analysis/assets/128135351/94262798-e881-4ea7-a69c-a0248d4e27ba)
# Data.describe
![image](https://github.com/sachinezhilmaran/Ex-04-Multivariate-Analysis/assets/128135351/e1d7a55e-88bd-403a-80ef-1f39de8d53f4)
# Checking the null values and Cleaning it
![image](https://github.com/sachinezhilmaran/Ex-04-Multivariate-Analysis/assets/128135351/d081566d-571f-48ce-ab61-e1ff480079e9)
![image](https://github.com/sachinezhilmaran/Ex-04-Multivariate-Analysis/assets/128135351/d2a25da6-b3c0-4226-9cc8-e78446fa299d)
# DATA TYPES
![image](https://github.com/sachinezhilmaran/Ex-04-Multivariate-Analysis/assets/128135351/9a504eb3-af0f-4fd4-8a03-b51ed4e1d145)
# SCATTER PLOT
![image](https://github.com/sachinezhilmaran/Ex-04-Multivariate-Analysis/assets/128135351/84f2fc2c-1230-47f7-8a3b-84f0665eaa8c)
# BAR PLOT
![image](https://github.com/sachinezhilmaran/Ex-04-Multivariate-Analysis/assets/128135351/e02bb2bd-53d4-460b-b512-aa7e4aeac565)
![image](https://github.com/sachinezhilmaran/Ex-04-Multivariate-Analysis/assets/128135351/7337d440-b166-4ee3-9752-d8877c80d1f0)
![image](https://github.com/sachinezhilmaran/Ex-04-Multivariate-Analysis/assets/128135351/1d0ffae4-b36e-4931-acce-da5d875a4542)
![image](https://github.com/sachinezhilmaran/Ex-04-Multivariate-Analysis/assets/128135351/64e5ebc8-67c3-4029-81fa-4653e3087db9)
# CORRELATION COEFFICIENT INTERPRETATION
![image](https://github.com/sachinezhilmaran/Ex-04-Multivariate-Analysis/assets/128135351/aae92081-f90d-4e5b-914b-e578ba5f7214)
# HEATMAP
![image](https://github.com/sachinezhilmaran/Ex-04-Multivariate-Analysis/assets/128135351/5eb35cd1-836c-4621-8b43-f02285003958)
# RESULT
Thus we have read the given data and performed the multivariate analysis with different types of plots.
