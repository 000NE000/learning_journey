> Supervised Learning > regression

## 0x00. Example outline
- **Goal:** Predict house prices based on house sizes using a linear model.

  
## 0x01. linear regression
#### 1.1 **Model Introduced:** 
- **Linear Regression Model:** Fits a straight line to data.
- **Notation:**
  - Input feature: `x` (e.g., house size)
  - Output target: `y` (e.g., house price)
  - Model parameters: `w` (weight/slope), `b` (bias/intercept)
  - Model function: 
    - Full: $f_{w,b}(x) = wx + b$
    - Simplified (for visualization): $f(x) = wx + b$

#### 1.2 Understanding the Training Process
- **Training Set:**
  - Collection of examples $(x^{(i)}, y^{(i)})$.
  - Total examples denoted by $m$.
- **Learning Process:**
  - Feed training data to algorithm.
  - Algorithm outputs a function $f$ that predicts $\hat{y}$ for a new input $x$.
#### 1.3 Cost Function
- **Purpose:** Measure how well the linear model fits the training data.
- **Error Calculation:**
  - For a single training example: $\text{Error} = f(x^{(i)}) - y^{(i)}$
  - Squared Error: $(f(x^{(i)}) - y^{(i)})^2$
- **Cost Function $J(w, b)$:**
  - Aggregate measure: 
    $$
    J(w, b) = \frac{1}{2m} \sum_{i=1}^{m} \Big(f_{w,b}(x^{(i)}) - y^{(i)}\Big)^2
    $$
  - Minimizing $J(w, b)$ aims to find best-fit parameters $w$ and $b$.

#### 1.3 Cost Function with One Parameter \(Only $w$\)
- **Simplified Model:** $f(x) = wx$ (with $b = 0$).
- **Visualization Steps:**
  - Plot different lines for various values of $w$.
  - Calculate corresponding cost $J(w)$ for each $w$.
  - Observe relationship:
    - When $w = 1$, perfect fit ⇒ $J(1) = 0$.
    - Other $w$ values yield higher cost.
- **Goal:** Find $w$ that minimizes $J(w)$.

#### 1.4 Extending to Two Parameters \($w and $b$\)
- **Full Model Visualization:**
  - 3D surface plot of cost function $J(w, b)$ — bowl-shaped surface.
  - Contour plots: 2D representation showing ellipses of constant cost.
- **Understanding Contours:**
  - Each contour (oval) represents points with equal cost.
  - Center of contours indicates the minimum cost point (optimal $w, b$).
#### 1.5 Relationship Between Model and Cost:
  - Changing $w$ and $b$ alters the fitted line.
  - Best parameters minimize the cost function, implying a better fit.
- **Visualization Techniques:**
  - 3D surface plots and contour plots aid in understanding how $J(w, b)$ varies.
  - Helps in conceptualizing the optimization process to find optimal $w$ and $b$.

## 0x02. Gradient Descent
> Systematically find parameters $w$ and $b$ that minimize the cost function $J(w, b)$ for linear regression.
#### 2.1 def
- **Gradient Descent:** An iterative optimization algorithm used broadly in ML, not just linear regression.
- **General Applicability:** Can minimize any differentiable function $J$, including models with many parameters $w_1, w_2, ..., w_n, b$.

- **Process Overview:**
  - Start with initial guesses for $w$ and $b$ (commonly set to 0).
  - Iteratively update parameters to reduce $J(w, b)$ by taking "baby steps" downhill.
  - **Visual Analogy:**
    - Imagine standing on a hilly landscape.
    - At each step, choose the direction of steepest descent (downhill) to reach a valley (local minimum).
  - then, we find **Local Minima:**
    - Different starting points may lead to different local minima.
    - In convex functions (e.g., linear regression’s squared error), there is a single global minimum, avoiding multiple local minima issues.

#### 2.2 Mathematical Implementation of Gradient Descent
- **Update Rules:**
  - For parameter $w$:
    $$
    w := w - \alpha \frac{\partial}{\partial w} J(w, b)
    $$
  - For parameter $b$:
    $$
    b := b - \alpha \frac{\partial}{\partial b} J(w, b)
    $$
  - **Learning Rate ($\alpha$):** Controls step size; small $\alpha$ leads to slow convergence, large $\alpha$ risks overshooting or divergence.
    - [Learning Rate ($\alpha$) Considerations]
      - **Too Small $\alpha$:**
        - Leads to very slow convergence due to tiny steps.
      - **Too Large $\alpha$:**
        - Can cause overshooting, failing to converge, or diverging.
    - **Optimal $\alpha$:**
      - Should be chosen to balance convergence speed and stability.

- **Simultaneous Updates:**
  - Compute new $w$ and $b$ (often stored in temporary variables) before updating them together to ensure correct gradient descent behavior.
  - Incorrect sequential updates can lead to errors due to using already updated parameters within the same iteration.
  - Positive derivative → decrease parameter value.
  - Negative derivative → increase parameter value.
  - As the minimum is approached, derivatives shrink, naturally reducing step sizes even with a fixed learning rate.

