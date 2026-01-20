# Disease Prediction Using Machine Learning

This project demonstrates how machine learning can be used to predict possible diseases based on patient symptoms.
It implements a complete supervised learning workflow, from data preprocessing to model training, evaluation, and user-input prediction.

The project is designed for learning and academic purposes and focuses on understanding how classification models work on healthcare-related data.

---

## 🎯 Project Objective

The main objective of this project is to:
- Understand supervised machine learning
- Learn how symptoms can be used as input features
- Train a model to predict diseases
- Build an end-to-end machine learning pipeline
- Add a user-input based prediction system

---

## 🧠 Machine Learning Problem Type

- **Learning Type:** Supervised Learning  
- **Problem Type:** Multiclass Classification  
- **Algorithm Used:** Random Forest Classifier  

This is a multiclass classification problem because the output can be one of many disease classes.

---

## 📂 Dataset Description

- **Source:** Kaggle – Disease Prediction Using Machine Learning dataset  

### Dataset Structure:
- Each row represents a patient record
- Each column represents a symptom
- Symptoms are encoded as:
  - `1` → symptom present
  - `0` → symptom absent
- The target column is `prognosis`, which contains the disease name

Two datasets are used:
- `Training.csv` → used to train the model
- `Testing.csv` → used to evaluate the model on unseen data

---

## 🧹 Data Preprocessing

Before training the model, the dataset is cleaned to ensure consistency.

### Steps performed:
- Removed unnecessary or unnamed columns (such as `Unnamed: 133`)
- Ensured both training and testing datasets have the same features
- Checked for duplicate columns

This step is important because machine learning models require identical feature sets during training and testing.

---

## 🔀 Feature and Label Separation

The dataset is split into:
- **Features (X):** All symptom columns (input data)
- **Labels (y):** The `prognosis` column (output to predict)

This separation allows the model to learn the relationship between symptoms and diseases.

---

## 🌲 Model Selection: Random Forest Classifier

Random Forest is an ensemble learning algorithm that:
- Builds multiple decision trees
- Combines their predictions using majority voting
- Reduces overfitting compared to a single decision tree

### Why Random Forest?
- Works well with high-dimensional data (many symptoms)
- Handles complex patterns
- Requires minimal parameter tuning
- Suitable for classification problems

---

## 🏋️ Model Training

The Random Forest model is trained using the training dataset.

During training:
- The model learns patterns between symptoms and diseases
- No rules are hardcoded
- Learning happens purely from the data

The trained model stores this knowledge for future predictions.

---

## 📊 Model Evaluation

The trained model is evaluated using the testing dataset.

### Evaluation Metric:
- **Accuracy**

Accuracy represents the percentage of correct predictions made by the model on unseen data.

### Result:
- The model achieved approximately **97% accuracy**

This indicates strong performance for a learning-based project.

---

## 🧪 User Input Disease Prediction (Interactive Feature)

In addition to dataset-based evaluation, a user-input prediction feature is implemented.

### How it works:
1. The user enters a list of symptoms
2. A binary input vector is created matching the training feature set
3. Entered symptoms are marked as `1`, others as `0`
4. The input is passed to the trained model
5. The model predicts the most likely disease

### Example:
```python
user_symptoms = ["fever", "cough", headache"]
predict_disease(user_symptoms)
