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

  * Multilingual text comments (Hindi + English)
  * Binary labels:

    * `0 → Non-toxic`
    * `1 → Toxic`

* Training set: **8,996 samples** (7,196 train / 1,800 validation after split)
* The dataset is near-balanced, which helps prevent model bias

---

## 📊 Dataset Analysis

![Label Distribution](graph.png)

Training label distribution: `{0: 3602, 1: 3594}` — near-perfectly balanced across both classes.

---

## ⚙️ Approach

### 🧹 Data Preprocessing

* Removing missing values and empty strings
* Removing duplicate entries
* Basic cleaning while preserving Hindi (Devanagari) and English text

---

### 🧠 Model Architecture

We use a pretrained transformer model:

👉 **textdetox/bert-multilingual-toxicity-classifier (Hugging Face)**

**Why this model?**

* Supports multilingual text (Hindi + English)
* Captures contextual semantics
* Leverages transfer learning for better performance on toxicity detection

---

### 🔤 Tokenization

* Used Hugging Face `AutoTokenizer`
* `max_length=128`, padding and truncation enabled
* Converts text into token IDs compatible with BERT

---

### 🏋️ Model Training

* Stratified 80/20 train/validation split
* Fine-tuned pretrained model on the labeled dataset
* Training configuration:
  * Epochs: 3
  * Batch size: 8 (train), 16 (eval)
  * Weight decay: 0.01
  * Warmup steps: 270 (~10% of total steps)

---

### 📏 Evaluation Metric

* Primary Metric: **ROC-AUC**
* Also evaluated with full classification report (precision, recall, F1)

---

## 📈 Results

| Metric | Score |
|---|---|
| Zero-shot ROC-AUC (before fine-tuning) | **0.9989** |
| Fine-tuned ROC-AUC (after training) | **0.9966** |
| Accuracy | **0.97** |
| Macro F1 | **0.97** |

**Classification Report (Validation Set — 1,800 samples):**

```
              precision    recall  f1-score   support

   Non-toxic       0.98      0.97      0.97       901
       Toxic       0.97      0.98      0.97       899

    accuracy                           0.97      1800
   macro avg       0.97      0.97      0.97      1800
weighted avg       0.97      0.97      0.97      1800
```

> Note: The pretrained model already achieves an exceptional zero-shot ROC-AUC of 0.9989, demonstrating strong out-of-the-box multilingual toxicity detection. Fine-tuning maintained this high performance with 0.9966 ROC-AUC.

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
* Google Colab (T4 GPU)
* Hugging Face Transformers
* Scikit-learn
* Pandas, NumPy, Matplotlib

---

## ▶️ How to Run

1. Upload the following files to Colab:
   * `toxic_labeled.xlsx` — training data
   * `toxic_no_label_evaluation.xlsx` — evaluation data

2. Install dependencies (run Cell 1 first, then restart runtime):

```
!pip install -U transformers
```

3. Run the notebook:

```
Execute all cells in bert_notebook.ipynb
```

4. Output:

* Generates `no_label.csv` with predicted labels
* Saves `graph.png` label distribution plot

---

## ⚙️ Reproducibility

* Random seed fixed to `42` across `random`, `numpy`, `torch`, and Hugging Face `set_seed`
* Device-agnostic — runs on both CPU and GPU environments
* All outputs saved in notebook cells for verification

---

## 💡 Key Features

* 🌍 Multilingual support (Hindi + English)
* ⚡ Transformer-based architecture
* 📊 ROC-AUC based evaluation with full classification report
* 🧠 Transfer learning from domain-specific toxicity classifier
* 🔍 Zero-shot baseline comparison included

---

## 🔮 Future Improvements

* Use advanced models like XLM-RoBERTa for broader language coverage
* Apply text augmentation to further improve generalization
* Deploy as a real-time moderation API

---

## 🤝 Conclusion

SafeSpeak demonstrates an effective and scalable approach to multilingual toxicity detection. By leveraging the `textdetox/bert-multilingual-toxicity-classifier` pretrained model, it achieves a **ROC-AUC of 0.9966** on the validation set with **0.97 macro F1**, while maintaining efficiency and full reproducibility.


---

💡 *"Simple, well-executed solutions outperform complex, incomplete ones."*
