# Amazon Transcribe

- Automatically convert speech to text
- Uses a deep learning process called ***automatic speech recognition (ASR)*** to convert speech to text quickly and accurately
- Automatically remove Personally Identifiable Information (PII) using Redaction
- Supports Automatic Language Identification for ***multi-lingual*** audio
- Amazon Transcribe is a pay-as-you-go service; pricing is based on seconds of transcribed audio, billed on a monthly basis.
- Use cases:
    - transcribe customer service calls
    - automate closed captioning and subtitling
    - generate metadata for media assets to create a fully searchable archive

**Improving Accuracy**

- Allows transcribe to capture domain-specific or non-standard terms (e.g technical words, acronyms, jargon)
- ***Custom Vocabularies (for words)***
    - Add specific words, phases, domain-specific terms
    - Good for brad names, acronyms
    - Increase recognition of a new word by providing hints (such as pronunciation
- ***Custom Language Models (for context)***
    - Train transcribe model on your own domain-specific text data
    - You can supply Amazon Transcribe with up to 2 GB of text data to train your model—this is referred to as **training data.** Optionally, when you have no (or few) in-domain transcripts, you can provide Amazon Transcribe with up to 200 MB of text data to tune your model—this is referred to as **tuning data**.
    - Training vs. tuning:
        - The purpose of training data is to teach Amazon Transcribe to recognize new terms and learn the context in which these terms are used. In order to create a robust model, Amazon Transcribe may require a large volume of relevant text data. Providing as much training data as possible, up to the 2 GB limit, is strongly recommended.
            
            The purpose of tuning data is to help refine and optimize the contextual relationships learned from your training data. Tuning data are not required to create a custom language model.
            
        - If you choose to include both data types, do **not** overlap your training and tuning data; training and tuning data should be unique. Overlapping data can bias and skew your custom language model, impacting its accuracy.
    
    Note: use both for highest accuracy!
    

**Toxicity Detection**

- ML-powered, voice-based toxicity detection capability
- Leverages speech cues: tone and pitch and text-based cues
- Toxicity categories: sexual harassment, hate speech, threat, abuse, profanity, insult and graphic

 

**Amazon Transcribe Medical**

- Designed specifically for healthcare providers.
- Recognizes medical terminology with high accuracy.
- Example: Transcribing a doctor’s notes into text

References

https://docs.aws.amazon.com/transcribe/latest/dg/custom-language-models.html