# Data masking and anonymization

**Data masking and anonymisation**

- dealing with PII or other sensitive data
- masking obfuscates data
    - for example masking all but the last 4 digits of a credit card or social security number
    - masking passwords
    - supported in **Glue DataBrew** and **Redshift**
    

**Anonymisation techniques**

- Replace with random
- shuffle
- encrypt (deterministic or probabilistic)
- hashing

<aside>
💡

AWS Glue DataBrew is a **visual data preparation tool** within the AWS Glue ecosystem that enables users to **clean, normalize, and transform data** without writing code. It offers over **250 pre-built transformations** to automate data preparation tasks, such as filtering anomalies, standardizing formats, and correcting invalid values. This approach can reduce the time required for data preparation by up to **80%** compared to traditional methods.  

</aside>