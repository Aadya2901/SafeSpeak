# 🛡️ SafeSpeak — Multilingual Toxic Comment Classification

## 🚀 Overview

**SafeSpeak** is an NLP-based system designed to detect toxic and harmful comments across multilingual text data. It leverages a pretrained transformer model to enable accurate and scalable moderation of user-generated content.

Developed during a global AI datathon, SafeSpeak addresses real-world challenges such as multilingual understanding and contextual toxicity detection.

---

## 🎯 Problem Statement

Online platforms face increasing challenges in moderating toxic content, especially in multilingual environments. Traditional models often fail to generalize across languages and capture contextual meaning.

**SafeSpeak aims to:**

* Detect toxic comments across multiple languages
* Provide robust classification using modern NLP techniques
* Optimize performance using **ROC-AUC metric**

---

## 📊 Dataset

* Dataset provided during the hackathon

* Contains:

  * Multilingual text comments
  * Binary labels:

    * `0 → Non-toxic`
    * `1 → Toxic`

* The dataset is relatively balanced, which helps in unbiased model training.

---

## 📊 Dataset Analysis

![Label Distribution](graph.png)

The dataset shows a near-balanced distribution of toxic and non-toxic samples.

---

## ⚙️ Approach

### 🧹 Data Preprocessing

* Lowercasing text
* Removing URLs and special characters
* Basic normalization while preserving Hindi and English text

---

### 🧠 Model Architecture

We use a pretrained transformer model:

👉 **textdetox/bert-multilingual-toxicity-classifier (Hugging Face)**

**Why this model?**

* Supports multilingual text (Hindi + English)
* Captures contextual semantics
* Leverages transfer learning for better performance

---

### 🔤 Tokenization

* Used Hugging Face tokenizer
* Converts text into tokenized format for BERT

---

### 🏋️ Model Training

* Fine-tuned pretrained model on dataset
* Optimized using:

  * Epoch tuning
  * Batch size adjustment

---

### 📏 Evaluation Metric

* Primary Metric: **ROC-AUC**
* Evaluates how well the model distinguishes toxic vs non-toxic comments

---

## 📈 Results

* **Train ROC-AUC Score: 0.85**
* Strong multilingual classification performance
* Effective handling of contextual toxicity

---

## 🔍 Example Predictions

```
Input: "you are stupid"
Prediction: 1 (toxic)

Input: "this is amazing"
Prediction: 0 (non-toxic)
```

---

## 🛠️ Tech Stack

* Python
* Google Colab
* Hugging Face Transformers
* Scikit-learn
* Pandas, NumPy, Matplotlib

---

## ▶️ How to Run

1. Install dependencies:

```
pip install -r requirements.txt
```

2. Run the notebook:

```
Execute all cells in bert_notebook.ipynb
```

3. Output:

* Generates `no_label.csv` with predicted labels

---

## ⚙️ Reproducibility

The solution is **device-agnostic** and runs on both CPU and GPU environments.

---

## 💡 Key Features

* 🌍 Multilingual support
* ⚡ Transformer-based architecture
* 📊 ROC-AUC based evaluation
* 🧠 Transfer learning approach

---

## 🔮 Future Improvements

* Use advanced models like XLM-RoBERTa
* Apply class balancing techniques
* Deploy as a real-time moderation API

---

## 🤝 Conclusion

SafeSpeak demonstrates an effective and scalable approach to multilingual toxicity detection. By leveraging pretrained transformer models, it achieves strong performance while maintaining efficiency.

---

## 📎 Submission

* Public GitHub repository
* Complete runnable code
* `no_label.csv` with predictions
* Reproducible pipeline

---

💡 *“Simple, well-executed solutions outperform complex, incomplete ones.”*
