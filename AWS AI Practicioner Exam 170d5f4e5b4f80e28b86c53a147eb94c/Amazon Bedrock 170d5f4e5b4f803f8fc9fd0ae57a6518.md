# Amazon Bedrock

- **General**
    - Build Generative AI (Gen-AI) applications on AWS
    - Fully-managed service, no servers for you to manage
    - Keep control of your data used to train the model
    - Pay-per-use pricing model
    - Unified APIs
    - Leverage a wide array of foundation models
    - Out-of-the-box features: RAG, LLM Agents…
    - Security, Privacy, Governance, and Responsible AI features
    - Bedrock operates ***serverlessly***, so you don’t need to manage servers or infrastructure.
    - Customization: Use “fine-tuning” or “prompt engineering” to tailor models to your business needs without requiring extensive training data.
        
        ![image.png](Amazon%20Bedrock%20170d5f4e5b4f803f8fc9fd0ae57a6518/image.png)
        
    - **APIs for Easy Integration:** Provides APIs to embed FMs into applications, making it straightforward to create generative AI features for your apps.
    - Easily integrates with other AWS services like Amazon SageMaker, AWS Lambda, and Amazon S3. Benefits from AWS’s security measures, ensuring data privacy and compliance.
- **Foundations models**
    1. Foundation Models are large **pre-trained** machine learning models designed for various tasks. Examples include models for text generation, summarization, translation, image generation, and more.
    - Foundation Models Available in Bedrock:
        - **Amazon Titan Models:**
            - Titan models are pretrained on large datasets and can perform a variety of tasks, such as text generation, text summarization, and language understanding.
            - These models are designed for general-purpose applications but can also be fine-tuned for specific business use cases.
        - Third-Party Models:
            - **Anthropic:** Focused on creating safer AI systems.
            - **Stability AI:** Specializes in image and generative tasks.
            - **AI21 Labs:** Known for language-centric models like content creation.
    - Models are optimized for text generation, summarization, and image generation tasks.
    - Amazon Bedrock makes a copy of the FM, available only to you, which you can further fine-tune with your data
    - none of your data is used to train FM
    
    ![image.png](Amazon%20Bedrock%20170d5f4e5b4f803f8fc9fd0ae57a6518/image%201.png)
    
    How to choose the **Base Foundation Model**?
    
    - Model types, performance requirements, capabilities, constraints, compliance
    - Level of customization, model size, inference options, licensing agreements,
    context windows, latency
    - Multimodal models (varied types of input and outputs)
        - A **multimodal model** is a type of machine learning model designed to process and integrate data from multiple modalities (different types of input, such as text, images, audio, video, or sensor data) to perform tasks that require a comprehensive understanding of diverse information sources.
- **PartyRock**
    - playground where anyone can build generative ai apps. No coding needed!
    - Powered by Bedrock: it uses amazon bedrock’s foundation (FMs) to bring your ideas to life
    - Build and share: create apps and share them with others to inspire and collaborae
- **Amazon Titan Model**
    - Trained on vast datasets, allowing them to handle complex natural language and data analysis tasks without requiring large-scale retraining.
    - Supports **fine-tuning** to adapt the model to industry-specific or organization-specific needs.
    - Titan generates high-dimensional vector **embeddings** representing semantic meaning.
    - Offers a **serverless** experience for easy integration into applications.
    - Easily configurable via **prompt engineering** for use-case-specific applications.
    - ***Image, text, and multimodal*** model choices via a fully-managed APIs
    - It can be customized with your data
    - **multimodal capabilities:** Titan models can handle various modalities, such as text and images, making them versatile for different applications.
    - **multimodal search:** Enable search across text and image data by generating embeddings that represent the semantic meaning of both modalities.
    - when to use Titan models:
        - Document summarization for legal or business contexts.
        - Generating personalized recommendations.
        - Sentiment analysis and text classification.
    - Titan integrates with:
        - **Amazon Bedrock**: To access Titan models without managing infrastructure.
        - **AWS Lambda**: To create serverless AI-driven applications.
        - **Amazon S3**: For storing and retrieving data used with Titan models.
    
    <aside>
    💡
    
    - **Amazon Titan Multimodal Embeddings G1** plays a critical role in **multimodal search** by generating **vector embeddings** for different data types, such as text and images. These embeddings are high-dimensional numerical representations that encode the semantic meaning of the data, making it possible to compare and search across different modalities.
    </aside>
    
    - Smaller models are more cost-effective (but they know less things)
    
    ![image.png](Amazon%20Bedrock%20170d5f4e5b4f803f8fc9fd0ae57a6518/image%202.png)
    
