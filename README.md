#  UCI Bank Marketing — Machine Learning & Deep Learning

A binary classification project using the **UCI Bank Marketing dataset** to predict whether a customer will subscribe to a term deposit.

This project compares **traditional Machine Learning models** with an **Artificial Neural Network (ANN)** built using TensorFlow/Keras.

---

##  Project Overview

The goal of this project is to predict whether a bank customer will subscribe to a term deposit based on demographic, financial, and marketing campaign information.

The project follows a complete Machine Learning workflow:

**Data → Preprocessing → Feature Engineering → Model Training → Evaluation → Model Comparison**

Three different models were implemented:

* Logistic Regression
* Random Forest
* Artificial Neural Network (ANN)

The main purpose was not only to achieve high accuracy, but also to understand how traditional Machine Learning models compare with a Neural Network when dealing with an imbalanced classification problem.

---

##  Dataset

**Dataset:** UCI Bank Marketing Dataset

The dataset contains information about customers contacted during a Portuguese bank's direct marketing campaigns.

### Target Variable

The target variable is:

`y`

* `yes` → Customer subscribed to a term deposit
* `no` → Customer did not subscribe

The dataset is an **imbalanced binary classification problem**, with significantly more negative (`no`) samples than positive (`yes`) samples.

---

##  Data Exploration

The dataset was explored to understand:

* Feature distributions
* Categorical variables
* Numerical variables
* Target class distribution
* Missing values
* Duplicate records
* Relationships between features and the target

The dataset was checked for:

* ✅ Null values
* ✅ Duplicate records
* ✅ Categorical feature distributions
* ✅ Target imbalance

---

##  Data Preprocessing

The following preprocessing steps were performed:

### Categorical Encoding

Categorical variables were converted into numerical representations using **One-Hot Encoding**.

Examples include:

* Job
* Marital status
* Education
* Contact type
* Month
* Previous outcome
* Housing loan
* Personal loan

### Feature Scaling

Numerical features were standardized using **StandardScaler**.

Scaling was particularly important for:

* Logistic Regression
* Artificial Neural Network

Random Forest does not require feature scaling because tree-based models make decisions using feature thresholds.

### Preprocessing Pipeline

A preprocessing pipeline was used to keep the transformations consistent between training and testing data.

---

# 🤖 Models

## 1. Logistic Regression

Logistic Regression was used as a traditional Machine Learning baseline.

It is useful for establishing a simple and interpretable benchmark for binary classification.

---

## 2. Random Forest

Random Forest was used as a tree-based Machine Learning model.

It combines multiple decision trees and can capture nonlinear relationships between features.

---

## 3. Artificial Neural Network

The main Deep Learning component of this project was a **feed-forward Artificial Neural Network (ANN)** implemented using **TensorFlow/Keras**.

### ANN Architecture

```text
Input Layer
     ↓
Dense Layer — 64 neurons — ReLU
     ↓
Dense Layer — 32 neurons — ReLU
     ↓
Output Layer — 1 neuron — Sigmoid
```

### Configuration

* Hidden layers: 2
* Neurons: 64 → 32
* Hidden activation: ReLU
* Output activation: Sigmoid
* Loss function: Binary Cross-Entropy
* Optimizer: Adam
* Epochs: 50
* Batch size: 32
* Validation split: 20%

The sigmoid output produces a probability between 0 and 1 for the positive class.

---

# 📈 Model Results

The models were evaluated using multiple classification metrics.

| Model               |   Accuracy |
| ------------------- | ---------: |
| Logistic Regression |     90.00% |
| Random Forest       | **90.45%** |
| ANN                 |     89.11% |

Random Forest achieved the highest overall accuracy.

However, accuracy alone does not tell the complete story because the dataset is imbalanced.

---

## 🎯 Minority Class Performance

For the positive class (`yes`), the models produced:

| Model               | Precision |   Recall | F1-Score |
| ------------------- | --------: | -------: | -------: |
| Logistic Regression |      0.64 |     0.35 |     0.45 |
| Random Forest       |      0.65 |     0.40 |     0.49 |
| ANN                 |      0.54 | **0.52** | **0.53** |

An interesting result was that the **ANN achieved the highest recall and F1-score for the minority class**, even though its overall accuracy was slightly lower than the traditional Machine Learning models.

This demonstrates why evaluating an imbalanced classification problem using accuracy alone can be misleading.

---

# 📉 Model Comparison

The project also includes visual comparisons of:

* Model Accuracy
* Precision
* Recall
* F1-score

These plots make it easier to understand the differences between traditional Machine Learning models and the ANN.

---

# 🧠 Key Learnings

Through this project, I gained practical experience with:

* Data preprocessing
* Exploratory Data Analysis
* One-Hot Encoding
* Feature scaling
* Scikit-learn pipelines
* Logistic Regression
* Random Forest
* Artificial Neural Networks
* TensorFlow/Keras
* Dense layers
* ReLU activation
* Sigmoid activation
* Binary Cross-Entropy
* Adam optimizer
* Model training and validation
* Confusion matrices
* Precision, Recall, and F1-score
* Imbalanced classification
* Comparing Machine Learning and Deep Learning models

One of the most important lessons was:

> **A model should not be judged by accuracy alone, especially when the target classes are imbalanced.**

---

# 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-learn
* TensorFlow
* Keras
* Jupyter Notebook / VS Code

---


# 🚀 How to Run

### 1. Clone the repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
```

### 2. Navigate to the project

```bash
cd UCI-Bank-Marketing
```

### 3. Install dependencies

```bash
pip install pandas numpy matplotlib scikit-learn tensorflow
```

### 4. Open the notebook

Open the `.ipynb` file using:

* Jupyter Notebook
* JupyterLab
* VS Code

### 5. Run the notebook

Run the cells sequentially to reproduce the preprocessing, model training, evaluation, and visualizations.

---

# 📊 Evaluation Metrics

The following metrics were used:

### Accuracy

Measures the percentage of total predictions that were correct.

### Precision

Measures how many predicted positive cases were actually positive.

### Recall

Measures how many of the actual positive cases were successfully identified.

### F1-Score

The harmonic mean of Precision and Recall.

For this project, **Recall and F1-score were particularly important** because the positive class was the minority class.

---

# 🔬 Future Improvements

Possible improvements for future versions include:

* Hyperparameter tuning
* Class weighting
* SMOTE / oversampling
* Early stopping
* Dropout regularization
* ANN architecture optimization
* ROC-AUC comparison
* Precision-Recall curves
* Cross-validation
* Feature importance analysis
* SHAP explainability
* More advanced Deep Learning architectures

---



