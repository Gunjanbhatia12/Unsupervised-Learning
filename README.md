# K-Means Clustering using Scikit-Learn

This project demonstrates the implementation of the **K-Means Clustering Algorithm** using **Python and Scikit-Learn**.  
K-Means is an **unsupervised machine learning algorithm** used to group similar data points into clusters based on their features.

The notebook creates a dataset, applies the K-Means algorithm, calculates cluster centers, and visualizes the clusters using a scatter plot.

---

## 📌 Project Overview

K-Means clustering works using the following steps:

1. Choose the number of clusters **K**
2. Randomly initialize **K centroids**
3. Assign each data point to the nearest centroid
4. Update centroids by computing the mean of assigned points
5. Repeat the process until the centroids stop changing

This project demonstrates the basic working of K-Means clustering using a simple dataset.

---

## 📂 Project Structure

```
K-Means-Clustering/
│
├── K-Mean.ipynb        # Jupyter Notebook containing the K-Means implementation
└── README.md           # Project documentation
```

---

## 🛠 Technologies Used

- **Python**
- **NumPy**
- **Scikit-Learn**
- **Matplotlib**
- **Jupyter Notebook**

---

## 📊 Dataset

A small dataset is manually created for clustering:

```
[20, 30]
[25, 35]
[80, 85]
[85, 90]
[50, 60]
[52, 58]
```

These are **two-dimensional data points** which will be grouped into clusters by the K-Means algorithm.

---

## ⚙️ Implementation Steps

### 1️⃣ Import Required Libraries

```python
import numpy as np
from sklearn.cluster import KMeans
import matplotlib.pyplot as plt
```

### 2️⃣ Create Dataset

```python
X = np.array([
    [20, 30],
    [25, 35],
    [80, 85],
    [85, 90],
    [50, 60],
    [52, 58]
])
```

### 3️⃣ Apply K-Means Clustering

```python
kmeans = KMeans(n_clusters=2, random_state=0)
kmeans.fit(X)
```

### 4️⃣ Get Cluster Labels and Centroids

```python
labels = kmeans.labels_
centroids = kmeans.cluster_centers_
```

### 5️⃣ Visualize Clusters

```python
plt.scatter(X[:,0], X[:,1], c=labels)
plt.scatter(centroids[:,0], centroids[:,1], marker='X')
plt.title("K-Means Clustering")
plt.xlabel("Feature 1")
plt.ylabel("Feature 2")
plt.show()
```

---

## 📈 Output

The model produces:

- **Cluster labels** for each data point
- **Cluster centroids**
- **Visualization of clustered data**

Example Output:

```
Cluster Labels: [0 0 1 1 0 0]
Centroids:
[[36.75 45.75]
 [82.5  87.5 ]]
```

---

## 📊 Visualization

The scatter plot shows:

- Data points colored according to cluster assignment
- Cluster centers marked with **X**

This helps visually understand how the K-Means algorithm groups similar data points.

---

## 🚀 How to Run the Project

1. Clone this repository

```
git clone https://github.com/your-username/k-means-clustering.git
```

2. Navigate to the project directory

```
cd k-means-clustering
```

3. Install required libraries

```
pip install numpy scikit-learn matplotlib
```

4. Run Jupyter Notebook

```
jupyter notebook
```

5. Open **K-Mean.ipynb** and run all cells.

---

## 📚 Learning Outcomes

By completing this project, you will understand:

- Unsupervised Machine Learning
- K-Means Clustering Algorithm
- Cluster Centroids
- Data Visualization using Matplotlib
- Basic Machine Learning workflow in Python

---

## 🔮 Future Improvements

- Apply **Elbow Method** to find the optimal number of clusters
- Use **real-world datasets**
- Add **Silhouette Score evaluation**
- Build a **Streamlit web application** for cluster visualization

---
# Dimensionality Reduction using PCA

This project demonstrates **Dimensionality Reduction using Principal Component Analysis (PCA)** with Python and Scikit-Learn.  
PCA is used to reduce high-dimensional data into fewer dimensions while preserving as much variance as possible.

The project applies PCA on the **Digits dataset** and visualizes the transformed data in **2D space**.

---

## 📌 Project Overview

High-dimensional datasets can be difficult to visualize and may increase computational complexity.  
**Principal Component Analysis (PCA)** helps reduce the number of features while maintaining important information.

In this project:

- The **Digits dataset** is loaded from Scikit-learn.
- PCA is applied to reduce the dataset to **2 principal components**.
- The reduced dataset is visualized using **Matplotlib scatter plot**.

---

## 📂 Dataset

The dataset used is the **Digits Dataset** from Scikit-learn.

Features of the dataset:

- 1797 samples of handwritten digits
- Each image is **8 × 8 pixels**
- Each image is flattened into **64 features**
- Target labels represent digits **0–9**

Dataset Source:
```
sklearn.datasets.load_digits()
```

---

## ⚙️ Technologies Used

- Python
- NumPy
- Scikit-learn
- Matplotlib
- Jupyter Notebook

---

## 🧠 Algorithm Used

### Principal Component Analysis (PCA)

PCA is an **unsupervised machine learning algorithm** used for dimensionality reduction.

Key concepts:

- Converts high-dimensional data into a **lower-dimensional space**
- Finds **principal components** that maximize variance
- Removes redundancy and noise
- Helps with **visualization and faster model training**

In this project:

- Original features: **64**
- Reduced features: **2 principal components**

---

## 🚀 Project Workflow

1. Import required libraries.
2. Load the digits dataset.
3. Extract feature matrix `X` and labels `y`.
4. Apply PCA with **2 components**.
5. Transform the dataset into reduced dimensions.
6. Visualize the reduced dataset using a **scatter plot**.

---

## 💻 Implementation

### Import Libraries

```python
from sklearn.datasets import load_digits
from sklearn.decomposition import PCA
import matplotlib.pyplot as plt
```

### Load Dataset

```python
data = load_digits()
X = data.data
y = data.target
```

### Apply PCA

```python
pca = PCA(n_components=2)
X_reduced = pca.fit_transform(X)
```

### Visualization

```python
plt.scatter(X_reduced[:,0], X_reduced[:,1], c=y)
plt.title("PCA Visualization of Digits Dataset")
plt.xlabel("Component 1")
plt.ylabel("Component 2")
plt.show()
```

---

## 📊 Output

The output is a **2D scatter plot** showing how the handwritten digits are distributed after dimensionality reduction.

- Each point represents an image from the dataset.
- Different colors represent different digit classes.
- PCA helps visualize high-dimensional data in **2D space**.

---

## 📈 Advantages of PCA

- Reduces dimensionality
- Improves visualization
- Removes correlated features
- Speeds up machine learning models
- Reduces overfitting

---

## 📁 Project Structure

```
DimensionalityReduction-PCA/
│
├── DimensionalityReduction(PCA).ipynb
└── README.md
```

---

## ▶️ How to Run the Project

1. Clone the repository

```
git clone https://github.com/your-username/repository-name.git
```

2. Navigate to the project folder

```
cd repository-name
```

3. Open the notebook

```
jupyter notebook
```

4. Run **DimensionalityReduction(PCA).ipynb**

---

## 🎯 Conclusion

This project demonstrates how **Principal Component Analysis (PCA)** can reduce high-dimensional data into a lower-dimensional representation while preserving important patterns.  
The visualization clearly shows the separation of digit classes in a **2D feature space**.

---

## 👨‍💻 Author

**Gunjan**

B.Tech Computer Science Engineering  
Machine Learning & AI Enthusiast
