# 🧠 Explainable NLP Model for Disease Prediction 🩺

This repository contains the code implementation for the paper **"Explainable ML Model for Disease Representation and Prediction"**. The project aims to build a disease prediction model using Natural Language Processing (NLP) techniques and advanced deep learning models to analyze Electronic Health Records (EHR) data. The goal is to predict diseases based on medical history while providing interpretable results for healthcare professionals.

## 📜 **Abstract**
This project implements an NLP-based disease prediction model, fine-tuning a **RoBERTa** model for medical diagnosis prediction based on EHR data. The model is designed to predict diseases like **Heart Failure (HF)** and **Pancreatic Cancer (PaCa)** and provide interpretable results using **SHAP** values to help medical experts understand the model’s predictions.

---

## 🛠️ **Methodology**

### 1. **Dataset**
We use the **Truven Health MarketScan® Research Database (2015)**, which includes EHRs and metadata like ICD-9 codes, demographics, and medical history. The dataset contains over **115 million records** that are preprocessed and tokenized for training the model.

### 2. **Disease Model**
The disease prediction model is built on the **RoBERTa** architecture, which is fine-tuned for medical diagnosis tasks using EHR data. The model is trained to predict future diseases based on a patient’s medical history encoded as ICD-9 codes.

#### **Pretraining**
- **Model**: RoBERTa base configuration (12 layers, 12 attention heads, 768 hidden size).
- **Task**: Masked Language Model (MLM) pretraining using EHR sequences to learn disease representations.
  
#### **Finetuning**
- **Task**: Predicting specific diseases using the fine-tuned RoBERTa model for two case studies:
  - **Diabetes & Heart Failure (DHF) Prediction**
  - **Pancreatic Cancer (PaCa) Prediction**

### 3. **Explainability with SHAP**
- **SHAP (SHapley Additive exPlanations)** is used to interpret the model's predictions, providing global and local explanations for the output.
  - **Global explanations** show feature importance across the dataset.
  - **Local explanations** analyze individual patient predictions, showing which medical codes influence the model’s decision.

---

## 📊 **Results**

### 1. **Evaluation Metrics**
The model’s performance is evaluated using:
- **AUC** (Area Under Curve)
- **F1 Score**
- **Accuracy**
- **Precision**
- **Recall**

### 2. **Performance Comparison**

| Task       | Model         | AUC   | F1 Score | Accuracy | Precision | Recall |
|------------|---------------|-------|----------|----------|-----------|--------|
| DHF        | MedBERT       | 89.63 | 89.63    | 89.63    | 89.57     | 89.67  |
| DHF        | Our Model     | 89.99 | 89.99    | 89.99    | 90.00     | 89.99  |
| PaCa       | MedBERT       | 89.06 | 89.05    | 89.06    | 89.69     | 88.42  |
| PaCa       | Our Model     | 89.11 | 89.11    | 91.11    | 89.70     | 88.56  |