- **Fine-Tuning a Model**
    - An **epoch** in machine learning, including fine-tuning, refers to **one complete pass through the entire training dataset** by the model. During fine-tuning, the model uses the training data to adjust its parameters, such as weights and biases, to better perform the specific task it is being fine-tuned for
    - When fine-tuning a model like the Amazon Titan Text Premier mode**l**, the goal is to optimize its performance on unseen data while avoiding overfitting. To determine the optimal number of epochs during fine-tuning, the following metrics are critical:
        - **Validation Output Accuracy**
            - Accuracy measures how well the model is performing on the validation set (data it hasn’t seen during training).
            - Tracking validation accuracy ensures the model generalizes well to new data.
            - If validation accuracy stops improving or starts to decline, it indicates the model may be overfitting.
        - **Validation Loss:**
            - Validation loss indicates how well the model is minimizing errors on the validation set.
            - Monitoring validation loss helps determine when the model stops improving or begins to overfit.
            - A rising validation loss after several epochs is a signal to stop training.
        
        <aside>
        💡
        
        Other parameters:
        
        - **Number of Epochs:** Refers to the number of complete passes through the training dataset. Too few epochs result in underfitting, while too many cause overfitting. Monitor **validation loss** or **early stopping** to determine the optimal number of epochs.
            
            <aside>
            💡
            
            NOTE: **learning rate** and **batch siz**e are used to determine the optimal number of epochs
            
            </aside>
            
        - **Training Loss:** Training loss only reflects the model’s performance on the training data. While it’s useful for monitoring convergence, it doesn’t indicate how well the model generalizes to new data (which is the goal of validation metrics).
        - **Learning Rate:** Determines how much the model weights are adjusted during each training step.
            
            **Importance:**
            
            - A **high learning rate** may lead to faster training but risks overshooting the optimal solution.
            - A **low learning rate** provides more precise updates but may slow down training.
            
            **Best Practices:** Start with a small learning rate (e.g., 10^{-5} or 10^{-4}) for fine-tuning, as pre-trained models already have well-initialized weights.
            
        - **Batch Size:** Number of training samples processed before the model updates its parameters.
        - **Weight Decay (L2 Regularization):**  Adds a penalty to large weights in the model to prevent overfitting.
        - **Dropout Rate:**  Fraction of neurons randomly set to zero during training to prevent overfitting.
        - **Loss Function:** Measures the error between the model’s predictions and the true labels.
        - **Layer Freezing and Unfreezing:** Decides which layers of the pre-trained model are updated during fine-tuning.
        - **Early Stopping Criteria:** Stops training when the validation performance stops improving.
        - **Data Augmentation:** Techniques to artificially expand the training dataset by applying transformations (e.g., flipping, rotation, or noise).
        </aside>
        
    - Adapt a copy of a foundation model with your data
    - Fine-tuning will change the weight of the base foundation model
    - Training data must:
        - Adhere to a specific format
        - Be stored in *Amazon S3*
    - To use fine-tuned model, you must use the “**Provisioned Throughput”** to use a fine-tuned model
    - Note: not all models can be fine-tuned ❗(few can and they are usually open source)
    
    ![image.png](Amazon%20Bedrock%20170d5f4e5b4f803f8fc9fd0ae57a6518/image%203.png)
    
