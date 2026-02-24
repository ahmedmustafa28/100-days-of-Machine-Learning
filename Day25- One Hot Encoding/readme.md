# One Hot Encoding

## 📌 Overview
This notebook demonstrates how to apply One Hot Encoding using Pandas and Scikit-learn to convert categorical features into numeric binary columns before training a machine learning model.

## 📂 Dataset
- The dataset is loaded from `cars.csv`.
- Categorical columns (`fuel`, `owner`, `brand`) are selected for encoding.
- Data is split into training and testing sets for the Scikit-learn approach.

## 🔄 Techniques Used

#### 1️⃣ Standard One Hot Encoding
- Applied to `fuel` and `owner` columns using `pd.get_dummies()`.
- Each unique category becomes its own binary indicator column.

#### 2️⃣ K-1 One Hot Encoding
- Same as above but uses `drop_first=True` to drop one column per feature.
- Prevents multicollinearity (the dummy variable trap) in linear models.

#### 3️⃣ One Hot Encoding with Scikit-learn
- Implemented using `sklearn.preprocessing.OneHotEncoder`.
- Encoder is fit on training data only, then applied to both train and test sets to avoid data leakage.

#### 4️⃣ Encoding with Top Categories
- Applied to the high-cardinality `brand` column.
- Infrequent categories (below a count threshold) are grouped into a single `"uncommon"` label before encoding.

## 🛠 Libraries Used
- NumPy
- Pandas
- Scikit-learn

## 🎯 Purpose
To understand how nominal categorical variables can be converted into numerical binary form for machine learning models.
