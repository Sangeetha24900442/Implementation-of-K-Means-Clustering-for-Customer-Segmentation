# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

# AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import the necessary packages using import statement.
2. Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().
3. Import KMeans and use for loop to cluster the data.
4. Predict the cluster and plot data graphs.
5. Print the output and end the program.
## Program:
```
*/
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Sangeetha S
RegisterNumber:  212224040287
*/

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
y_pred = km.predict(data.iloc[:,3:])
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
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="brown",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```
# Output:

## Read Data:

<img width="928" height="370" alt="image" src="https://github.com/user-attachments/assets/61710f9b-825d-4eb9-9555-479af90ec756" />

## Data info:

<img width="834" height="290" alt="image" src="https://github.com/user-attachments/assets/bb9cd781-e3c7-4c6a-ae25-fbb5877cf323" />

## Checking Null Data:

<img width="936" height="301" alt="image" src="https://github.com/user-attachments/assets/d27b7584-7a11-44e0-a89b-6dc56dc6a390" />

## PLOT-ELBOW METHODS:

<img width="935" height="707" alt="image" src="https://github.com/user-attachments/assets/54baa976-08fc-41f9-a048-cfe22a7b9b4b" />

## CLUSTER:


<img width="611" height="178" alt="image" src="https://github.com/user-attachments/assets/4af0660f-561d-4f14-aad8-78f391983bab" />

## ARRAY:


<img width="789" height="272" alt="image" src="https://github.com/user-attachments/assets/8387c362-ed35-4d79-907f-5b7026fa3c38" />

## OUTPUT:
<img width="939" height="744" alt="image" src="https://github.com/user-attachments/assets/c1b3694d-bd50-4440-8fdf-da7f65417553" />



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
