Advanced Python – Final Project  
Date: 16 Feb 2026  

## Project Overview

This project collects real GitHub developer data using the GitHub REST API and builds a classification model to categorize developers into three contribution levels:

- Low
- Medium
- High

The project focuses strictly on:
1. Data collection
2. Feature engineering
3. Classification modeling
4. Model evaluation
5. Demo prediction

---

## Data Collection

We collected 200 GitHub users using the GitHub Search API.

Query used:
followers > 10

Features collected:
- followers
- following
- public_repos
- public_gists

Rate limiting was handled using time.sleep(0.3).

The final dataset is stored as:
my_github_data_200.csv

---

## Feature Engineering

Initial attempt:
- Label created from followers
- Result: 30% accuracy

Improved approach:
- contributor_score = public_repos × 1.0 + public_gists × 2.0
- Labels derived from contributor_score
- Result: 87.5% accuracy

Key learning:
Label and features must be correlated.

---

## Model

Algorithm:
Random Forest Classifier

Training configuration:
- Train/Test split: 80/20
- Stratified sampling
- random_state = 42

Evaluation metrics:
- Accuracy
- Precision
- Recall
- F1-score
- Feature importance analysis

Final accuracy:
87.5%

---

## Project Structure

project/
│
├── data_collection.ipynb
├── classification_model.ipynb
├── my_github_data_200.csv
├── README.md
├── requirements.txt
└── presentation.pptx
