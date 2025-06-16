← [Back to AWS AI Practitioner Exam](../AWS%20AI%20Practitioner%20Exam.md)

# LLM (Large Language Model)

![image.png](LLM%20(Large%20Language%20Model)/image.png)

![image.png](LLM%20(Large%20Language%20Model)/image%201.png)

![image.png](LLM%20(Large%20Language%20Model)/image%202.png)

![image.png](LLM%20(Large%20Language%20Model)/image%203.png)

![image.png](LLM%20(Large%20Language%20Model)/image%204.png)

![image.png](LLM%20(Large%20Language%20Model)/image%205.png)

![image.png](LLM%20(Large%20Language%20Model)/image%206.png)

- Fine Tuning
    
    ![image.png](LLM%20(Large%20Language%20Model)/image%207.png)
    
    ### **1. Full Fine-Tuning**
    
    ### **What It Is**
    
    - **Definition**: Training the **entire pre-trained model** (all layers and parameters) on a custom dataset.
    - **Use Cases**:
        - When the downstream task is **significantly different** from the model’s original training data (e.g., medical text analysis using a general-purpose LLM).
        - When maximum performance is critical, and resources are available.
    
    ### **AWS Implementation**
    
    - **Services/Tools**:
        - **Amazon SageMaker**: Use `Training Jobs` with GPU instances (e.g., `ml.p3` or `ml.g5`).
        - **SageMaker JumpStart**: Pre-configured notebooks for fine-tuning open-source models (e.g., Llama 2, Mistral).
        - **Amazon S3**: Store training data and model artifacts.
    - **Steps**:
        1. Prepare a labeled dataset (e.g., CSV/JSON files).
        2. Configure hyperparameters (learning rate, batch size, epochs).
        3. Launch a SageMaker Training Job with the base model and dataset.
        4. Deploy the fine-tuned model to a SageMaker endpoint.
    
    ### **Pros & Cons**
    
    - ✅ **Pros**: Higher accuracy, better adaptation to complex tasks.
    - ❌ **Cons**:
        - Expensive (requires GPU instances for large models).
        - Time-consuming (training from scratch).
        - Risk of overfitting with small datasets.
    
    ### **Parameter-Efficient Fine-Tuning (PEFT)**
    
    ### **What It Is**
    
    - **Definition**: Updating **only a small subset of the model’s parameters** to adapt it to a new task.
    - **Common Techniques**:
        - **LoRA (Low-Rank Adaptation)**: Adds trainable low-rank matrices to model layers.
        - **Prompt Tuning**: Learns soft prompts (continuous vectors) to guide model behavior.
        - **Adapter Layers**: Inserts small neural networks between transformer layers.
    
    ### **AWS Implementation**
    
    - **Services/Tools**:
        - **SageMaker Hugging Face DLCs**: Use libraries like `peft` and `transformers` for LoRA or adapters.
        - **AWS Trainium/Inferentia**: Cost-effective chips for PEFT workloads.
    - **Steps**:
        1. Load a pre-trained model (e.g., from Hugging Face Hub).
        2. Apply PEFT methods (e.g., LoRA) to freeze most parameters.
        3. Train only the new parameters on the custom dataset.
        4. Merge the tuned parameters with the base model for inference.
    
    ### **Pros & Cons**
    
    - ✅ **Pros**:
        - **Cost-effective**: Uses fewer computational resources.
        - **Faster training**: Smaller parameter updates.
        - Avoids catastrophic forgetting (retains original model knowledge).
    - ❌ **Cons**:
        - May underperform on highly specialized tasks.
        - Limited flexibility compared to full fine-tuning.

https://aws.amazon.com/blogs/machine-learning/train-a-large-language-model-on-a-single-amazon-sagemaker-gpu-with-hugging-face-and-lora/