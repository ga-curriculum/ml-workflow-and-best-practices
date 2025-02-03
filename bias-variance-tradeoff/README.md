<h1>
  <span class="headline">ML Workflow and Best Practices</span>
  <span class="subhead">Bias-Variance Tradeoff</span>
</h1>

**Learning objective:** By the end of this lesson, you will be able to describe:
- Bias in a machine learning model
- Variance in a machine learning model
- A machine learning model's performance using bias-variance tradeoff

## An Introduction to Bias-Variance Tradeoff
The bias-variance tradeoff is a fundamental concept in machine learning that describes the balance between underfitting and overfitting. It determines a model’s ability to generalize well to unseen data.

## Bias
Imagine we are learning to shoot at a target. If we aim without adjusting for the wind and distance, all our shots will land far from the target center. In ML terms, a model with high bias makes simplistic assumptions, resulting in poor performance on both training and test data.

Bias measures how much the model’s predictions differ from the true values due to incorrect assumptions.
High Bias leads to **underfitting (Model is oversimplified)**. Models with high bias: 
- Lead to poor performance on both training and test datasets.
- Do not capture complex patterns. 

For example, Linear Regression algorithms with few features on the dataset usually end up in a machine learning model with a high bias.

### How to Reduce Bias
- By using a more complex model (For example, using Decision Tree instead of Linear Regression).
- By increase the number of features.

## Variance
Again, lets imagine we are learning to shoot at a target. If we over-adjust every time we shoot, considering tiny variations in wind speed and hand movement, our shots will be spread all over the target. In ML terms, model with high variance memorizes the training data instead of learning general patterns, leading to poor test performance.

Variance measures how much the model’s predictions fluctuate for different training datasets. High Variance leads to **overfitting (model is too complex)**. Models with high variance: 
- Demonstrate high accuracy on training data but poor generalization on test data.
- Capture noise instead of meaningful patterns.

For example, Deep Neural Networks (DNN) with too many layers usually end up in a machine learning model with high variance.

### How to Reduce Variance
- Using a simpler model (For example, using Random Forest instead of Deep Neural Network).
- Reducing the number of features (Feature Selection).
- Increasing training data. 

## Bias-Variance Tradeoff
When trying to reduce the bias, we will inevitably increase the variance, and vice-versa. The goal is to find the "sweet spot" where there is a perfect balance between bias and variance to minimize total error and improve generalization.

A well-balanced model should have low bias and low variance to generalize well on unseen data. The tradeoff between bias and variance determines model performance on training and test datasets.

## Addressing the Tradeoff:
We can use **cross-validation** to assess performance on unseen data and prevent overfitting. (Please refer to the cross validation lesson)
