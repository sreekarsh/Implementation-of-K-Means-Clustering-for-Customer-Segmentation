# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import dataset and print head,info of the dataset  
2.check for null values   
3.Import kmeans and fit it to the dataset    
4.Plot the graph using elbow method    
5.Print the predicted array    
6.Plot the customer segments    
## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: MASINA SREE KARSH
RegisterNumber: 212223100033
*/
```
```

import pandas as pd

import matplotlib.pyplot as plt

data=pd.read_csv("/content/Mall_Customers (1).csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans

wcss=[]

for i in range(1,11):

kmeans=KMeans(n_clusters=i,init="k-means++")

kmeans.fit(data.iloc[:,3:])

wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)

plt.xlabel("No_of_Clusters")

plt.ylabel("wcss")

plt.title("Elbow Method")

km=KMeans(n_clusters=5)

km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])

y_pred

data["cluster"]=y_pred

df0=data[data["cluster"]==0]

df1=data[data["cluster"]==1]

df2=data[data["cluster"]==2]

df3=data[data["cluster"]==3]

df4=data[data["cluster"]==4]

plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")

plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")

plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")

plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")

plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")

plt.legend()

plt.title("Customer Segment")

```

## Output:
1.DATA.HEAD():

![image](https://github.com/sreekarsh/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139841918/083f5f8a-d62a-4dd9-816f-f0ee75cc999f)


2.DATA.INF0():

![image](https://github.com/sreekarsh/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139841918/0f6edb98-a5e7-4ac6-ad96-d48e6840ed90)


3.DATA.ISNULL().SUM():

![image](https://github.com/sreekarsh/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139841918/9a6ca918-c4b5-4671-8f17-94e6803fb13d)


4.PLOT USING ELBOW METHOD:

![image](https://github.com/sreekarsh/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139841918/83eff70f-c494-401c-8631-4969432c8578)


5.K-MEANS CLUSTERING:

![image](https://github.com/sreekarsh/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139841918/16ffb9e5-e570-4df9-9c8e-64c5a1533733)


6.Y_PRED ARRAY:

![image](https://github.com/sreekarsh/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139841918/ab1dbfcb-bff8-46c3-890c-2b0ebe38a01e)

7.CUSTOMER SEGMENT:

![image](https://github.com/sreekarsh/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139841918/8fd21125-c318-4a98-9466-aefea1f076de)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
