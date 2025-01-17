# learning_journey
A comprehensive record of my learning journey in Python, ML, NLP, and PyTorch

It is also designed to build an “artistic works” recommendation system and deploy it as a service. Below is an in-depth roadmap and a directory structure for scalable organization.

[concept list](https://github.com/000NE000/learning_journey/blob/main/0x01_basics/concept_tree/WhatShouldILearn.md)
---

## 1. Roadmap Overview

### **Phase 1**
- **Goal**: Build a solid foundation in Python, ML, and NLP fundamentals, and learn basic PyTorch usage.
  - **Key Tasks**:
    - Complete a Python course (e.g., Codecademy).
    - Implement practice exercises for machine learning fundamentals and simple NLP tasks.
    - Familiarize yourself with PyTorch syntax and basic neural network examples (e.g., CNN/RNN).

### **Phase 2**
- **Goal**: Collect data (movies, books) and define labeling standards (“values you can get” from each work).
  - **Key Tasks**:
    - Crawl or fetch data from IMDb, TMDb API, Goodreads, and Google Books API.
    - Define labels (e.g., inspiration, emotional stimulation, educational value) for each item.
    - Perform text preprocessing (tokenization, lemmatization/stemming, stopword removal) and conduct EDA to check data distribution, null values, and duplicates.
    - Finalize project architecture by determining which model or approach to adopt.

### **Phase 3**
- **Goal**: Develop a meaning-based embedding and recommendation algorithm using Python and PyTorch.
  - **Key Tasks**:
    - Research or experiment with various text embedding methods (Word2Vec, GloVe, FastText, BERT).
    - Implement a recommendation model (e.g., content-based, collaborative filtering, or hybrid).
    - Evaluate performance (Precision, Recall, F1 Score). Tune hyperparameters (learning rate, batch size, network depth).
    - Integrate with **FastAPI** to expose recommendation endpoints. Containerize the app with **Docker**.

### **Phase 4**
- **Goal**: Deploy the service to the cloud, test reliability, and finalize documentation.
  - **Key Tasks**:
    - Push Docker images to AWS/GCP and configure the environment (AWS Elastic Beanstalk, EC2, or GCP services).
    - Conduct stress testing to measure API throughput and optimize performance.
    - Implement monitoring (Sentry, ELK stack, or custom logging).
    - Document the entire project for GitHub and your portfolio. Write technical blog posts and share them on LinkedIn or GitHub Pages.

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