- **Instruction-based Fine Tuning**
    - Improves the performance of a pre-trained FM on domain-specific tasks
    - = further trained in a particular field or area of knowledge
    - Instruction-based fine-tuning uses **labeled examples** that are **prompt-response pairs**
    
    ![image.png](Amazon%20Bedrock%20170d5f4e5b4f803f8fc9fd0ae57a6518/image%204.png)
    
- **Continued Pre-training**
    - like fine-tuning, but with unlabeled data
    - just feed it text to familiarize the model with:
        - your own business documents or whatever
    - Provide **unlabeled data** to continue the training of an FM
    - Also called ***domain-adaptation fine-tuning***, to make a model expert in a specific domain
        - For example: feeding the entire AWS documentation to a model to make it an expert on AWS
    - It is good to feed industry-specific terminology into a model (acronyms, etc…)
    - Can continue to train the model as more data becomes available
    
    ![image.png](Amazon%20Bedrock%20170d5f4e5b4f803f8fc9fd0ae57a6518/image%205.png)
    
- **Single-Turn Messaging**
    - refers to an interaction between a user and a system (such as a chatbot or an API) where the conversation consists of only one exchange: the user sends a message or request, and the system responds without maintaining any context or continuity from previous interactions.
    - Part of instruction-based fine-tuning
    - system (optional): context for the conversation.
    - messages: An array of message objects, each containing:
        - role: Either user or assistant
        - content: The text content of the message
    
    ![image.png](Amazon%20Bedrock%20170d5f4e5b4f803f8fc9fd0ae57a6518/image%206.png)
    
    ![image.png](Amazon%20Bedrock%20170d5f4e5b4f803f8fc9fd0ae57a6518/image%207.png)
    
- **Multi-Turn Messaging**
    - refers to conversational interactions where multiple exchanges (or “turns”) occur between a user and a system, with the system retaining context across the interaction. This type of messaging enables more complex, dynamic conversations and workflows, as the system can build upon previous inputs.
    - To provide instruction-based fine tuning for a conversation (vs SingleTurn Messaging)
    - **Context Retention:** The system maintains the state and context of the conversation, allowing it to reference or build upon previous exchanges.
    - Chatbots = multi-turn environment
    - You must alternate between “user” and “assistant” roles
    
    ![image.png](Amazon%20Bedrock%20170d5f4e5b4f803f8fc9fd0ae57a6518/image%208.png)
    
    **Key Components of Multi-Turn Messaging**
    
    1.	**Session Management:** Each conversation is treated as a session where the context is stored temporarily for the duration of the interaction.
    
    2.	**Intent Recognition:** The system identifies the user’s intent (e.g., booking a ticket, troubleshooting, or placing an order) and maintains the focus of the conversation.
    
    3.	**Slot Filling:** Collecting required information (slots) step-by-step to complete a task. For instance, gathering destination, departure city, and date for a flight booking.
    
    4.	**Error Handling:**
    
    - Handles incomplete or ambiguous inputs by asking follow-up questions:
    - User: “I need a table for dinner.”
    - System: “For how many people?”
    
    **Advantages of Multi-Turn Messaging**
    
    1.	**Enables Complex Interactions:** Suitable for workflows requiring multiple inputs or decision points.
    
    2.	**Improved User Experience:** Reduces the burden on users to provide all information in a single message.
    
    3.	**Personalization:** Adapt responses based on prior inputs, making the conversation feel more natural and personalized.
    
    **Examples of Multi-Turn Messaging Use Cases**
    
    1. **Chatbots:**
        - Customer support bots that troubleshoot issues interactively.
        - Virtual assistants for booking appointments or managing schedules.
    
    2.	**E-Commerce:**
    
    - A shopping assistant that helps users select products based on preferences:
    
    3.	**Healthcare:**
    
    •	Collecting patient information step-by-step during online consultations.
    
    <aside>
    💡
    
    **Fine-Tuning: good to know**
    
    - Re-training an FM requires a higher budget
    - **❗ Instruction-based fine-tuning is usually cheaper as computations are less intense and the amount of data required is usually less**
    - It also requires experienced ML engineers to perform the task
    - You must prepare the data, do the fine-tuning, evaluate the model
    - **Running a fine-tuned model is also more expensive (provisioned
    throughput)**
        - Running a **pre-trained model** (like Amazon Titan) in **on-demand mode** means you only pay when making requests.
        - Running a **fine-tuned version** with **provisioned throughput** means you’re paying for continuous availability, even if requests are not being made.
    </aside>
    
