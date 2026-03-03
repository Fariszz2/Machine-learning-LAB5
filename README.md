# Machine Learning Lab – Feature Engineering & Model Evaluation  

The goal is to prepare the dataset for machine learning by:
- Engineer meaningful features
- Experiment with different classification rules
- Compare feature importance rankings
- Evaluate model performance using Confusion Matrix
- Analyze whether feature selection improves results

## Jupyter Notebook
📓 **Notebook:**  
- [View Notebook on GitHub](./Lab5_FeatureEngineering.ipynb)
- [View Notebook Rendered (nbviewer)](https://nbviewer.org/github/Fariszz2/Machine-learning-LAB5/blob/main/Lab5_FeatureEngineering.ipynb)

## Dataset Description

The dataset contains 187,531 property listings with 21 features, including:

- Price (in rupees)
- Carpet Area
- Super Area
- Bathroom
- Furnishing
- Transaction
- Ownership
- Location
- Status
- and more

---

# Task 1 – Feature Engineering

### Engineered Feature:
`Price_per_Sqft = Price / Carpet Area`

### Justification:

Price per square foot is a critical real estate metric that reflects the true value of a property relative to its size. While total price increases with area, price per unit area captures market demand and location-based valuation differences. This feature enhances the model’s ability to distinguish high-value properties.

---

# Task 2 – Alternative Rule for Classification

Two definitions for "luxury" / high-price properties were tested:

1. Median-based threshold  
2. 75th percentile threshold  

Changing the rule affected class balance and model behavior.  
A stricter threshold (75th percentile) resulted in fewer positive samples and slightly different classification performance.

---

# Task 3 – Top-k Location Reduction

To reduce dimensionality, location categories were grouped:

- Top 10 locations
- Top 30 locations
- Top 50 locations

Remaining locations were labeled as `"Other"`.

### Observations:
- Smaller `top_k` simplified the model but lost location detail.
- Larger `top_k` increased dimensionality and slightly improved accuracy.
- Trade-off between complexity and performance was observed.

---

# Task 4 – Optional Feature Selection

Feature selection was performed using:

`SelectKBest (f_regression)`

The selected features were compared against the baseline model.

### Evaluation Metrics:
- Accuracy
- Confusion Matrix
- Feature Importances

### Result:

Feature selection had (choose based on your result):

- Minimal impact on performance  
- Slight improvement  
- Slight decrease in accuracy  

In this dataset, area-related features were already strong predictors, so removing features did not significantly improve performance.

---

# Model Evaluation

### Classifier Used:
Random Forest Classifier

### Evaluation Tools:
- Accuracy Score
- Confusion Matrix
- Top Feature Importances

### Confusion Matrix Analysis:
The model effectively distinguished high-priced properties, though some misclassifications occurred near the threshold boundary.

---

## 👨‍💻 Author

**fariszz** 
