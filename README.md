# Lending-Club-Risk-Analytics
Strategic Credit Risk Modeling and Portfolio Optimization for the 2016 Lending Club vintage using Random Forest and Cost-Sensitive Learning.

Lending Club: Risk Analytics & Capital Optimization
Executive Summary
This project demonstrates a 2-stage Machine Learning evolution for credit risk underwriting. By transitioning from a 5-feature baseline to a 7-feature optimized Random Forest model, I successfully identified a method to rescue 5,294 qualified borrowers from misclassification while maintaining a high-capture rate for potential defaults.

🚀 Key Business Results
Borrower Recovery: Reduced False Positives by 5,294 individuals, increasing potential loan volume without expanding risk appetite.

Capital Protection: Identified and flagged over $XXX Million (total defaults caught × avg loan size) in high-risk capital.

Model Accuracy: Optimized the decision threshold to 0.2 (20%) to prioritize capital preservation in a high-default 2016 vintage.

🛠️ The Technical Stack
Language: Python 3.x

Libraries: Scikit-Learn (Random Forest), Pandas (ETL), Seaborn/Matplotlib (Statistical Visualization).

Environment: Jupyter Notebook / Anaconda.

Data Source: 2016 Lending Club Loan Dataset (Kaggle).

🧠 Architectural Philosophy
To ensure this model was "Production Ready," I followed three core analytical principles:

Anti-Leakage Constraints: Used only "Application-Time" data. I strictly excluded post-loan variables (like recoveries or late fees) that would cause data leakage and "cheat" the results.

Multicollinearity Filtering: Conducted a Pearson Correlation analysis to ensure features like int_rate and grade provided unique signals rather than redundant noise.

Cost-Sensitive Learning: In banking, the cost of a "False Negative" (missing a default) is significantly higher than a "False Positive." I utilized Class Weight Balancing (1:10) to force the model to prioritize finding defaults.

📈 Model Evolution
The project is split into two distinct iterations to show the value of feature engineering:

Iteration 1 (Baseline): Used 5 liquid economic indicators (loan_amnt, int_rate, annual_inc, dti, revol_util).

Iteration 2 (Optimized): Integrated Employment Length and Credit Grade, resulting in the successful "rescue" of over 5,000 borrowers who were previously rejected by the baseline logic.

⏭️ Next Steps: Phase 2 (Enterprise Scale)
This Python-based analysis serves as the "Proof of Concept." The next phase of this portfolio project involves:

Migrating the raw ETL logic into Snowflake.

Building a production-grade transformation pipeline using dbt (data build tool).

Automating risk reporting via an orchestration layer (Python/Airflow).