- **GuardRails**
    - **Amazon Bedrock Guardrails** help developers and businesses build safe, reliable, and compliant applications powered by foundational models.
    - These guardrails are designed to ensure that the outputs generated by foundational models adhere to specific guidelines, reduce the risk of harmful or inappropriate content, and align with organizational policies.
        - content filtering for prompts and responses
        - works with text foundation models
        - word filtering
        - topic filtering
        - profanities
        - PII removal (or masking)
        - **Contextual Grounding Check**
            - Helps to prevent hallucinations
            - measure “grounding” (how similar the response is to the contextual data retrieved)
            - and relevance (of response to the query)
        - can be incorporated into agents and knowledge bases
        - may configure the “blocked message” response
    
    - Guardrail Features
        - **Content Filtering**
            - Pre-built filters: bedrock provides content filtering for categories like hate speech, profanity, sexual content, violence, self-harm
            - Configurable Thresholds: adjust the sensitivity of filters to match your risk tolerance
            - Custom Filters: create your own filters based on keywords, regular expressions or other criteria
            - Actions: choose how to handle flagged content (e.g flag for review, modify, block)
        - **Topic Denial:**
            - Define denied topics: specify topics that you want to prevent the AI from discussing (e.g politics, religion)
            - enforcement: guardrails can block or redirect conversations that veer into denied topics
        - Other Safeguards:
            - prompt injection protection
            - jailbreak preventions: make it harder for users to trick the model into bypassing safety measures
            - sensitive information masking: automatically redact or mask sensitive data in user inputs and model responses
            - hallucination reduction
    - **Amazon Bedrock Guardrails** focus on:
        - **Content Moderation:** Automatically identify and filter harmful, inappropriate, or unsafe outputs generated by foundational models.
        - **Safety Enhancements:**
            - Provide mechanisms to avoid unsafe behaviors or outputs in applications that use generative AI.
            - Examples include flagging or blocking biased, offensive, or non-compliant content
        - **Customization for Compliance:** Enable businesses to define and enforce rules to comply with industry regulations, ethical guidelines, or organizational standards.
        - **Human Feedback Integration:** Allow human-in-the-loop workflows for reviewing and refining generated content to meet quality and safety standards.
    - **What Does It Do?**
        - **Detects and Blocks Unsafe Outputs:**  Ensures that generated content does not violate ethical or organizational standards. Examples:
            - Blocking hateful or offensive language.
            - Preventing biased recommendations or discriminatory responses.
        - Control the interaction between users and Foundation Models (FMs)
        - Filter undesirable and harmful content
        - Remove Personally Identifiable Information (PII)
        - Enhanced privacy
        - Reduce hallucinations: Ability to create multiple Guardrails and monitor and analyze user inputs that can
        violate the Guardrails
        - Enhances Explainability: Provides insights into why certain outputs were flagged or modified, helping improve trust in generative AI systems.
        
        https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html
        
- **Transfer learning**
    - machine learning technique where a model developed for one task is reused as the starting point for another related task. It leverages knowledge gained from a pre-trained model, such as patterns or features learned from one dataset, and applies it to a different but related problem.
        - Widely used for image classification
        - And for NLP (models like BERT and GPT)
        - Can appear in the exam as a general ML concept
        - Fine-tuning is a specific kind of transfer learning
