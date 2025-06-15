# Embeddings and vectors

- **Embeddings** are dense, low-dimensional vector representations of high-dimensional data (e.g., text, images, audio) in a continuous vector space.
    - They capture semantic relationships, positioning similar items (e.g., "cat" and "dog") closer together and dissimilar items farther apart.
    - Embeddings convert real-world objects into complex mathematical representations that capture inherent properties and relationships between real-world data.
- **Purpose and Importance**
    - Enable machine learning models to process unstructured data by converting it into a numerical format.
    - Preserve contextual meaning, making them critical for tasks like natural language processing (NLP), image recognition, and recommendation systems.
- **Key Characteristics**
    - **Dimensionality**: Typically lower than the original data (e.g., 50–300 dimensions).
    - **Semantic Similarity**: Allows mathematical operations (e.g., "king" - "man" + "woman" ≈ "queen").
    - **Context Awareness**: Advanced embeddings (e.g., from transformers) capture context beyond static word meanings
- **How They’re Created**: Embeddings are typically generated using models like **Word2Vec**, **GloVe, BERT**, or other neural networks trained on large datasets. On AWS, you might use pre-trained models or fine-tune them using SageMaker.
    - **Word2Vec** - predicting either the context words given a target word
    - **GloVe  (Global Vectors for Word Representation)** - focuses more on the statistical co-occurrence of words across a large corpus
    - **BERT (Bidirectional Encoder Representations from Transformers) -**  It’s a transformer-based model that’s designed to capture context bidirectionally—that is, it looks at both the words before and after a target word when determining its representation.

### **Reduce data dimensionality**

- Data scientists use embeddings to ***represent high-dimensional data in a low-dimensional space.*** In data science, the term *dimension* typically refers to a feature or attribute of the data. Higher-dimensional data in AI refers to datasets with many features or attributes that define each data point. This can mean tens, hundreds, or even thousands of dimensions. For example, an image can be considered high-dimensional data because each pixel color value is a separate dimension.
- Embeddings reduce the number of dimensions by identifying commonalities and patterns between various features. This consequently reduces the computing resources and time required to process raw data.

### Embedding models

- **Embedding models** are algorithms trained to encapsulate information into dense representations in a multi-dimensional space. Data scientists use embedding models to enable ML models to comprehend and reason with high-dimensional data. These are common embedding models used in ML applications.
- ***Principal component analysis* (*PCA*)** is a dimensionality-reduction technique that reduces complex data types into low-dimensional vectors. It finds data points with similarities and compresses them into embedding vectors that reflect the original data. While PCA allows models to process raw data more efficiently, information loss may occur during processing.
- ***Singular value decomposition* (*SVD*)** is an embedding model that transforms a matrix into its singular matrices. The resulting matrices retain the original information while allowing models to better comprehend the semantic relationships of the data they represent. Data scientists use SVD to enable various ML tasks, including image compression, text classification, and recommendation.
- **Word2Vec** is an ML algorithm trained to associate words and represent them in the embedding space. Data scientists feed the Word2Vec model with massive textual datasets to enable natural language understanding. The model finds similarities in words by considering their context and semantic relationships.
    
    There are two variants of Word2Vec—Continuous Bag of Words (CBOW) and Skip-gram. CBOW allows the model to predict a word from the given context, while Skip-gram derives the context from a given word. While Word2Vec is an effective word embedding technique, it cannot accurately distinguish contextual differences of the same word used to imply different meanings. 
    
- **BERT** is a transformer-based language model trained with massive datasets to understand languages like humans do. Like Word2Vec, BERT can create word embeddings from input data it was trained with. Additionally, BERT can differentiate contextual meanings of words when applied to different phrases. For example, BERT creates different embeddings for ‘play’ as in *“I went to a play”* and *“I like to play.”*

---

**Storing Embedding:**

1.  **S3 (**Object Storage for Embeddings)
    - scalable and durable: store massive numbers of embeddings as objects in S3 buckets
    - cost-effective: leverage S3’s tiered storage classes (e.g standard, inteligent-tiering, glacier) for cost optimisation
    - Data lake integration: part of the data lake architecture, enabling easy access for other services
    - Note: S3 is primary for storage. It doesn’t have built-in capabilities for semantic search (finding similar embeddings).  You will need to integrate with services like OpenSearch
    - Use cases:
        - storing raw embedding files (e.g csv, parequet)
        - archiving historical embeddings
2. **Amazon DynamoDB**
    - key-value store: efficiently store and retrieve embeddings using unique keys
    - High scalability: handles high throughput and low latency for demanding applications
    - flexible schema: adapt to changing data structures and requirements
3. **OpenSearch Service**
    - k-NN Search: efficiently perform k-nearest neighbour searches to find similar embeddings
    - Vector Field support: optimized for storing and searching vector data
    - scalability and analytics: scale to massive datasets and perform analytics on embeddings
    - Use cases:
        - similarity search applications (e.g product recommendations, image retrieval)
        - building complex search and analytics pipelines
4. **Other RAG vector databases:**
    - documentDb
    - aurora
    - RDS for postgresSql
    - neptune