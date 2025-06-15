# Hyperparameter tuning

**Hyperparameters vs. Parameters**

1. **Model Parameters:** Learned from the data during training. Example: Weights and biases in neural networks, coefficients in linear regression.

2.	**Hyperparameters:** Set manually before training and govern the learning process. Example: Learning rate, number of hidden layers, number of clusters in K-Means.

**Hyperparameters** are the external settings of a model that are not learned from the data but are set before training begins. These parameters significantly influence how a model learns and generalizes. *Examples*: learning rate, batch size, number of epochs, and regularization

**Hyperparameter tuning** is the process of optimizing the **hyperparameters** of a machine learning model to improve its performance. 

Hyperparameter tuning:
• Finding the best hyperparameters values to optimize the model performance
• Improves model accuracy, reduces overfitting, and enhances generalization

How to do it?

- Grid search, random search
- Using services such as ***SageMaker Automatic Model Tuning (AMT)***

| **Hyperparameter** | **Effect** |
| --- | --- |
| **Learning Rate** | Controls the step size during optimization. Small values lead to slow convergence, while large values may overshoot the minimum. 
- How large or small the steps are when updating the model's weights during training
- High learning rate can lead to faster convergence but risks overshooting the optimal solution, while a low learning rate may result in more precise but slower convergence |
| **Batch Size** | number of samples processed before model weights are updated. 
Smaller sizes lead to noisy updates, while larger sizes reduce variability but may miss finer patterns. |
| **Number of Epochs** | Defines how many times the entire dataset is passed through the model. Too few epochs can lead to underfitting, while too many may cause overfitting. |
| **Number of Hidden Layers** | Affects the depth of neural networks. More layers increase model complexity and capacity to learn complex patterns but may lead to overfitting. |
| **Number of Neurons per Layer** | Controls the number of units in each layer. More neurons allow the model to capture intricate patterns but increase computation cost and risk of overfitting. |
| **Dropout Rate** | Reduces overfitting by randomly disabling neurons during training. A high dropout rate may hinder learning, while a low rate may not effectively prevent overfitting. |
| **Regularization** | Adjusting the balance between simple and complex model. Penalize large weights to prevent overfitting. Common types: L1 (Lasso) and L2 (Ridge). |
| **Optimizer** | Determines how the model updates weights during training. Examples include SGD, Adam, and RMSProp. The choice impacts convergence speed and stability. |
| **Max Depth (Decision Trees)** | Limits the depth of trees in algorithms like Decision Trees and Random Forests to avoid overfitting. |
| **Number of Trees (Random Forest)** | Affects the robustness and diversity of the ensemble model. More trees improve performance but increase computation time. |
| **Learning Rate (Gradient Boosting)** | Controls the contribution of each tree in Gradient Boosted Machines. A smaller rate improves accuracy but requires more trees. |
| **Kernel Type (SVM)** | Specifies the transformation of data for support vector machines. Options include linear, polynomial, and RBF (Radial Basis Function). |
| k**(K-Nearest Neighbors)** | Determines the number of neighbors considered during classification or regression. Smaller values make the model more sensitive to noise, while larger values may oversimplify. |
| ε**(DBSCAN)** | Defines the maximum distance between points in a cluster. Smaller values result in finer clusters, while larger values may merge clusters. |
| **Momentum** | Accelerates convergence by considering past gradients in optimization algorithms like SGD. |

## **What are the hyperparameter tuning techniques?**

Numerous hyperparameter tuning algorithms exist, although the most commonly used types are Bayesian optimization, grid search and randomized search.

### Bayesian optimization

Bayesian optimization is a technique based on Bayes’ theorem, which describes the probability of an event occurring related to current knowledge. When this is applied to hyperparameter optimization, the algorithm builds a probabilistic model from a set of hyperparameters that optimizes a specific metric. It uses regression analysis to iteratively choose the best set of hyperparameters.

### Grid search

With grid search, you specify a list of hyperparameters and a performance metric, and the algorithm works through all possible combinations to determine the best fit. Grid search works well, but it’s relatively tedious and computationally intensive, especially with large numbers of hyperparameters.

### Random search

Although based on similar principles as grid search, random search selects groups of hyperparameters randomly on each iteration. It works well when a relatively small number of the hyperparameters primarily determine the model outcome.