- **Amazon Bedrock Evaluating a Model**
    - Evaluate a model for quality control
    - Built-in task types:
        - Text summarization
        - question and answer
        - text classification
        - open-ended text generation…
    - Bring your own prompt dataset or use built-in curated prompt datasets
    - Scores are calculated automatically
    - Model scores are calculated using various statistical methods (e.g. BERTScore, F1…)
    
    - **Benchmark datasets:**
        - Curated collections of data designed specifically to evaluate the performance of language models
        - Wide range of topics, complexities, linguistic phenomena
        - Helpful to measure: accuracy, speed and efficiency, scalability
        - Some benchmark datasets allow you to very quickly detect any kind of bias and potential discrimination against a group of people
        - You can also create your benchmark dataset that is specific to your business
        
        ![image.png](Amazon%20Bedrock%20170d5f4e5b4f803f8fc9fd0ae57a6518/image%209.png)
        
- **Evaluating a Model Human Evaluation**
    - Choose a work team to evaluate
        - Employees of your company
        - Subject-Matter Experts (SMEs)
    - Define metrics and how to evaluate
        - Thumbs up/down, ranking…
    - Choose from **Built-in task types** (same as Automatic) or add a custom task
    
    ![image.png](Amazon%20Bedrock%20170d5f4e5b4f803f8fc9fd0ae57a6518/image%2010.png)
    
- **Automated Metrics to evaluate an FM**
    
    ![image.png](Amazon%20Bedrock%20170d5f4e5b4f803f8fc9fd0ae57a6518/image%2011.png)
    
    ![image.png](Amazon%20Bedrock%20170d5f4e5b4f803f8fc9fd0ae57a6518/image%2012.png)
    
- **Business Metrics to Evaluate a Model On**
    - ***User Satisfaction*** – gather users’ feedbacks and assess their satisfaction with the model responses (e.g., user satisfaction for an ecommerce platform)
    - ***Average Revenue Per User (ARPU)*** – average revenue per user attributed to the Gen-AI app (e.g., monitor ecommerce user base revenue)
    - ***Cross-Domain Performance*** – measure the model’s ability to perform cross different domains tasks (e.g., monitor multi-domain ecommerce platform)
    - ***Conversion Rate*** – generate recommended desired outcomes such as purchases (e.g., optimizing ecommerce platform for higher conversion rate)
    - ***Efficiency*** – evaluate the model’s efficiency in computation, resource utilization…
    (e.g., improve production line efficiency)
- **RAG & Knowledge Bases**
    
    **Retrieval-Augmented Generation (RAG)** is a hybrid framework that combines information retrieval techniques with generative AI models to enhance the generation of text. Instead of relying solely on the model’s internal knowledge, RAG integrates external knowledge sources, such as databases or document repositories, to provide contextually accurate and up-to-date responses.
    
    - like an open-book exam for LLM’s
    - you query some external database for teh answers instead of relying on LLM
    - then, work those answers into the prompt for the LLM to work with or use tools and functions to incorporate the search into the LLM in a slightly more principled way
    
    **Pros & Cons**
    
    - faster & cheaper way to incorporate new or proprietary information into GenAI vs. finetuning
    - updating info is just a matter of updating the db
    - can leverage “semantic search” via vector stores (that use embeddings)
    - can prevent “hallucinations” when you ask the model about something it wasn’t trained on
    - Cons: you have made the world's most overcomplicated search engine. very sensitive to the prompt templates you use to incorporate your data,
    
    Use Cases of RAG:
    
    1. **Customer Support:** Assistants that retrieve product documentation or FAQs to provide detailed and accurate answers.
    2. **Legal Research:** Summarizing legal precedents or extracting information from case law repositories.
    3. **Healthcare:** Providing doctors with patient-specific recommendations by retrieving information from medical databases.
    4. **Education:** Answering student queries by pulling information from textbooks, notes, or online resources.
    5. **E-Commerce:** Generating product descriptions or answering customer inquiries using a knowledge base of product details.
    
    **Challenges of RAG:**
    
    1. **Retrieval Quality:** The system’s effectiveness depends heavily on the quality and relevance of the retrieved documents.
    2. **Latency:**Retrieving and processing external information can introduce delays.
    3. **Integration Complexity:** Requires careful integration of retrieval and generative modules.
    4. **Knowledge Maintenance:** External knowledge sources must be kept up-to-date to ensure reliability.
    
    **Choosing a database (Knowledge base data store) for rag:**
    
    - you could use whatever database is appropiate for the type of data you are retireving
        - graph database
        - open search or something for traditional text search
        - almost every example you find of RAG uses a Vector database:
            - Note Elasticsearch / OpenSearch can function as vector DB
            
    - Allows a Foundation Model to reference a data source outside of its training data
    - Bedrock takes care of creating Vector Embeddings in the database of your choice based on your data
    - Use where real-time data is needed to be fed into the Foundation Model
    
    ![image.png](Amazon%20Bedrock%20170d5f4e5b4f803f8fc9fd0ae57a6518/image%2013.png)
    
    ![image.png](Amazon%20Bedrock%20170d5f4e5b4f803f8fc9fd0ae57a6518/image%2014.png)
    
    ![image.png](Amazon%20Bedrock%20170d5f4e5b4f803f8fc9fd0ae57a6518/image%2015.png)
    
    ![image.png](Amazon%20Bedrock%20170d5f4e5b4f803f8fc9fd0ae57a6518/image%2016.png)
    
