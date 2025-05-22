# Recruitment_Ethics

Analysis of an automatic résumé screening model to identify discriminatory behavior based on **gender, age** and **nationality**. Developed and implemented debiasing techniques to mitigate biased model behavior.

---

## Fairness in Recruitment Decision Algorithms

This project investigates bias in AI-driven hiring algorithms used to prescreen job candidates, focusing on **fairness and discrimination issues**. Using the anonymized **Aequitas STEM hiring dataset**, we:

- Evaluate traditional machine learning models and neural networks  
- Identify sources of bias such as:  
  - Bias inherent in model design  
  - Bias from historical human judgments reflected in training data  
  - Bias via discriminatory proxies detected with explainability tools (SHAP, LIME)  

- Apply fairness metrics like **Demographic Parity** and **Equalized Odds**  
- Implement bias mitigation techniques including **Reweighting** and **Adversarial Debiasing**

Our findings highlight persistent fairness challenges and emphasize the need for **transparency, accountability, and ongoing fairness assessment** in AI recruitment tools to promote equality and diversity in hiring.

---

## 5.2 Reweighting Technique

Reweighting addresses dataset imbalances by assigning higher weights to elements from underrepresented groups, effectively balancing the data distribution.

### Sensitive Features Considered

- **Sex**  
- **Age**  
- **Citizenship**  
- **Protected Status**

Groups are combinations of these features (e.g., “male-young-European-non protected”). Weights are computed based on the inverse frequency of each group.

---

### Group Distribution Before Reweighting

| Sex    | Age    | Citizenship | Protected Category | Count | %    |
|--------|--------|-------------|--------------------|-------|------|
| Male   | Young  | European    | No                 | 5980  | 60.7 |
| Male   | Senior | European    | No                 | 1612  | 16.4 |
| Female | Young  | European    | No                 | 1597  | 16.2 |
| ...    | ...    | ...         | ...                | ...   | ...  |

*Full table available in the full report.*

---

### Group Distribution After Reweighting

| Sex    | Age    | Citizenship | Protected Category | Count | %    |
|--------|--------|-------------|--------------------|-------|------|
| Female | Young  | European    | Yes                | 844   | 8.6  |
| Male   | Senior | European    | No                 | 844   | 8.6  |
| Female | Senior | European    | Yes                | 840   | 8.5  |
| ...    | ...    | ...         | ...                | ...   | ...  |

---

### Model Performance After Reweighting

| Model               | Accuracy | Precision | Recall | F1-score | ROC AUC |
|---------------------|----------|-----------|--------|----------|---------|
| Linear Regression    | 0.678    | 0.762     | 0.468  | 0.580    | -       |
| Decision Tree        | 0.809    | 0.812     | 0.778  | 0.668    | 0.795   |
| Naïve Bayes          | 0.779    | 1.000     | 0.534  | 0.808    | 0.696   |
| XGBoost              | 0.809    | 0.844     | 0.734  | 0.767    | -       |
| kNN                  | 0.785    | 0.759     | 0.783  | 0.681    | 0.728   |
| Neural Network (avg) | 0.755    | 0.751     | 0.768  | 0.699    | 0.729   |

---

## Summary

- Reweighting balances group sizes but **does not** correct intrinsic biases stemming from historic hiring rates.  
- Model performance on reweighted data is comparable to that on the original data.  
- Fairness metrics (Demographic Parity, Equalized Odds) show limited improvement post-reweighting.  

---

*For more details, data tables, and discussion, please refer to the full report.*



