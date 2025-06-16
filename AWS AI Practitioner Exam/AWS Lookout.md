← [Back to AWS AI Practitioner Exam](../AWS%20AI%20Practitioner%20Exam.md)

# AWS Lookout

- ***identify unusual patterns*** or potential issues in various domains, such as manufacturing, equipment monitoring, business metrics, and vision-based data.
- uses ML to detect and diagnose anomalies
- identify unusual variances
    - business performance
    - ad campaigns etc.
- As stated above, Lookout for Metrics is a general purpose anomaly detection tool for time-series data. This means all problems that it can solve are going to start by relying on time-series data. To be more precise, if it is about understanding behavior over time, Lookout for Metrics can help, if it is about specific behavior events then Lookout for Metrics will not be helpful.
- **Detectors** monitor **datasets** to find **anomalies**
- the thing that you are optimizing is the **measure** (label), the features that influence it are **dimensions**
- specialized version for industrial use:
    - ***for equipment***: integrate with equipment sensors for predictive maintenance
    - ***for vision:*** automate quality inspection with computer vision

- **References**
    
    https://github.com/aws-samples/amazon-lookout-for-metrics-samples/blob/main/LookoutForMetricsInPlainEnglish.md