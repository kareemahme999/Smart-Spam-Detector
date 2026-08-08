<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=30&duration=3000&pause=1000&color=2E74B5&center=true&vCenter=true&width=650&lines=Optimized+Spam+Detection+System;Machine+Learning+%7C+NLP+%7C+Classification;Naive+Bayes+%C2%B7+SVM+%C2%B7+Random+Forest;Powered+by+Scikit-Learn+%F0%9F%A4%96" alt="Typing SVG" />

<br/>

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-1E7B34?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)

**An end-to-end Machine Learning pipeline that classifies SMS/email messages as `Spam` or `Ham` — from raw text to a production-ready, saved model.**

<img src="https://media4.giphy.com/media/qgQUggAC3Pfv687qPC/giphy.gif" width="500"/>

</div>

---

## 📌 Overview

Spam messages don't just clutter inboxes — they carry phishing links, scams, and malicious content that put users at risk. This project builds an **Optimized Spam Detection System** for an Email Service Provider client: a machine-learning pipeline that automatically flags incoming messages as spam or legitimate, with high accuracy and a low false-positive rate so real messages never get lost.

Five models were trained, evaluated, and compared — then the best one was fine-tuned with hyperparameter search and saved for deployment.

> 🏆 **Best model:** Optimized SVM (GridSearchCV-tuned) — **97.87% test accuracy**

---

## ✨ Features

- 🧹 **Full text-cleaning pipeline** — lowercasing, URL removal, noise stripping
- 🔤 **TF-IDF feature extraction** with English stop-word removal
- 🤖 **5 models trained & compared**: Naive Bayes, Logistic Regression, SVM, Random Forest, and a hyperparameter-optimized SVM
- 🎯 **GridSearchCV hyperparameter tuning** for the best-performing model
- 📊 **Full evaluation suite** — accuracy, precision, recall, F1-score, confusion matrices
- 💾 **Saved, reusable model** — trained SVM + TF-IDF vectorizer persisted with `joblib`
- 📈 **Spam-probability output** ready (`predict_proba`) for app integration

---

## 🧠 Models & Results

| Model                          | Accuracy   | Spam Precision | Spam Recall | Spam F1 |
|---------------------------------|:----------:|:---------------:|:-----------:|:-------:|
| Naive Bayes                    | 94.78%     | 1.00            | 0.59        | 0.74    |
| Logistic Regression            | 95.45%     | 0.99            | 0.65        | 0.78    |
| SVM (default)                  | 97.20%     | 0.99            | 0.79        | 0.88    |
| Random Forest                  | 96.71%     | 1.00            | 0.74        | 0.85    |
| **Optimized SVM (GridSearchCV)** | **97.87%** | **0.98**        | **0.85**    | **0.91**|

<div align="center">
<img src="https://img.shields.io/badge/🏆_Best_Model-Optimized_SVM_(97.87%25)-1E7B34?style=for-the-badge"/>
</div>

---

## 🗂️ Project Structure

```
spam-detection-system/
├── data/
│   └── spam.csv                  # SMS Spam Collection dataset
├── models/
│   ├── spam_classifier_svm.pkl   # Saved best model (Optimized SVM)
│   └── tfidf_vectorizer.pkl      # Saved TF-IDF vectorizer
├── notebooks/
│   └── main.ipynb                # Full pipeline: EDA → cleaning → training → evaluation
├── README.md
└── requirements.txt
```

---

## ⚙️ Tech Stack

| Category        | Tools |
|------------------|-------|
| Language          | Python 3.10+ |
| Data handling      | Pandas, NumPy |
| ML / NLP          | Scikit-learn (TF-IDF, Naive Bayes, Logistic Regression, SVM, Random Forest) |
| Visualization      | Matplotlib |
| Model persistence  | Joblib |

---

## 🚀 Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/<your-username>/spam-detection-system.git
cd spam-detection-system
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Run the notebook
```bash
jupyter notebook notebooks/main.ipynb
```

### 4. Use the saved model
```python
import joblib

model = joblib.load("models/spam_classifier_svm.pkl")
vectorizer = joblib.load("models/tfidf_vectorizer.pkl")

message = ["Congratulations! You've WON a $1000 gift card. Click here now!"]
features = vectorizer.transform(message)

prediction = model.predict(features)[0]
probability = model.predict_proba(features)[0]

print("Spam" if prediction == 1 else "Ham")
print(f"Spam probability: {probability[1]*100:.1f}%")
```

---

## 📊 Dataset

- **Name:** SMS Spam Collection Dataset
- **Source:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/) (Kaggle mirror available)
- **Size:** 5,572 messages → 5,169 after deduplication
- **Classes:** Ham (87.4%) / Spam (12.6%)

---

## 🔮 Future Improvements

- [ ] Add stemming / lemmatization to the preprocessing pipeline
- [ ] Try word embeddings (Word2Vec, FastText) instead of TF-IDF
- [ ] Deploy as a Streamlit web app with live spam-probability scoring
- [ ] Add cross-validation-based confidence intervals to the comparison table

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!
Feel free to check the [issues page](../../issues) or open a pull request.

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

<div align="center">

### 📬 Contact

**TechMaster Academy** · Phase 03 / Project 03
techmasterr.official@gmail.com

<sub>Built with ❤️ and a lot of TF-IDF vectors.</sub>

</div>
