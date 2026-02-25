# Titanic Survival Prediction — With & Without Pipeline

## 📌 Overview
This project demonstrates how to build a Titanic survival prediction model using a `DecisionTreeClassifier`, comparing a manual step-by-step preprocessing approach against a clean, production-ready Scikit-learn `Pipeline`. It also includes two prediction notebooks showing how each approach handles new input data differently.

---

## 📂 Dataset
- The dataset is loaded from `train.csv` (Titanic training data).
- Irrelevant columns (`PassengerId`, `Name`, `Ticket`, `Cabin`) are dropped.
- Data is split into training and testing sets (80/20 split).
- The `Age` and `Embarked` columns contain missing values that require imputation.

## 📊 Dataset Columns

| Column | Type | Description |
|---|---|---|
| `Pclass` | Numeric | Passenger class (1, 2, 3) |
| `Sex` | Categorical | male / female |
| `Age` | Numeric | Passenger age (has missing values) |
| `SibSp` | Numeric | Number of siblings/spouses aboard |
| `Parch` | Numeric | Number of parents/children aboard |
| `Fare` | Numeric | Ticket fare |
| `Embarked` | Categorical | Port of embarkation — C, Q, S (has missing values) |
| `Survived` | Target | 0 = No, 1 = Yes |

---

## 📁 Notebooks

#### 1️⃣ Titanic-without-using-pipeline.ipynb
Manually applies each preprocessing step one by one:
- `SimpleImputer` → fills missing values in `Age` and `Embarked`
- `OneHotEncoder` → encodes `Sex` and `Embarked`
- `MinMaxScaler` → scales numeric features
- All transformed arrays are manually concatenated using `np.concatenate()`
- A `DecisionTreeClassifier` is trained and evaluated (~78% accuracy)
- Each transformer and the model are exported separately as individual `.pkl` files (`ohe_sex.pkl`, `ohe_embarked.pkl`, `clf.pkl`)

#### 2️⃣ Titanic-using-pipeline.ipynb
Bundles all preprocessing and modelling steps into a single `Pipeline` using `ColumnTransformer`:
- **Step 1** — Impute missing values in `Age` (mean) and `Embarked` (most frequent)
- **Step 2** — One-hot encode `Sex` and `Embarked`
- **Step 3** — Scale all features using `MinMaxScaler`
- **Step 4** — Select top 8 features using `SelectKBest` with `chi2`
- **Step 5** — Train a `DecisionTreeClassifier`
- The entire pipeline is exported as a single `pipe.pkl` file
- Also attempts `GridSearchCV` for hyperparameter tuning

#### 3️⃣ Predict-without-pipeline.ipynb
Shows the complexity of making a prediction without a pipeline:
- Loads three separate pickle files (`ohe_sex.pkl`, `ohe_embarked.pkl`, `clf.pkl`)
- Manually transforms each part of the input and concatenates them before predicting

#### 4️⃣ Predict-using-pipeline.ipynb
Shows how clean prediction becomes with a pipeline:
- Loads a single `pipe.pkl` file
- Passes raw input directly — the pipeline handles all preprocessing automatically

```python
pipe.predict(np.array([2, 'male', 31.0, 0, 0, 10.5, 'S'], dtype=object).reshape(1,7))
```

---

## 🔄 Key Comparison

| | Without Pipeline | With Pipeline |
|---|---|---|
| Preprocessing | Manual, step-by-step | Bundled in one object |
| Saved files | 3 separate `.pkl` files | 1 single `.pkl` file |
| Prediction code | Complex — transform each column manually | Simple — pass raw input directly |
| CV / Tuning | Not straightforward | Works natively with `GridSearchCV` |

---

## 🛠 Libraries Used
- NumPy
- Pandas
- Scikit-learn

## 🎯 Purpose
To understand how Scikit-learn `Pipeline` simplifies the entire machine learning workflow — from preprocessing to prediction — making code cleaner, less error-prone, and easier to deploy compared to the manual approach.
