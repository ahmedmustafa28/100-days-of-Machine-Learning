# 📘 Ordinal and Label Encoding in Machine Learning
## 📌 Project Overview

This notebook demonstrates how to convert categorical data into numerical format using Ordinal Encoding and Label Encoding. These preprocessing techniques are essential before training machine learning models.

## 📂 Dataset Information

Dataset loaded from: customer.csv

Selected relevant feature columns

Split data into training and testing sets using train_test_split

## ⚙️ Libraries Used

NumPy

Pandas

Scikit-learn

## 🔄 Data Preprocessing Steps
### 1️⃣ Data Loading

Imported dataset using Pandas

Selected required columns

Checked sample records

### 2️⃣ Train-Test Split

Features and target variable separated

Dataset split into training and testing sets

## 🔢 Ordinal Encoding
### 📌 Purpose

Used when categorical features have a natural order.

### 🛠 Implementation

Used sklearn.preprocessing.OrdinalEncoder

Defined custom category order:

Quality: Poor < Average < Good

Education: School < UG < PG

Fitted encoder on training data

Transformed both training and test data

## 🔠 Label Encoding
### 📌 Purpose

Used to encode the target variable into numeric labels.

### 🛠 Implementation

Used sklearn.preprocessing.LabelEncoder

Fitted encoder on target variable (y_train)

Transformed both training and test target values

## 🎯 Conclusion

This notebook shows how categorical features and target variables can be converted into numeric form using Scikit-learn encoders, making the dataset ready for machine learning algorithms.
