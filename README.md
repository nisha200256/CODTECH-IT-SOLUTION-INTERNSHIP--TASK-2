# 🛍️ Machine Learning on Online Retail II Dataset: Order Cancellation Prediction

## 📌 Objective

This project demonstrates how to build a machine learning classification model using the **Online Retail II dataset** to predict whether an order is likely to be **cancelled**, based on features such as quantity, unit price, invoice time, and total price.

---

## 📁 Dataset Overview

- **Dataset**: [Online Retail II](https://archive.ics.uci.edu/ml/datasets/Online+Retail+II)
- **Source**: UCI Machine Learning Repository
- **Format**: Excel (`.xlsx`) with two sheets:  
  - `Year 2009-2010`
  - `Year 2010-2011`
- **Selected Sheet**: `Year 2010-2011`
- **Size**: ~500,000 rows

---

## 🎯 Target Variable

- **Cancelled** (Binary):
  - `1` = The invoice is a cancellation (Invoice number starts with `C`)
  - `0` = Normal purchase

---

## ⚙️ Technologies Used

- Python 3.8+
- pandas, NumPy
- scikit-learn
- matplotlib, seaborn

---

## 🚀 Project Workflow

### 1. Data Loading and Cleaning
- Read the dataset from Excel
- Drop rows with missing `Customer ID` or `Description`
- Remove entries with `Quantity = 0`

### 2. Feature Engineering
- New binary label: `Cancelled` (based on invoice number)
- Extracted `Hour` and `DayOfWeek` from invoice timestamp
- Created `TotalPrice` = `Quantity × Price`

### 3. Model Pipeline
- **Selected Features**:
  - `Quantity`, `Price`, `Hour`, `DayOfWeek`, `TotalPrice`
- **Model**: Random Forest Classifier
- **Preprocessing**: StandardScaler
- **Train-Test Split**: 80/20

### 4. Evaluation
- Confusion Matrix
- Classification Report (Precision, Recall, F1-score)
- Feature Importance Plot

---

## 📈 Example Insights

- Cancellations often happen during business hours (9–17).
- Low total price and small quantities tend to be associated with cancellations.
- Random Forest identified `TotalPrice` and `Quantity` as top predictors.

---

## 📦 Files Included

- `retail_order_classification.ipynb` — Complete ML notebook
- `README.md` — This project documentation

---

## 🧠 Next Steps

- Add more features like `Country` or `Customer Frequency`
- Use time-series analysis to detect suspicious activity
- Deploy the model via API or stream in real-time using Spark or Kafka

---

## 📬 Questions or Feedback?

Feel free to open an issue or contact the author!
