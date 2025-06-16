← [Back to AWS AI Practitioner Exam](../AWS%20AI%20Practitioner%20Exam.md)

# Data Ingestion and Storage

**Types of data:**

1. Structured
    
    Structured data refers to data that is organized and formatted in a predefined manner, typically in the form of tables or databases with rows and columns. This type of data is suitable for traditional machine learning algorithms that require well-defined features and labels. The following are types of structured data.
    
    **Tabular data:** This includes data stored in spreadsheets, databases, or CSV files, with rows representing instances and columns representing features or attributes.
    
    **Time-series data:** This type of data consists of sequences of values measured at successive points in time, such as stock prices, sensor readings, or weather data.
    
2. Unstructured

Unstructured data is data that lacks a predefined structure or format, such as text, images, audio, and video. This type of data requires more advanced machine learning techniques to extract meaningful patterns and insights.

**Text data:** This includes documents, articles, social media posts, and other textual data.

**Image data:** This includes digital images, photographs, and video frames.

- semi-structured

**Properties of Data**

- Volume
- Velocity
- Variety

Data lake

Data LakeHouse

Data Warehouse

- **Data Mesh**
    - coined in 2019, it’s more about governance and organization
    - individual teams own “data products” within a given domain
    - these data products serve various “use cases” around the organization
    - “Domain-based data managment
    - Federated governance with central standards
    - Self-service tooling & infrastructure
    - Data lakes, warehouses etc may be a part of it
        - but a data mesh is more about the data management paradigm, an not the specific technologies or architectures
- **ELT & ETL Pipelines and Orchestration**
    
    ### ELT
    
    **ETL Pipelines**
    
    - ETL - ***Extract, Transform, Load*** - Process used to move data from a source system into data warehouse
    - Extract:
        - retrieve raw data from the source system, which can be databases, CRMs, flat files, APIs, or other data repositories
        - Ensure data integrity during the extraction phase
        - can be done in real time or in batches, depending on requirements
    - **Transform**
        - convert the extracted data into a format suitable  for the target data warehouse
        - can involve various operations as:
            - data cleansing (e.g removing duplicates, fixing errors)
            - data enrichment (e.g adding additional data for other sources)
            - format change s(e.g date formatting, string manipulation)
            - aggregation or computations (e.g calculating totals or averages)
            - encoding or decoding data
            - handling missing values
    - **Load**
        - move the transformed data into the target data warehouse or another data repository
        - can be done in batches (all at once ) or in a streaming manner (as data becomes available)
        - ensure that data maintains its integrity during the loading phase
    - **Manage**
        - This process must be automated in some reliable way
        - AWS Glue
        - Orchestration services:
            - EventBridge
            - Amazon Managed workflows for apache airflow
            - step functions
            - lamba
            - glue workflows
            
- **Data Sources**
    - JDBC
        - Java Database Connectivity
        - Platform-independent
        - language independent
    - ODBC
        - Open database Connectivity
    - Raw logs
    - API’s
    - Streams