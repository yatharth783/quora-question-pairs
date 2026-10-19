
# Quora Question Pairs — AI-Powered Question Similarity

### Are these questions really the same?

An ML-powered web application that compares two questions and predicts whether they are duplicates. Built using Python, scikit-learn, and Streamlit.

## Features

- Compare two questions and predict Duplicate or Not Duplicate.
- Text preprocessing and feature engineering.
- Random Forest with engineered features and Bag-of-Words.
- TF-IDF + Logistic Regression with word and character n-grams.
- Model evaluation using accuracy, precision, recall, F1-score, and confusion matrix.
- Dark-themed Streamlit interface.
- Saved model comparison metrics.

## Tech Stack

- Python
- Streamlit
- pandas and NumPy
- scikit-learn
- NLTK
- Beautiful Soup
- fuzzywuzzy
- distance
- joblib

## Model Performance

Reported results from a comparison run on 80,858 rows:

| Model | Accuracy | Precision | Recall | F1-score |
|---|---:|---:|---:|---:|
| Random Forest | 80.31% | 74.90% | 70.18% | 72.46% |
| TF-IDF + Logistic Regression | 79.52% | 68.30% | 83.12% | 74.98% |

**Important:** These are experimental results. Verify that the comparison test data was excluded from training both models before presenting these metrics as a fair benchmark.

### Understanding the Metrics

- **Accuracy:** Percentage of all predictions that are correct.
- **Precision:** How often a predicted duplicate is actually a duplicate.
- **Recall:** How many actual duplicate pairs the model identifies.
- **F1-score:** Balance between precision and recall.

In the reported comparison, Logistic Regression achieved higher recall and F1-score, while Random Forest achieved higher accuracy and precision.

## Project Structure

```text
quora-question-pairs/
├── app.py
├── train_model.py
├── train_tfidf_model.py
├── compare_models.py
├── requirements.txt
├── train.csv
└── models/
    ├── quora_rf_model.pkl
    ├── count_vectorizer.pkl
    ├── stopwords.pkl
    ├── metadata.json
    ├── quora_tfidf_lr_model.pkl
    ├── comparison_test.csv
    ├── tfidf_lr_results.json
    └── model_comparison_results.json
```

This structure is illustrative; your actual files may differ. Avoid uploading large datasets or artifacts that should not be public.

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/yatharth783/quora-question-pairs.git
cd quora-question-pairs
```

### 2. Create a Virtual Environment (Windows CMD)

```cmd
python -m venv .venv
.venv\Scripts\activate
```

### 3. Install Dependencies

```cmd
python -m pip install -r requirements.txt
```

### 4. Run the Application

```cmd
python -m streamlit run app.py
```

Streamlit will provide a local URL, usually `http://localhost:8501`.

## Training Models

The training scripts expect `train.csv` with these columns:

- `question1`
- `question2`
- `is_duplicate`

Labels:
- `1` = Duplicate questions
- `0` = Non-duplicate questions

Train and evaluate using:

```cmd
python train_model.py
python train_tfidf_model.py
python compare_models.py
```

Run only the scripts you need and ensure the required dependencies and dataset are available.

**For a fair comparison:** Train both models on the same training split and evaluate them on the same untouched test split. Prevent test data from leaking into training or vectorizer fitting.

## Limitations

- Predictions are estimates and may be incorrect.
- Similar words do not always mean similar intent.
- TF-IDF represents statistical word and character patterns; it does not fully understand meaning like a human.
- Results depend on preprocessing, dataset splits, and model settings.
- The reported metrics should not be treated as a definitive fair benchmark until train/test separation is verified.

## Future Improvements

- Fair, leakage-free model benchmarking.
- Hyperparameter and classification-threshold tuning.
- More detailed error analysis.
- Explore sentence embeddings or transformer-based models.
- Add automated tests and deploy the Streamlit application.

