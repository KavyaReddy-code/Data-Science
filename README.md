# 🚨 Early Brand Crisis Detection using Hybrid NLP, ML, and Deep Learning

## 📌 Project Overview
This project focuses on **early detection of brand crises** using social media data by combining **Natural Language Processing (NLP), Machine Learning (ML), Deep Learning (DL), and anomaly detection techniques**.

The system analyzes sentiment trends over time and identifies potential crisis signals before they escalate, enabling proactive decision-making.

---

## 🎯 Objectives
- Perform **sentiment analysis** on social media text (positive, negative, neutral)
- Compare **ML, LSTM, and BERT models**
- Detect **anomalies in negative sentiment trends**
- Develop a **hybrid crisis score**
- Identify **early warning signals (lead-time detection)**

---

## 📊 Dataset Overview
- **Total records:** 10,000 social media posts
- **After deduplication:** 216 unique texts
- **Classes:** Positive, Negative, Neutral (balanced)
- **Final split:**
  - Training: 172
  - Testing: 44

⚠️ **Key Insight:**  
97.8% duplicate content was found, which initially caused **data leakage** and unrealistic model performance.

---

## ⚙️ Methodology

### 1. Data Preprocessing
- Removed URLs, mentions, punctuation, numbers
- Text normalization and cleaning
- Deduplication to remove repeated content

### 2. Models Implemented

#### 🔹 Machine Learning (Baseline)
- Logistic Regression
- Linear SVM
- TF-IDF feature extraction

#### 🔹 Deep Learning
- Bidirectional LSTM

#### 🔹 Transformer Model
- BERT (`bert-base-uncased`)

---

## 📈 Model Performance

| Model | Accuracy | Precision | Recall | F1-score |
|------|---------:|----------:|-------:|---------:|
| Logistic Regression | 0.6818 | 0.6974 | 0.6818 | 0.6854 |
| Linear SVM | 0.6818 | 0.7146 | 0.6818 | 0.6851 |
| LSTM | 0.3409 | 0.1162 | 0.3409 | 0.1733 |
| BERT | **0.7727** | **0.7666** | **0.7727** | **0.7652** |

✅ **Best Model:** BERT  
❌ **LSTM Limitation:** Failed due to small dataset size

---

## 📉 Time-Series Analysis
- Daily and weekly sentiment trends analyzed
- 7-day moving average applied for smoothing
- Negative sentiment spikes identified over time

---

## 🚨 Anomaly Detection

### Methods Used
- Z-score (statistical)
- Isolation Forest (machine learning)

| Method | Anomalies Detected |
|--------|-------------------:|
| Z-score | 6 |
| Isolation Forest | 34 |
| Agreed Anomalies | 1 |

---

## ⚡ Hybrid Crisis Score
A custom crisis score was developed using:
- Negative sentiment intensity
- Anomaly detection signals
- Post volume trends

### 📊 Results
- **Peak crisis:** 12 October 2025
- **Crisis score:** 0.886
- **Early warning lead-time:** **68 days**

✅ The model successfully detected signals **before the crisis peak**

---

## 🔍 Key Findings
- Data quality is more important than data size
- Removing duplicates prevents **data leakage**
- Traditional ML models perform well on small datasets
- LSTM fails with limited data
- BERT performs best due to **contextual understanding**
- Combining **sentiment + time-series + anomaly detection** improves insights

---

## ⚠️ Limitations
- Small dataset after deduplication (216 samples)
- Limited generalizability
- Only text-based analysis (no images/videos)
- Potential noise in social media data

---

## 🔮 Future Work
- Use larger and more diverse datasets
- Include **multimodal analysis (text + images)**
- Improve anomaly detection with deep learning
- Deploy a real-time monitoring system

---

## 🛠️ Technologies Used
- Python
- Scikit-learn
- TensorFlow / Keras
- Hugging Face Transformers
- Pandas
- NumPy
- Matplotlib
- Isolation Forest

---

## 📁 Project Structure
```text
├── data/
├── notebooks/
├── models/
├── results/
└── README.md
