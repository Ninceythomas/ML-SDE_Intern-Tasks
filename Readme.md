AI-Based Vulnerability Detection System

Task 1: LLM Prompt Optimization
Task 2: ML-Based Vulnerability Classifier

**Project Overview**

This project focuses on improving the core intelligence layer of an AI-powered vulnerability detection system. The system connects to GitHub repositories, scans source code, and automatically identifies potential security vulnerabilities.

The work is divided into two tightly connected parts:

Task 1: Enhancing how a Large Language Model (LLM detects and explains vulnerabilities using advanced prompt engineering.

Task 2: Building and evaluating a Machine Learning (ML) model that automatically classifies whether a code snippet is vulnerable and predicts its vulnerability type.

All implementation is done entirely in Python using Jupyter Notebooks, making the work easy to run, test, and extend.

**Task 1 — LLM Prompt Optimization**
Objective

The goal of Task 1 is to improve how the LLM reasons about security vulnerabilities and how accurately it explains them. The focus is on reducing false positives, improving clarity of explanations, and producing structured outputs for production-ready integration.

Key Work Done

Designed a baseline prompt to simulate the original system behavior.

Created an improved prompt with strict rules, structured JSON output enforcement, and vulnerability type constraints.

Added few-shot learning examples so the LLM learns through real security patterns.

Implemented Python-based LLM API calling logic.

Added robust JSON extraction from model outputs.

Built a comparison framework to evaluate baseline vs improved prompts.

Enforced a standard output structure:

{
  "vuln_type": "SQL Injection",
  "explanation": "User input is concatenated directly into the SQL query without parameterization",
  "confidence": 0.87
}

Key Improvements Achieved

More consistent vulnerability detection

Reduced hallucinations and false positives

Reliable machine-readable JSON output

Better confidence calibration

Clear, short, human-readable explanations

**Task 2 — ML-Based Vulnerability Classifier**
Objective

The goal of Task 2 is to train a Machine Learning model that automatically:

Predicts whether a given code snippet is Safe or Vulnerable

Identifies the specific type of vulnerability

Dataset Format

Each data sample follows the format:

{
  "id": 1,
  "language": "python",
  "code": "query = 'SELECT * FROM users WHERE name=' + user",
  "label": "vulnerable",
  "vuln_type": "SQLi"
}

Workflow Implemented

Data creation and cleaning

Tokenization and text normalization

TF-IDF feature extraction

Baseline Logistic Regression model

Improved Logistic Regression model with tuning

Binary classification (Safe vs Vulnerable)

Multi-class classification for vulnerability type

Performance evaluation using:

Accuracy

Precision

Recall

F1-score

Confusion matrix visualization

Performance comparison table

Final technical interpretation of results

Key Results

TF-IDF + Logistic Regression provides strong baseline performance

Improved model tuning increases stability and recall

Binary classification achieves reliable vulnerability detection

Multi-class model successfully predicts common vulnerability categories

Overall approach is lightweight and production-friendly

**Technology Stack**

Python 3.x

Jupyter Notebook / Google Colab

scikit-learn

pandas

numpy

matplotlib

seaborn

openai (Task 1)

**Repository Structure**
.
├── Task_1_LLM_Prompt_Optimizer.ipynb
├── Task_2_ML_Vulnerability_Classifier.ipynb
├── README.md

**How to Run the Project**
1. Install Required Libraries
pip install openai scikit-learn pandas numpy matplotlib seaborn

2. Run Task 1 (LLM Prompt Optimization)

Open Task_1_LLM_Prompt_Optimizer.ipynb

Set your API key as an environment variable:

export OPENAI_API_KEY="your_api_key_here"


Run the notebook cell by cell

The notebook will generate structured vulnerability predictions and prompt comparison results

3. Run Task 2 (ML Vulnerability Classifier)

Open Task_2_ML_Vulnerability_Classifier.ipynb

Run all cells sequentially

The notebook will:

Train models

Show evaluation metrics

Display confusion matrix

Output final predictions

**What Worked Best**

Few-shot learning in Task 1 significantly improved LLM reasoning accuracy

Strict JSON schema enforcement prevented malformed outputs

TF-IDF with Logistic Regression gave excellent performance with low computational cost

Parameter tuning improved recall and F1-score

Binary classification proved highly reliable for vulnerability detection

Future Improvements

Integrate CodeBERT or GraphCodeBERT embeddings

Add static analysis features from tools like Semgrep or CodeQL

Expand dataset size for better generalization

Include data augmentation using code mutation

Deploy the full pipeline as a microservice API
