← [Back to AWS AI Practitioner Exam](../AWS%20AI%20Practitioner%20Exam.md)

# Data Lakes

![image.png](Data%20Lakes/image.png)

# AWS Lake Formation

### Overview

- **AWS Lake Formation** is a **data lake** to centrally govern, secure, and globally share data for analytics and machine learning.
- **Data Lake** is persistent data stored in Amazon S3 and managed by Lake Formation using a Data Catalog.

### Key Features

- Manage fine-grained access control for your data lake data on Amazon S3.
- Manage metadata in AWS Glue Data Catalog.
- Provides its own permissions model that augments the **identity and access management** model:
    - Simple grant or revoke mechanism similar to relational database management system (RDBMS).
- Share data internally and externally across multiple AWS accounts, AWS organizations, or directly with IAM principals in another account.
- Permissions are enforced using granular controls at the column, row, and cell levels across:
    - **Athena**
    - **Quicksight**
    - **Redshift Spectrum**
    - **EMR**
    - **Glue**

### Important Terminology

- **Blueprint**: A data management template that enables you to easily ingest data into a data lake. From a blueprint, you can create a workflow.
- **Workflow**: A container for a set of related AWS Glue jobs, crawlers, and triggers.
- **Data Catalog**: Your persistent metadata store. It is a managed service that lets you store, annotate, and share metadata.
- **Data Lake Administrator**: A principal who can grant any principal (including self) any permission on any Data Catalog resource or data location.

### Key Points

- **AWS Lake Formation** and **AWS Glue** share the same Data Catalog.
- It supports structured and unstructured data, as well as raw data and transformed data.