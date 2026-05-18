# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Start the program:Import the required libraries and load the customer dataset.
2.Preprocess the data:Select important features such as Age, Income, and Spending Score, and handle missing values if any.
3.Choose the number of clusters (K):Decide the number of customer groups using the Elbow Method or by assumption.
4.Apply the K-Means algorithm:Initialize cluster centroids and assign each customer to the nearest centroid.
Update centroids repeatedly until the clusters become stable.
5.Visualize and analyze the clusters:Display the clustered customer groups using graphs and interpret customer segments for business decision-making.
6.Stop the program 

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: MENAKA M S
RegisterNumber:212225040232
*/
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans

data = {
    'CustomerID': [1,2,3,4,5,6,7,8,9,10],
    'Gender': ['Male','Female','Female','Male','Female','Male','Male','Female','Female','Male'],
    'Age': [19,21,20,23,31,22,35,30,25,28],
    'Annual Income (k$)': [15,16,17,18,19,20,21,22,23,24],
    'Spending Score (1-100)': [39,81,6,77,40,76,6,94,3,72]
}

df = pd.DataFrame(data)

X = df[['Annual Income (k$)', 'Spending Score (1-100)']]

kmeans = KMeans(n_clusters=3, init='k-means++', random_state=42)
df['Cluster'] = kmeans.fit_predict(X)  # Automatically fits and assigns clusters

plt.figure(figsize=(8,6))
for i in range(3):
    plt.scatter(X[df['Cluster']==i]['Annual Income (k$)'],
                X[df['Cluster']==i]['Spending Score (1-100)'],
                label=f'Cluster {i+1}')

plt.scatter(kmeans.cluster_centers_[:,0], kmeans.cluster_centers_[:,1],
            s=200, c='yellow', label='Centroids', marker='X')

plt.title('Customer Segmentation (K-Means)')
plt.xlabel('Annual Income (k$)')
plt.ylabel('Spending Score (1-100)')
plt.legend()
plt.show()

print(df)

```

## Output:
![K Means Clustering for Customer Segmentation](sam.png)
<img width="673" height="508" alt="image" src="https://github.com/user-attachments/assets/34d1c113-3392-464c-a59b-9c2614dffec9" />
<img width="600" height="421" alt="image" src="https://github.com/user-attachments/assets/16869f79-9c6f-4b16-bebd-1d2befecfd8f" />


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