#### 2.3 Applying Gradient Descent to Linear Regression
- **Model Recap:**
  - Linear regression model: $ f(x) = wx + b $
  - Cost function: Mean squared error over training data.
###### **Derivatives for Linear Regression:**
  - Derivative w.r.t $w$:
    $$
    \frac{\partial}{\partial w} J(w,b) = \frac{1}{m} \sum_{i=1}^m \Big(f(x^{(i)}) - y^{(i)}\Big) x^{(i)}
    $$
  - Derivative w.r.t $b$:
    $$
    \frac{\partial}{\partial b} J(w,b) = \frac{1}{m} \sum_{i=1}^m \Big(f(x^{(i)}) - y^{(i)}\Big)
    $$
###### **Gradient Descent Algorithm for Linear Regression:**
  - Update $w$ and $b$ using the formulas above until convergence.
  - Convergence is guaranteed to the global minimum for convex functions like the squared error cost.

## 0x03. Multiple Features
#### 3.0 notation
- **Features and Parameters**:
  - $X_1, X_2, X_3, X_4$: Represent the four different features.
  - $\mathbf{X} = (X_1, X_2, X_3, X_4)$: Feature vector.
  - $\mathbf{w} = (w_1, w_2, w_3, w_4)$: Weight vector.
  - $b$: Bias term.
- **Model Representation**:
  $$
  f_{\mathbf{w}, b}(\mathbf{X}) = w_1X_1 + w_2X_2 + w_3X_3 + w_4X_4 + b
  $$
  - **Vectorized Form**:
    $$
    f_{\mathbf{w}, b}(\mathbf{X}) = \mathbf{w} \cdot \mathbf{X} + b
    $$
#### 3.1 vectorization
- **Definition**: Performing operations on entire vectors or matrices simultaneously rather than using explicit loops.
- **Benefits**:
  - **Efficiency**: Faster execution, especially with large datasets.
  - **Conciseness**: Reduced and cleaner code.

```python
import numpy as np

# Parameters and features
w = np.array([0.1, 4, 10, -2])
b = 80
x = np.array([1416, 3, 2, 40])

# Unvectorized computation
f = 0
for j in range(len(w)):
    f += w[j] * x[j]
f += b

# Vectorized computation
f_vectorized = np.dot(w, x) + b
```

#### 3.2 Feature Scaling
##### importance of Feature Scaling
- **Objective**: Enable gradient descent to run faster and more efficiently by ensuring all features have comparable ranges.
- **Issue Without Scaling**:
  - Features with large ranges (e.g., size from 300 to 2000) can cause associated parameters to take on inappropriate values.
  - Example:
    - **Parameters**: $w_1 = 50$, $w_2 = 0.1$, $b = 50$
    - **Prediction**: $50 \times 2000 + 0.1 \times 5 + 50 = 100,550$ (Far from actual $500,000$)
  - Swapping parameters:
    - **Parameters**: $w_1 = 0.1$, $w_2 = 50$, $b = 50$
    - **Prediction**: $0.1 \times 2000 + 50 \times 5 + 50 = 500$
    - **Result**: Accurate prediction matching actual price.
##### Effect on Gradient Decent
- **Unscaled Features**:
  - Contour plots show elongated ellipses.
  - Gradient descent may bounce and take longer to converge.
- **Scaled Features**:
  - Contour plots resemble circles.
  - Gradient descent converges more directly and quickly.

##### Methods of Feature Scaling
1. **Min-Max Scaling**:
   - **Formula**: 
     $$
     \text{scaled\_}x_j = \frac{x_j - \text{min}(x_j)}{\text{max}(x_j) - \text{min}(x_j)}
     $$
   - **Example**:
     - $x_1$ ranges from 300 to 2000:
       $$
       \text{scaled\_}x_1 = \frac{x_1}{2000}
       $$
     - $x_2$ ranges from 0 to 5:
       $$
       \text{scaled\_}x_2 = \frac{x_2}{5}
       $$
2. **Mean Normalization**:
   - **Formula**:
     $$
     \text{mean\_normalized\_}x_j = \frac{x_j - \mu_j}{\text{max}(x_j) - \text{min}(x_j)}
     $$
   - **Example**:
     - For $x_1$ with $\mu_1 = 600$:
       $$
       \text{mean\_normalized\_}x_1 = \frac{x_1 - 600}{2000 - 300} = \frac{x_1 - 600}{1700}
       $$
3. **Z-Score Normalization**:
   - **Formula**:
     $$
     \text{z\_score\_}x_j = \frac{x_j - \mu_j}{\sigma_j}
     $$
   - **Parameters**:
     - $\mu_j$: Mean of feature $x_j$
     - $\sigma_j$: Standard deviation of feature $x_j$
   - **Example**:
     - For $x_1$ with $\mu_1 = 600$ and $\sigma_1 = 450$:
       $$
       \text{z\_score\_}x_1 = \frac{x_1 - 600}{450}
       $$
