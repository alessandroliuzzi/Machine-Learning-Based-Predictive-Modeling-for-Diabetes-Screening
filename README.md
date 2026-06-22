# Explainable Machine Learning for 5-Year Diabetes Risk Prediction

This repository implements a non-linear predictive pipeline to forecast the onset of diabetes within a 5-year follow-up horizon using the Pima Indians Diabetes dataset. 

Following a rigorous **model selection phase** where multiple algorithms were evaluated, **LightGBM** was selected as the champion model for its superior ability to map complex physiological interactions. To bridge the gap between predictive power and clinical understanding, the pipeline integrates advanced explainability frameworks to unpack the model's decision-making process.

### 🌟 Key Features
* **Model Selection Framework:** Benchmarked multiple classifiers, selecting LightGBM for its optimal trade-off between predictive metrics and non-linear flexibility.
* **Global Interpretability:** Summary SHAP plots and Partial Dependence Plots (PDP) paired with rug plots to map the geometric shape of primary risk drivers (Glucose, BMI) without overinterpreting sparse data regions.
* **Local Interpretability:** Individual Conditional Expectation (ICE) lines to reveal hidden patient heterogeneity, alongside SHAP Waterfall plots to trace individual patient risk trajectories from the dataset's base expected value to the final log-odds prediction.


## ⚙️ Reproducibility Guide

To replicate the model selection, training, and explainability analysis (SHAP, PDP, ICE) locally, follow these structured steps.

### 1. Prerequisites & Environment Setup
It is highly recommended to use an isolated Python environment (Python 3.8+) to avoid dependency conflicts. Run the following commands in your terminal:

&nbsp;&nbsp;&nbsp;&nbsp;*git clone https://github.com/alessandroliuzzi/Machine-Learning-Based-Predictive-Modeling-for-Diabetes-Screening.git*

&nbsp;&nbsp;&nbsp;&nbsp;*cd Machine-Learning-Based-Predictive-Modeling-for-Diabetes-Screening*

&nbsp;&nbsp;&nbsp;&nbsp;*python -m venv venv*

Activate the virtual environment:

&nbsp;&nbsp;On Windows: &nbsp;&nbsp;*venv\Scripts\activate*

&nbsp;&nbsp;On macOS/Linux: &nbsp;&nbsp;*source venv/bin/activate*

### 2. Install Dependencies
Install all required packages and visualization libraries (including Jupyter to run the notebook), using the provided requirements file:

&nbsp;&nbsp;&nbsp;&nbsp;*pip install --upgrade pip*

&nbsp;&nbsp;&nbsp;&nbsp;*pip install -r requirements.txt*

### 3. Data & Reproducibility
* Dataset: The notebook automatically loads the Pima Indians Diabetes dataset from the local data/ directory. Ensure the diabetes.csv file remains in that designated folder to guarantee a seamless local execution.
* Random Seeds: To guarantee identical splits during the model selection phase and consistent LightGBM optimization, a fixed random seed has been hardcoded across train-test splits, cross-validation folds, and LightGBM hyperparameters (random_state / seed).

### 4. Running the Pipeline
You can inspect the fully executed pipeline, text comments, and all generated charts directly on GitHub by clicking on the notebook file.

To run the pipeline locally and interact with the code:
1. Ensure your virtual environment is activated and launch the Jupyter interface:
   
&nbsp;&nbsp;&nbsp;&nbsp;*jupyter notebook*

2. A browser window will automatically open showing the project directory. **Click on diabetes_predictive_modeling.ipynb** to open it.
3. To trigger the full automated pipeline (Data preprocessing -> Model Selection -> Champion Model Training [LightGBM] -> SHAP/PDP/ICE Generation), navigate to the top menu inside the notebook and select **Kernel -> Restart & Run All**.

All global explanations and local evaluation plots (such as Patient 12's waterfall plot) will be rendered dynamically beneath the notebook cells.
