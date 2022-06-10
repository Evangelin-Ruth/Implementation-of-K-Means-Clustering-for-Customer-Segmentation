# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm

step 1:
Import the necessary packages using import statement.

step 2:
Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

step 3:
Import KMeans and use for loop to cluster the data.

step 4:
Predict the cluster and plot data graphs.

step 5:
Print the outputs and end the program
## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Evangelin.S
RegisterNumber:  212221230025
*/

import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")
data.head(
data.info())
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")


```

## Output:
## Data.head():
![image](https://user-images.githubusercontent.com/94219798/172998945-8ca5fd53-6d3f-444f-8bc4-f053e31d5695.png)

## Data.info():
![image](https://user-images.githubusercontent.com/94219798/172998979-643c6e9c-c657-4ab2-a8c6-9c2d3518796c.png)

## Data.isnull().sum():
![image](https://user-images.githubusercontent.com/94219798/172999010-d809df8e-2cae-468d-b146-d2882d1a72aa.png)

## plt-Elbow Method:
![image](https://user-images.githubusercontent.com/94219798/172999044-bb39d7e8-68d4-4b8f-912f-7dd56483cc65.png)

## Km.fit(data.iloc):
![image](https://user-images.githubusercontent.com/94219798/172999074-4c0c0b0f-30fe-44aa-bda8-bae86592d599.png)

## plt-Customer Segments:
![image](https://user-images.githubusercontent.com/94219798/172999120-8bf86671-eea1-4372-9b65-7ca58f832bad.png)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