- **Rag in Bedrock: Knowledge Base**
    - you can upload your own documents or structured data (via S3, maybe with a JSON schema) into Bedrock “knowledge bases”
        - other sources: web crawler, Conflunce, Salesforce, Sharepoint
    - Must use an embedding model:
        - for which you must have obtained model access
        - currently Cohere or Amazon titan
        - ***you can control the vector dimension***
    - and a vector store of some sort:
        - for development, a serverless openSearch instance may be used by default
        - MemoryDB now has vector capabilities
        - or Aurora, MongoDb Atlas, Pinecone, Redis Enterprise Cloud
    - You can control the “chunking” of your data: how many tokens are represented by each vector
- **AWS Bedrock & CloudWatch**
    
    ![image.png](Amazon%20Bedrock%20170d5f4e5b4f803f8fc9fd0ae57a6518/image%2017.png)
    
- **Bedrock studio**
    - Creates a web app workspace for Bedrock without AWS accounts
    - Uses Single Sign On integration with IAM and your own Identity Provider (IDP)
    - Users can collaborate on projects and components
- **Bedrock flows**
    - Amazon Bedrock Flows is a **visual builder** designed to simplify the creation of AI workflows. It acts as an orchestrator for AI applications, enabling users to construct workflows ranging from simple chatbots to intricate business solutions.
    - Two notable new features include **guardrails for enhanced safety** and **traceability for debugging and performance optimization**.
    - **Highlights**
        
        •	🎛️ **Visual Workflow Creation**: Users can create workflows via a drag-and-drop interface with various nodes.
        
        •	🧠 **Node Types**: Includes prompt nodes for AI interactions, knowledge-based nodes for data retrieval, and condition nodes for decision-making.
        
        •	🛡️ **Guardrails**: Protect sensitive information like customer names and emails by masking it.
        
        •	🔍 **Traceability**: Allows debugging by showing input/output details and execution paths for every node.
        
        •	🏗️ **Generative AI Integration**: Works with large language models to categorize queries or provide professional responses.
        
    
    •	📂 **Knowledge Base Integration**: Enables retrieval of structured data (e.g., order details) for specific queries.
    
    •	🗂️ **Scenario Demonstration**: Showcases building a workflow to classify inputs as “company-specific” or “generic.”
    
    •	💡 **Customization**: Lets users define custom logic using Lambda functions and other AWS services.
    
    •	🌟 **Use Cases**: Ideal for building secure, scalable AI applications, especially in customer service.
    
    •	🚀 **Deployment**: Flows can be deployed via AWS Management Console or APIs for integration with AI pipelines.
    
    https://www.youtube.com/watch?v=h9cyC6eQnBo
    
