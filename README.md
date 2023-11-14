## Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import standard libraries in python for finding Implementation-of-K-Means-Clustering-for-Customer-Segmentation.

2.Initialize and print the data.head(),data.info(),data.isnull().sum()

3.Import sklearn.cluster import KMeans

4.Calculate the value of KMeans Clusters.

5.Plot the graph from Elbow method and find y_pred values .

6.Plot the graph from Customer Segments Graph.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by:s.monicka 
RegisterNumber: 212221220033 
*/
```
```
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("/content/Mall_Customers.csv")

print("data.head() function:")
data.head()

print("data.info():")
data.info()

print("data.isnull().sum() function:")
data.isnull().sum()

from sklearn.cluster import KMeans
wcss=[] #Within-Cluster Sum of Square.

for i in range(1,11):
kmeans=KMeans(n_clusters=i,init="k-means++")
kmeans.fit(data.iloc[:,3:])
wcss.append(kmeans.inertia_)
         
print("Elbow method Graph:")
plt.plot(range(1,11),wcss)
plt.xlabel("No of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

print("KMeans clusters:")
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])

print("y_pred:")
y_pred=km.predict(data.iloc[:,3:])
y_pred

print("Customer segments Graph:")
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
plt.title("Customer Segments")
```
## Output:
## data head()
![image](https://github.com/Monicka19/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/143497806/51973e40-8d03-4994-bdc3-4b223d2959e2)
## data.info()
![image](https://github.com/Monicka19/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/143497806/e62967b7-6de6-4626-8b7f-57bfe5438189)
## data.isnull().sum()
![image](https://github.com/Monicka19/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/143497806/8c49d9ce-6697-42da-9cc1-8675f9cb3ca5)
## Elbow method graph
![image](https://github.com/Monicka19/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/143497806/95d35a19-7d79-4d1e-a480-d4d3f8198ef0)
## K means clusters
![image](https://github.com/Monicka19/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/143497806/07fb12ba-abbc-4991-9114-2d2dd91f716f)
## y_pred
![image](https://github.com/Monicka19/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/143497806/87bf8af6-3b35-4ffa-bd21-fc4053e4556c)
## customers segments graph
![image](https://github.com/Monicka19/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/143497806/cbe4f475-9570-4ef9-bc44-1e23d43d07ce)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
