# EC2 hardware for AI

- GPU-based Intances (P3,P4,P5,…G3,…G6)
- **AWS Titanium**:
    - Custom-designed chip for **ML model training**.
    - ML chip built to perform Deep Learning on 100B+ parameter models
    - Trn I instance has for example 16 Trainium Accelerators
    - 50% cost reduction when training model
- **AWS Inferentia**
    - Custom-designed chip for **ML inference**.
    - ML chip built to deliver inference at high performance and low cost
    - Infl, inf2 instances are powered by AWS Inferentia
    - Up to 4x throughput and 70% cost reduction

<aside>
💡

- Trn&Inf have the lowest environmental footprint
</aside>

What is the role of Amazon titan multimodal embeddings?

**Amazon Titan Multimodal Embeddings** is a feature provided by AWS within the context of **foundation models**. Its primary purpose is to generate **numerical embeddings** (vector representations) for **text** and **images** in a shared space, enabling tasks that require understanding and comparing information across multiple modalities (e.g., text-to-image or image-to-text scenarios).