- 🤑 **Bedrock cost-savings**
    - **On-Demand:** Great for unpredictable workloads with no long-term commitment.
    - **Batch:** Provides up to 50% discounts, ideal for non-urgent tasks.
    - **Provisioned Throughput:** Reserve capacity for predictable workloads and get discounts compared to on-demand pricing, Suitable for consistent, high-volume usage.
    - **Temperature, Top K, Top P:** Controls output randomness but has no impact on pricing.
    - **Model Size:** Smaller models are usually cheaper; costs vary by provider.
    - **Number of Input and Output Tokens:** ***Main driver of costs*;** optimizing token usage can reduce expenses.
- **CloudTrail Lake and Bedrock**
    
    Amazon **CloudTrail Lake** and **Amazon Bedrock** can be integrated to enhance **auditability**, **compliance**, and **security monitoring** in your generative AI workflows. By using CloudTrail Lake, you can capture, query, and analyze Amazon Bedrock activity logs, providing insights into the API calls made to foundational models, data access patterns, and more.
    
    CloudTrail Lake is managed data lake that allows users to srore and queryCloudtrail events using SQL-like query language. Customers can ingest CloudTrail events into CloudTrail Lake to analyze API activity, including user interactions with amazon bedrock
    
    CloudTrail Lake automatically captures API activity for AWS services, including Amazon Bedrock. Key events logged include:
    
    •	**InvokeModel**: Calls to foundational models like Anthropic, Stability AI, or Amazon Titan.
    
    •	**ListModels**: Requests to retrieve the list of available foundational models.
    
    •	**CreateModelCustomizationJob**: Custom model training or fine-tuning requests.
    
    •	**DeleteJob**: Actions to stop or delete running Bedrock jobs.
    
- **Chunking strategies**
    
    Amazon Bedrock allows users to interact with **foundation models (FMs)** for tasks like summarization, semantic search, and Q&A. Since foundation models have token limits, **chunking strategies** are critical to ensure efficient input processing while preserving context
    
    **Understanding Token Limits in Foundation Models**
    
    - **Token Limit Overview:**
        - Foundation models in Amazon Bedrock have a maximum number of tokens they can process in a single input.
        - Tokens include both words and punctuation marks (e.g., “hello” = 1 token; “hello, world!” = 3 tokens).
        - **Why Token Limits Matter:**
        - Exceeding the token limit results in errors or truncation of input.
        - Proper chunking ensures inputs are processed within these limits while maintaining coherence.
    
    **How Chunking Strategies Address Token Limits**
    
    **1. Fixed-Length Chunking**
    
    •	Divides text into fixed-sized chunks, usually based on the number of tokens.
    
    •	Ensures that each chunk fits within the model’s token limit.
    
    •	Simple to implement and process.
    
    •	May break sentences or paragraphs, potentially losing context.
    
    •	Best suited for embeddings or tasks where context across chunks is less critical.
    
    **2. Sentence-Based Chunking**
    
    •	Splits text at sentence boundaries to preserve natural language structure.
    
    •	Reduces the likelihood of breaking important context within sentences.
    
    •	Results in variable chunk sizes, which may need further alignment to token limits.
    
    •	Effective for tasks like summarization, Q&A, and machine translation.
    
    **3. Semantic Chunking**
    
    •	Groups sentences or paragraphs based on semantic similarity or related topics using foundation models.
    
    •	Creates meaningful chunks that retain logical coherence.
    
    •	Useful for tasks like summarization, semantic search, and topic-based analysis.
    
    •	Requires additional computation to analyze semantic relationships.
    
    **4. Sliding Window Chunking**
    
    •	Uses overlapping chunks to retain context across boundaries.
    
    •	Example: If one chunk spans tokens 1–500, the next chunk spans tokens 400–900.
    
    •	Helps preserve continuity between adjacent chunks.
    
    •	Effective for tasks requiring long-context retention, like summarization or Q&A.
    
    •	May increase redundancy and computational overhead.
    
    **Hierarchical Chunking**
    
    •	Splits input into smaller “child” chunks grouped under larger “parent” chunks.
    
    •	Maintains a multi-resolution structure, enabling broad context at higher levels and detailed focus at lower levels.
    
    •	Ideal for long-document processing and multi-level summaries.
    
    •	Suitable for tasks requiring both fine-grained and high-level insights (e.g., knowledge extraction or question answering).
    
    •	Requires careful structuring of parent-child relationships to avoid losing cross-level dependencies.
    
    **Lambda-Based Chunking**
    
    •	Custom chunking logic implemented via AWS Lambda functions.
    
    •	Fully customizable to meet specific domain or input requirements.
    
    •	Can integrate semantic, hierarchical, or any hybrid strategy.
    
    •	Useful for tasks requiring specialized input preprocessing (e.g., legal, financial, or scientific documents).
    
    •	Requires expertise to design and deploy the Lambda function.
    
    •	Allows maximum flexibility but may introduce latency if not optimized.
    
    **. Dynamic Chunking**
    
    •	Adjusts chunk sizes dynamically based on content type or task requirements.
    
    •	Can split text at logical sections (e.g., paragraphs, headings) rather than fixed sizes.
    
    •	Balances context preservation and adherence to token limits.
    
    •	Useful for documents with irregular structures, such as mixed media or highly variable content.
    
