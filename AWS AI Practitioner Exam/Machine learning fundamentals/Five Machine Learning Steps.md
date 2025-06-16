← [Back to Machine Learning Fundamentals](../Machine%20learning%20fundamentals.md)

# Five Machine Learning Steps

![image.png](Five%20Machine%20Learning%20Steps/image.png)

**Step One: Define the Problem**

**Step Two: Build a Dataset**

![image.png](Five%20Machine%20Learning%20Steps/image%201.png)

- ***Impute*** is a common term referring to different statistical tools which can be used to calculate missing values from your dataset.

**Step Three: Model Training**

- The model training algorithm iteratively updates a model's parameters to minimize some loss function.
- *Hyperparameters* are settings on the model which are not changed during training but can affect how quickly or how reliably the model trains, such as the number of clusters the model should identify.
- *Model parameters*: Model parameters are settings or configurations the training algorithm can update to change how the model behaves. Depending on the context, you’ll also hear other more specific terms used to describe model parameters such as *weights* and *biases*. Weights, which are values that change as the model learns, are more specific to neural networks.
- ***Loss function**:* A loss function is used to codify the model’s distance from this goal. For example, if you were trying to predict a number of snow cone sales based on the day’s weather, you would care about making predictions that are as accurate as possible. So you might define a loss function to be “the average distance between your model’s predicted number of snow cone sales and the correct number.” You can see in the snow cone example this is the difference between the two purple dots.

**Step Four: Model Evaluation**

**Log loss** seeks to calculate how *uncertain* your model is about the predictions it is generating.

**Model Accuracy** is the fraction of predictions a model gets right.

**Step Five: Model Inference**

Once you have trained your model, have evaluated its effectiveness, and are satisfied with the results, you're ready to *generate predictions* on real-world problems using unseen data in the field. In machine learning, this process is often called **inference**.