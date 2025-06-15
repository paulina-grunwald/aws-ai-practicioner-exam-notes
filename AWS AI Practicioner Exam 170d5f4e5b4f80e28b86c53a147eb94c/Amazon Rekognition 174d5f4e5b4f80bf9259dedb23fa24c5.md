# Amazon Rekognition

- allows to find objects, people, scenes in images and videos using ML
- facial analysis and facial search to do user verification, people counting
- create database of “familiar faces” or compare against celebrities
- Use cases:
    - Labeling
    - Content Moderation
    - Text detection
    - Face detection and analysis
    - face search and verification
    - celebrity recognition
    - pathing (e.g sports game analysis)

**Custom Labels**

- Examples: find your logo in social media posts, identify your products on stores shelves (National Football League - NFL - uses it to find their logo in pictures
- label your training images and upload them to amazon rekognition
- only needs a few hundred images or less
- amazon rekognition creates a custom model on your images set
- new subsequent images will be categorized the custom way you have defined

**Content Moderation:**

- Automatically detects inappropiate. unwanted or offensive content
- Example: filter out harmful images in social media, broadcast media, advertising
- Bring down human review to 1-5% of total content volume
- integrated with amazon argumented AI for human review
- ***Custom Moderation Adaptors:***
    - extends Rekognition capabilities by providing your own **labeled** set of images
    - enhance the accuracy of content moderation or create a specific use case of moderation

- **Amazon Recognition Segment**
    - image recognition service that detects objects, scenes, and activities
    - detects changes of scene (or ‘shots’) within a video.
    - By leveraging this capability, we can precisely pinpoint all the scenes in our video, allowing us to process only relevant still frames. By feeding each still frame into the model, we create a caption for each scene.

- **References**
    
    https://aws.amazon.com/blogs/media/analyzing-and-tagging-video-for-optimal-ad-targeting-and-placement/
    
    https://aws.amazon.com/blogs/machine-learning/analyze-customer-reviews-using-amazon-bedrock/