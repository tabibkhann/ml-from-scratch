# Logistic Regression from Scratch: Heart Disease Prediction

Logistic regression implemented in NumPy, verified against scikit-learn, and used to predict heart disease from 13 clinical measurements.

## What's covered

- **From-scratch implementation:** sigmoid, log loss and gradient descent in NumPy, tested on a 2D toy dataset with its decision boundary plotted
- **A gradient bug:** a flipped sign in an earlier version made the loss rise every epoch; the notebook reproduces the bug and the fix
- **Data-quality checks:** a duplicate row, invalid codes standing in for missing values, and labels that appear to be inverted in the Kaggle copy of the dataset
- **Leak-free preprocessing:** the train/test split is done first; imputation, one-hot encoding and scaling are fitted on the training data only
- **Verification:** the from-scratch coefficients match scikit-learn's (with regularisation switched off), and the two models make identical test predictions
- **Evaluation beyond accuracy:** majority-class baseline, confusion matrix, precision and recall for the disease class, the effect of the decision threshold, and 5-fold cross-validation

## Results

| Metric | Value |

| Baseline (always predict "no disease") | 54.1% |
| Test accuracy | 85.2% |
| 5-fold cross-validated accuracy | 83.7% ± 4.9% |
| Recall, disease class (threshold 0.5) | 75.0% |
| Precision, disease class (threshold 0.5) | 91.3% |

The test set has 61 patients, so these figures vary noticeably between splits.

## Dataset

Cleveland heart disease data from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/45/heart+disease) (Janosi, Steinbrunn, Pfisterer and Detrano, 1988), in the version commonly shared on Kaggle as `heart.csv`. The UCI data is licensed under CC BY 4.0.

In this version, `target = 1` appears to mean *no* disease. The notebook shows the evidence and creates a `disease` column where 1 means heart disease.

## How to run

Place `heart.csv` in the same folder as `logistic_regression.ipynb`, then open the notebook in Google Colab or Jupyter and run all cells.

Requirements: `numpy`, `pandas`, `matplotlib`, `scikit-learn`
