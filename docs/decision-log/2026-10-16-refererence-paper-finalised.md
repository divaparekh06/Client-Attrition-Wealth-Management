# Reference Paper for the review is Finalised

**Date:** 2026-10-26
**Context:** I was required to finalize a base paper to start my work for this project, where I would first be required to review this paper, followed by making a standard, quality ML Project based on my leaarnings and then eventually writing and publishing a research paper.

**Options considered:** The other research papers I considered were:
1. Investigating customer churn in banking: a machine learning approach and visualization app for data science and management (source: https://www.sciencedirect.com/science/article/pii/S2666764923000401)
2. Forecasting Client Retention - A machine learning Approach (source: https://www.sciencedirect.com/science/article/abs/pii/S0969698919302668)
3. Reducing Customer Attrition with Machine Learning for Financial Institutions (source: http://support.sas.com/resources/papers/proceedings18/1769-2018.pdf)
4. Offestting Client Attrition - A playbook for wealth managers (source: https://alphafmc.com/insights/offsetting-client-attrition-a-playbook-for-wealth-managers/)
**Decision:** Investigating customer churn in banking: a machine learning approach and visualization app for data science and management
**Reasoning:**
- Same dataset as yours. It’s the 10,000-row Kaggle bank churn data (Table 3), with about 20% churners (Fig. 2). Your results can be compared directly with theirs.
- Clear baseline numbers to beat. Tables 4 and 5 give accuracy, sensitivity, specificity, AUC and F1 for four models (logistic regression, SVM, random forest, XGBoost), with and without SMOTE.
- It shows the imbalance problem in action. Without SMOTE, sensitivity is only 12–44%. With SMOTE it rises to 60–71%, and accuracy drops. That tradeoff is worth reproducing and explaining yourself.
- The authors say why accuracy isn’t enough. They name sensitivity as the key metric for churn.
- Useful EDA and feature engineering. They find that churn rises with age (especially after 40), that Germany is the highest-churn country, and that customers with two products stay while those with three leave. They also build three features: TenureByAge, BalanceSalaryRatio and CreditScoreGivenAge.
- Honest about its limits. The conclusion admits the data is limited and has no recency features (behavior just before leaving). It suggests country-specific models and automated retraining.
- Good reading leads in its references. It cites Schaeffer & Sanchez (2020), which is your Paper 2. It also cites Lemmens & Gupta (2020) on managing churn for profit, Guliyev & Tatoglu (2021) on explainable ML for bank churn, and Machado & Karray (2022) on customer risk-adjusted revenue. The last three look relevant to your value-at-risk and SHAP angle.


