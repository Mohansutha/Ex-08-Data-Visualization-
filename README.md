# Ex-08-Data-Visualization-

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

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


# CODE
~~~
# Importing packages
import pandas as pd
import numpy as np

# Importing visualization libraries
import seaborn as sns
import matplotlib.pyplot as plt

df_super = pd.read_csv('Superstore.csv')

df_super.head(5)

df_super=df_super.groupby(by=["Category"]).sum()
labels=[]
for i in df_super.index:
    labels.append(i)  
plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
plt.pie(df_super["Profit"],colors = colors,labels=labels, autopct = '%0.0f%%')
plt.show()


sns.set_style('whitegrid')
sns.countplot(x='Segment',data=df_super, palette='rainbow')

sns.set_style('whitegrid')
sns.countplot(x='Category',data=df_super, palette='rainbow')

sns.set_style('whitegrid')
sns.countplot(x='Sub-Category',data=df_super, palette='rainbow')

sns.set_style('whitegrid')
sns.countplot(x='Region',data=df_super, palette='rainbow')

sns.set_style('whitegrid')
sns.countplot(x='Ship Mode',data=df_super, palette='rainbow')

category_hist = sns.FacetGrid(df_super, col='Ship Mode', palette='rainbow')
category_hist.map(plt.hist, 'Category')
category_hist.set_ylabels('Number')

subcategory_hist = sns.FacetGrid(df_super, col='Segment', height=10.5, aspect=4.6)
subcategory_hist.map(plt.hist, 'Sub-Category')
subcategory_hist.set_ylabels('Number')

grid = sns.FacetGrid(df_super, row='Category', col='Sub-Category', height=2.2, aspect=1.6)
grid.map(sns.barplot, 'Profit', 'Segment', alpha=.5, ci=None)
grid.add_legend()
~~~

# OUPUT
![o1](https://user-images.githubusercontent.com/94828335/171544289-e0e9806c-3da9-4e1a-8242-7858ae4351d8.png)

![o2](https://user-images.githubusercontent.com/94828335/171544316-2a72d648-7281-498f-a143-d0fb05d11f79.png)

![o3](https://user-images.githubusercontent.com/94828335/171544330-f59ab790-357c-4d57-8954-0628bc824986.png)

![o4](https://user-images.githubusercontent.com/94828335/171544356-c6acedf1-5b88-4eb4-8eb7-5f92e6c2ef90.png)

![o5](https://user-images.githubusercontent.com/94828335/171544374-39c64241-265a-4a6b-b4d1-321cdb901dfe.png)

![o6](https://user-images.githubusercontent.com/94828335/171544406-a84b5d74-683c-4d7c-8979-ee1cdd81009a.png)

![o7](https://user-images.githubusercontent.com/94828335/171544421-17dc1617-0f9f-4185-a53f-1a39e45452ff.png)

![o8](https://user-images.githubusercontent.com/94828335/171544454-daaca2b3-3d97-4b2d-8170-55304d2a9ecf.png)

![o9](https://user-images.githubusercontent.com/94828335/171544476-a0a63fb6-4558-4a9f-83ce-4453947a7b4d.png)

![o10](https://user-images.githubusercontent.com/94828335/171544503-d8832240-e950-4257-ba30-bdf731c73aa0.png)

RESULT :

Data Visualization has been performed on a complex dataset and saved the data to a file


