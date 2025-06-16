← [Back to AWS AI Practitioner Exam](../AWS%20AI%20Practitioner%20Exam.md)

# Overfitting vs. underfiting

## **What is Overfitting?**

- undesirable [machine learning](https://aws.amazon.com/what-is/machine-learning/) behavior that occurs when the machine learning model gives accurate predictions for training data but not for new data.
- An overfit model can give inaccurate predictions and cannot perform well for all types of new data.

## **Why does overfitting occur?**

- Overfitting occurs when the model cannot generalize and fits too closely to the training dataset instead.
- Overfitting happens due to several reasons, such as:
    - The training data size is too small and does not contain enough data samples to accurately represent all possible input data values.
    - The training data contains large amounts of irrelevant information, called noisy data.
    - The model trains for too long on a single sample set of data.
    - The model complexity is high, so it learns the noise within the training data.

**Overfitting examples**

Consider a use case where a machine learning model has to analyze photos and identify the ones that contain dogs in them. If the machine learning model was trained on a data set that contained majority photos showing dogs outside in parks , it may may learn to use grass as a feature for classification, and may not recognize a dog inside a room.

Another overfitting example is a machine learning algorithm that predicts a university student's academic performance and graduation outcome by analyzing several factors like family income, past academic performance, and academic qualifications of parents. However, the test data only includes candidates from a specific gender or ethnic group. In this case, overfitting causes the algorithm's prediction accuracy to drop for candidates with gender or ethnicity outside of the test dataset.

## **How can you detect overfitting?**

The best method to detect overfit models is by testing the machine learning models on more data with with comprehensive representation of possible input data values and types. Typically, part of the training data is used as test data to check for overfitting. A high error rate in the testing data indicates overfitting. One method of testing for overfitting is given below.

**K-fold cross-validation**

Cross-validation is one of the testing methods used in practice. In this method, data scientists divide the training set into K equally sized subsets or sample sets called folds. The training process consists of a series of iterations. During each iteration, the steps are:

1.    Keep one subset as the validation data and train the machine learning model on the remaining K-1 subsets.

2.    Observe how the model performs on the validation sample.

3.    Score model performance based on output data quality.

Iterations repeat until you test the model on every sample set. You then average the scores across all iterations to get the final assessment of the predictive model.

## **How can you prevent overfitting?**

You can prevent overfitting by diversifying and scaling your training data set or using some other data science strategies, like those given below.

**Early stopping**

Early stopping pauses the training phase before the machine learning model learns the noise in the data. However, getting the timing right is important; else the model will still not give accurate results.

**Pruning**

You might identify several features or parameters that impact the final prediction when you build a model. Feature selection—or pruning—identifies the most important features within the training set and eliminates irrelevant ones. For example, to predict if an image is an animal or human, you can look at various input parameters like face shape, ear position, body structure, etc. You may prioritize face shape and ignore the shape of the eyes.

**Regularization**

Regularization is a collection of training/optimization techniques that seek to reduce overfitting. These methods try to eliminate those factors that do not impact the prediction outcomes by grading features based on importance. For example, mathematical calculations apply a penalty value to features with minimal impact. Consider a statistical model attempting to predict the housing prices of a city in 20 years. Regularization would give a lower penalty value to features like population growth and average annual income but a higher penalty value to the average annual temperature of the city.

**Ensembling**

Ensembling combines predictions from several separate machine learning algorithms. Some models are called weak learners because their results are often inaccurate. Ensemble methods combine all the weak learners to get more accurate results. They use multiple models to analyze sample data and pick the most accurate outcomes. The two main ensemble methods are bagging and boosting. Boosting trains different machine learning models one after another to get the final result, while bagging trains them in parallel.

**Data augmentation**

Data augmentation is a machine learning technique that changes the sample data slightly every time the model processes it. You can do this by changing the input data in small ways. When done in moderation, data augmentation makes the training sets appear unique to the model and prevents the model from learning their characteristics. For example, applying transformations such as translation, flipping, and rotation to input images.

## **What is underfitting?**

Underfitting is another type of error that occurs when the model cannot determine a meaningful relationship between the input and output data. You get underfit models if they have not trained for the appropriate length of time on a large number of data points.

**Underfitting vs. overfitting**

Underfit models experience high bias—they give inaccurate results for both the training data and test set. On the other hand, overfit models experience high variance—they give accurate results for the training set but not for the test set. More model training results in less bias but variance can increase. Data scientists aim to find the sweet spot between underfitting and overfitting when fitting a model. A well-fitted model can quickly establish the dominant trend for seen and unseen data sets.

## **How can AWS minimize overfitting errors in your machine learning models?**

You can use [Amazon SageMaker](https://aws.amazon.com/sagemaker/) to build, train, and deploy machine learning models for any use case with fully managed infrastructure, tools, and workflows. Amazon SageMaker has a built-in feature called [Amazon SageMaker Model Training](https://aws.amazon.com/sagemaker/train/) that automatically analyzes data generated during training, such as input, output, and transformations. As a result, it can detect and report overfitting and other inaccuracies without manual intervention.

For example, you can:

- Automatically stop the training process when the desired accuracy is achieved.
- Capture training metrics in real-time.
- Receive alerts when overfitting is detected.

Reduce the time and cost of training machine learning models.Get started with machine learning on AWS by [creating a free account](https://portal.aws.amazon.com/gp/aws/developer/registration/index.html) today!