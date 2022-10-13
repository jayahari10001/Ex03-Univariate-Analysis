import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/SuperStore.csv")
df
df.info()
df.isnull().sum()
df['Postal Code']=d['Postal Code'].fillna(d['Postal Code'].mode()[0])
df.head()
df.boxplot()
df['Ship Mode'].value_counts()
df['Segment'].value_counts()
df['City'].value_counts()
df['State'].value_counts()
df['Region'].value_counts()
df['Category'].value_counts()
df['Sub-Category'].value_counts()
df_count = df.groupby(by=["Category"]).count()
df_sum = df.groupby(by=["Category"]).sum()
labels=[]
for i in df_count.index:
    labels.append(i)
plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
myexplode = [0, 0.2,0]
plt.pie(df_count["Sales"], colors = colors,explode = myexplode, labels=labels, autopct = "%0.0f%%",shadow = True) 
plt.show()
