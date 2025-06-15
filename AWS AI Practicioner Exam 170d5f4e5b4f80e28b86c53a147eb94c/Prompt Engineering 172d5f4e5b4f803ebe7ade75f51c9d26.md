# Prompt Engineering

**Prompt engineering** is designing and optimizing input prompts to guide the behavior of generative AI models, such as GPT, DALL·E, or Amazon Bedrock’s foundation models. It involves crafting input text or commands in a way that elicits the desired response from the model.

Improved Prompting technique consists of:

- ***Instructions*** – a task for the model to do (description, how the model should perform)
- ***Context*** – external information to guide the model
- ***Input data*** – the input for which you want a response
- ***Output Indicator*** – the output type or format

- **Negative Prompting**
    - A technique where you explicitly instruct the model on what not to include
    or do in its response
    - Negative Prompting helps to:
        - ***Avoid Unwanted Content*** – explicitly states what not to include, reducing the chances
        of irrelevant or inappropriate content
        - ***Maintain Focus*** – helps the model stay on topic and not stray into areas that are not
        useful or desired
        - ***Enhance Clarity*** – prevents the use of complex terminology or detailed data, making
        the output clearer and more accessible
        
        ![image.png](Prompt%20Engineering%20172d5f4e5b4f803ebe7ade75f51c9d26/image.png)
        

![image.png](Prompt%20Engineering%20172d5f4e5b4f803ebe7ade75f51c9d26/image%201.png)

![image.png](Prompt%20Engineering%20172d5f4e5b4f803ebe7ade75f51c9d26/image%202.png)

Temperature controls the randomness of the model’s output:

- **Low Temperature (e.g., 0.2):** Makes the model more deterministic and focused, leading to repetitive but precise outputs.
- **High Temperature (e.g., 0.8 or above):** Increases randomness, making the output more creative and varied but potentially less accurate.

- **Top P** – Use nucleus sampling. In nucleus sampling, Anthropic Claude computes the cumulative distribution over all the options for each subsequent token in decreasing probability and cuts it off after it reaches a particular probability specified by top P. You should alter either temperature or top P, but not both.
- **Top K** – Only sample from the top K options for each subsequent token. Use top K to remove long tail low probability responses.
- **Prompt Latency**
    - Latency is how fast the model responds
    - It’s impacted by a few parameters:
        - The model size
        - The model type itself (Llama has a different performance than Claude)
        - The number of tokens in the input (the bigger the slower)
        - The number of tokens in the output (the bigger the slower)
    - Latency is not impacted by Top P, Top K, Temperature
- **Zero-Shot Prompting**
    - Present a task to the model without providing examples or explicit training for that specific task
    - You fully rely on the model’s general knowledge
    - The larger and more capable the FM, the more likely you’ll get good results
- **PEFT - Parameter-Efficient Fine-Tuning**
    - PEFT is collection of methods to efficently adapt large pre-trained language models (LLMs) to specify tasks by fine-tuning only a small number of extra model parameters
    - instead of updating all parameters, PEFT introduces small modifications or additions to model. keeping most of the original parameters frozen
    - Popular PEFT techniques:
        - **Adapter layers**: intoduce small, task-specific layers within the existing model architecture
        - **Prefix-tuning:** prepend learnable prompt tokens to the input sequences, guiding the model’s behaviour without modifying its code parameters
        - **LoRA(Low-Rank Adaptation)** - Inject low-rank matrices into specific layers to efficently capture task-specific knwoledge
        - **BitFit:** Fine-tune only the bias terms of the model, offering a highly parameter-efficient approach
    - Benefits of PEFT:
        - reduces cost
        - mitigates overfitting
        - preservers general knowledge: helpts maintaing the mode’s performance on previously learned tasks
        - Faster adaptation: enables quicker adaptation to new tasks with fewer training examples
        - Efficient Deployment: facilitates deployment on resources-constrained devices like mobile phones and edge devices
- **Prompt P-tuning**
    - Prompt learning is a paradigm in natural language processing (NLP) that focuses on teaching language models to better understand and respond to instructions or prompts.
    - P-tuning is specific technique within prompt learning that aims to optimize the performance of pre-trained language models on various downstream tasks
    - it involves learning soft prompts (continuous embeddings) that can be prepended to input sequences effectively guiding the model’s behaviour.