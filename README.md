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

## Sensitive Features Considered

- **Sex**  
- **Age**  
- **Citizenship**  
- **Protected Status**

Groups are combinations of these features (e.g., “male-young-European-non protected”). The python notebook named after a specific category represents the training outcomes of the models after that specific category has been debiased. The standard traning notebook instead contains the original biased results.
*For more details, data tables, and discussion, please refer to the full report.*



