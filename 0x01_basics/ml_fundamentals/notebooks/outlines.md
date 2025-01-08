## 0x01. 
#### 1.1 Definition of Machine Learning
- **Arthur Samuel's Definition**:
	- Machine learning is the field of study that gives computers the ability to learn without being explicitly programmed.
	- Example: Samuel's checkers-playing program from the 1950s.
		- The program improved by playing tens of thousands of games against itself.
		 - It learned which positions led to wins or losses and eventually became better at checkers than Samuel.
- **Learning from Experience**:
	- The more opportunities (or data) a learning algorithm has, the better it performs.
	- Example:
		- A computer playing fewer games would perform worse due to limited learning opportunities.
- **Importance of Practice Questions**:
	- Questions during learning help reinforce understanding.
	- Getting the correct answer initially is less important than practicing the concepts.
#### 1.2 Types of Machine Learning
###### 1) **Supervised Learning**:
- Most widely used in real-world applications.
- Focuses on learning from labeled data.
- Supervised learning has seen the most advancements and innovation. These approaches form the foundation of modern machine learning systems.
###### 2) **Unsupervised Learning**:
- Focuses on finding patterns in data without labeled outputs.
- key practical concepts
	- **Recommender Systems**
	- **Reinforcement Learning**

#### 1.3 Practical Advice for Applying Machine Learning
###### **Importance of Application**:
- Knowing how to use tools is as important as understanding them.
	-  metaphor: Having advanced tools like a state-of-the-art hammer but not knowing how to build a house renders the tools ineffective.

## 0x02. Supervised Learning in ML
#### 2.1 def
- Supervised learning refers to algorithms that learn from **input-output mappings (x to y)**.
- Key characteristic
	- The algorithm is trained using examples that include the **correct output labels (y)** for the given inputs (x).
	- After training, the algorithm can predict outputs (y) for new inputs (x) it has never seen before.
- examples
	- **Spam Filtering**:
		- Input: An email.
		- Output: Whether it is spam or not.
	- **Speech Recognition**:
		- Input: An audio clip.
		- Output: The corresponding text transcript.
	- **Machine Translation**:
		- Input: Text in one language (e.g., English).
		- Output: Translated text in another language (e.g., Spanish, Arabic).
	- **Online Advertising**:
		- Input: Ad information and user data.
		- Output: Prediction of whether the user will click on the ad.
		- **Significance**: Drives significant revenue for online platforms by optimizing ad clicks
	- **Self-Driving Cars**:
		- Input: Images and sensor data.
		- Output: Positions of other vehicles or obstacles
	- **Manufacturing (Visual Inspection)**:
		- Input: Image of a product.
		- Output: Detection of scratches, dents, or defects.
#### 2.2 workflow of supervised learning
###### 1st **Train the Model**:
 - Provide examples of inputs (x) and their corresponding labels (y).
 - The model learns patterns from these pairs.
###### 2nd. **Make Predictions**:
 - Use the trained model to predict outputs (y) for new inputs (x) it has not encountered before.

#### 2.3 Types of Supervised Learning
###### **Regression**:
- Predicts continuous numerical values.
- Example: House prices, where predictions could be any number (e.g., $150,000 or $183,000).
###### **Classification**:
- Classification is a type of supervised learning algorithm that predicts **categories** or **classes** instead of continuous numbers.
	- Unlike regression, classification outputs a **small, finite set of possible outputs** (e.g., 0 or 1).
- Example: Spam or not spam (binary classification).
- **Example of Multi-Class Classification**:
	- In cancer detection, malignant tumors could be further classified into **Type 1** or **Type 2** cancers, leading to three output categories: 0, 1, 2.
	- decision boundary![decision boundary](https://file%2B.vscode-resource.vscode-cdn.net/Users/macforhsj/Desktop/learning_journey/0x01_basics/ml_fundamentals/notebooks/figure/Pasted%20image%2020250108130119.png?version%3D1736314329913)

#### 2.4 **Significance**:
- 99% of the economic value from machine learning comes from supervised learning today.
- Major drivers include applications in advertising, manufacturing, and more.

