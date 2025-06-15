# Parameters/Assessment Types for Bias Evaluation

1. **Prompt Stereotyping** 
    - **Purpose**: Test if the model generates stereotypical or biased outputs when given prompts related to sensitive attributes (e.g., gender, age, ethnicity).
    - **Method**: Design prompts that intentionally probe for stereotypes (e.g., "Nurses are usually [gender/ethnicity]").
    - **AWS Tools**:
        - Use **Amazon SageMaker Clarify** to analyze model outputs for bias.
        - **Amazon Bedrock** includes safety evaluations for foundation models.
2. **Bias Metrics (Statistical Fairness)**
    - **Disparate Impact Ratio**: Measures disproportionate outcomes for protected groups.
    - **Demographic Parity**: Checks if predictions are independent of sensitive attributes.
    - **Equalized Odds**: Ensures similar true/false positive rates across groups.
    - **AWS Tool**: **Amazon SageMaker Clarify** calculates these metrics automatically.
3. **Counterfactual Testing**
    - **Purpose**: Test if changing sensitive attributes (e.g., gender in a prompt) leads to unfair differences in outputs.
    - **Example**: Compare outputs for "She is a CEO" vs. "He is a CEO".
4. **Toxicity Detection**
    - **Purpose**: Identify harmful or offensive language directed at specific groups.
    - **AWS Tool**: **Amazon Comprehend Toxicity Detection API**.
5. **Semantic Robustness**
    - **Purpose**: Ensure model outputs remain consistent and unbiased even with paraphrased or rephrased inputs.
    - **Example**: Test if "older people are bad at tech" vs. "seniors struggle with technology" triggers similar biases.
6. **Representation Analysis**
    - **Purpose**: Check if training data or outputs under/over-represent certain groups.
    - **AWS Tool**: **Amazon SageMaker Data Wrangler** for dataset analysis.
7. **Contextual Fairness**
    - **Purpose**: Evaluate if the model treats sensitive topics (e.g., religion, politics) neutrally.

### **AWS Services for Bias Mitigation**

- **Amazon SageMaker Clarify**: Detects bias in data/models and explains predictions.
- **AWS AI Service Cards**: Provide transparency on fairness for services like Amazon Lex.
- **Amazon Bedrock**: Evaluates foundation models for safety, including bias.