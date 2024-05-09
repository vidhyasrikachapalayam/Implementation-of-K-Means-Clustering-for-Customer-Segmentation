# EX8 Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import pandas and matplotlib.pyplot

2.Read the dataset and transform it

3.Import KMeans and fit the data in the model

4.Plot the Cluster graph 

## Program:
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: vidhyasri.k
RegisterNumber:  212222230170
```
```
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("/content/Mall_Customers.csv")

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
plt.xlabel("No.of Clusters")
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
plt.title("Customer Segments")

```

## Output:
data.head() function:

![image](https://github.com/vidhyasrikachapalayam/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477817/9898af79-e200-451d-b2cf-74552d1ecd45)

data.info():

![image](https://github.com/vidhyasrikachapalayam/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477817/a8d67e7c-c317-4069-80c3-c7edff3e4e56)
data.isnull().sum():

![image](https://github.com/vidhyasrikachapalayam/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477817/43f695ef-cc5b-4062-b194-dbba995e30f1)

Elbow Method Graph:

![image](https://github.com/vidhyasrikachapalayam/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477817/ec138f84-2f15-428c-a8a2-028bd788c02d)


KMeans Clusters:

![image](https://github.com/vidhyasrikachapalayam/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477817/383526f4-8be9-4c07-84b5-b8f57ea1c8ee)

y-pred:

![image](https://github.com/vidhyasrikachapalayam/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477817/64f11d83-1940-4fa3-896f-4f85947305ac)

Customer Segment Graph:

![image](https://github.com/vidhyasrikachapalayam/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477817/1c871df4-d4e3-47fa-8e99-e23d7f2d263f)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
