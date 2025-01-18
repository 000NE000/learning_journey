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





