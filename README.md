# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1.Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the outputs and end the program 

## Program:

/*
Program to implement the K Means Clustering for Customer Segmentation.

Developed by:Mahalakshmi.k

RegisterNumber:212222240057  
*/


import pandas as pd

import matplotlib.pyplot as plt

data=pd.read_csv('/content/Mall_Customers.csv')


data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans

wcss=[]

for i in range (1,11):

  kmeans=KMeans(n_clusters=i,init="k-means++")
  
  kmeans.fit(data.iloc[:,3:])
  
  wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss,color="cadetblue")

plt.xlabel("No. of Clusters")

plt.ylabel("wcss")

plt.title("Elbow Method")

km=KMeans(n_clusters = 5)

km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])

y_pred

data["cluster"]=y_pred

df0 = data[data["cluster"]==0]

df1 = data[data["cluster"]==1]

df2 = data[data["cluster"]==2]

df3 = data[data["cluster"]==3]

df4 = data[data["cluster"]==4]

plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="mediumpurple",label="cluster0")

plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="darkseagreen",label="cluster1")

plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="lightskyblue",label="cluster2")

plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")

plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="pink",label="cluster4")

plt.legend()

plt.title("Customer Segments")
*/

## Output:

1.data.head()

![1 data head()](https://github.com/maha712/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121156360/c70c888e-a9a5-467a-88d8-c3a726b9e64c)

2.data.info():

![2 data info()](https://github.com/maha712/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121156360/f7ef62c2-040f-4e95-ad31-dd3cda35b94f)

3.null value:

![3 null value](https://github.com/maha712/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121156360/50aa6995-2e3a-4306-a4c1-e03be6f72633)

4.Elbow Graph:

![4 Elbow Graph](https://github.com/maha712/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121156360/af53802e-cc49-4f41-976b-0576a2479160)

5.Cluster Formation:

![5 Cluster Formation](https://github.com/maha712/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121156360/02c0c14b-8d51-45f1-af20-ef9354fe2bb2)

6.predicted value:

![6 predicted value](https://github.com/maha712/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121156360/6dddb75a-7a5d-4e96-9e9a-37c883bed9db)

7.Cluster representing customer-segments graph:

![7 Cluster representing customer-segments graph](https://github.com/maha712/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121156360/d14a5f2f-a34d-4e41-8794-beea128104ad)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
