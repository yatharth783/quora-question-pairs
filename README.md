
# Quora Question Pair Similarity using NLP
A Natural Language Processing (NLP) and Machine Learning project that explores whether two questions have the same meaning. The project compares a Bag of Words (BoW) baseline with models that use basic and advanced engineered text features.

## 🚀 Project Notebooks

This project includes four Jupyter notebooks covering EDA, baseline modelling, feature engineering, and advanced text preprocessing.

## 📌 Features

- Exploratory Data Analysis (EDA)
- Text preprocessing using NLP techniques
- Bag of Words (BoW) feature extraction
- Basic text features such as character length and word count
- Advanced features for question-pair comparison
- Common word and token-overlap analysis
- Fuzzy matching features
- t-SNE visualization of engineered features
- Duplicate and non-duplicate question classification

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- NLTK
- XGBoost
- FuzzyWuzzy
- Plotly
- Google Colab / Jupyter Notebook

### Workflow

```text
Question Pair Input
        ↓
Text Preprocessing
        ↓
Exploratory Data Analysis
        ↓
Bag of Words (BoW)
        ↓
Feature Engineering
        ↓
Machine Learning Model
        ↓
Duplicate / Non-Duplicate Prediction
```

## 📂 Project Structure

```text
NLP-Question-Pair-Similarity/
│
├── initial_EDA.ipynb
├── only_bow.ipynb
├── bow_with_basic_feature.ipynb
├── bow_with_preproceesing_and_advanced_feature.ipynb
└── README.md
```

## 📊 Notebooks Description

- **initial_EDA.ipynb:** Explores the dataset and analyzes question-pair patterns.
- **only_bow.ipynb:** Implements a baseline approach using Bag of Words features.
- **bow_with_basic_feature.ipynb:** Combines BoW with basic text features.
- **bow_with_preproceesing_and_advanced_feature.ipynb:** Explores text preprocessing, advanced feature engineering, fuzzy matching, and visualization.

## 📁 Dataset

The notebooks use a Quora Question Pairs-style dataset containing two questions and a target label indicating whether the questions are duplicates.

Expected columns include:
- `question1`
- `question2`
- `is_duplicate`

The dataset must be available at the file path specified in the notebook.

## ⚙️ Installation

Install the required Python libraries:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn nltk xgboost fuzzywuzzy distance plotly
```

For notebooks using NLTK stopwords:

```python
import nltk
nltk.download('stopwords')
```

## ▶️ How to Run

1. Clone or download this repository.
2. Open the notebook in Google Colab or Jupyter Notebook.
3. Upload the dataset and update its file path if required.
4. Install any missing dependencies.
5. Run the notebook cells sequentially.
6. Compare the different feature-engineering approaches and model results.

## 🔮 Future Improvements

- Add TF-IDF and word embedding approaches.
- Experiment with transformer-based sentence embeddings.
- Evaluate models using precision, recall, F1-score, and ROC-AUC.
- Build an interactive web application for question-pair predictions.
- Improve model performance through hyperparameter tuning.