##### practical tips
- Aim for features to range approximately between $-1$ and $1$.
- Scaling is especially important for features with vastly different ranges.
- Feature scaling rarely harms model performance and is generally recommended.
#### 3.3 Recognizing Gradient Descent Convergence
##### Monitoring Convergence
- **Learning Curve**:
  - Plot the cost function $J$ versus the number of iterations.
  - **Axes**:
    - Horizontal: Number of iterations
    - Vertical: Cost $J$
- **Indicators of Proper Convergence**:
  - Cost $J$ decreases consistently with each iteration.
  - The curve flattens out, indicating the algorithm is approaching the global minimum.
- **Signs of Issues**:
  - Cost $J$ increases in some iterations, suggesting potential problems with the learning rate or code bugs.
##### Automatic Convergence Tests
- **Epsilon ($\epsilon$)**:
  - Define a small threshold value (e.g., $0.001$).
  - **Convergence Criteria**:
    - If the change in cost $J$ between iterations is less than $\epsilon$, declare convergence.
- **Challenges**:
  - Choosing an appropriate $\epsilon$ is difficult.
  - Visual inspection of the learning curve is often more reliable.

##### Debugging Gradient Descent
- **Check Learning Rate ($\alpha$)**:
  - If $J$ increases, $\alpha$ might be too large.
- **Verify Update Rules**:
  - Ensure parameters are updated using subtraction:
    $$
    w_j := w_j - \alpha \frac{\partial J}{\partial w_j}
    $$
  - Incorrectly using addition can cause divergence.
#### 3.4 Choosing an Appropriate Learning Rate
##### Effects of Learning Rate ($\alpha$)
- **Too Small**:
  - Gradient descent converges very slowly.
- **Too Large**:
  - Gradient descent may fail to converge and cause $J$ to increase.

##### Strategies for Selecting $\alpha$
1. **Trial and Error**:
   - Start with a small $\alpha$ (e.g., $0.001$).
   - Gradually increase (e.g., $0.003$, $0.01$, $0.03$, etc.) until $J$ decreases consistently.
2. **Incremental Scaling**:
   - Multiply $\alpha$ by a factor (e.g., $3$) iteratively.
   - Identify the largest $\alpha$ that still results in consistent decrease in $J$.
3. **Debugging with Small $\alpha$**:
   - Use a very small $\alpha$ to ensure $J$ decreases.
   - If it doesn't, there may be a bug in the implementation.

##### Practical Tips
- Balance between convergence speed and stability.
- Plot learning curves for different $\alpha$ values to visualize performance.
- Use scaled features to allow for larger $\alpha$ and faster convergence.

#### 3.5 Feature Engineering and Polynomial Regression

##### Feature Engineering
- **Objective**: Enhance model performance by creating new features based on existing ones.
- **Example**:
  - Original Features: $x_1$ (lot width), $x_2$ (lot depth)
  - New Feature: $x_3 = x_1 \times x_2$ (lot area)
- **Benefits**:
  - Captures interactions between features.
  - Can lead to more accurate and flexible models.

##### Polynomial Regression
- **Definition**: Extends linear regression by adding polynomial terms of the original features to model non-linear relationships.
- **Example**:
  - Original Feature: $x$
  - Polynomial Features: $x$, $x^2$, $x^3$
  - Model:
    \[
    f_{\mathbf{w}, b}(x) = w_1 x + w_2 x^2 + w_3 x^3 + b
    \]
- **Advantages**:
  - Can fit curves and capture more complex patterns in data.
- **Considerations**:
  - Requires feature scaling, especially for higher-degree terms to prevent numerical instability.
  - Increased feature degrees can lead to overfitting if not managed properly.

##### Implementing Polynomial Regression
1. **Create Polynomial Features**:
   - Transform original features into polynomial terms.
2. **Scale Features**:
   - Apply feature scaling to ensure all features have comparable ranges.
3. **Apply Gradient Descent**:
   - Use gradient descent on the expanded feature set to find optimal parameters.

##### Practical Tips
- Use feature engineering to incorporate domain knowledge.
- Regularize polynomial terms to prevent overfitting.
  - Overfitting occurs when the process of creating or selecting features leads to a model that is too complex. This complexity allows the model to capture noise and irrelevant patterns in the training data, rather than just the meaningful relationships. Consequently, while the model may achieve high accuracy on the training set, its performance significantly degrades on new, unseen data.
- Utilize libraries like Scikit-learn for efficient implementation:
  ```python
  from sklearn.preprocessing import PolynomialFeatures
  from sklearn.linear_model import LinearRegression

  # Create polynomial features
  poly = PolynomialFeatures(degree=3)
  X_poly = poly.fit_transform(X)

  # Fit linear regression on polynomial features
  model = LinearRegression()
  model.fit(X_poly, y)
  ```