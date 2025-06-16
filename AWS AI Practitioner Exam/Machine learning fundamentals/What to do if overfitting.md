← [Back to Machine Learning Fundamentals](../Machine%20learning%20fundamentals.md)

# What to do if overfitting?

- Overfitting is when the model gives good predictions for training data but not for the new data
- Why:
    - The training data size is too small and does not represent all possible input values
    - The model trains too long on a single sample set of data
    - Model complexity is high and learns from the “noise” within the training data
- How can you prevent overfitting?
- Increase the training data size
- Early stopping the training of the model
- Data augmentation (to increase diversity in the dataset)
- Adjust hyperparameters (but you can’t “add” them)