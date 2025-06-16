← [Back to AWS AI Practitioner Exam](../AWS%20AI%20Practitioner%20Exam.md)

# AWS Glue

- **General**
    - **AWS Glue** is a fully managed extract, transform, and load (ETL) service that simplifies the process of preparing and loading data for analytics, machine learning, and application development. It automates the tedious tasks of data discovery, conversion, mapping, and job scheduling.
    - serverless data integration service that makes it easy for analytics users to discover, prepare, move, and integrate data from multiple sources
    - **Key Features Relevant to AI/ML**
        1. **Data Cataloging**: AWS Glue automatically discovers and catalogs metadata about your data stores into a central repository known as the ***Glue Data Catalog***. This metadata is crucial for AI/ML models to understand the structure and schema of the data they process.
        2. **ETL Capabilities**: With AWS Glue, you can create and run ETL jobs to clean, enrich, and transform raw data into formats suitable for machine learning models. This ensures that data fed into AI/ML algorithms is accurate and well-structured.
        3. **Data Preparation with DataBrew**: *AWS Glue DataBrew* offers a visual interface for data preparation, allowing users to clean and normalize data without writing code. This feature is particularly useful for data scientists and analysts preparing data for machine learning tasks.
    
- **Glue Studio**
    - allows to visually build ETL pipelines (also known as Visual ETL)
    - A pipeline is composed of **nodes**:
        - **Sources**: The data you plan to use.
        - **Transforms**: What you want to do to the data.
        - **Targets**: Where you want to send the data
        
        ![image.png](AWS%20Glue/image.png)
        
- **Glue Jobs**
    
    ![image.png](AWS%20Glue/image%201.png)
    
- **Glue Data Catalog**
    
    **AWS Glue Data Catalog** is a **fully managed, Apache Hive Metastore-compatible catalog service** that makes it easy for customers to store, annotate, and share metadata about their data.
    
    ![image.png](AWS%20Glue/image%202.png)
    
- **Glue Data Catalog - Crawler**
    
    ![image.png](AWS%20Glue/image%203.png)
    
- **Glue Data Quality**
    
    ![image.png](AWS%20Glue/image%204.png)
    
- **Glue Data Brew**
    
    ![image.png](AWS%20Glue/image%205.png)