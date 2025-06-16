← [Back to AWS AI Practitioner Exam](../AWS%20AI%20Practitioner%20Exam.md)

# OpenSearch

- AWS fully manages OpenSearch (formerly Elasticsearch) clusters, handling deployment, scaling, and maintenance. It is a managed **full-text search service** that makes it easy to deploy, operate, and scale OpenSearch, a popular open-source search and analytics engine.
- **Use Cases**:
    - Log and event analytics (e.g., monitoring ML pipelines).
    - Real-time application monitoring.
    - Full-text search and semantic search (e.g., for NLP applications).
    - Anomaly detection using built-in ML features.
    - **Data Storage for ML Models**:
        - Store **embeddings** (vector representations) for semantic search in NLP tasks.
        - Index large datasets used for training or inference.
    - **Anomaly Detection**:
        - Use OpenSearch’s **built-in ML** to detect anomalies in time-series data (e.g., spikes in error logs)
- **Cost Optimization**:
    - Use **Reserved Instances** for long-term workloads.
    - Delete unused indices or enable **Index State Management (ISM)** for automated retention.
- **Multimodal Search**
    
    **Multimodal search** allows users to retrieve relevant information by combining multiple types of data modalities, such as text, images, audio, or video, instead of being limited to traditional text-based queries. This approach provides greater flexibility by enabling more diverse ways of querying and retrieving information, which is especially valuable in use cases like:
    
    - Searching for images using textual descriptions (e.g., “Find pictures of sunset beaches”).
    - Locating text or documents based on an image or visual input.
    - Enabling richer search experiences by integrating textual and non-textual inputs.
- **k-Nearest Neighbor (k-NN) search**
    - Short for its associated ***k-nearest neighbors* algorithm**, k-NN for Amazon OpenSearch Service lets you search for points in a vector space and find the "nearest neighbors" for those points
    - se cases include recommendations (for example, an "other songs you might like" feature in a music application), image recognition, and fraud detection.

### **Use Cases for AI/ML**

- **Retrieval-Augmented Generation (RAG)**:
    - OpenSearch serves as an external knowledge base to enhance LLM responses by retrieving relevant data based on vector similarity. You should understand that RAG combines OpenSearch with services like Amazon Bedrock to provide contextually accurate answers.
- **Semantic Search**:
    - By storing embeddings, OpenSearch enables searching for meaning rather than exact keyword matches, a key concept in modern AI applications.
- **Recommendation Systems**:
    - It can power similarity-based recommendations by matching user preferences (as vectors) with item embeddings.

### **How It Fits into AWS AI Ecosystem**

- **Amazon Bedrock Integration**:
    - OpenSearch can be paired with Bedrock’s Knowledge Bases to provide private data for RAG, improving the relevance of generative AI outputs.
- **Amazon SageMaker**:
    - Models trained in SageMaker can generate embeddings that are indexed and stored in OpenSearch for downstream AI tasks.
- **Data Pipeline**:
    - OpenSearch often works with AWS Glue (for data preparation) and Amazon S3 (for raw data storage) to ingest and process data before it’s used in AI workflows.

### **Comparison with Other AWS Services**

- The exam may ask you to identify when to use OpenSearch versus other AWS database services that support vectors, such as:
    - **Amazon Aurora** (with PostgreSQL compatibility for **pgvector**): A relational database option for structured data with vector support.
    - **Amazon Neptune**: A graph database for relationship-focused AI use cases.
    - **Amazon DocumentDB**: A MongoDB-compatible option for document-based data with vector capabilities.
    - **Key Point**: OpenSearch is typically the go-to choice for search-heavy, unstructured data, and large-scale vector search due to its performance and flexibility.

---

- **References**
    
    https://aws.amazon.com/blogs/big-data/amazon-opensearch-services-vector-database-capabilities-explained/
    
    https://aws.amazon.com/blogs/big-data/build-multimodal-search-with-amazon-opensearch-service/
    
    https://www.youtube.com/watch?v=Umi67JCfCbU