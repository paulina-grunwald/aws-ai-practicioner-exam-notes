# Random Notes

**Underfit models experience high bias, whereas, overfit models experience high variance**

Your model is underfitting the training data when the model performs poorly on the training data. This is because the model is unable to capture the relationship between the input examples (often called X) and the target values (often called Y). 

Your model is overfitting your training data when you see that the model performs well on the training data but does not perform well on the evaluation data. This is because the model is memorizing the data it has seen and is unable to generalize to unseen examples.

Underfit models experience high bias — they give inaccurate results for both the training data and test set. On the other hand, overfit models experience high variance - they give accurate results for the training set but not for the test set. More model training results in less bias but variance can increase. Data scientists aim to find the sweet spot between underfitting and overfitting when fitting a model. A well-fitted model can quickly establish the dominant trend for seen and unseen data sets.

---

**A multimodal model can accept a mix of input types such as audio/text and create a mix of output types such as video/image**

A multimodal model is an artificial intelligence system designed to process and understand multiple types of data, such as text, images, audio, and video. Unlike unimodal models, which handle a single type of data, multimodal models can integrate and make sense of information from various sources, allowing them to perform more complex and versatile tasks.

Multimodal models represent a significant advancement in AI, enabling the integration and understanding of multiple types of data. By combining different modalities, these models can perform a wide range of complex tasks, making them highly versatile and powerful tools in various fields.

---

**Self-supervised learning**

It works when models are provided vast amounts of raw, almost entirely, or completely unlabeled data and then generate the labels themselves.

Foundation models use self-supervised learning to create labels from input data. In self-supervised learning, models are provided vast amounts of raw completely unlabeled data and then the models generate the labels themselves. This means no one has instructed or trained the model with labeled training data sets.

---

**Gives the ability to use machine learning to generate predictions without the need to write any code**

Amazon SageMaker Canvas gives you the ability to use machine learning to generate predictions without needing to write any code. With Canvas, you can chat with popular large language models (LLMs), access Ready-to-use models, or build a custom model trained on your data.

Incorrect options:

**Provides one-click, end-to-end solutions for many common machine learning use cases** - Amazon SageMaker JumpStart supports this feature.

**Explains how input features contribute to the model predictions during model development and inference** - Amazon SageMaker Clarify supports this feature.

**The fastest and easiest way to prepare tabular and image data for machine learning** - Amazon SageMaker Data Wrangler supports this feature.

---

Large language models (LLM) are very large deep learning models that are pre-trained on vast amounts of data. The underlying transformer is a set of neural networks that consist of an encoder and a decoder with self-attention capabilities. The encoder and decoder extract meanings from a sequence of text and understand the relationships between words and phrases in it.

Large language models (LLMs) are one class of Foundation Models. For example, OpenAI's generative pre-trained transformer (GPT) models are LLMs. LLMs are specifically focused on language-based tasks such as such as summarization, text generation, classification, open-ended conversation, and information extraction.

AWS recommends AWS Bedrock and Amazon SageMaker JumpStart as the best-fit services for developing LLM based solutions.

**Amazon Bedrock**

Amazon Bedrock is the easiest way to build and scale generative AI applications with foundation models. Amazon Bedrock is a fully managed service that makes foundation models from Amazon and leading AI startups available through an API, so you can choose from various FMs to find the model that's best suited for your use case. With Bedrock, you can speed up developing and deploying scalable, reliable, and secure generative AI applications without managing infrastructure.

**Amazon SageMaker JumpStart**

Amazon SageMaker JumpStart is a machine learning hub with foundation models, built-in algorithms, and prebuilt ML solutions that you can deploy with just a few clicks. With SageMaker JumpStart, you can access pre-trained models, including foundation models, to perform tasks like article summarization and image generation. Pretrained models are fully customizable for your use case with your data, and you can easily deploy them into production with the user interface or SDK.

Incorrect options:

**Amazon Q** - Amazon Q is a generative AI–powered assistant for accelerating software development and leveraging companies' internal data. Amazon Q generates code, tests, and debugs. It has multistep planning and reasoning capabilities that can transform and implement new code generated from developer requests.

**AWS Trainium** - AWS Trainium is the machine learning (ML) chip that AWS purpose-built for deep learning (DL) training of 100B+ parameter models. Each Amazon Elastic Compute Cloud (Amazon EC2) Trn1 instance deploys up to 16 Trainium accelerators to deliver a high-performance, low-cost solution for DL training in the cloud.

**AWS Inferentia** - AWS Inferentia is an ML chip purpose-built by AWS to deliver high-performance inference at a low cost. AWS Inferentia accelerators are designed by AWS to deliver high performance at the lowest cost in Amazon EC2 for your deep learning (DL) and generative AI inference applications.

References:

---

[Hugging Face](https://huggingface.co/) introduced the [Parameter-Efficient Fine-Tuning library](https://huggingface.co/blog/peft) (PEFT). This library allows you to freeze most of the original model weights and replace or extend model layers by training an additional, much smaller, set of parameters. This makes training much less expensive in terms of required compute and memory.

---

**RMSE (Root Mean Square Error)** is a metric specifically designed for regression problems, where the goal is to predict a continuous numerical value. It measures the average magnitude of the errors between the predicted values and the actual values. In the context of classifying emails as spam or not spam, the output is categorical (spam or not spam), not a continuous numerical value. Therefore, RMSE is not a suitable metric for this type of classification problem**.** 

---

**ROUGE** is a widely adopted metric specifically designed for evaluating the quality of automatic summarization systems. It works by comparing the generated summary against one or more human-written reference summaries and calculating the overlap of n-grams (sequences of one or more words) between them. Higher ROUGE scores generally indicate a better match between the generated summary and the reference summaries, suggesting that the generated summary captures the essential information from the original text.

- Accuracy is typically used for classification tasks, where the goal is to predict a discrete label or category. It’s not directly applicable to summarization, where the output is a continuous piece of text.
- RMSE is a common metric for regression tasks, where the goal is to predict a numerical value. It’s not suitable for evaluating text summarization, which involves generating text, not predicting numbers.
- **BLEU** is primarily used for evaluating machine translation systems. While it also relies on n-gram overlap, it’s specifically designed for comparing translations to reference translations and might not be the most appropriate metric for summarization.

---

**To fine-tune the LLMs and improve their performance:** Human feedback can be used as a reward signal in techniques like Reinforcement Learning from Human Feedback (RLHF) to guide the model’s learning and improve its ability to generate responses that align with human preferences.

**To identify potential biases or inconsistencies in the models:** Human evaluation can help uncover biases or inconsistencies in the model’s outputs, allowing developers to address these issues and improve the model’s fairness and ethical behavior.

**To track changes in model performance over time:** By regularly collecting human feedback, you can monitor how the model’s performance evolves over time, identify potential degradation or drift, and take corrective actions if necessary.