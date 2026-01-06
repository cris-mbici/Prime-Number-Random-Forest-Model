# Predicting Prime Numbers with Machine Learning

## Overview

This notebook explores whether machine learning models can learn to distinguish prime numbers from non-prime numbers.

Prime numbers follow strict mathematical rules. This project tests how far statistical models can go when given only simple numerical features, without using traditional prime-checking algorithms.

---

## What This Notebook Does

### Data Generation
- Generates integers from **2 to 9,999**
- Labels each number as prime or non-prime using **SymPy**
- Highlights the strong class imbalance between primes and non-primes

### Feature Engineering
- Creates modular features based on:
  - Modulo 2, 3, 5, 6, and 30
- These features capture basic divisibility and residue patterns
- Adds optional “probably prime” indicators to test whether explicit rules help

### Modeling
- Trains **Random Forest** and **XGBoost** classifiers
- Uses **stratified 10-fold cross-validation**
- Evaluates with:
  - Precision  
  - Recall  
  - F1-score  
  - Confusion matrices  
- Accuracy is included but not relied on heavily due to class imbalance

### Tuning and Evaluation
- Applies grid search to tune hyperparameters
- Evaluates performance before and after tuning
- Tests the final model on larger numbers around one million

### Analysis
- Examines feature importance to understand model behavior
- Experiments with K-means and hierarchical clustering for comparison

---

## Results

- Random Forest outperforms XGBoost on this task
- Hyperparameter tuning improves prime detection, especially recall
- Simple divisibility features dominate model decisions
- The raw numeric value contributes very little
- Unsupervised clustering does not separate primes from non-primes meaningfully

---

## What I Learned

- The models learn divisibility shortcuts, not primality itself
- Accuracy is misleading for imbalanced classification problems
- Feature engineering matters more than model complexity
- Deterministic, rule-based problems have clear limits for machine learning

---

## How to Run

Open the notebook in Jupyter and run the cells in order.

### Requirements
- Python
- NumPy
- Pandas
- SymPy
- scikit-learn
- XGBoost
- Matplotlib
- Seaborn

---

## Notes

This project focuses on understanding how machine learning behaves on structured mathematical problems, where classical algorithms already provide exact answers.
