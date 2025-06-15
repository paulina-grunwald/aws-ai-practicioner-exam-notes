# Supervised Learning

![image.png](Supervised%20Learning%20175d5f4e5b4f808db758f116793932ad/image.png)

**Classifications** 

![image.png](Supervised%20Learning%20175d5f4e5b4f808db758f116793932ad/image%201.png)

***Classification Algorithms:***

- Logistic Regression
- K-Nearest Neibhours
- Support Vector Machines
- Kernel SVM
- Naive Bays
- Decision Tree Clasification
- Random Forest Classification

**Linear Regression**

- Linear regression falls under supervised learning because it learns from labeled training data. The model is trained to minimize the difference between predicted and actual values by optimizing a cost function, typically the **Mean Squared Error (MSE)**

![image.png](Supervised%20Learning%20175d5f4e5b4f808db758f116793932ad/image%202.png)

- Linear regression is a fundamental algorithm in supervised learning. It is used primarily for regression tasks where the goal is to predict a continuous output variable based on one or more input features.
- Linear regression models the relationship between the input features (independent variables) and the target variable (dependent variable) by fitting a linear equation to the observed data. It assumes a linear relationship between the input and output.
- There are different regression algorithms that use the error to predict future variables:
    - *Mean squared error (MSE)*
    - *Root mean squared error (RMSE)*
    - *Mean absolute Error (MAE)*

### ***Decision tree***

- The decision tree supervised machine learning technique takes some given inputs and applies an *if-else structure to predict an outcome*. An example of a decision tree problem is predicting customer churn. e.g if a customer doesn’t visit an application after signing up, the model might predict churn. Or if the customer accesses the application on multiple devices and the average session time is above a given threshold, the model might predict retention.
- can handle non-liniary and interactions between features but may overfit if not pruned

### Support Vector Regression (SVR)

- effective for complex, high-dimensional data

### ***Neural network***

- A neural network solution is a more complex supervised learning technique. To produce a given outcome, it takes some given inputs and performs one or more layers of mathematical transformation based on adjusting data weightings. An example of a neural network technique is predicting a digit from a handwritten image.
- Can model high complex relationships but require large amounts of data and can be computationally expensive

---

Key Considerations for Regressions

•	**Outliers:** Extreme values can significantly impact model performance. Consider removing or transforming them.

•	**Overfitting vs. Underfitting:** Overfitting occurs when the model learns the noise in the training data too well, underfitting when it fails to capture the underlying pattern. Regularization techniques can help prevent overfitting.

•	**Feature Scaling:** Some algorithms require features to be on a similar scale to converge quickly.

•	**Model Selection and Tuning:** Choosing the right algorithm and its hyperparameters is an iterative process.

- A ***categorical label*** has a discrete set of possible values, such as "is a cat" and "is not a cat."
- A **continuous (regression) label** does not have a discrete set of possible values, which means possibly an unlimited number of possibilities.
- **Discrete**: A term taken from statistics referring to an outcome taking on only a finite number of values (such as days of the week).

In **supervised** learning, there are two main identifiers you will see in machine learning:

- A **categorical** label *has a* discrete *set of possible values. In a machine learning problem in which you want to identify the type of flower based on a picture, you would train your model using images that have been labeled with the categories of flower you would want to identify. Furthermore, when you work with categorical labels, you often carry out* classification tasks*, which are part of the supervised learning family.
- A **continuous** (regression) label *does not have a discrete set of possible values, which often means you are working with numerical data. In the snow cone sales example, we are trying to predict the* number* of snow cones sold.

![image.png](Supervised%20Learning%20175d5f4e5b4f808db758f116793932ad/image%203.png)