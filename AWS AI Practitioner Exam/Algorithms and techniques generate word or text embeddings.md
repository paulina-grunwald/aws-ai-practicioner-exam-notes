← [Back to AWS AI Practitioner Exam](../AWS%20AI%20Practitioner%20Exam.md)

# Algorithms and techniques generate word or text embedding

### **1. GloVe (Global Vectors for Word Representation)**

- **Purpose**: Creates embeddings by analyzing **global word co-occurrence statistics** across a corpus.
- **Key Features**:
    - Combines the benefits of Word2Vec (local context) and matrix factorization (global statistics).
    - Example: "ice" and "steam" are related but distinct, captured via co-occurrence with words like "solid" or "gas".
- **AWS Use Case**:
    - Used in Amazon SageMaker's built-in algorithms for topic modeling or recommendation systems.

---

### **2. FastText**

- **Purpose**: Extends Word2Vec by incorporating **subword information** (character n-grams).
- **Key Features**:
    - Handles rare or misspelled words (e.g., "running" ≈ "runnin" + "ing").
    - Effective for morphologically rich languages (e.g., Turkish, Finnish).
- **AWS Use Case**:
    - Deployed in SageMaker for text classification in multilingual applications.

---

### **3. BERT (Bidirectional Encoder Representations from Transformers)**

- **Purpose**: Generates **contextual embeddings** using transformer architecture.
- **Key Features**:
    - Captures word meaning based on **entire sentence context** (e.g., "bank" in "river bank" vs. "bank account").
    - Pre-trained on masked language modeling and next-sentence prediction.
- **AWS Use Case**:
    - Integrated into **Amazon Comprehend** for entity recognition, sentiment analysis, and custom model training.

---

### **4. ELMo (Embeddings from Language Models)**

- **Purpose**: Produces **context-aware embeddings** using deep bidirectional LSTMs.
- **Key Features**:
    - Generates different embeddings for the same word in different contexts.
    - Example: "play" in "play music" vs. "play football" has distinct vectors.
- **AWS Use Case**:
    - Used in legacy NLP pipelines but largely replaced by BERT/transformers in modern AWS workflows.

---

### **5. Doc2Vec (Paragraph Vectors)**

- **Purpose**: Extends Word2Vec to **embed entire documents or paragraphs**.
- **Key Features**:
    - Represents text chunks (e.g., product reviews, articles) as vectors for similarity comparisons.
- **AWS Use Case**:
    - Powers document clustering or recommendation systems in SageMaker.

---

### **6. Transformer-Based Models (GPT, RoBERTa, T5)**

- **Purpose**: State-of-the-art models for **contextual understanding** and generative tasks.
- **Key Features**:
    - Use self-attention mechanisms to weigh word relationships dynamically.
    - Pre-trained on massive datasets and fine-tuned for specific tasks.
- **AWS Use Case**:
    - Available via **Amazon SageMaker JumpStart** (Hugging Face models) or **AWS Bedrock** (proprietary models like Titan).

---

### **Comparison Table**

| **Algorithm** | **Embedding Type** | **Strengths** | **Weaknesses** |
| --- | --- | --- | --- |
| Word2Vec | Static (word-level) | Fast, efficient for semantic analogies | Ignores context, struggles with OOV |
| GloVe | Static (word-level) | Captures global co-occurrence patterns | Less effective for rare words |
| FastText | Static (subword-level) | Handles OOV and morphology | Larger model size |
| BERT/ELMo | Contextual (sentence) | Context-aware, SOTA performance | Computationally heavy |
| Doc2Vec | Static (document-level) | Represents entire documents | Less nuanced than transformers |

---

### **AWS-Specific Insights**

- **SageMaker Built-in Algorithms**: Supports Word2Vec, GloVe, and FastText for custom embeddings.
- **Pre-trained Models**: Use **JumpStart** for BERT, RoBERTa, or GPT-2 fine-tuning.
- **Managed Services**: **Amazon Comprehend** uses BERT-like models under the hood for NLP tasks.

---

### **Exam Focus Areas**

- **When to Use Which Algorithm**:
    - **Word2Vec/FastText**: Simple semantic tasks (e.g., product recommendations).
    - **BERT/Transformers**: Context-dependent tasks (e.g., chatbots, sentiment analysis).
- **Cost vs. Performance**: BERT requires more resources but offers higher accuracy.