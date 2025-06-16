← [Back to AWS AI Practitioner Exam](../AWS%20AI%20Practitioner%20Exam.md)

# Model Optimization Techniques

- **Pruning**
    - **technique** in machine learning aimed at optimizing a model by **removing unnecessary or less important components** (e.g., weights, neurons, or layers) without significantly impacting the model’s performance.
    - The primary goal is to make the model more **efficient** in terms of speed, memory, and computational cost.
- **Distillation**
    - it is a knowledge transfer technique where a smaller, more efficient “student” model is trained to replicate the behavior of a larger, more complex “teacher” model. The student model learns from the teacher’s output (soft target) in addition to original training data, allowing it to capture some of the knowledge and generalization capabilities of the largest model while being significantly smaller and faster
    - 
- Weight Sharing
- **Quantization**
    - reduces the recession of the model’s weights; it doesn’t create a new, smaller mocel
- **Fine-tuning**
    - Adapting a pre-trained model to a specific task by training on new data.
    - Customizing foundation models (e.g., GPT, BERT) for domain-specific tasks.
    - it doesn't inherently reduce model’s size in fact fine tuning can sometimes even slightly increase model size if additional parameters are introduced