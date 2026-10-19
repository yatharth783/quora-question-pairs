# quora-question-pairs
A Natural Language Processing (NLP) and Machine Learning project that explores whether two questions have the same meaning. The project compares a Bag of Words (BoW) baseline with models that use basic and advanced engineered text features.
**Problem Statement**
Question-and-answer platforms can contain many questions that ask the same thing using different wording. This project treats duplicate-question detection as a binary classification task and predicts whether a pair of questions is duplicate or non-duplicate.
- 1 — duplicate questions
- 0 — non-duplicate questions
**Project Notebooks**
| Notebook | Purpose |
|---|---|
| `initial_EDA.ipynb` | Exploratory Data Analysis (EDA), target-label distribution, and dataset inspection. |
| `only_bow.ipynb` | Baseline model using Bag of Words representations of both questions. |
| `bow_with_basic_feature.ipynb` | BoW combined with basic text features such as word counts, common words, and word-share features. |
| `bow_with_preproceesing_and_advanced_feature.ipynb` | Text preprocessing, advanced engineered features, fuzzy matching, t-SNE visualizations, and model experiments. |
**Workflow**
1. Load and inspect the question-pair dataset.
2. Explore duplicate and non-duplicate question pairs.
3. Clean and preprocess question text where required.
4. Convert questions into numerical representations using CountVectorizer (Bag of Words).
5. Create additional features to describe the question pairs.
6. Train and evaluate classification models.
7. Visualize selected engineered features and their patterns.
**Features Explored**
Bag of Words
CountVectorizer converts text into numeric word-count vectors. The notebooks experiment with different vocabulary limits and use the vectors for both questions as model input.
Basic Features
- Character length and word count of each question
- Number of common words
- Total words across both questions
- Word-share ratio
Advanced Features
- Common-word and common-token overlap measures
- Stopword-related overlap features
- First-word and last-word equality
- Absolute question-length difference and mean length
- Longest common substring ratio
- Fuzzy matching scores, including QRatio, partial_ratio, token_sort_ratio, and token_set_ratio
- t-SNE 2D and 3D visualizations of engineered features
Feature definitions depend on the implementation in each notebook.
Machine Learning Models
The notebooks experiment with:
- Random Forest Classifier
- XGBoost Classifier
The code uses a train/test split and evaluates predictions using accuracy and confusion matrices in the model experiments. The notebooks use different feature configurations, so their scores should not be compared directly unless the data split and evaluation setup are made consistent.
Dataset
The notebooks expect a train.csv dataset accessible at /content/train.csv in Google Colab. The dataset should contain question-pair fields such as:
- question1
- question2
- is_duplicate
- id, qid1, and qid2 (where available)
The dataset is not included in this repository by this README. Upload it to your Colab session or change the path in the notebooks to match your environment. Check the dataset's terms before redistributing it publicly.
**Requirements**
The notebooks use Python and common data science/NLP libraries, including:
- NumPy and Pandas
- Matplotlib and Seaborn
- scikit-learn
- NLTK
- FuzzyWuzzy
- distance
- Plotly
- XGBoost
- Beautiful Soup (bs4)
**How to Run**
1. Clone or download this repository.
2. Open a notebook in Google Colab or Jupyter Notebook.
3. Upload train.csv to the Colab session, or update the dataset path in the notebook.
4. Install any missing dependencies.
5. Run the notebook cells from top to bottom.
6. Compare the BoW baseline with the basic-feature and advanced-feature experiments.
**Limitations and Notes**
- Model performance depends on the dataset sample, preprocessing, features, and model settings.
- Some experiments use sampled data; results should not be assumed to represent full-dataset performance.
- The notebooks are experimental and may need small changes for newer library versions.
**Future Improvements**
- Add a reusable function to predict whether two user-provided questions are duplicates.
- Compare BoW with TF-IDF, sentence embeddings, or transformer-based models.
- Tune model hyperparameters with cross-validation.
- Package preprocessing and prediction into a reproducible pipeline.
- Build a simple web interface for interactive question-pair comparison.
  
**Tech Stack**
Python · Pandas · NumPy · NLTK · scikit-learn · XGBoost · FuzzyWuzzy · Plotly · Matplotlib · Seaborn · Google Colab
