# Column Transformer

## 📌 Overview
This notebook demonstrates how to use `ColumnTransformer` from Scikit-learn to apply multiple preprocessing steps to different columns simultaneously, comparing the manual approach against the streamlined `ColumnTransformer` approach.

## 📂 Dataset
- The dataset is loaded from `covid_toy.csv`.
- Contains 100 records with patient information and a `has_covid` target label.
- The `fever` column contains 10 missing values that require imputation.
- Data is split into training and testing sets (80/20 split).

## 📊 Dataset Columns
| Column | Type | Description |
|---|---|---|
| `age` | Numeric | Patient age |
| `gender` | Categorical | Male / Female |
| `fever` | Numeric | Body temperature (has missing values) |
| `cough` | Ordinal | Cough severity — Mild / Strong |
| `city` | Categorical | City of residence |
| `has_covid` | Target | Yes / No |

## 🔄 Approaches Compared

#### 1️⃣ Without Column Transformer *(Aam Zindagi)*
Each column is preprocessed separately and the results are manually concatenated using `np.concatenate()`:
- `SimpleImputer` → applied to `fever`
- `OrdinalEncoder` → applied to `cough` (Mild < Strong)
- `OneHotEncoder` → applied to `gender` and `city`
- `age` extracted as-is

#### 2️⃣ With Column Transformer *(Mentos Zindagi)*
All transformations are bundled into a single `ColumnTransformer` object, applying each transformer to its respective columns in one step — cleaner, less error-prone, and pipeline-ready.

## 🛠 Libraries Used
- NumPy
- Pandas
- Scikit-learn

## 🎯 Purpose
To understand how `ColumnTransformer` simplifies and consolidates multiple preprocessing steps into a single, reusable object — replacing repetitive manual transformations with a clean, pipeline-compatible workflow.
