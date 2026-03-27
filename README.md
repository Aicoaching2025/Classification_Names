## Name Gender Classifier | PROJECT 3


## Overview
This project builds a name gender classifier using the NLTK Names Corpus and a Naive Bayes 
Classifier — one of three classifiers described in Chapter 6 of *Natural Language Processing 
with Python*. The classifier is trained to predict whether a name is male or female based on 
character-level features extracted from the name itself.

## Methodology
The Names Corpus (7,944 labeled names) was split into three subsets:
- **Training set:** 6,944 names — used to train the model
- **Dev-test set:** 500 names — used to evaluate and refine features iteratively
- **Test set:** 500 names — held out for final evaluation only

Features were engineered across five iterations, with dev-test accuracy checked after each 
addition to measure improvement:

| Version | Features Added | Dev-test Accuracy |
|---------|---------------|-------------------|
| v1 | Last letter only | 75.40% |
| v2 | + Last two letters | 78.40% |
| v3 | + First letter, last three letters | 79.40% |
| v4 | + Name length, vowel count | **80.20%** |
| v5 | + Boolean suffix flags | 79.80% |

## Results
V4 was selected as the final model with a peak dev-test accuracy of **80.20%**. Evaluated 
against the held-out test set for the first and only time, the model achieved **79.20%** — 
a gap of 1 percentage point, confirming the model generalizes well to unseen names.

## Classifier Selection
Naive Bayes was chosen over Decision Tree and Maximum Entropy classifiers for three reasons:
it handles sparse, high-dimensional feature spaces efficiently; it trains fast enough to 
support rapid iterative dev-test evaluation; and it produces interpretable feature importance 
rankings via `show_most_informative_features()`.

## Tools and Libraries
- Python 3
- NLTK
- pandas
- matplotlib

## File
- `Classifier.ipynb` — full notebook including feature engineering, visualizations, and analysis
