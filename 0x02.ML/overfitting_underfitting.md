# Overfitting and Underfitting in Machine Learning

## 0x00 Introduction to Overfitting and Underfitting

### 0.1 Definitions
- **Overfitting**: a.k.a High Variance
  - **Description**: When a model learns not only the underlying patterns in the training data but also the noise and random fluctuations.
  - **Consequence**: High performance on training data but poor performance on validation or test data.
  
- - **High Variance (Overfitting)**: The model is highly sensitive to fluctuations in the training data.
- **Underfitting**: a.k.a High Bias
  - **Description**: When a model is too simple to capture the underlying patterns in the data.
  - **Consequence**: Poor performance on both training and validation/test data.
  - **High Bias (Underfitting)**: The model has strong assumptions, leading to systematic errors. 


### 0.2 Linear Regression Example
- **Scenario**: Predicting housing prices based on the size of the house.
- **Underfitting**:
  - **Model**: Simple linear regression (straight line).
  - **Outcome**: Poor fit; fails to capture the flattening trend as house size increases.
  - **Interpretation**: High bias.
- **Overfitting**:
  - **Model**: High-order polynomial regression (e.g., 4th order).
  - **Outcome**: Perfect fit on training data but wiggly and unrealistic predictions on new data.
  - **Interpretation**: High variance.

### 0.3 Classification Example
- **Scenario**: Classifying tumors as malignant or benign based on features like tumor size and patient age.
- **Underfitting**:
  - **Model**: Simple logistic regression with a linear decision boundary.
  - **Outcome**: Inadequate separation of classes; poor fit.
- **Overfitting**:
  - **Model**: Logistic regression with high-order polynomial features.
  - **Outcome**: Complex decision boundary that fits training data perfectly but fails to generalize.

### 0.4 Consequences of Overfitting and Underfitting

#### Overfitting
- **Poor Generalization**: Model performs well on training data but poorly on new, unseen data.
- **Increased Variance**: Predictions vary significantly with different training sets.
- **Complex Models**: Often have unnecessary complexity, making them harder to interpret.

#### Underfitting
- **Inadequate Learning**: Model fails to capture the underlying trend of the data.
- **High Bias**: Systematic errors due to overly simplistic assumptions.
- **Poor Performance**: Low accuracy on both training and test data.

## 0x01. Addressing Overfitting and Underfitting

### 1.1 Collect More Training Data
- **Effect**: Reduces overfitting by providing more examples for the model to learn from.
- **Advantage**: Helps the model generalize better.
- **Limitation**: Not always feasible due to data availability constraints.

### 1.2 Feature Selection
- **Description**: Use a subset of relevant features to simplify the model.
- **Methods**:
  - **Manual Selection**: Based on domain knowledge.
  - **Automated Methods**: Techniques like Recursive Feature Elimination (RFE) or feature importance from tree-based models.
- **Benefit**: Reduces model complexity and mitigates overfitting.

### 1.3 Regularization
- **Purpose**: Penalize large coefficients to constrain model complexity.
- **Types**:
  - **L2 Regularization (Ridge)**:
    $$
    J(\mathbf{w}, b) = \frac{1}{2m} \sum_{i=1}^{m} \left( f(\mathbf{x}^{(i)}) - y^{(i)} \right)^2 + \frac{\lambda}{2m} \sum_{j=1}^{n} w_j^2
    $$
  - **L1 Regularization (Lasso)**:
    $$
    J(\mathbf{w}, b) = \frac{1}{2m} \sum_{i=1}^{m} \left( f(\mathbf{x}^{(i)}) - y^{(i)} \right)^2 + \frac{\lambda}{m} \sum_{j=1}^{n} |w_j|
    $$
- **Effect**: Encourages smaller weights, leading to simpler models that generalize better.
- **Implementation**:
  - **Linear Regression**: Add regularization terms to the cost function and adjust gradient descent updates.
  - **Logistic Regression**: Similar approach with adjusted cost functions and gradient updates.

### 1.4 Regularization Example in Linear Regression
- **Original Cost Function**:
  $$
  J(\mathbf{w}, b) = \frac{1}{2m} \sum_{i=1}^{m} \left( f(\mathbf{x}^{(i)}) - y^{(i)} \right)^2
  $$
- **Regularized Cost Function (L2)**:
  $$
  J(\mathbf{w}, b) = \frac{1}{2m} \sum_{i=1}^{m} \left( f(\mathbf{x}^{(i)}) - y^{(i)} \right)^2 + \frac{\lambda}{2m} \sum_{j=1}^{n} w_j^2
  $$
- **Gradient Descent Update for $w_j$**:
  $$
  w_j := w_j - \alpha \left( \frac{1}{m} \sum_{i=1}^{m} \left( f(\mathbf{x}^{(i)}) - y^{(i)} \right) x_j^{(i)} + \frac{\lambda}{m} w_j \right)
  $$
- **Effect**: Shrinks $w_j$ towards zero, reducing model complexity.

### 1.5 Practical Tips for Balancing Overfitting and Underfitting

- **Monitor Learning Curves**: Plot training and validation performance to identify overfitting or underfitting.
- **Cross-Validation**: Use techniques like k-fold cross-validation to assess model generalization.
- **Simplify the Model**: Start with a simple model and gradually increase complexity as needed.
- **Regularization Parameter ($\lambda$)**:
  - **Selection**: Use techniques like grid search or cross-validation to find an optimal $\lambda$.
  - **Trade-Off**: Higher $\lambda$ reduces overfitting but may lead to underfitting; lower $\lambda$ allows more complexity but risks overfitting.

