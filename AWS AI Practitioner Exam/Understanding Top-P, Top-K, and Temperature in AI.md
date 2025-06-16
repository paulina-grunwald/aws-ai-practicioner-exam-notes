← [Back to AWS AI Practitioner Exam](../AWS%20AI%20Practitioner%20Exam.md)

# Understanding Top-P, Top-K, and Temperature in AI Model Outputs

When working with **generative AI models** (like chatbots, text generation models, and large language models), we use different techniques to control how **random** or **predictable** the model’s output is. The three main parameters used for this are:

1.	**Temperature** 🥵🥶 – Controls randomness.

2.	**Top-K Sampling** 🎯 – Limits choices to the top K most probable words.

3.	**Top-P Sampling (Nucleus Sampling)** 🌊 – Limits choices to the top P percentage of cumulative probability.

**1. Temperature – Controls Randomness**

**What it does:**

•	**Higher temperature (e.g., 1.5 or 2.0)** makes the model more creative and unpredictable.

•	**Lower temperature (e.g., 0.2 or 0.3)** makes the model more deterministic and repetitive.

•	**Temperature of 1.0** is the default, meaning no extra randomness is applied.

💡 **Example:**

If we ask a language model:

👉 *“What’s the best way to start a morning?”*

•	**Temperature = 0.1 (Low, Very Predictable)**

•	“Drink a glass of water and go for a walk.”

•	**Temperature = 1.0 (Balanced)**

•	“Some people prefer coffee, others meditate, and a few jump straight into work.”

•	**Temperature = 2.0 (Very Creative & Random)**

•	“Start your day with a dance party, then invent a new breakfast recipe!”

**When to use it:**

•	Use **low temperature (0.1–0.3)** for **factual answers** (e.g., math problems, scientific facts).

•	Use **medium (0.5–1.0)** for **conversational responses**.

•	Use **high (1.5–2.0)** for **creative writing** (stories, poetry, jokes).