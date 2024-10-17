# EX8-Implementation of Hierarchical Clustering using linkage methods
## DATE:
## AIM:
To implement Hierarchical Clustering using single and complete linkage method

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
step 1 : Ensure your data is organized properly. Each row represents a data point, and each
column represents a feature.
step2: Use one of the linkage methods (e.g., single, complete, average, or ward) to calculate
the distance between clusters and generate the linkage matrix.
step3: A dendrogram helps visualize the hierarchical structure and merge process of clusters.
step4 : Decide the number of clusters by cutting the dendrogram at a certain height or by
specifying a maximum distance. This step gives the final cluster assignments.

## Program:
```
/*
Program to implement Hierarchical Clustering using single and complete linkage method
Developed by: monisha.L
RegisterNumber:  2305001019
*/
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from scipy.cluster.hierarchy import dendrogram, linkage, fcluster # Changed 'dendog
from sklearn.preprocessing import StandardScaler
df=pd.read_csv('/content/Hclus_EX8.csv')
df.head()
X=df[['StudentID','Marks']].values
X
#Perform hierarchical clustering (agglomerative)
Z=linkage(X, method='complete')
#Plot dendogram
plt.figure(figsize=(5,2))
plt.title("Dendogram for Student Segmentation")
labels=range(1,len(df)+1)
dendrogram(Z,labels=labels)
plt.xlabel("Student ID")
17/10/2024, 12:54 jenisha768/EX08-Implementation-of-Hierarchical-Clustering-using-linkage-methods
https://github.com/jenisha768/EX08-Implementation-of-Hierarchical-Clustering-using-linkage-methods 1/5
plt.ylabel("Marks")
plt.show()
#Cut the dendrogram to form clusters(let's say we want 5 clusters)
max_clusters=2
clusters=fcluster(Z,max_clusters,criterion='maxclust')
clusters
#Scatter plot with different colors for each cluster
plt.figure(figsize=(5,2))
plt.scatter(X[:,0],X[:,1],c=clusters,cmap='rainbow',s=100)
plt.title("Student segmented (Hierarchical Clustering)")
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()
Z=linkage(X, method='single')
#Plot dendogram
plt.figure(figsize=(5,2))
plt.title("Dendogram for Student Segmentation")
labels=range(1,len(df)+1)
dendrogram(Z,labels=labels)
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()
#Cut the dendrogram to form clusters(let's say we want 5 clusters)
max_clusters=2
clusters=fcluster(Z,max_clusters,criterion='maxclust')
clusters
#Scatter plot with different colors for each cluster
plt.figure(figsize=(5,2))
plt.scatter(X[:,0],X[:,1],c=clusters,cmap='rainbow',s=100)
plt.title("Student segmented (Hierarchical Clustering)")
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()
```

## Output:
![image](https://github.com/user-attachments/assets/d6335a57-6161-4faa-b661-c9c8de5b64f0)
![image](https://github.com/user-attachments/assets/2c035f27-4c82-4f89-8100-352127aae579)
![image](https://github.com/user-attachments/assets/73d91758-c2c4-4291-a143-e368ef2dde9f)
![image](https://github.com/user-attachments/assets/f6c8a3fe-ea2c-4e89-8731-a216c47aa7af)
![image](https://github.com/user-attachments/assets/ab02f8f1-1fbf-4c98-ba67-2ad0ea08391f)
![image](https://github.com/user-attachments/assets/2105349c-3ae7-4d4f-a0f1-d9940a044ec4)
![image](https://github.com/user-attachments/assets/fac3040c-0498-4c71-a26f-56f10686e126)










## Result:
Thus the implementation of Hierarchical Clustering using single and complete linkage method in python programming and verified successfully.
