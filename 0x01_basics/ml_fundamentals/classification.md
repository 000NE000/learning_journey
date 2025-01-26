## 0x00. Logistic Regression
### 0.1 binary classification
###### **Classification vs. Regression**:
- **Regression**: Predicts continuous values.
- **Classification**: Predicts discrete categories or classes.
###### **Definition**: Classification problems where the output variable $y$ can take on only one of two possible values.
### 0.2 **Common Terminology**:
- **Classes/Categories**: Interchangeable terms representing the possible outcomes.
- **Positive Class**: Often represented as $1$ (e.g., spam, malignant tumor).
- **Negative Class**: Often represented as $0$ (e.g., not spam, benign tumor).
- **Examples**:
  - **Spam Detection**: Email is either spam ($1$) or not spam ($0$).
  - **Fraud Detection**: Financial transaction is either fraudulent ($1$) or legitimate ($0$).
  - **Medical Diagnosis**: Tumor is either malignant ($1$) or benign ($0$).

### 0.3 Why Linear Regression Is Not Ideal for Classification
- Applying Linear Regression to Classification
  - **Method**: Use linear regression to predict $y$, then apply a threshold (e.g., $0.5$) to classify.
  - **Issues**:
    - **Unbounded Outputs**: Linear regression can predict values outside the $[0, 1]$ range.
    - **Poor Decision Boundaries**: Sensitive to outliers and can result in inaccurate classifications.
  - Example Scenario
    - **Initial Parameters**:
      - $w_1 = 50$, $w_2 = 0.1$, $b = 50$
      - **Prediction**: $f(\mathbf{x}) = 50 \times 2000 + 0.1 \times 5 + 50 = 100,550$ (Incorrect)
    - **Swapped Parameters**:
      - $w_1 = 0.1$, $w_2 = 50$, $b = 50$
      - **Prediction**: $f(\mathbf{x}) = 0.1 \times 2000 + 50 \times 5 + 50 = 500$ (Correct)

## 0x01. Logistic Regression

### 1.0 Introduction to Logistic Regression
- **Purpose**: A classification algorithm used to predict binary outcomes.
- **Advantages Over Linear Regression**:
  - **Bounded Outputs**: Outputs probabilities between $0$ and $1$.
  - **Proper Decision Boundaries**: More suitable for classification tasks.

### 1.1 Sigmoid Function (Logistic Function)
- **Definition**:
  $$
  g(z) = \frac{1}{1 + e^{-z}}
  $$
  where $z = \mathbf{w} \cdot \mathbf{x} + b$.
- **Characteristics**:
  - **Range**: $(0, 1)$
  - **S-Shape Curve**: As $z \to \infty$, $g(z) \to 1$; as $z \to -\infty$, $g(z) \to 0$.
  - **Threshold Point**: $g(0) = 0.5$

### 1.2 Decision Boundary
- **Definition**: The line (or curve) that separates the two classes.
- **Linear Decision Boundary**:
  $$
  \mathbf{w} \cdot \mathbf{x} + b = 0
  $$
- **Polynomial Decision Boundary**:
  - Incorporates higher-order terms (e.g., $x_1^2$, $x_2^2$) to model non-linear separations.

### 1.3 Probability Interpretation
- **Output**: Represents the probability that $y = 1$ given $\mathbf{x}$.
  $$
  P(y = 1 \mid \mathbf{x}) = g(\mathbf{w} \cdot \mathbf{x} + b)
  $$
- **Thresholding**:
  - **Common Threshold**: $0.5$
  - **Decision Rule**:
    $$
    \hat{y} = 
    \begin{cases} 
      1 & \text{if } g(z) \geq 0.5 \\
      0 & \text{otherwise}
    \end{cases}
    $$

### 1.3 Cost Function for Logistic Regression

#### Inadequacy of Squared Error for Classification
- **Issues**:
  - **Non-Convexity**: Leads to multiple local minima.
  - **Inappropriate Penalties**: Does not align well with probabilistic interpretations.

#### Logistic Loss (Cross-Entropy Loss)
- **Definition**:
  $$
  L(f(\mathbf{x}), y) = -y \log(f(\mathbf{x})) - (1 - y) \log(1 - f(\mathbf{x}))
  $$
- **Overall Cost Function**:
  $$
  J(\mathbf{w}, b) = -\frac{1}{m} \sum_{i=1}^{m} \left[ y^{(i)} \log(f(\mathbf{x}^{(i)})) + (1 - y^{(i)}) \log(1 - f(\mathbf{x}^{(i)})) \right]
  $$
- **Advantages**:
  - **Convexity**: Ensures a single global minimum.
  - **Probabilistic Foundation**: Aligns with maximum likelihood estimation.

### 1.4 Gradient Descent for Logistic Regression

#### Gradient Descent Update Rules
- **Parameters Update**:
  $$
  w_j := w_j - \alpha \frac{\partial J}{\partial w_j}
  $$
  $$
  b := b - \alpha \frac{\partial J}{\partial b}
  $$
- **Derivatives**:
  $$
  \frac{\partial J}{\partial w_j} = \frac{1}{m} \sum_{i=1}^{m} \left( f(\mathbf{x}^{(i)}) - y^{(i)} \right) x_j^{(i)}
  $$
  $$
  \frac{\partial J}{\partial b} = \frac{1}{m} \sum_{i=1}^{m} \left( f(\mathbf{x}^{(i)}) - y^{(i)} \right)
  $$

#### !!!Vectorized Implementation
- **Prediction Vector**:
  $$
  \mathbf{f} = g(\mathbf{X} \mathbf{w} + b)
  $$
- **Gradient Calculation**:
  $$
  \nabla_{\mathbf{w}} J = \frac{1}{m} \mathbf{X}^T (\mathbf{f} - \mathbf{y})
  $$
  $$
  \nabla_{b} J = \frac{1}{m} \sum_{i=1}^{m} (f(\mathbf{x}^{(i)}) - y^{(i)})
  $$
- **Parameter Update**:
  $$
  \mathbf{w} := \mathbf{w} - \alpha \nabla_{\mathbf{w}} J
  $$
  $$
  b := b - \alpha \nabla_{b} J
  $$

#### Practical Considerations
- **Feature Scaling**: Enhances convergence speed.
- **Learning Rate ($\alpha$)**:
  - **Too Small**: Slow convergence.
  - **Too Large**: Risk of overshooting the minimum.

#### Practical Tips for Logistic Regression

- **Feature Scaling**: Always scale features to similar ranges to improve gradient descent efficiency.
- **Learning Rate Selection**: Experiment with different $\alpha$ values to find a balance between speed and stability.
- **Decision Boundary Visualization**: Helps in understanding model performance and making necessary adjustments.
- **Use of Libraries**: Utilize tools like Scikit-learn for efficient implementation and experimentation.
- **Monitoring Convergence**: Plot learning curves to ensure that the cost function decreases consistently.

## 0