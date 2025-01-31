>프로젝트 아이디어: 예술 작품(영화, 책 등)을 단순한 장르 분류가 아닌, “얻을 수 있는 것” 또는 “예술 경험이 주는 의미”를 기반으로 추천하는 시스템 구축.
> chatbot 형식의 구현
> > 선결적 질문 가능 등 구체적인 구현 아이디어 필요
> 


---
1. **Foundations in Programming and Data**: Begin with the basics of Python, data manipulation, and version control because these are prerequisites for everything else.

2. **Machine Learning Fundamentals**: Learn the core ML concepts and algorithms before diving into complex models like deep learning or specialized domains.

3. **Deep Learning Basics**: Once you’re comfortable with ML fundamentals, focus on neural networks and frameworks like TensorFlow or PyTorch.

4. **Natural Language Processing (NLP)**: Since your project involves “meaning” and “value,” NLP techniques will be crucial for extracting insights from text-based data.

5. **Recommendation Systems**: Build expertise in designing recommendation systems, which are the backbone of your project.
---
# list of concepts
## **1. Foundations in Programming and Data**
#### 1.1 **Python Basics**
- Learn Python syntax: variables, loops, conditionals, and functions.
- Explore libraries for numerical and data handling:
	- **NumPy**: Array manipulation, linear algebra, and mathematical operations.
	- **Pandas**: DataFrames for organizing and analyzing tabular data.
#### 1.2 **Data Manipulation**
- Learn to handle missing data, duplicates, and incorrect values.
- Perform data aggregation, grouping, and reshaping.
- Tools: Pandas, OpenPyXL (for Excel), CSV handling.
#### 1.3 **Data Visualization**
- Tools: Matplotlib, Seaborn.
- Plot types: Histograms, scatter plots, box plots, heatmaps.
#### 1.4 **Version Control**
- Basics of Git: Cloning, branching, committing, and pushing to repositories.
- Platforms: GitHub, GitLab.
## 2. **Machine Learning Fundamentals**
#### 2.1 **Core ML Concepts**
###### Supervised Learning: Training with labeled data.
- **Regression**: Linear Regression, Logistic Regression.
- **Classification**: Decision Trees, Naive Bayes, SVMs.
###### Unsupervised Learning: Learning without labels.
- Clustering: K-Means, DBSCAN.
- Dimensionality Reduction: Principal Component Analysis (PCA).
#### 2.2 **Model Evaluation**
- Train-Test Split: Evaluating models on unseen data.
- Metrics:
	- Regression: Mean Squared Error (MSE), R².
	- Classification: Accuracy, Precision, Recall, F1 Score, ROC-AUC.

#### 2.3 **ML Pipeline**
- Data preprocessing: Normalization, scaling, encoding categorical variables.
- Model training, hyperparameter tuning, and evaluation.
#### 2.4 **Libraries**
- Scikit-learn: Core library for implementing ML algorithms.
- Joblib: Model persistence for saving trained models.
## 3. **Deep Learning Basics**
#### 3.1 **Neural Networks**
- Understand perceptrons, activation functions (ReLU, sigmoid, softmax), and loss functions.
- Architecture:
	- Input Layer: Feature input.
	- Hidden Layers: Intermediate transformations.
	- Output Layer: Predictions.
#### 3.2 **Optimization**
- Gradient Descent: How models learn.
- Advanced optimizers: Adam, RMSprop.
#### 3.3 **Frameworks**
- TensorFlow: Google’s framework for building scalable models.
- PyTorch: Flexible, research-friendly framework.

#### 3.4 **Building Models**
- Sequential API: Quickly stack layers for basic models.
- Functional/Custom API: Create complex architectures (e.g., ResNet).

#### 3.5 **Applications**
- Image classification, time series forecasting.

## 4. **Natural Language Processing (NLP)**
#### 4.1 **Text Preprocessing**
- Tokenization: Splitting text into meaningful units.
- Stopwords removal: Removing common but unimportant words.
- Lemmatization/Stemming: Converting words to base forms.
#### 4.2 **Feature Extraction**
- Bag of Words (BoW): Represent text as word occurrence counts.
- TF-IDF: Highlight important words relative to the document and corpus.
#### 4.3 **Word Embeddings**
- Learn distributed representations: Word2Vec, GloVe.
- Pretrained models: BERT, GPT via Hugging Face Transformers.
#### 4.4 **NLP Applications**
- Sentiment analysis: Classify emotions in text.
- Topic modeling: Extract themes from large text data.
- Named Entity Recognition (NER): Identify entities like names, dates.
## 5. **Recommendation Systems**
#### 5.1 **Content-Based Filtering**
- Recommend items based on their attributes:
	- Example: If a user likes “Inception,” suggest movies with similar themes or directors.
- Tools: Cosine similarity, feature engineering.
#### 5.2 **Collaborative Filtering**
- User-based: Recommend based on similar users’ preferences.
- Item-based: Suggest items similar to those the user has rated highly.
- Techniques: Matrix factorization, Alternating Least Squares (ALS).
#### 5.3 **Hybrid Approaches**
- Combine collaborative and content-based methods.
#### 5.4 **Deep Learning in Recommendations**
- Use neural networks to learn latent representations of users and items.
	- Example: Neural Collaborative Filtering (NCF).
#### 5.5 **Evaluation Metrics**
- Precision@k, Recall@k: Assess recommendations at top-k positions.
- Mean Average Precision (MAP), Normalized Discounted Cumulative Gain (NDCG).