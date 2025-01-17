## Phase1: Foundations in Python, ML, and NLP

### Tasks:
// python basic은 생략 (기초 역량)

1. **Master Data Handling with Pandas and NumPy**
   - **Resources**:
     - [Pandas Official Documentation](https://pandas.pydata.org/docs/).
     - [NumPy Tutorials](https://numpy.org/doc/stable/user/quickstart.html).
     - [numpy exercise](https://github.com/rougier/numpy-100/tree/master)
     - [pandas exercise](https://github.com/guipsamora/pandas_exercises)
   - **Practice**:
     - exercising by reference in others docs
     - Load datasets like [Titanic](https://www.kaggle.com/c/titanic) or [Iris](https://archive.ics.uci.edu/ml/datasets/iris).
     - Perform filtering, grouping, and aggregation.
     - Visualize data with Matplotlib and Seaborn: [Seaborn Gallery](https://seaborn.pydata.org/examples/index.html).
  

1. **Machine Learning Basics**
   - **Resources**:
     - [ML fundamentals by Anderew Ng](https://www.coursera.org/learn/machine-learning).
     - [Scikit-learn Quickstart](https://scikit-learn.org/stable/getting_started.html).
     - [deep learning specialization by Anderew Ng](https://www.coursera.org/specializations/deep-learning)
     - [NLP by Andrew Ng]()
  
   - **Implementation**:
     - Train a Linear Regression model on a small dataset like housing prices ([Kaggle Housing Prices Dataset](https://www.kaggle.com/c/house-prices-advanced-regression-techniques)).

---

## Phase2: Data Collection and Preprocessing

### Tasks:
1. **Collect Data**
   - **Resources**:
     - IMDb: [IMDbPy Documentation](https://imdbpy.readthedocs.io/en/latest/).
     - TMDb: [TMDb API Documentation](https://developer.themoviedb.org/reference/intro/getting-started).
     - Goodreads: [Goodreads API](https://www.goodreads.com/api).
     - Google Books: [Google Books API](https://developers.google.com/books/docs/v1/getting_started).
   - **Implementation**:
     - Write Python scripts to fetch data and save them as CSV/JSON files.

2. **Clean and Explore Data**
   - **Resource**: [Data Cleaning in Pandas](https://pandas.pydata.org/pandas-docs/stable/user_guide/cookbook.html#data-cleaning).
   - **Implementation**:
     - Remove nulls, duplicates, and inconsistent entries.
     - Visualize data distribution using Seaborn.

3. **Text Preprocessing**
   - **Resources**:
     - [NLTK Quickstart Guide](https://www.nltk.org/).
     - [SpaCy Tutorials](https://spacy.io/usage).
   - **Implementation**:
     - Tokenize, remove stopwords, and lemmatize text data.
     - Convert text to TF-IDF vectors using Scikit-learn: [Text Feature Extraction](https://scikit-learn.org/stable/modules/feature_extraction.html).

---

## Phase3: Model Development

### Tasks:
1. **Text Embeddings**
   - **Resource**: [Hugging Face Transformers Documentation](https://huggingface.co/docs/transformers/index).
   - **Implementation**:
     ```python
     from transformers import pipeline
     nlp = pipeline("feature-extraction", model="bert-base-uncased")
     embeddings = nlp("Example text here")
     ```

2. **Recommendation Algorithm**
   - **Resource**: [Recommendation Systems in Python](https://www.analyticsvidhya.com/blog/2018/06/comprehensive-guide-recommendation-engine-python/).
   - **Implementation**:
     - Content-based filtering using cosine similarity.
     - Collaborative filtering using matrix factorization (SVD in Scikit-learn).
     - Evaluate using Precision@K, Recall@K:
       ```python
       from sklearn.metrics import precision_score, recall_score
       ```

3. **Hyperparameter Tuning**
   - **Resource**: [Scikit-learn Hyperparameter Tuning](https://scikit-learn.org/stable/modules/grid_search.html).
   - **Implementation**:
     ```python
     from sklearn.model_selection import GridSearchCV
     grid = GridSearchCV(estimator, param_grid, scoring='accuracy')
     ```

---
