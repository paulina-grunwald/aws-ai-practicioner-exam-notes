# 📖 Glossary

- **Bias** - refers to systematic and unfair preferences or prejudices embedded in the machine learning model’s prediction or outputs
- **Embeddings** map words, phrases, or other data into **vectors** (numerical arrays) in a continuous space. The key purpose is to represent semantic meaning:
    - Words with similar meanings (e.g., "king" and "queen") are closer in the vector space.
    - Relationships like analogies (e.g., "man → woman ≈ king → queen") are preserved.
- **Overfitting** - occurs when the model performs well on training data but performs poorly on  unseen production data
    
    Overfitting happens due to several reasons, such as:
    
    - The training data size is too small and does not contain enough data samples to represent all possible input data values accurately.
    - The training data contains large amounts of irrelevant information, called noisy data.
    - The model trains for too long on a single sample set of data.
    - The model complexity is high, so it learns the noise within the training data.
- **Underfitting** - occurs when the model performs poorly on training data but on unseen or production data. This means the model is too basic or has not evolved properly.
- **Perplexity** - how skillful the model is in predicting the “probability” of generating the sequence of prompts or responses based on the input provided. Perplexity also means “how much confused the model to make predictions” and therefore this metric will say how much “probability” the model possesses to generate output or a sequence of words.
- **Stable diffusion is the** core function of forward diffusion. It's a process where Gaussian noise ( a type of random noise with a bell-shaped distribution) is gradually added to the original image over multiple steps. This creates a sequence of increasingly noisy images, culminating in an image that is almost pure noise.
- **AUC (Area under the ROC Curve)** is a powerful metric for evaluating classification models, especially when you need to understand the *trade-off between true positive rate (sensitivity) and false positive rate(1-speciality)*. The ROC curve plots the true positive rate against the false positive rate at various classification thresholds, and the AUC represents the overall area under the curve. A higher AUC indicates a better model that can effectively distinguish between the positive and negative classes across different thresholds.
    
     https://docs.aws.amazon.com/sagemaker/latest/dg/autopilot-metrics-validation.html#:~:text=AUC%20scores%20vary%20between%200,better%20than%20a%20random%20classifier.&text=BalancedAccuracy%20is%20a%20metric%20that,accurate%20predictions%20to%20all%20predictions
    
- **Data Lineage** - a detailed history of data within a machine learning project. It tracks the data’s origin, transformations (e.g. cleaning, feature engineering), and its journey through the ML pipeline. This tracking is essential for debugging issues, ensuring reproducibility, meeting auditing and compliance requirements, and gaining insights into model behavior.
- **Self Attention** - is at the heart of transformers architecture’s ability to understand context and relationships within a sequence of data (like words in a sentence). it does by computing attention weights for each token in relation to all other tokens. these weights essentially tell the model how much “focus” or “attention” to five to each token when processing another token. This allows the model to dynamically prioritize different parts of the input based on their contextual relevant to the current token being processed.
- **tokenizer -**  converts human-readable text into machine-readable format, specifically a vector of token Ids, which the model can then process further. (converts human-readable text into a vector of token IDs)
- **Prompt tuning -** is a technique used to optimize the input prompts given to large language models (LLMs) like GPT to improve their performance for specific tasks. Instead of fine-tuning the model’s weights (which requires extensive computational resources), **prompt tuning focuses on modifying the input text** to guide the model’s responses in a more desirable way.
- **chain of thought prompting**- is an approach to improving the performance of large language models on tasks that require reasoning and multi-step problem-solving. Instead of simply asking a model to provide a single-step answer, chain-of-thought prompting involves explicitly guiding the model through a logical sequence of intermediate steps, encouraging it to “think out loud” before arriving at a final response.
    
    *“What is the sum of 5 and 3?”*
    
    A chain-of-thought prompt, on the other hand, would encourage the model to break the problem down and reason step-by-step:
    
    *“If I have 5 apples and someone gives me 3 more, I start with 5, then add 3 to get a total of 8. So, the sum of 5 and 3 is 8.”*
    
    This stepwise reasoning allows the model to clarify its logic, reduce errors, and produce more accurate and interpretable results. The approach is especially useful for tasks that require multiple layers of reasoning or analysis.
    
- **PEFT - Parameter-Efficient FIne-Tuning** - Parameter-Efficient Fine-Tuning (PEFT) is an approach that **fine-tunes only a small subset of a large model’s parameters**, rather than modifying all the weights. This makes fine-tuning **more efficient, cost-effective, and scalable**, especially for large language models (LLMs) like GPT, BERT, and LLaMA.
    
    Fine-tuning large models is expensive and requires significant compute resources. PEFT **reduces memory and computation costs** while achieving performance close to full fine-tuning. It’s especially useful when:
    
    •	You have **limited GPU resources**.
    
    •	You want to fine-tune models for **multiple tasks efficiently**.
    
    •	The base model is **already good**, but you need **domain-specific improvements**.
    
- **prompt leaking** - attacks aim to extract the original prompt, which might include sensitive instructions, context, or even proprietary prompt engineering techniques
- **Prompt injection** occurs when someone deliberately inserts unauthorized or harmful instructions into a model’s input prompt to influence or manipulate the model’s behavior. Essentially, it’s a way of tricking the model into producing responses that it wasn’t intended to generate, bypassing built-in safeguards or policies.
    
    *Prompt injection* is about inserting malicious instructions to control the model’s output.
    
    *Prompt leaking* is about uncovering hidden instructions that aren’t supposed to be visible to users.
    
- **Data representativeness** - how well the training data captures the range of situations, features, and variations that the model will encounter when it’s applied in the real world. Essentially, it’s about ensuring that the dataset accurately reflects the diversity, complexity, and distribution of the actual problem space.
- ***Impute*** is a common term referring to different statistical tools which can be used to calculate missing values from your dataset.
- **Embeddings** - numerical representations of real-world object that ML and AI system use to understand complex knowledge domains like humans do. Embeddings convert real-world objects into complex mathematical representations that capture inherent properties and relationships between real-world data.
- **Word2Vec** - Word2Vec is a popular neural network-based technique for **learning word representations (embeddings)** from large text corpora. The algorithm aims to create vector representations (embeddings) for words in a way that words with similar meaning or that appear in similar context are located close to each other in the vector space. This allows the model to capture both semantic relationships (words with similar meaning) and syntatic relationships(words that tend to occur together in grammatical structures)

- References:
    
    https://aws.amazon.com/what-is/overfitting/