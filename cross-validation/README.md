<h1>
  <span class="headline">ML Workflow and Best Practices</span>
  <span class="subhead">Cross Validation</span>
</h1>

**Learning objective:** By the end of this lesson, you will be able to describe cross validation technique and explain how it can improve a machine learning model's performance.


## An Introduction to Cross Validation 

**Cross-validation** is a systematic model evaluation approach used to assess how well a machine learning model generalizes to unseen data. Instead of splitting the dataset into just training and test sets, cross-validation resamples the dataset multiple times to provide a more reliable estimate of model performance. It ensures that every data point is used for both training and testing, improving the reliability of the performance evaluation.

### The Need for Cross Validation
A single train-test split may not be reliable because:
- Model performance depends on the split (different splits may give different results).
- Limited data means some important patterns might be left out.
- Avoid overfitting and underfitting by testing multiple splits.

Cross-validation helps by:
- Using data efficiently by training and testing on multiple subsets.
- Ensuring the model generalizes well to new data.

## Step-by-Step Process

1. **Divide the Data into Folds**:
   - The dataset is divided into `k` equal (or approximately equal) parts, known as **folds**.
   - The value of `k` (e.g., 5, 10) determines the number of splits. Each fold should represent the overall distribution of the dataset.

2. **Iterative Training and Testing**:
   - In each iteration, one fold is set aside as the **testing set**, and the remaining `k-1` folds are combined to form the **training set**.
   - For example, in a 5-fold cross-validation:
     - Fold 1 is used as the testing set, and Folds 2-5 are used as the training set.
     - Next, Fold 2 is used as the testing set, and Folds 1, 3-5 are used as the training set.
     - This process repeats until each fold has been used as the testing set once.

3. **Train and Test the Model**:
   - For each iteration, the model is trained on the training set and evaluated on the testing set.
   - Metrics such as accuracy, precision, recall, F1 score, or mean squared error (MSE) are calculated for each fold.

4. **Aggregate the Results**:
   - After completing all iterations, the performance metrics from each fold are averaged to provide an overall performance score.
   - The standard deviation of the metrics across folds may also be calculated to assess the consistency of the model.

### Example Illustration

For a 5-fold cross-validation, consider a dataset divided into 5 folds:

| Iteration | Training Folds       | Testing Fold |
|-----------|----------------------|--------------|
| 1         | Fold 2, 3, 4, 5      | Fold 1       |
| 2         | Fold 1, 3, 4, 5      | Fold 2       |
| 3         | Fold 1, 2, 4, 5      | Fold 3       |
| 4         | Fold 1, 2, 3, 5      | Fold 4       |
| 5         | Fold 1, 2, 3, 4      | Fold 5       |

Each fold serves as the testing set exactly once, and every data point in the dataset is included in a testing set once.

## Key Considerations

### Preserving Data Distribution:
For classification tasks, stratified cross-validation is often used to ensure the proportion of each class is consistent across all folds.
  
### Choosing the Number of Folds (`k`):
Common values of `k` are 5 and 10. A higher `k` results in more training data per fold but increases computational cost. For small datasets, a higher value of `k` or **Leave-One-Out Cross-Validation (LOOCV)** (where each data point is a fold) may be beneficial.

### Avoiding Data Leakage:
Ensure that no information from the testing set is used during training, especially for time series data or problems involving temporal relationships.

## Advantages of Cross-Validation

1. **Efficient Use of Data**: Each data point is used for both training and testing, maximizing data utility.
2. **Reliable Evaluation**: Provides a robust estimate of model performance by averaging results across multiple iterations.
3. **Model Selection**: Facilitates comparison between different models or configurations using consistent evaluation metrics.

By following this process, cross-validation helps to evaluate models thoroughly and ensures that the chosen model generalizes well to unseen data.