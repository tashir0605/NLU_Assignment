# 📰 BBC News Binary Classifier: Sport vs. Politics

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Scikit-Learn](https://img.shields.io/badge/Library-Scikit--Learn-orange)

A Machine Learning project that classifies news articles into **Sport** or **Politics** categories using Natural Language Processing (NLP) techniques. This project compares three supervised learning algorithms, achieving **100% accuracy** with Multinomial Naive Bayes on the test set.

---

## 📊 Key Results

We evaluated three models on a subset of the BBC News Dataset. The **Multinomial Naive Bayes** model proved to be the most effective for this specific task due to the high-dimensional, sparse nature of text data.

| Model | Accuracy | F1-Score |
| :--- | :--- | :--- |
| **Multinomial Naive Bayes** | **100.00%** | **1.00** |
| Support Vector Machine (SVM) | 99.46% | 1.00 |
| Logistic Regression | 98.92% | 0.99 |

### Visual Performance Comparison
*(Upload your 'image_f5bbe6.png' here to show the bar chart)*
![Model Accuracy Comparison](image_f5bbe6.png)

---

## 🧠 Project Overview

### The Goal
Automate the tagging of news articles to streamline content management systems. This project focuses on binary classification between two distinct topics: **Sport** (Label 1) and **Politics** (Label 0).

### The Dataset
* **Source:** [BBC News Dataset](http://mlg.ucd.ie/datasets/bbc.html) (D. Greene and P. Cunningham, 2006).
* **Filtering:** The original 5-category dataset was filtered to retain only `Sport` and `Politics` articles.
* **Total Samples:** 928 documents (511 Sport, 417 Politics).
* **Preprocessing:** Lowercasing, Regex cleaning, Stop-word removal (NLTK), and Lemmatization.

### The Pipeline
1.  **Text Cleaning:** Removing noise (special characters, numbers) and temporal artifacts.
2.  **Feature Extraction:** **TF-IDF (Term Frequency-Inverse Document Frequency)** with a max feature limit of 3,000.
3.  **Modeling:** Training MNB, SVM (Linear Kernel), and Logistic Regression on an 80/20 train-test split.
4.  **Evaluation:** Using Accuracy, Confusion Matrices, and Cross-Validation.

---

## 🔍 Model Interpretation & Insights

While 100% accuracy is often suspicious, our investigation revealed why it happened:

1.  **Distinct Vocabulary:** The intersection of words between Sport (*match, goal, cup*) and Politics (*election, minister, tax*) is minimal.
2.  **Temporal Bias:** Feature importance analysis showed **"Germany"** as the #1 keyword for Sport. This is an artifact of the dataset being from 2004-2005, during preparations for the **2006 FIFA World Cup**.

#### Confusion Matrix
*(Upload your 'image_f5bbae.png' here)*
![Confusion Matrix](image_f5bbae.png)

---

## 🚀 How to Run

### Prerequisites
* Python 3.x
* Jupyter Notebook or Google Colab

### Installation
1.  Clone the repo:
    ```bash
    git clone [https://github.com/your-username/bbc-news-classifier.git](https://github.com/tashir0605/bbc-news-classifier.git)
    ```
2.  Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```

### Usage
Open the `notebook.ipynb` file in Jupyter or Colab and run all cells. The notebook will:
1.  Load and clean the dataset.
2.  Train the models.
3.  Generate the visualization plots.
4.  Output the final classification report.

---

## 📂 Project Structure

```text
├── dataset/
│   └── bbc_data.csv        # The filtered raw data
├── images/                 # Saved plots (Confusion Matrix, Bar Charts)
├── notebook.ipynb          # Main analysis and code
├── README.md               # Project documentation
└── requirements.txt        # Python dependencies

## 📜 License
This project is open-source and available under the MIT License.
