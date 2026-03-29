---
layout: post
title: ML Basics Review
date: 2024-05-12
description: Supervised and unsupervised learning, bias-variance tradeoff, regularization (L1/L2/Elastic Net), regression and classification metrics, SVM, and logistic regression.
tags: fundamentals
categories:
giscus_comments: false
related_posts: false
---

## Supervised Learning
Supervised learning consists of input values (independent variables) and target/output values (dependent variables) with the goal of creating function for mapping the input values to the output values accurately. It is called "supervised" learning because the model is provided with correct training, allowing it to make predictions/classifications on unseen data.

## Unsupervised Learning
Unsupervised learning consists of just input data with no output/target data. The goal of unsupervised learning is to find relationship/characteristics/patterns among the input data. Algorithms for unsupervised learning aim to cluster together similar data or find patterns that indicate the hidden characteristic of the data. Because there are no correct outputs provided for training, the algorithm explores the data with no prior knowledge.

## Reinforcement Learning
Reinforcement learning deals with an agent interacting with an environment to maximize its cumulative reward/minimize the penalty. The agent learns by taking actions in an environment and receiving feedback in the form of rewards or penalties. The goal is to learn the optimal policy - a set of actions that maximize the cumulative reward over time.

## Steps in ML Pipeline
Here are the following steps for creating a machine learning pipeline:
1. Data Collection
2. Data Preprocessing - Data balancing to prevent bias, data normalization, cleaning up missing values...
3. Feature Engineering - Transforming raw data into useful features
4. Data Splitting - Split the new data into train/valid/test data
5. Model Selection - Choose the optimal model depending on specific use cases
6. Model Training - Train the model where it learns the patterns and relationships
7. Model Evaluation - Model is evaluated on performance and generalization ability
8. Model Optimization - Hyperparameter tuning, new feature creation, different regularization methods
9. Model Deployment
10. Model Maintenance

## Generative Models
Generative models aim to model the probability distribution of the input data. They learn the joint probability distribution between features and output labels (if available).

$$
P(X, Y) = P(Y) * P(X|Y)
$$

where $$P(Y)$$ represents prior probability of $$Y$$ and $$P(X|Y)$$ represents the conditional probability of $$X$$ given $$Y$$. Generative models learn both $$P(Y)$$ and $$P(X|Y)$$.

## Discriminative Models
Discriminative models aims to learn the decision boundaries that separate different classes or categories. They learn the conditional probability of the output labels given the input features $$P(Y|X)$$.

## Bias vs. Variance
- **Bias Error:** A model with high bias tends to oversimplify the underlying patterns in the data and make strong assumptions. This results in underfitting.
- **Variance Error:** High variance refers to the instability of the model's predictions caused by small changes in the training data. A model with high variance is overly complex and sensitive to noise.

As bias is decreased (model is more complex), variance tends to increase, and vice versa.

## Regularization
Regularization helps prevent overfitting by adding a regularization term to the loss function:

$$
J_{reg} = J + \alpha * R(w)
$$

### L1 Regularization (Lasso)
Adds the sum of the absolute values of the model weights as a penalty term. Encourages sparsity (can drive some parameters to zero):

$$
R(w) = ||w||_1 = |w_1| + |w_2| + ... + |w_n|
$$

### L2 Regularization (Ridge)
Adds the sum of the squared values of the model's parameters as a penalty term. Promotes smaller parameter values:

$$
R(w) = ||w||_2^2 = w_1^2 + w_2^2 + ... + w_n^2
$$

### L1 vs. L2
- **L1** encourages sparsity, pushing some parameters to zero. Acts as feature selection.
- **L2** penalizes larger parameter values but does not push them to zero. Distributes weight values more evenly.

### Elastic Net Regularization
Combination of L1 and L2:

$$
J_{reg} = J + \alpha * \{\lambda * L1(w) + (1 - \lambda) * L2(w)\}
$$

## Regression Models
The goal of regression is to predict a continuous, numerical value.

- **MSE:** $$MSE = \frac{1}{n}\sum_{i=1}^{n}(y_i - \hat{y}_i)^2$$
- **RMSE:** $$RMSE = \sqrt{\frac{1}{n}\sum_{i=1}^{n}(y_i - \hat{y}_i)^2}$$
- **MAE:** $$MAE = \frac{1}{n}\sum_{i=1}^{n}|y_i - \hat{y}_i|$$
- **R-Squared:**

$$
\begin{gathered}
R^2 = 1 - \frac{\sum_{i=1}^{n}(y_i - \hat{y}_i)^2}{\sum_{i=1}^{n}(y_i - \bar{y}_i)^2} \\
\text{Where } \hat{y} \text{ is predicted value and } \bar{y} \text{ is mean of predicted value}
\end{gathered}
$$

## Classification Models
The goal is to predict a discrete, categorical outcome or label.

- **Accuracy:** $$\frac{TP+TN}{TP+TN+FP+FN}$$
- **Precision:** $$\frac{TP}{TP+FP}$$
- **Recall:** $$\frac{TP}{TP + FN}$$
- **F1 Score:** $$2 * \frac{Precision * Recall}{Precision + Recall}$$
- **Specificity:** $$\frac{TN}{TN+FP}$$
- **AUC-ROC:** Assesses the model's ability to discriminate between positive and negative instances across different classification thresholds.

## SVM
Aims to find the hyperplane that separates two classes with the largest possible margin.

$$
\begin{gathered}
w^Tx + b = 0 \\
\text{Where w is the normal vector to the hyperplane, } \\
\text{x is the feature vector and b is the bias term}
\end{gathered}
$$

SVM minimizes the norm of the weight vector subject to correct classification:

$$
\begin{gathered}
\text{minimize: } \frac{1}{2} * ||w||^2 \\
\text{subject to: } y_i * (w^Tx_i + b) \ge 1
\end{gathered}
$$

### Kernel Trick in SVM
Implicitly transforms features into higher-dimensional space without explicitly calculating the transformed features.
- Linear Kernel: $$K(x, y) = x^Ty$$
- Polynomial Kernel: $$K(x, y) = (ax^Ty + c)^d$$
- Gaussian (RBF) Kernel: $$K(x, y) = \exp(-\gamma||x-y||^2)$$

## Logistic Regression
Models the probability of the class being in class 1 using the sigmoid function:

$$
\begin{gathered}
h_\theta(x) = \sigma(\theta^Tx) \\
\text{Where } h_\theta(x) \text{ represents the predicted probability of the target variable } \\
\text{in class 1 for the input feature vector x, with } \theta \text{ being the weights}
\end{gathered}
$$

Cost Function:

$$
J(\theta) = -\frac{1}{m} \sum_{i=1}^{m}[y_i \log(h_\theta(x_i)) + (1-y_i) \log(1-h_\theta(x_i))]
$$
