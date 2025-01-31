> 1st Extract themes, emotions and learning
> 2nd mapping

### A. Theme Extraction

1. Keyword Extraction
	•	Techniques:
	•	TF-IDF: Identify important words based on their frequency and uniqueness.
	•	RAKE (Rapid Automatic Keyword Extraction): Extract key phrases from the text.
	•	TextRank: Graph-based ranking for keyword extraction.
	•	Tools: Scikit-learn, RAKE-NLTK, Gensim.

2. Topic Modeling
	•	Techniques:
	•	Latent Dirichlet Allocation (LDA): Discovers topics based on word distributions.
	•	Non-Negative Matrix Factorization (NMF): Identifies additive components representing themes.
	•	Tools: Gensim, Scikit-learn.
	•	Process:
	1.	Vectorize the text data using CountVectorizer or TfidfVectorizer.
	2.	Apply LDA or NMF to uncover underlying themes.
	3.	Interpret and label the discovered topics based on prominent keywords.

3. Mapping to Predefined Themes
	•	Create a Mapping Dictionary: Align extracted keywords/topics with your predefined theme categories.
	•	Automated Matching: Use similarity measures or rule-based matching to assign themes to movies.
	•	Example:
	•	Keywords like “sacrifice,” “love” → Love and Sacrifice (HR1)
	•	Keywords like “justice,” “equality” → Social Justice (SI1)

### B. Emotion Extraction

1. Sentiment Analysis
- Purpose: Determine the overall sentiment (positive, negative, neutral) of reviews and plot summaries.
- Tools: VADER, TextBlob, Hugging Face’s BERT-based models.
- Process:
	1.	Apply sentiment analysis to user reviews and plot summaries.
	2.	Aggregate sentiment scores to understand the movie’s emotional tone.

2. Emotion Detection
- Purpose: Identify specific emotions (e.g., joy, sadness, fear) expressed in the text.
- Tools: Hugging Face Transformers, DeepMoji, Emotion Recognition Models.
- Process:
	1.	Use pre-trained emotion detection models to analyze the text.
	2.	Extract and categorize emotions associated with each movie.

### C. Learning Outcome Extraction

1. Identify Educational and Insightful Content
- Techniques:
- Aspect-Based Sentiment Analysis: Focus on specific aspects like plot, characters to determine what users learned.
- Keyword Matching: Look for phrases indicating learning outcomes (e.g., “learned about,” “understood,” “gained insight into”).
- Process:
	1.	Extract sentences or phrases that indicate learning or insights.
	2.	Categorize these into predefined learning outcomes (e.g., Knowledge Acquisition, Social Awareness).

## Mapping Extracted Data to Theme Categories

A. Establish Mapping Rules
- Keyword-to-Theme: Define which keywords or phrases correspond to each theme.
- Emotion-to-Theme: Link specific emotions to relevant themes based on context.
- Learning-to-Theme: Associate learning outcomes with themes that naturally convey them.

B. Implement Mapping Logic
- Automated Scripts: Develop scripts to automatically assign themes, emotions, and learnings based on extracted keywords and detected emotions.
- Thresholds: Set confidence thresholds to ensure accurate mappings (e.g., only assign a theme if keyword match score > 0.7).

C. Multi-label Assignments
- Allow Multiple Assignments: A single movie can have multiple themes, emotions, and learnings.
- Prioritize Primary Themes: Assign primary and secondary themes based on relevance and prominence.