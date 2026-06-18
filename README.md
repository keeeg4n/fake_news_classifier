# Fake News Classifier — truDefender

A machine learning web application that classifies news articles as **FAKE** or **REAL** using Natural Language Processing (NLP). Built with Flask and a Naive Bayes classifier trained on a labelled news dataset.

---

## Abstract

Misinformation and fake news have become a significant challenge in the digital age. truDefender tackles this by leveraging NLP and machine learning to analyse the title and body of a news article and determine whether it is genuine or fabricated. The model is trained using a Naive Bayes classifier on a labelled news dataset, providing fast and reliable predictions through a clean web interface.

---

## How It Works

1. User enters a news **title** and **body text**
2. The text is concatenated and passed to the trained Naive Bayes classifier
3. The model outputs either **FAKE NEWS ⚠️** or **REAL NEWS 👍**

---

## Model

Three classification approaches were explored in the notebooks:

| Model | Notebook |
|---|---|
| Naive Bayes | `notebooks/Fake News Classifier.ipynb` |
| Logistic Regression | `notebooks/news-classification-logistic-regression.ipynb` |
| Stochastic Gradient Descent | `notebooks/news-classification-stochastic-gradient-descent.ipynb` |

The best performing model is saved as `model/fake_news_classification.pkl` and served via the Flask app.

---

## Tech Stack

| Category | Tools |
|---|---|
| Language | Python |
| Web Framework | Flask |
| ML / NLP | scikit-learn, joblib |
| Data Handling | Pandas, NumPy |
| Visualisation | Seaborn, Plotly |
| Frontend | Bootstrap 5, Jinja2 |

---

## Project Structure

```
fake_news_classifier/
├── server.py                   # Flask web application
├── fake_news_model.py          # Model loader and prediction logic
├── requirements.txt
├── model/
│   ├── fake_news_classification.pkl          # Trained Naive Bayes model
│   └── news.csv                              # Dataset
├── notebooks/
│   ├── Fake News Classifier.ipynb
│   ├── news-classification-logistic-regression.ipynb
│   └── news-classification-stochastic-gradient-descent.ipynb
├── templates/
│   ├── base.html
│   ├── index.html
│   └── fake_news.html
└── static/
    └── res/img/
```

---

## Requirements

- Python 3.8+

```bash
pip install flask joblib scikit-learn seaborn
```

---

## Usage

**Step 1 — Clone the repository**
```bash
git clone https://github.com/keeeg4n/fake_news_classifier.git
cd fake_news_classifier
```

**Step 2 — Create and activate a virtual environment**
```bash
python3 -m venv venv

# Linux / macOS
source venv/bin/activate

# Windows
venv\Scripts\activate
```

**Step 3 — Install dependencies**
```bash
pip install -r requirements.txt
```

**Step 4 — Run the app**
```bash
python server.py
```

**Step 5 — Open in browser**

Navigate to `http://127.0.0.1:5000`, enter a news title and body, and click **Check**.

---

## Applications

- **Media Literacy:** Helps readers verify news before sharing
- **Social Media Moderation:** Can be integrated as a content screening tool
- **Journalism:** Assists fact-checkers in flagging suspicious articles

---

## Advantages & Limitations

**Advantages**
- Fast inference — results in milliseconds
- Lightweight model, no GPU required
- Works on any news article regardless of topic

**Limitations**
- Model accuracy depends on the quality and diversity of training data
- May struggle with satirical content or opinion pieces
- Not a definitive fact-checking tool — always verify with trusted sources
