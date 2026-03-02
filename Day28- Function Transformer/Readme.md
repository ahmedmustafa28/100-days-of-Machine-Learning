# 📊 Function Transformer in Machine Learning
### Improving Model Performance Using Log Transformation

---

## 📌 Project Overview
This project demonstrates how to use `FunctionTransformer` from Scikit-Learn to apply mathematical transformations (log transformation) on skewed features and analyze their impact on model performance.
The notebook uses selected features from the Titanic dataset and compares model accuracy before and after transformation.

---

## 🎯 Objectives
- Understand why skewed features can affect model performance
- Apply log transformation using `FunctionTransformer`
- Compare Logistic Regression and Decision Tree performance
- Learn how to selectively transform columns using `ColumnTransformer`

---

## 📂 Dataset
The dataset used is the Titanic training dataset (`train.csv`).

## 📊 Features Used

| Feature | Description |
|---|---|
| `Age` | Passenger age |
| `Fare` | Ticket fare |
| `Survived` | Target variable (0 = No, 1 = Yes) |

---

## 🛠 Technologies & Libraries
- Python 3.x
- pandas
- numpy
- matplotlib
- seaborn
- scipy
- scikit-learn

---

## 📊 Exploratory Data Analysis
The notebook performs:
- Distribution plots (PDF)
- Q-Q plots for normality checking

#### Observations
- `Fare` is highly right-skewed
- `Age` is closer to normal distribution
- Logistic Regression may benefit from normalization

---

## 🤖 Models Implemented
Two models are trained and evaluated:

#### 1️⃣ Logistic Regression
Sensitive to feature distribution and scaling.

#### 2️⃣ Decision Tree Classifier
Generally insensitive to monotonic transformations.

#### Evaluation Metrics
- Accuracy Score
- Cross-validation score

---

## 🔄 Feature Transformation

#### Log Transformation
Log transformation is applied using:

```python
FunctionTransformer(func=np.log1p)
```

`log1p` is used to safely handle zero values.

---

## 📈 Before vs After Transformation

| Model | Before Transformation | After Log Transformation |
|---|---|---|
| Logistic Regression | Moderate | Improved |
| Decision Tree | Similar | Similar |

#### Key Insight
- Log transformation improves linear model performance
- Tree-based models are mostly unaffected
- Transforming only skewed features is best practice

---

## 🎯 Selective Column Transformation
Using `ColumnTransformer`, log transformation is applied only to `Fare`:

```python
ColumnTransformer(
    [('log', FunctionTransformer(np.log1p), ['Fare'])],
    remainder='passthrough'
)
```

This ensures cleaner and more practical preprocessing.

---

## 🧠 Key Learnings
- Feature distribution matters for linear models
- Log transformation reduces skewness
- `FunctionTransformer` allows custom mathematical preprocessing
- `ColumnTransformer` enables selective feature engineering
- Always evaluate impact using cross-validation

---

## 🚀 How to Run
1. Clone the repository
2. Install dependencies
3. Open the notebook
4. Run cells sequentially

```bash
pip install pandas numpy matplotlib seaborn scipy scikit-learn
```

---

## 📌 Conclusion
This project demonstrates the importance of feature engineering in machine learning workflows. Applying appropriate transformations can significantly improve model performance, especially for linear algorithms.
