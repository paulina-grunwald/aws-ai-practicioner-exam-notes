← [Back to AWS AI Practitioner Exam](../AWS%20AI%20Practitioner%20Exam.md)

# Amazon Q Buisness

- **General**
    - Fully managed Gen-AI assistant for your employees
    - Based on your *company’s knowledge and data*
        - Answer questions, provide summaries, generate content, automate tasks
        - Perform routine actions (e.g., submit time-off requests, send meeting invites)
    - Built on ***Amazon Bedrock*** (but you can’t choose the underlying FM)
    
    ![image.png](Amazon%20Q%20Buisness/image.png)
    
    - **Data Connectors** (fully managed RAG) – connects to 40+ popular enterprise data sources
        - Amazon S3, RDS, Aurora, WorkDocs…
        - Microsoft 365, Salesforce, GDrive, Gmail, Slack, Sharepoint…
    - **Plugins** – allows you to interact with 3rd party services
        - Jira, ServiceNow, Zendesk, Salesforce…
        - Custom Plugins – connects to any 3rd party application using APIs
    
    ![image.png](Amazon%20Q%20Buisness/image%201.png)
    
    - Users can be authenticated through **IAM Identity Center**
    - Users receive responses generated only from the documents they have access to
    - IAM Identity Center can be configured with external Identity Providers
        - IdP(external identity provider: Google Login, Microsoft Active Directory…
    
    ![image.png](Amazon%20Q%20Buisness/image%202.png)
    
- **Admin Controls**
    - Controls and customize responses to your organizational needs
    - Admin controls == Guardrails
    - Block specific words or topics
    - Respond only with internal information (vs using external knowledge)
    - Global controls & topic-level controls (more granular rules)
    
    ![image.png](Amazon%20Q%20Buisness/image%203.png)
    
- **Amazon Q Apps (Q Business)**
    - Create Gen AI-powered apps without coding by using natural language
    - Leverages your company’s internal data
    - Possibility to leverage plugins (Jira, etc…)
    
    https://aws.amazon.com/blogs/aws/amazon-q-business-now-generally-available-helps-boost-workforce-productivity-with-generative-ai/
    
- **Amazon Q Developer**
    - Answer questions about the AWS documentation and AWS service selection
    - Answer questions about resources in your AWS account
    - Suggest CLI (Command Line Interface) to run to make changes to your account
    - Helps you do bill analysis, resolve errors, troubleshoot…
    
    ![image.png](Amazon%20Q%20Buisness/image%204.png)
    
    ![image.png](Amazon%20Q%20Buisness/image%205.png)
    
    ![image.png](Amazon%20Q%20Buisness/image%206.png)
    
    - Integrates with IDE (Integrated Development Environment) to help with your software development needs
        - Answer questions about AWS development
        - Code completions and code generation
        - Scan your code for security vulnerabilities
        - Debugging, optimizations, improvements
    - A/B Testing:
        - In the context of Amazon Q Developer, the service team leverages A/B testing to evaluate the impact of new model variants on the developer experience. This helps in gathering real-world feedback from a subset of users before rolling out changes to the entire user base.
        1. **Control group:** Developers in the control group continue to receive the base Amazon Q Developer experience, serving as the benchmark against which changes are measured.
        2. **Treatment group:** Developers in the treatment group are exposed to the new model variant or feature, providing a contrasting experience to the control group.
    - Multi-Model Hosting
- **Amazon Q for Amazon QuickSight**
    - ask questions about your BI data within QuickSight
    - Generative BI capabilities to quickly build compelling visuals, summarize insights, answer data questions and build data stories using natural language
- **Amazon Q for Amazon Connect**
    - real time conversations with the customer along with relevant company content
- **Amazon Q for AWS Supply chain**
    - get intelligent answers about what is happening in their supply chain

- **References**
    
    https://aws.amazon.com/blogs/devops/how-a-b-testing-and-multi-model-hosting-accelerate-generative-ai-feature-development-in-amazon-q/