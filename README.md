# EXP8 - Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## Aim:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm:
1.Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the outputs and end the program. 

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: SUNIL KUMAR T
RegisterNumber:  212223240164
*/

import matplotlib.pyplot as plt
import pandas as pd
data=pd.read_csv('Mall_Customers.csv')
print(data)

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
plt.xlabel("No.of clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])
print(y_pred)

data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="brown",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="yellow",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="blue",label="cluster4")
plt.legend()
plt.title("consumer segments")
```

## Output:
# DATASET
![image](https://github.com/K-Dharshini/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139334830/32e1a8a2-23c3-4553-aeb6-43a8c7104305)

# data.head()
![image](https://github.com/K-Dharshini/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139334830/a3a1e858-66c8-465c-a628-e684724e17cb)

# data.info()
![image](https://github.com/K-Dharshini/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139334830/6822853c-8019-43cd-8827-7f0be8997c37)

# CHECKING IF NULL VALUES ARE PRESENT
![image](https://github.com/K-Dharshini/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139334830/feda994c-be9e-4694-bc53-3a83865ed5fa)

# FOR LOOP TO CLUSTER THE DATA
![image](https://github.com/K-Dharshini/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139334830/bd5938bd-23de-4403-8f84-163af8e038df)

# ELBOW METHOD GRAPH
![image](https://github.com/K-Dharshini/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139334830/90b5bbf2-eec2-40ee-8dda-698f75ef0d72)

# FITTING OF DATA IN KMEANS
![image](https://github.com/K-Dharshini/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139334830/ac93cc33-09b7-455d-b142-3e18e44258da)

# PREDICTING THE VALUES
![image](https://github.com/K-Dharshini/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139334830/ef2c0caa-561b-4d25-86fa-1769d45f445a)

# KMEANS CLUSTERING GRAPH
![image](https://github.com/K-Dharshini/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139334830/aa3507a6-fdf7-4302-b988-1ac196fae683)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
