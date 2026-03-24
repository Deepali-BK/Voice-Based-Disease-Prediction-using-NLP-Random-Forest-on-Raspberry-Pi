# 🏥 Interactive Health Bot

### Voice-Based Disease Prediction using NLP & Random Forest on Raspberry Pi

---

## 📌 Overview

The **Interactive Health Bot** is an edge-based AI system that predicts diseases from user-reported symptoms using a **voice-driven interface**. The system converts speech to text, extracts meaningful symptoms using **Natural Language Processing (NLP)**, and classifies possible diseases using a **Random Forest model**.

The solution is deployed on a **Raspberry Pi**, enabling a low-cost, real-time healthcare assistant with both **audio and graphical feedback**.

> 🏆 Designed a bot on classifying diseases from user symptoms extracted with help of NLP using Random Forest Classifier on a Raspberry Pi achieving an accuracy of **95.02%**. Received a funding of **₹37,000** by Innovative and Entrepreneurship Development Centres (IEDC) from Indian Govt.

---

## 🚀 Features

* 🎙️ Voice-based symptom input (Speech-to-Text)
* 🧠 NLP pipeline for symptom extraction
* 🔍 Fuzzy matching & synonym detection for better accuracy
* 🌳 Random Forest-based disease prediction
* 📊 Probability-based output with iterative refinement
* 🔊 Text-to-Speech feedback
* 🖥️ GUI using Tkinter
* ⚡ Edge deployment on Raspberry Pi

---

## 🧩 System Architecture
```
User Speech Input
        ↓
Speech-to-Text (STT)
        ↓
NLP Processing Pipeline
        ↓
Symptom Extraction & Matching
        ↓
Random Forest Classifier
        ↓
Disease Prediction (with probabilities)
        ↓
Text-to-Speech (TTS) + GUI Output
```

---

## 🧠 NLP Pipeline

### 1. Speech Processing

* Audio input captured via microphone
* Converted to text using Speech Recognition APIs
* Output passed as raw string for NLP processing

### 2. Text Preprocessing

* Tokenization (`word_tokenize`)
* Stopword removal
* Stemming (Porter Stemmer)
* Lemmatization (WordNet Lemmatizer)

### 3. Feature Extraction

* Part-of-Speech (POS) tagging
* Extraction of symptom-relevant tokens (nouns/adverbs)
* N-gram generation (bi-grams, tri-grams)

### 4. Semantic Matching

* Synonym expansion using WordNet
* Fuzzy matching using Levenshtein distance
* Phonetic matching using:
  * Soundex
  * Metaphone

### 5. Output Validation

* Extracted symptoms verified via user interaction (Yes/No)
* Final symptom list passed to classifier

---

## 🌳 Machine Learning Model

### Model Used

* **Random Forest Classifier**

### Key Steps

* Label Encoding of target variable (diseases)
* Binary symptom representation (1 = present, 0 = absent)
* Training using Scikit-learn

### Important Parameters

* `n_estimators = 10` (optimized experimentally)

### Core Methods Used

* `fit()` – Train model
* `fit_transform()` – Encode target variable
* `predict_proba()` – Get disease probabilities
* `classes_` – Retrieve disease labels

---

## 🔄 Prediction Workflow

1. Extract symptoms from NLP pipeline
2. Create filtered dataset (`df_copy`) based on input symptoms
3. Compute probability of possible diseases
4. Remove least probable diseases
5. If any disease probability > **0.7 → return prediction**
6. Else:
   * Prompt user for additional symptoms
   * Iterate (max 2 times)
7. Output:
   * Identified symptoms
   * Possible diseases
   * Probability scores

---

## 🖥️ User Interface

* Built using **Tkinter**
* Provides:
  * Visual symptom confirmation
  * Audio feedback (TTS)
  * Interactive Q&A flow

---

## 🛠️ Tech Stack

**Languages & Libraries**

* Python
* NLTK
* Pandas
* Scikit-learn

**Speech Processing**

* SpeechRecognition
* gTTS
* pyttsx3

**Algorithms & Techniques**

* NLP (Tokenization, Lemmatization, POS Tagging)
* Fuzzy Matching (Levenshtein Distance)
* Phonetic Matching (Soundex, Metaphone)
* Random Forest Classification

**Hardware**

* Raspberry Pi

---

## 📊 Results

* ✅ Achieved **95.02% classification accuracy**
* ⚡ Real-time inference on edge device
* 💰 Received **₹37,000 funding** by Innovative and Entrepreneurship Development Centres (IEDC) from Indian Govt.

---
## 📄 Publication

> [Symptoms Extraction from a Voice Input using Natural Language Processing](https://www.ijert.org/research/symptoms-extraction-from-a-voice-input-using-natural-language-processing-IJERTV9IS040645.pdf)
> — *International Journal of Engineering Research & Technology (IJERT)*

---

## 🔮 Future Improvements

* Integration with larger medical datasets
* Deep learning-based NLP (BERT, transformers)
* Mobile/web deployment
* Multi-language support
* Improved real-time latency optimization

---

## 📜 License

This project is for academic and research purposes.
