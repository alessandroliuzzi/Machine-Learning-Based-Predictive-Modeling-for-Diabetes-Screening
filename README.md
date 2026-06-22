# Explainable Machine Learning for 5-Year Diabetes Risk Prediction

This repository implements a non-linear predictive pipeline to forecast the onset of diabetes within a 5-year follow-up horizon using the Pima Indians Diabetes dataset. 

Following a rigorous **model selection phase** where multiple algorithms were evaluated, **LightGBM** was selected as the champion model for its superior ability to map complex physiological interactions. To bridge the gap between predictive power and clinical understanding, the pipeline integrates advanced explainability frameworks to unpack the model's decision-making process.

### 🌟 Key Features
* **Model Selection Framework:** Benchmarked multiple classifiers, selecting LightGBM for its optimal trade-off between predictive metrics and non-linear flexibility.
* **Global Interpretability:** Summary SHAP plots and Partial Dependence Plots (PDP) paired with rug plots to map the geometric shape of primary risk drivers (Glucose, BMI) without overinterpreting sparse data regions.
* **Local Interpretability:** Individual Conditional Expectation (ICE) lines to reveal hidden patient heterogeneity, alongside SHAP Waterfall plots to trace individual patient risk trajectories from the dataset's base expected value to the final log-odds prediction.
