# learning_journey
A comprehensive record of my learning journey in Python, ML, NLP, and PyTorch

It is also designed to build an “artistic works” recommendation system and deploy it as a service. Below is an in-depth roadmap and a directory structure for scalable organization.

[concept list](https://github.com/000NE000/learning_journey/blob/main/0x01_basics/concept_tree/WhatShouldILearn.md)
---

## 1. Roadmap
[how to study?](https://github.com/000NE000/learning_journey/blob/main/studying_ref.md)

#### **Phase A: Quick Theoretical Overview (Pre-Learning)**
1. **Python Basics**
   - Short tutorial or reference to learn core syntax (variables, loops, functions).
   - Familiarize yourself with basic data structures and how they’re used in Python.

2. **Basic Data Structures & Git**
   - **Data Structures**: Lists, dictionaries, sets (briefly).
   - **Git Concepts**: Understanding branching, committing, merging.

3. **ML Fundamentals**
   - **Core Concepts**: Difference between supervised and unsupervised learning, bias-variance trade-off.
   - **Evaluation Metrics**: Accuracy, Precision, Recall, MSE, AUC.
   - **ML Pipeline**: Data preprocessing → Model training → Validation → Deployment.

4. **Deep Learning Fundamentals**
   - **Neural Networks**: Activation functions, forward/backpropagation.
   - **Optimization**: Gradient descent, Adam optimizer.
   - **Frameworks**: Basic knowledge of TensorFlow or PyTorch structure.

#### **Phase B: Hands-On Implementation**
1. **Python & Data Handling**
   - **Data Manipulation**: Practice with Pandas/NumPy (handling missing data, grouping, merging).
   - **Data Visualization**: Use Matplotlib/Seaborn to plot histograms, scatter plots, heatmaps.
   - **Git in Practice**: Create a repository, commit changes, branch for experiments.

2. **ML Coding**
   - **Simple Models**: Implement Linear Regression, Logistic Regression, Decision Trees using Scikit-learn.
   - **Train-Test Split**: Evaluate performance with real data (accuracy, confusion matrix, etc.).
   - **Hyperparameter Tuning**: GridSearchCV or RandomizedSearchCV.

3. **Deep Learning Implementation**
   - **Basic Neural Networks**: Build an MNIST classifier in PyTorch or TensorFlow.
   - **Hyperparameter Tweaks**: Adjust learning rate, batch size, epochs, and observe results.

4. **NLP & Text Processing**
   - **Text Preprocessing**: Tokenization, lemmatization, removing stopwords (NLTK or SpaCy).
   - **Feature Extraction**: BoW, TF-IDF, Word2Vec, GloVe.
   - **Advanced**: Explore pretrained transformers (e.g., BERT) for richer embeddings.

5. **Recommendation System Development**
   - **Data Collection**: Gather artistic work data (movies, books) and label them with “values/meaning.”
   - **Content-Based Filtering**: Use item attributes (keywords, embeddings) with cosine similarity.
   - **Collaborative Filtering**: Implement a basic matrix factorization approach (SVD).
   - **Hybrid Approach**: Combine content-based + collaborative filtering for better accuracy.
   - **Evaluation**: Use Precision@k, Recall@k, NDCG to measure recommendation quality.

---

#### **Phase C: Integration & Deployment**
1. **Integration**
   - Merge ML/NLP components into a single pipeline.
   - Implement a simple API with FastAPI or Flask to serve recommendations.

2. **Docker & Cloud**
   - Create a `Dockerfile` for containerization.
   - Deploy to AWS, GCP, or Heroku for real-world accessibility.

3. **Project Documentation**
   - Maintain a `README.md` describing the entire project flow.
   - Write a brief technical blog or article to showcase your system’s features.

4. **Continuous Improvement**
   - Gather user feedback, refine labels and embeddings.
   - Experiment with different neural architectures or advanced recommendation algorithms.

---

## 2. Study vs. Practice Breakdown

| **Concept**                 | **Theory-First**                                     | **Hands-On**                                              |
|-----------------------------|------------------------------------------------------|-----------------------------------------------------------|
| **Python Basics**           | Watch a quick intro tutorial                        | Write small scripts, data manipulation tasks              |
| **Data Structures & Git**   | Read about Git flow                                 | Create repos, make branches, merge PRs                    |
| **ML Fundamentals**         | Understand supervised/unsupervised, metrics         | Implement regression/classification on real datasets      |
| **Deep Learning Basics**    | Learn NN concepts (ReLU, backprop, gradient descent)| Build a basic PyTorch/TensorFlow model                    |
| **NLP**                     | Learn text preprocessing theory                     | Tokenize, lemmatize, create embeddings with code          |
| **Recommendation Systems**  | Compare content-based vs. collaborative filtering   | Implement both, experiment with matrix factorization      |
| **Deployment & Docker**     | Read about containerization                         | Write a Dockerfile, deploy to a cloud service             |

---

## 3. Suggested Timeline

1. **Weeks 1–2**: Quick Theoretical Study (Python, ML, Git).
2. **Weeks 3–4**: Practical Python & Data Manipulation, Simple ML Models.
3. **Weeks 5–6**: Deep Learning Basics, NLP Implementation.
4. **Weeks 7–8**: Recommendation System Development & Evaluation.
5. **Weeks 9–10**: API Integration, Docker, Cloud Deployment.
6. **Weeks 11–12**: Final Documentation, Testing, and Improvements.

> **Tip**: You can shorten or lengthen each phase depending on your schedule.

---

## **How to Proceed**
1. **Pre-Learning**: Spend a short time reading or watching tutorials on each concept.
2. **Hands-On Practice**: Immediately apply theory in coding mini-projects.
3. **Documentation**: Keep track of everything in a `progress_log.md`.
4. **Refinement**: Continuously revisit any theoretical gaps as needed.

---
---

## 2. Directory Structure

Below is the recommended directory layout. Each `0x` folder represents a major phase in your learning and project cycle. You can customize subfolders as you see fit.

**Highlights**:
1. **0x01_basics**: Python, ML, NLP, and PyTorch fundamentals.  
2. **0x02_data_preparation_project_design**: Data collection and project structure.  
3. **0x03_model_development**: Embeddings, recommendation algorithm, tuning, and experiment logs.  
4. **0x04_service_deployment**: FastAPI, Docker, cloud setup, and production testing.  
5. **0x05_documentation_portfolio**: Final project documentation, blog posts, presentations, and portfolio website.

---

## 3. Learning & Project Practices

1. **Daily/Weekly Logging**  
   - Update `progress_log.md` in each folder (e.g., `0x01_basics/progress_log.md`) with daily or weekly goals and reflections.

2. **Version Control**  
   - Commit frequently with clear messages: `"Add initial data preprocessing script"`, `"Tune hyperparameters for BERT model"`, etc.

3. **Notebook Organization**  
   - Place Jupyter Notebooks under relevant folders (e.g., `ml_nlp_fundamentals/notebooks/`) to maintain clarity.

4. **Documentation**  
   - For major decisions or changes, add `.md` documents (e.g., `design_docs.md`, `api_docs.md`) so everything is tracked.

5. **Experiment Tracking**  
   - Use `experiments/notebooks/` for iterative experiments.  
   - (Optional) Set up MLflow in `experiments/mlflow_logs/` to track experiment metadata.

6. **Docker & Cloud**  
   - Store Docker configs in `docker/`, main Python API code in `fastapi_app/`, and cloud environment setup docs in `cloud_deployment/`.

7. **Final Presentation & Blog**  
   - Summaries go to `final_report/` and `slides/`.  
   - Draft blog posts in `tech_blog_posts/`.  
   - If you want a personal site or GitHub Pages, use `portfolio_site/`.

---

## 4. Best Practices & Next Steps

- **Set Milestones**:  
  Create clear milestones (e.g., “Finish Month 2 Basics,” “Complete Data Preprocessing,” “Deploy Minimal Viable Product”) to monitor progress.

- **Maintain Readability**:  
  Add docstrings and comments in your code. Write concise and descriptive commit messages to ensure easy collaboration or future references.

- **Expand & Adapt**:  
  As your project or learning scope grows, create additional subfolders (like `transformers/` or `reinforcement_learning/`) or parallel folders if you explore more topics.

- **Continuous Learning**:  
  Regularly update the readme or `progress_log.md` to document changes in your plan or newly discovered resources.

---

