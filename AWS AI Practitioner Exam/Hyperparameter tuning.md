← [Back to AWS AI Practitioner Exam](../AWS%20AI%20Practitioner%20Exam.md)

# Hyperparameter tuning

<aside>
💡

Hyperparameters are external configuration variables that data scientists use to manage machine learning model training. Sometimes called *model hyperparameters*, the hyperparameters are manually set before training a model. They're different from parameters, which are internal parameters automatically derived during the learning process and not set by data scientists.

</aside>

- settings that define the model structure and learning algorithm
- set before training beings
- examples: learning rate, batch size, number of epochs and regularization

**Hyperparameter tuning:** 

- finding the best hyperparameters values to optimize the model performance
- improves model accuracy, reduces overfitting and enhance generalization

**How to do it?**

- **grid search:** With grid search, you specify a list of hyperparameters and a performance metric, and the algorithm works through all possible combinations to determine the best fit. Grid search works well, but it’s relatively tedious and computationally intensive, especially with large numbers of hyperparameters.
- **Bayesian optimization:** based on Bayes’ theorem, which describes the probability of an event occurring related to current knowledge. When this is applied to hyperparameter optimization, the algorithm builds a probabilistic model from a set of hyperparameters that optimizes a specific metric. It uses regression analysis to iteratively choose the best set of hyperparameters.
- **random search:** Although based on similar principles as grid search, random search selects groups of hyperparameters randomly on each iteration. It works well when a relatively small number of the hyperparameters primarily determine the model outcome.
- using services like ***SageMaker Automatic Model Tuning (ATM)***

- **Learning Rate**
    - How large or small the steps are when updating the model’s weights during training
    - How learning rate can lead to faster convergence but risks overshooting the optimal solution, while a low learning rate may result in more precise but slow convergence
- **Learning rate decay** is a gradual reduction in the learning rate over time to speed up learning

• *Momentum* is the direction of the next step with respect to the previous step

- *Momentum* is the direction of the next step with respect to the previous step
- *Neural network nodes* refers to the number of nodes in each hidden layer
- *Neural network layers* refers to the number of hidden layers in a neural network
- *Mini-batch size* is training data batch size
- • *Eta* is step size shrinkage to prevent overfitting

**Batch Size:**

- number of training examples used to update the model weights in one interation
- small bathes can lead to more stable learning but require more time to compute, while larger batches are faster but may lead to less stable updates

**Number of Epochs:**

- refer to how many times the model will iterate over the entire dataset
- too few epochs can lead to underfitting, while to many may cause overfitting

**Regularization**

- adjusting the balance between simple and complex model
- increase regularization to reduce overfitting

- **References**
    
    https://aws.amazon.com/what-is/hyperparameter-tuning/