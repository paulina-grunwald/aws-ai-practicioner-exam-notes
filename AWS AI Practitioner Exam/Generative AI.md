← [Back to AWS AI Practitioner Exam](../AWS%20AI%20Practitioner%20Exam.md)

# Generative AI

- **What is Generative AI?**
    
    ![image.png](Generative%20AI/image.png)
    
    ![image.png](Generative%20AI/image%201.png)
    
    - Gen-AI is a subset of Deep Learning
    - **Generative AI** refers to a category of artificial intelligence (AI) systems designed to generate new, original content such as text, images, audio, video, or even code. These systems leverage machine learning models, particularly deep learning, to produce outputs that mimic human-like creativity and intelligence.
    - Models are trained on large datasets, such as text corpora, image libraries, or audio recordings.
    - used to generate new data that is similar to data it was trained on.
- **Foundation Model**
    
    ![image.png](Generative%20AI/image%202.png)
    
    - To generate data, we must rely on a Foundation Model
    - Foundation Models are trained on a wide variety of input data
    - The models may cost tens of millions of dollars to train Example: GPT-4o is the foundation model behind ChatGPT
    - There is a wide selection of Foundation Models from companies:
        - OpenAI
        - Meta (Facebook)
        - Amazon
        - Google
        - Anthropic
    - Some foundation models are open-source (free: Meta, Google BERT) and others under a commercial license (OpenAI, Anthropic, etc…)
    - **Transfer Learning:** Fine-tuned with smaller, domain-specific datasets for specialized tasks.
- **FM lifecycle**
    
    The foundation model lifecycle is a comprehensive process that involves several stages, each playing a crucial role in developing and deploying effective and reliable foundation models.
    
    1. **Data selection**
        
        Unlabeled data can be used at scale for pre-training because it is much easier to obtain compared to labeled data. Unlabeled data includes raw data, such as images, text files, or videos, with no meaningful informative labels to provide context. FMs require training on massive datasets from diverse sources.
        
    2.  **Pre-training**
        
        Although traditional ML models rely on supervised, unsupervised, or reinforcement learning patterns, FMs are typically pre-trained through self-supervised learning. With self-supervised learning, labeled examples are not required. Self-supervised learning makes use of the structure within the data to autogenerate labels.
        
        During the initial pre-training stage, the FM's algorithm can learn the meaning, context, and relationship of the words in the datasets. For example, the model might learn whether drink means beverage, the noun, or swallowing the liquid, the verb.
        
        After the initial pre-training, the model can be further pre-trained on additional data. This is known as continuous pre-training. The goal is to expand the model's knowledge base and improve its ability to understand and generalize across different domains or tasks.
        
- **Large Language Models (LLM)**
    - Type of AI designed to generate coherent human-like text
    - One notable example: GPT-4 (ChatGPT / Open AI)
    - Trained on a large corpus of text data
    - Usually a very big models
        - Billions of parameters
        - Trained in books, articles, websites, and other textual data
    - Can perform language-related tasks
        - Translation, Summarization
        - Question answering
        - Content creation
    
    <aside>
    🔥
    
    The output of LLM is **non-deterministic** (generated text may be different for every user that uses the same prompt)
    
    </aside>