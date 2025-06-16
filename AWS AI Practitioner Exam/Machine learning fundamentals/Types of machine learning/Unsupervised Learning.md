← [Back to Types of Machine Learning](../Types%20of%20machine%20learning.md)

# Unsupervised Learning

In **unsupervised learning**, there are no labels for the training data. A machine learning algorithm tries to learn the underlying patterns or distributions that govern the data. We will explore this in-depth in this lesson.

- **Clustering**
    
    **Clustering** is a core technique in **unsupervised learning**, where the goal is to group similar data points into clusters based on patterns and features in the data, without the use of labeled data.
    
    ![image.png](Unsupervised%20Learning/image.png)
    
    **Key Characteristics of Clustering**
    
    1. **No Labels Required:** Clustering works on unlabeled datasets, discovering structures purely from the data itself.
    2. **Similarity-Based:** Data points are grouped based on their similarity, typically measured using distance metrics like **Euclidean distance**, **Manhattan distance**, or **cosine similarity**.
    3. **Data Representation:** Clusters can represent categories, groups, or segments that provide insights into the dataset.
- **Association**
    
    Association is the process of finding a relationship between variables thorough association
    
    Algorithms:
    
    - Apriori
    - Euclat
    - FP-Growth
- **Dimensionality Reduction**
    - is a process of reducing the amount of data while retaining data integrity. often used as pre-processing stage
    - Algorithms:
        - Principal Component Analysis (PCA)
        - Linear Discriminant Analysis (LDA)
        - Generalized Discriminant Analysis (GDA)
        - Singular Value Decomposition (SVD)
        - Latent Dirichlet allocation (LDA)
        - Latent Semantic Analysis (LSA, pLSA, GLSA)
        - t-SNE