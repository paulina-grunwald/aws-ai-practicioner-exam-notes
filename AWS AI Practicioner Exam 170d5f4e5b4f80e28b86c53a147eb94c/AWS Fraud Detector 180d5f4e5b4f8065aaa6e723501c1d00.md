# AWS Fraud Detector

- fully managed fraud detection service that identify potential fraudulent online activities such as online payment fraud and the creation of fake accounts
- fully managed ML model customised to your data
    - automatic model creation
    - continuous learning over time
- insights into importance of your features (model variables)
- ingest data from **S3** or an **API**
- ***rule-based actions*** (you set up your own rules on what to do when fraud detector detects any issues)
- SageMaker integration

![image.png](AWS%20Fraud%20Detector%20180d5f4e5b4f8065aaa6e723501c1d00/image.png)

- Comes with following predefining models which you will train your data against:
    - **Online Fraud Insights** -optimized to detect fraud when little historical data is available about the entity being evaluated, for example w new customer is registering online for a new account
    - **Transaction Fraud Insights**
    - **Account Takeover Insights** - if account is compromised by physing on another type of attack
- using the aws SDK Fraud Detector ce be integrated with step functions, kinesis, lambda etc

![image.png](AWS%20Fraud%20Detector%20180d5f4e5b4f8065aaa6e723501c1d00/image%201.png)

![image.png](AWS%20Fraud%20Detector%20180d5f4e5b4f8065aaa6e723501c1d00/image%202.png)

![image.png](AWS%20Fraud%20Detector%20180d5f4e5b4f8065aaa6e723501c1d00/image%203.png)

- **Reference:**
    
    https://www.youtube.com/watch?v=OlTBXw8MIuU