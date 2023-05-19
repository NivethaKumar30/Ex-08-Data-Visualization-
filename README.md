# Ex-07-Data-Visualization-

## AIM
To Perform Data Visualization on the given dataset and save the data to a file. 

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.


# CODE:
```
import pandas as pd
import numpy as np
df=pd.read_csv("Supermarket.csv")
df
df.head()

#Data Visualization using Seaborn

import seaborn as sns
from matplotlib import pyplot as plt

# Line plot

plt.figure(figsize=(8,5))
sns.lineplot(x="Segment",y="Region",data=df,marker='o')
plt.xticks(rotation = 90)
sns.lineplot(x='Ship Mode',y='Category', hue ="Segment",data=df)
sns.lineplot(x="Category",y="Sales",data=df,marker='o')

# Scatterplot

sns.scatterplot(x='Category',y='Sub-Category',data=df)
sns.scatterplot(x='Category', y='Sub-Category', hue ="Segment",data=df)
plt.figure(figsize=(10,7))
sns.scatterplot(x="Region",y="Sales",data=df)
plt.xticks(rotation = 90)

# Boxplot

sns.boxplot(x="Sub-Category",y="Discount",data=df)
sns.boxplot( x="Profit", y="Category",data=df)

# Barplot

sns.barplot(x="Sub-Category",y="Sales",data=df)
plt.xticks(rotation = 90)
sns.barplot(x="Category",y="Sales",data=df)
plt.xticks(rotation = 90)

# Pointplot

sns.pointplot(x=df["Quantity"],y=df["Discount"])

#Count plot

sns.countplot(x="Category",data=df)
sns.countplot(x="Sub-Category",data=df)

# Histogram

sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')

# KDE Plot

sns.kdeplot(x="Profit", data = df,hue='Category')

#Data Visualization Using MatPlotlib

# Plot

plt.plot(df['Category'], df['Sales'])
plt.show()

# Heatmap

df.corr()
plt.subplots(figsize=(12,7))
sns.heatmap(df.corr(),annot=True)

# Piechart

df1=df.groupby(by=["Ship Mode"]).sum()
labels=[]
for i in df1.index:
    labels.append(i)
colors=sns.color_palette("bright")
plt.pie(df1["Sales"],labels=labels,autopct="%0.0f%%")
plt.show()

# Histogram

plt.hist(df["Sub-Category"],facecolor="peru",edgecolor="blue",bins=10)
plt.show()

# Bargraph

plt.bar(df.index,df['Category'])
plt.show()

# Scatterplot

plt.scatter(df["Region"],df["Profit"], c ="blue")
plt.show()              

# Boxplot

plt.boxplot(x="Sales",data=df)
plt.show()
```

# OUPUT:





#RESULT:

Thus data visualisation is performed on the given data set using tools available in matplotlib and seaborn.
