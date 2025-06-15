# Amazon Comprehend

- **General**
    
    **AWS Comprehend** is a fully managed **natural language processing (NLP)** service that uses machine learning to extract insights from text. It enables businesses to uncover the meaning and relationships within their text data, making it easier to analyze unstructured data.
    
    - Fully managed and serverless service
    - Uses machine learning to find insights and relationships in text
        - Language of the text
        - Extracts *key phrases,* *places*, *people, brands, or events*
        - Understand how positive or negative the text is ***(sentiment analysis)***
        - Analyzes text using **tokenization** and parts of speech
        - Automatically organizes a ***collection*** of text files by topic
    - Sample use cases:
        - analyze customer interactions (emails) to find what leads to a positive or negative experience
        - Create and group articles by topics that Comprehend will uncover
    - Easily integrates with other AWS services like **Amazon S3**, **AWS Lambda**, and **Amazon SageMaker** for building end-to-end pipelines.
    
    **Pros:**
    
    - Easy to use and fast to set up.
    - Suitable for general-purpose tasks.
    - No need for labeled training data.
    
    **Cons:**
    
    - Limited to generic use cases.
    - May not perform well for domain-specific tasks.
- **Use Cases**
    1. **Customer Sentiment Analysis:** Analyze customer reviews, social media posts, or surveys to gauge overall sentiment.
    2. **Content Categorization:** Organize documents, emails, or customer queries into relevant categories.
    3. **Fraud Detection:** Identify patterns or specific entities in text data related to fraudulent activities.
    4. **Healthcare and Life Sciences:** Extract medical entities (e.g., drug names, diseases) from clinical notes using custom entity recognition.
    5. **Legal and Financial Document Analysis:** Extract entities like contract dates, parties, or payment terms for easier document processing.
    6. **Topic Discovery:** Group large sets of documents to identify trends and themes in customer feedback or research papers.
- **Named Entity Recognition (NER)**
    - *Extracts predefined, general-purpose entities* like people, places, organizations, dates, and other standard categories, from text
    
    ![image.png](Amazon%20Comprehend%20174d5f4e5b4f800082d6cbaaeabe234c/image.png)
    
- **Custom Capabilities: Custom Classification**
    
    Standard capabilities are pre-built features that use AWS’s general-purpose NLP models. They work out of the box without requiring any additional training or customization.
    
    **Custom Classification** in **AWS Comprehend** allows you to create machine learning models tailored to your specific text categorization needs. Unlike standard classification, which uses pre-defined categories, custom classification enables you to define your own categories and train a model to classify text into those categories based on labeled examples.
    
    - Types:
        - **Multi-Class Classification:** Assigns one label per text sample. Each text belongs to **exactly one category** out of a predefined set of categories.
        - **Multi-Label Classification:** Assigns **one or more categories (labels)** to a single text sample. A single input can belong to **multiple categories** simultaneously.
            - Key Characteristics:
                - **Overlapping Categories:** Text samples can have multiple relevant labels.
                - **Use Case:** Best suited when categories are not mutually exclusive. e.g tagging articles
                
    - *Organize documents into categories* (classes) that you define. Example: categorize customer emails so that you can provide guidance based on the type of the customer request
    - Detects primary language of the text → Example: “Bonjour, comment ça va?” → Language: French.
    - Text classification: Classifies text into pre-defined general categories (e.g., “News,” “Sports”).
    - Supports different document types (text, PDF, Word, images...)
    - ***Real-time Analysis*** – single document, synchronous
    - ***Async Analysis*** – multiple documents (batch), Asynchronous
    
    ![image.png](Amazon%20Comprehend%20174d5f4e5b4f800082d6cbaaeabe234c/image%201.png)
    
    ![image.png](Amazon%20Comprehend%20174d5f4e5b4f800082d6cbaaeabe234c/image%202.png)
    
- **Custom Capabilities: Custom Entity Recognition**
    - Analyze text for specific terms and noun-based phrases
    - Extract terms like policy numbers, or phrases that imply a customer escalation, anything specific to your business
    - Train the model with custom data such as a list of the entities and documents that contain them
    - Real-time or Async analysis
- **Custom Capabilities use cases & pros/cons**
    
    ![image.png](Amazon%20Comprehend%20174d5f4e5b4f800082d6cbaaeabe234c/image%203.png)
    
    **Use Cases:**
    
    - Classifying legal documents (e.g., contracts, NDAs).
    - Identifying specialized entities like drug names or chemical formulas.
    - Categorizing customer reviews based on domain-specific needs.
    
    **Pros:**
    
    - Tailored to your specific business requirements.
    - Improves accuracy for specialized or niche tasks.
    - Can handle unique entities or categories not covered by standard models.
    
    **Cons:**
    
    - Requires labeled training data.
    - Longer setup time due to data preparation and model training.
    - Additional cost for training and storage.
- **Custom Models**
    
    **Capabilities of Custom Models in Amazon Comprehend**
    
    - You can create custom models for entity recognition or document classification
        - Trained on your own data
    - Comprehend manages your model versioning
    - Custom models may be copied between AWS accounts
    - Other account then import the model
        - Must be in same region
        - Needs its ARN region, and optional KMS key
        - Can be done from Comprehend console
        
    1. **Custom Classification:**
        - Categorize text into user-defined labels based on your unique requirements.
        - Example: Categorizing support tickets into labels like “Billing Issue,” “Technical Support,” or “General Inquiry.”
    2. **Custom Entity Recognition (Custom NER):**
    - Identify domain-specific entities in text that are not recognized by Comprehend’s pre-trained models.
    - Example: Extracting specific terms like product IDs, drug names, or financial transaction codes.
    
- **References**
    
    https://www.youtube.com/watch?v=NC8r7dkcqkQ
    
    https://www.youtube.com/watch?v=QsqHvDPRSSQ
    
    https://www.youtube.com/watch?v=oDk5aOd400c