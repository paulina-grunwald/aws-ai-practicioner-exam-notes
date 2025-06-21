← [Back to Machine Learning Fundamentals](../Machine%20learning%20fundamentals.md)

# Reinforcement Learning from Human Feedback (RLHF)

- use human feedback to help ML models to self-learn more efficienty
- in reinforcement learning there is a reward function
- RLHF incorporate human feedback in the reward function, to be more aligned with human goals, wants and needs:
    - first, the model’s response is compared to human responses
    - then, humans assess the quality of the model’s responses
- RLHF is used throughout GenAI applications including LLM Models
- RLHF significantly enhances the model performance

**How RLHF Works:**

1. ***Step 1: Pretraining***
- Train a base model using supervised learning on large datasets.
- Example: A language model pretrained to predict the next word in a sentence.
1. ***Step 2: Collect Human Feedback***
- Present multiple model-generated outputs for the same input to human annotators.
- Humans rank or compare outputs based on quality, relevance, safety, or other criteria.
1. ***Step 3: Train a Reward Model***
- Use the human feedback data to train a reward model that predicts which outputs align better with human preferences.

4.	***Step 4: Fine-Tune with RL***

- Apply reinforcement learning to fine-tune the base model using the reward model as the objective.
- The base model is adjusted to generate outputs that maximize the predicted reward.

**Applications of RLHF**

1. **Chatbots and Conversational AI:**
- Improve the quality, relevance, and safety of chatbot responses.
- Example: Fine-tuning ChatGPT to avoid harmful or biased responses and to provide more user-aligned answers.
1. **Content Moderation:** Train models to flag inappropriate or harmful content by aligning with human moderation guidelines.
2. **Creative Content Generation:** Fine-tune models for creative writing or artwork generation that aligns with specific human preferences. Example: Generating art or stories that match a particular style.
3. **Personalization:** Tailor recommendations (e.g., in search engines or streaming platforms) to individual or group preferences. Example: A movie recommendation system fine-tuned to prioritize family-friendly content for a household.
4. **Decision Support:** Align decision-making systems in healthcare or finance with ethical guidelines or human judgment. Example: AI-assisted diagnosis models that recommend treatments preferred by physicians.

How does it work? Example: internal company knowhow bot

- Data collection
- Supervised fine-tuning of language model
- Build a separate reward model
- optimize the language model with the reward-based model


https://aws.amazon.com/what-is/reinforcement-learning-from-human-feedback/
