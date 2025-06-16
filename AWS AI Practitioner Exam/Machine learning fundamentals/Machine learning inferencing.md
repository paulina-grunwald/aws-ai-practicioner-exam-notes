← [Back to Machine Learning Fundamentals](../Machine%20learning%20fundamentals.md)

# Machine learning inferencing

- inferencing is when a model is making prediction on new data
- **RealTime**
    - Computer have to make decision quickly as data arrives
    - Speed is prefered over perfect accuracy
    - example: chatbots
- **Batch**
    - large amount of data that is analyzed all at once
    - often used for data analysis
    - speed of result is usually not a concern and accuracy is

**Inferencing at the Edge**

- Edge devices are usually devices with less computing power that are close to where the data is generated, in places where internet connections can be limited
- **Small Language Model (SLM)** on the edge device (e.g raspberry Pi)
    - very low latency
    - low compute footprint
    - offline capability, local inference
- **Large Language Model (LLM)** on remote server
    - More powerful model
    - higher latency
    - must be online to be access