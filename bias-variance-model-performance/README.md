<h1>
  <span class="headline">ML Workflow and Best Practices</span>
  <span class="subhead">Train-Test Splitting</span>
</h1>

Bias-Variance & Model Performance
=================================

Learning Objectives
-------------------

By the end of this lesson, you will be able to:

-   Understand the bias-variance tradeoff and its impact on model performance.
-   Identify overfitting and underfitting in machine learning models.
-   Apply regularization techniques to improve generalization.
-   Use performance metrics to evaluate model effectiveness.

Overview
---------------

A well-performing machine learning model strikes a balance between **bias** (error from overly simplistic assumptions) and **variance** (error from excessive sensitivity to training data). This lesson explores how to diagnose and manage these issues.

**1\. Understanding the Bias-Variance Tradeoff**
------------------------------------------------

Bias and variance are two key sources of error in machine learning models:

-   **High Bias (Underfitting):** Model is too simple, failing to capture patterns in the data.
-   **High Variance (Overfitting):** Model learns noise instead of underlying patterns, performing well on training data but poorly on new data.
-   **Optimal Tradeoff:** Achieved when the model generalizes well without overfitting.

<div class="mermaid">
graph LR;
    A[Total Error] -->|Bias Component| B[Underfitting];
    A -->|Variance Component| C[Overfitting];
    B -->|Increase Complexity| D[Optimal Model];
    C -->|Reduce Complexity| D;
</div>

**2\. Identifying Overfitting and Underfitting**
------------------------------------------------

### **Symptoms:**

| Condition | Training Error | Test Error | Model Complexity |
| --- | --- | --- | --- |
| **Underfitting** | High | High | Too simple |
| **Overfitting** | Low | High | Too complex |
| **Optimal Model** | Low | Low | Balanced complexity |

### **Visualization of Bias-Variance Tradeoff**

<div class="mermaid">
graph TD;
    A[High Bias] -->|Increase Model Complexity| B[Balanced Model];
    B -->|Increase Further| C[High Variance];
</div>

**3\. Regularization Techniques**
---------------------------------

Regularization helps control model complexity and prevents overfitting:

-   **L1 Regularization (Lasso):** Shrinks some feature coefficients to zero, performing feature selection.
-   **L2 Regularization (Ridge):** Penalizes large coefficients, encouraging smaller, more generalizable weights.
-   **Dropout (Neural Networks):** Randomly drops neurons during training to prevent dependency on specific patterns.

**Example Code: Ridge vs. Lasso Regression**

```
from sklearn.linear_model import Ridge, Lasso
from sklearn.model_selection import train_test_split
from sklearn.metrics import mean_squared_error
from sklearn.datasets import load_diabetes
import pandas as pd

# Load dataset
data = load_diabetes()
df = pd.DataFrame(data.data, columns=data.feature_names)
X_train, X_test, y_train, y_test = train_test_split(df, data.target, test_size=0.2, random_state=42)

# Apply Ridge and Lasso Regression
ridge = Ridge(alpha=1.0).fit(X_train, y_train)
lasso = Lasso(alpha=0.1).fit(X_train, y_train)

# Evaluate models
ridge_pred = ridge.predict(X_test)
lasso_pred = lasso.predict(X_test)
print("Ridge MSE:", mean_squared_error(y_test, ridge_pred))
print("Lasso MSE:", mean_squared_error(y_test, lasso_pred))

```

**4\. Evaluating Model Performance**
------------------------------------

Model evaluation metrics help assess generalization:

| Regression Metrics | Classification Metrics |
| --- | --- |
| Mean Squared Error (MSE) |Accuracy
Root Mean Squared Error (RMSE) |Precision Recall
R² Score | F1 Score


```
from sklearn.metrics import accuracy_score, precision_score, recall_score, f1_score

# Example: Evaluating a classification model
true_labels = [1, 0, 1, 1, 0, 1, 0, 0, 1, 0]
pred_labels = [1, 0, 1, 0, 0, 1, 0, 1, 1, 0]

print("Accuracy:", accuracy_score(true_labels, pred_labels))
print("Precision:", precision_score(true_labels, pred_labels))
print("Recall:", recall_score(true_labels, pred_labels))
print("F1 Score:", f1_score(true_labels, pred_labels))

```

**Interactive Exercise: Diagnosing Model Performance** 
---------------------------------------------------------------

**Task:** Train a simple model and test different regularization strengths to observe how bias and variance change.

-   Adjust `alpha` values in Ridge/Lasso and record test performance.
-   Discuss how different levels of regularization impact bias-variance tradeoff.

**Discussion: Applying Bias-Variance Concepts in Real Projects** 
------------------------------------------------------------------------

In real-world ML applications:

-   When is overfitting more problematic than underfitting?
-   What trade-offs exist between interpretability and generalization?
-   Can you think of a time where overfitting or underfitting was relevant when working with a client?

**Key Takeaways**
-----------------

-   **Bias-variance tradeoff** is crucial for optimizing model performance.
-   **Regularization techniques** help control model complexity.
-   **Evaluation metrics** provide insights into model effectiveness.
-   **Choosing the right balance** ensures models generalize well without overfitting or underfitting.