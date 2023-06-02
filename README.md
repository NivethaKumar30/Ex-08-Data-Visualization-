# Ex-08-Data-Visualization-

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

![image](https://github.com/NivethaKumar30/Ex-08-Data-Visualization-/assets/119559844/87b83010-454b-4116-b811-b47823ad94f3)

![image](https://github.com/NivethaKumar30/Ex-08-Data-Visualization-/assets/119559844/80dc0443-ed92-4a22-aeb4-f57ef2b63f57)

![image](https://github.com/NivethaKumar30/Ex-08-Data-Visualization-/assets/119559844/589010d3-af6d-45d1-b4e2-7aa0aa8f3e99)

![image](https://github.com/NivethaKumar30/Ex-08-Data-Visualization-/assets/119559844/0437e6a9-c62f-4b6b-b01a-ccbb5c4ab2b0)

![image](https://github.com/NivethaKumar30/Ex-08-Data-Visualization-/assets/119559844/665f59c4-d54c-46ed-99b5-fc472233b7f1)

![image](https://github.com/NivethaKumar30/Ex-08-Data-Visualization-/assets/119559844/b5ccf138-5734-4439-9b62-05458a89f936)

![image](https://github.com/NivethaKumar30/Ex-08-Data-Visualization-/assets/119559844/1fb57eda-96a9-4446-98c9-dc4f2f4d841f)

![image](https://github.com/NivethaKumar30/Ex-08-Data-Visualization-/assets/119559844/b529c52e-5bbc-4740-b092-8b9545e0c1b7)

![image](https://github.com/NivethaKumar30/Ex-08-Data-Visualization-/assets/119559844/ed42487e-4b09-4c34-8816-7a91b83124bf)

![image](https://github.com/NivethaKumar30/Ex-08-Data-Visualization-/assets/119559844/7e8914a0-651c-40e7-9887-b5b4dbad9918)

![image](https://github.com/NivethaKumar30/Ex-08-Data-Visualization-/assets/119559844/da20cf84-f160-40dd-96b1-32083d193995)

![image](https://github.com/NivethaKumar30/Ex-08-Data-Visualization-/assets/119559844/a928f28e-d8de-4d76-a5fd-c03a2eab13a7)

![image](https://github.com/NivethaKumar30/Ex-08-Data-Visualization-/assets/119559844/77047a4b-a6c4-4616-9f3c-74c25ca33037)

![image](https://github.com/NivethaKumar30/Ex-08-Data-Visualization-/assets/119559844/b800d777-9948-48e5-875e-48e7b57ea282)

![image](https://github.com/NivethaKumar30/Ex-08-Data-Visualization-/assets/119559844/13340d39-84dc-48c1-921f-ab6b0a10a0e1)

![image](https://github.com/NivethaKumar30/Ex-08-Data-Visualization-/assets/119559844/105fb8ed-8928-4195-887b-9b4ae798dc3c)

![image](https://github.com/NivethaKumar30/Ex-08-Data-Visualization-/assets/119559844/3d45087d-0952-4c6f-8262-576bbeece5f6)

![image](https://github.com/NivethaKumar30/Ex-08-Data-Visualization-/assets/119559844/f02ad0f6-1118-4e4c-9164-30115b2abab3)

![image](https://github.com/NivethaKumar30/Ex-08-Data-Visualization-/assets/119559844/4a5d3860-f6da-4e08-a20d-f3efe4ca292a)

![image](https://github.com/NivethaKumar30/Ex-08-Data-Visualization-/assets/119559844/385c547d-ea68-4951-82aa-9a19e71bdbb3)

![image](https://github.com/NivethaKumar30/Ex-08-Data-Visualization-/assets/119559844/2f9d7f4f-3991-45f8-8fb1-1e95ca8dc8ef)

![image](https://github.com/NivethaKumar30/Ex-08-Data-Visualization-/assets/119559844/b0433334-a4cb-48d0-82f9-e821b9950b68)

![image](https://github.com/NivethaKumar30/Ex-08-Data-Visualization-/assets/119559844/064f837f-e903-48e2-830c-dea4ccd98150)

![image](https://github.com/NivethaKumar30/Ex-08-Data-Visualization-/assets/119559844/443b4e1f-1723-457b-8238-4c4b84b40bcd)


#RESULT:

Thus data visualisation is performed on the given data set using tools available in matplotlib and seaborn.
