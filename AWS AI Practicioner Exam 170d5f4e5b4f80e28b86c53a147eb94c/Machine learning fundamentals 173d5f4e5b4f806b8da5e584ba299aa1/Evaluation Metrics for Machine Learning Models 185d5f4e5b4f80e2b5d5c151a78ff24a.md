# Evaluation Metrics for Machine Learning Models

**Classification Models:**

1. **Accuracy:** Proportion of correctly classified instances over the total instances.
2. **Precision:** Measures the proportion of true positives out of predicted positives.
3. **Recall (Sensitivity/True Positive Rate):** Measures the proportion of true positives out of actual positives.
4. **F1-Score:** Harmonic mean of precision and recall.
5. **ROC-AUC (Receiver Operating Characteristic – Area Under Curve):** Measures the trade-off between true positive rate and false positive rate.
6. **Logarithmic Loss (Log Loss):** Penalizes incorrect predictions based on their confidence level.
7. **Confusion Matrix:** Provides a matrix of True Positives, False Positives, True Negatives, and False Negatives.
8. **Specificity (True Negative Rate):** Measures the proportion of true negatives out of actual negatives.

**Regression Models:**

1. **Mean Absolute Error (MAE):** Average of absolute differences between predicted and actual values.
2. **Mean Squared Error (MSE):** Average of squared differences between predicted and actual values.
3. **Root Mean Squared Error (RMSE):** Square root of the MSE; gives errors in the same units as the output.
4. **R-squared (Coefficient of Determination):** Measures the proportion of variance in the dependent variable explained by the model.
5. **Mean Absolute Percentage Error (MAPE):** Measures the percentage error between actual and predicted values.

**Clustering Models:**

1.	**Silhouette Score**

•	Measures how similar a data point is to its own cluster compared to other clusters.

•	Ranges from -1 to 1; higher is better.

2.	**Calinski-Harabasz Index**

•	Ratio of between-cluster dispersion to within-cluster dispersion.

3.	**Davies-Bouldin Index**

•	Measures cluster compactness and separation; lower is better.

4.	**Dunn Index**

•	Ratio of minimum inter-cluster distance to maximum intra-cluster distance.

5.	**Adjusted Rand Index (ARI)**

•	Measures the similarity between two clustering results, corrected for chance.

**Natural Language Processing Models:**

1.	**BLEU (Bilingual Evaluation Understudy)**

•	Evaluates text generation or translation by comparing n-gram matches.

2.	**ROUGE (Recall-Oriented Understudy for Gisting Evaluation)**

•	Measures overlap between generated and reference text (used in summarization).

3.	**Perplexity**

•	Evaluates language models; lower perplexity indicates better predictive performance.

4.	**BERTScore**

•	Measures semantic similarity between generated and reference text using BERT embeddings.