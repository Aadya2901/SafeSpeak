# 🛡️ SafeSpeak — Multilingual Toxic Comment Classification

## 🚀 Overview 

**SafeSpeak** is an intelligent NLP-based system designed to detect toxic and harmful comments across multiple languages. It leverages state-of-the-art transformer models to enable accurate, scalable moderation of user-generated content.

Developed during a global AI datathon, SafeSpeak addresses real-world challenges such as multilingual understanding and class imbalance in text classification.

---

## 🎯 Problem Statement

Online platforms face increasing challenges in moderating toxic content, especially in multilingual environments. Traditional models often fail to generalize across languages and struggle with imbalanced datasets.

**SafeSpeak aims to:**

* Detect toxic comments across multiple languages
* Provide robust classification using modern NLP techniques
* Optimize performance using **ROC-AUC metric**

---

## 📊 Dataset

* Dataset provided at the start of the hackathon
* Contains:

  * Multilingual text comments
  * Binary toxicity labels
* Highly imbalanced (majority non-toxic samples)

---

## ⚙️ Approach

### 🧹 Data Preprocessing

* Lowercasing text
* Removing URLs and special characters
* Basic text normalization

---

### 🧠 Model Architecture

We use **transfer learning** with a pretrained transformer model:

👉 **Multilingual BERT / DistilBERT**

**Why this approach?**

* Supports multiple languages
* Captures contextual meaning
* Eliminates need for training from scratch

---

### 🔤 Tokenization

* Utilized pretrained tokenizer from HuggingFace
* Converts raw text into model-readable format

---

### 🏋️ Model Training

* Fine-tuned the pretrained model on the dataset
* Optimized using:

  * Learning rate tuning
  * Epoch selection
  * Batch size adjustment

---

### 📏 Evaluation Metric

* Primary Metric: **ROC-AUC**
* Suitable for imbalanced datasets
* Measures classification performance effectively

---

## 🧪 Experiments & Improvements

* Built a baseline model for initial benchmarking
* Transitioned to transformer-based approach
* Iteratively improved performance via tuning

---

## 📈 Results

* Achieved strong ROC-AUC score on validation data
* Demonstrated effective multilingual classification
* Robust performance on imbalanced data

---

## 🛠️ Tech Stack

* Python
* Google Colab
* Hugging Face Transformers
* Scikit-learn
* Pandas, NumPy

---

## 💡 Key Features

* 🌍 Multilingual support
* ⚡ Efficient transformer-based architecture
* 📊 Robust evaluation using ROC-AUC
* 🧠 Transfer learning for faster development

---

## 🔮 Future Improvements

* Use advanced models like XLM-RoBERTa
* Apply data balancing techniques (SMOTE, class weights)
* Deploy as a real-time moderation API

---

## 🤝 Conclusion

SafeSpeak demonstrates a scalable and effective approach to detecting toxic content in multilingual environments. By leveraging pretrained transformer models, it achieves strong performance while maintaining efficiency.

---

## 📎 Submission

* Clean and reproducible code
* Modular pipeline
* Well-documented implementation

---

💡 *“Simple, well-executed solutions outperform complex, incomplete ones.”*
