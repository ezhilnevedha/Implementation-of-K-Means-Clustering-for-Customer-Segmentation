# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.start the program.

2.Import libraries.

3.Read the given CSV file.

4.Import KMeans and use for loop to cluster the data.

5.Predict the cluster and plot data graphs.

6.Print the outputs and end the program.

7.End the program.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Ezhil Nevedha.K
RegisterNumber:  212223230055
*/
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("C:/Users/admin/Desktop/INTR MACH/Mall_Customers.csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss= [] #with-in the cluster sum of square

for i in range(1, 11):
    kmeans= KMeans(n_clusters = i , init= "k-means++")
    kmeans.fit(data.iloc[:, 3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11) , wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters= 5)
km.fit(data.iloc[:, 3:])

KMeans(n_clusters= 5)

y_pred= km.predict(data.iloc[:,3:])
y_pred

data["cluster"]= y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"], df0["Spending Score (1-100)"] , c="red", label="cluster0")
plt.scatter(df1["Annual Income (k$)"], df1["Spending Score (1-100)"] , c="black", label="cluster1")
plt.scatter(df2["Annual Income (k$)"], df2["Spending Score (1-100)"] , c="blue", label="cluster2")
plt.scatter(df3["Annual Income (k$)"], df3["Spending Score (1-100)"] , c="green", label="cluster3")
plt.scatter(df4["Annual Income (k$)"], df4["Spending Score (1-100)"] , c="magenta", label="cluster4")
plt.legend()
plt.title("Customer Segements")
```

## Output:
### Elbow method:
![371959749-58fe6ec7-1168-4f7a-97cb-ae8341df32d0](https://github.com/user-attachments/assets/326a4e0b-a9cb-4740-a7a3-cb7c06636370)

### Y-prediction
![371961308-c19298aa-d647-4178-a42d-c1f915580aad](https://github.com/user-attachments/assets/178a25f9-69ed-4867-b47d-e926114b736e)

### Customer segments(cluster)
![371960262-a85d1a33-a76a-4ea5-8411-7cf70a66d2bb](https://github.com/user-attachments/assets/31e8c8e6-6075-4b71-8862-12fff3c548ab)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