- **LLM Agents**
    - Manage and carry out ***various multi-step tasks*** related to infrastructure provisioning, application deployment, and operational activities
    - Task coordination: perform tasks in the correct order and ensure
    information is passed correctly between tasks
    - Agents are configured to perform specific pre-defined ***action groups (By using separate action groups, the LLM can be guided on when to use the knowledge base and when to call the API, making the system more flexible and maintainable.)***
        - prompt informs the FM when to use it e.g “use this function to determine the current weather in a city”
        - You must define the parameters your tool (Lambda function) expects:
            - define name, description, type and if its required or not
            - the description is actually important and will be used by LLM to extract the required info from the user prompt
            - you can also allow the FM to *go back and ask the user* for missing information it needs for a tool
            - This can be done using OpenAi-style schemas or visually with a table in Bedrock UI
    - Agents may also have **knowledge bases** associated with them
        - again, a prompt tells the LLM when it should use it e.g use this for answering a question about x
        - this is “agentic RAG” - RAG is just another tool
    - Optional ***“Code Interpreter”*** allows the agent to write its own code to answer questions or produce charts
    - Integrate with other systems, services, databases and APIs to exchange data or initiate actions
    - Leverage **RAG** to retrieve information when necessary
    
    ![image.png](Amazon%20Bedrock%20170d5f4e5b4f803f8fc9fd0ae57a6518/image%2018.png)
    
    ![image.png](Amazon%20Bedrock%20170d5f4e5b4f803f8fc9fd0ae57a6518/image%2019.png)
    
- **Deploying Bedrock agents**
    - create an “alias” for an agent: this creates a deployed snapshot
    - ***On-Demand throughput(ODT):***
        - Allows an agent to run at quotas set at the account level
    - ***Provisioned throughput (PT)***
        - allows you to purchase an increased rate and number of tokens for your agent
    - Your application can use **InvokeAgent** request using your alias ID and an **Agents** for **Amazon Bedrock Runtime Endpoint**
- **Other features**
    - imported models: import models from S3 or SageMaker
    - Model evaluation
        - Automatic: accuracy, toxicity, robustness, BERTScore, F1 etc
        - Test against your own prompts or built-in prompt datasets
        - Human: Bring your own team
        - Human: AWS-managed team
    - Provisioned throughput
    - Watermark detection: Detects if an image was generated by Titan

---

- **References**
    
    https://workshops.aws/categories/Amazon%20Bedrock
    
    https://www.youtube.com/watch?v=aEA6X_IElpc
    
    https://www.youtube.com/watch?v=vyppgNFzhvM
    
    https://www.youtube.com/watch?v=nSQrY-uPWLY
    
    [Amazon Bedrock Demo](https://aistylist.awsplayer.com/)
    
    https://www.youtube.com/watch?v=hnyDDfo8e9Q
    
    https://docs.aws.amazon.com/bedrock/latest/userguide/titan-multiemb-models.html