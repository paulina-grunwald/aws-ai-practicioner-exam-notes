← [Back to AWS AI Practitioner Exam](../AWS%20AI%20Practitioner%20Exam.md)

# Model Metric validation

https://docs.aws.amazon.com/sagemaker/latest/dg/autopilot-metrics-validation.html

https://docs.aws.amazon.com/sagemaker/latest/dg/canvas-metrics.html

**1. Classification Metrics**

| **Metric** | **Purpose** | **Formula/Example** | **AWS Tools** |
| --- | --- | --- | --- |
| **Accuracy** | Measures overall correctness of predictions. | `(TP + TN) / (TP + TN + FP + FN)` | SageMaker Model Monitor |
| **Precision** | % of positive predictions that are correct. | `TP / (TP + FP)` | SageMaker Clarify (bias analysis) |
| **Recall (Sensitivity)** | % of actual positives correctly identified. | `TP / (TP + FN)` | Amazon Comprehend (e.g., entity recognition) |
| **F1 Score** | Balances precision and recall (harmonic mean). | `2 * (Precision * Recall) / (Precision + Recall)` | SageMaker Autopilot (model tuning) |
| **AUC-ROC** | Measures model’s ability to distinguish classes (0.5=random, 1=perfect). | Area under the Receiver Operating Characteristic curve. | SageMaker Debugger (model performance analysis) |
|  |  |  |  |
- **Accuracy**
    - Accuracy measures the **overall correctness** of a model’s predictions. It answers: *"What percentage of all predictions did the model get right?"*
    - **Usage:** Commonly used in both binary and multiclass classification problems. However, in datasets with imbalanced classes, accuracy might be misleading. Always pair it with metrics like **F1, precision, or recall** for a complete picture.
    
    ![image.png](Model%20Metric%20validation/image.png)
    
- **Area under the Curve (AUC)**
    - AUC refers to the Area Under the Receiver Operating Characteristic (ROC) Curve. It evaluates the model’s ability to distinguish between classes by plotting the True Positive Rate (Recall) against the False Positive Rate at various threshold settings.
    - **Usage:** Primarily used for binary classification tasks, especially when dealing with ***imbalanced*** datasets. AUC provides insight into the model’s performance across all classification thresholds.
- Balanced Accuracy
    - **Definition:** Balanced Accuracy accounts for imbalanced datasets by averaging the recall obtained on each class.
    
    ![image.png](Model%20Metric%20validation/image%201.png)
    
    **Usage:** Useful in scenarios with imbalanced class distributions, ensuring that the model’s performance is fairly evaluated across all classes.
    
- **F1 Score**
    - A metric for evaluating **classification models** (e.g., spam detection, sentiment analysis).
    - Combines **precision** (accuracy of positive predictions) and **recall** (ability to find all positives) into a single score.
    
    ![image.png](Model%20Metric%20validation/image%202.png)
    
    **Use Cases**:
    
    - Imbalanced datasets (e.g., fraud detection, medical diagnosis).
    - When both false positives and false negatives are critical (e.g., safety-critical systems).
    - Ideal for binary classification problems, especially when there’s a need to balance between Precision and Recall.
    
    **Example**:
    
    - **Spam detection**:
        - Precision = % of emails flagged as spam that are actually spam.
        - Recall = % of actual spam emails correctly identified.
        - F1 balances these to avoid over-penalizing one error type.
    - **Amazon SageMaker** automatically calculates F1 for classification tasks.
    - Use **SageMaker Clarify** to evaluate F1 alongside bias metrics.
- **Precision**
    
    **Definition**:
    
    - *"How accurate are your positive predictions?"*
    - Measures the **quality** of your model’s positive guesses.
    
    **Formula**:
    
    ![image.png](Model%20Metric%20validation/image%203.png)
    
    **Example**:
    
    Imagine a **spam detection model**:
    
    - **True Positives (TP)**: 10 emails correctly labeled as spam.
    - **False Positives (FP)**: 5 emails were incorrectly labeled as spam (they were important).
    - **Precision**: 1010+5=0.6710+510​=0.67 or **67%**.
    
    **What it tells you**:
    
    - **High precision**: When your model says "positive," it’s usually right.
    - **Low precision**: Your model has too many false alarms.
    
    **When to prioritize precision**:
    
    - When **false positives are costly** (e.g., wrongly accusing someone of fraud, blocking legitimate emails).
- **Recall**
    - *"How many actual positives did you catch?" ⇒* Measures the **completeness** of your model’s positive predictions.
    
    **Formula**:
    
    ![image.png](Model%20Metric%20validation/image%204.png)
    
    **Example**:
    
    Same spam detection model:
    
    - **True Positives (TP)**: 10 emails correctly labeled as spam.
    - **False Negatives (FN)**: 15 spam emails missed by the model (they went to the inbox).
    - **Recall**: 1010+15=0.410+1510​=0.4 or **40%**.
    
    **What it tells you**:
    
    - **High recall**: Your model finds most of the actual positives.
    - **Low recall**: Your model misses too many actual positives.
    
    **When to prioritize recall**:
    
    - When **false negatives are dangerous** (e.g., missing cancer in a medical test, failing to detect fraud).

### **Visual Analogy**

Imagine fishing with a net:

- **Precision**: How many fish you caught are actually fish (not trash).
- **Recall**: How many fish in the lake you caught (vs. escaped).
- **F1 Score**: A balance between catching only fish (precision) and catching all fish (recall).

---

- **BERT Score**
    - A metric for evaluating **text generation tasks** (e.g., machine translation, summarization).
    - Uses contextual embeddings from **BERT** (a transformer model) to measure semantic similarity between generated text and reference text.
    
    **How it works**:
    
    1. Encodes candidate and reference texts into BERT embeddings.
    2. Computes cosine similarity between embeddings for each token.
    3. Aggregates similarities (precision, recall, F1 variants).
    
    **Advantages over BLEU/ROUGE**:
    
    - Captures **semantic meaning** (not just n-gram overlap).
    - Robust to paraphrasing and syntactic variations.
    
    **Use Cases**:
    
    - Evaluating chatbots, translation models, or summarization systems.
    - Testing LLM outputs for semantic accuracy.
    
    **Example**:
    
    - **Machine translation**:
        - Reference: "The cat sat on the mat."
        - Candidate: "A cat was sitting on the rug."
        - BERT Score rewards semantic equivalence despite word differences.
    
    **AWS Integration**:
    
    - Use **Hugging Face models on SageMaker** to compute BERT Score.
    - Custom evaluation scripts in SageMaker Processing Jobs.
- ROGUE
- BLEU

### **Exam Tips**

- Focus on **F1 vs. AUC-ROC**: F1 is for imbalanced classes; AUC-ROC measures overall class separation.
- **BERTScore vs. BLEU**: BERTScore captures semantics, while BLEU focuses on n-gram overlap.
- **Bias Metrics**: SageMaker Clarify is AWS’s go-to tool for fairness evaluations.
- **Toxicity/Hallucinations**: Critical for responsible AI (often tested in LLM use cases).