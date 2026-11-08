Linear Regression from Scratch

Linear regression implemented in NumPy two ways, and verified against scikit-learn.

## What's covered

- **Closed-form solution:** least squares using the Moore–Penrose pseudo-inverse, `b = pinv(X) @ y`
- **Gradient descent:** learning the slope and intercept iteratively by minimising mean squared error, including how the learning rate affects convergence and divergence
- **Effect of noise:** fitting data generated from `y = 2x + 3` at three noise levels and showing how R² and MAE change
- **Verification:** both from-scratch implementations produce the same coefficients as scikit-learn's `LinearRegression`
- **Simple vs multiple regression:** comparing one and two input features, and how correlated features affect coefficient interpretation

## Results

| Method | Slope | Intercept |
|---|---|---|
| Pseudo-inverse (NumPy) | 2.005 | 3.112 |
| Gradient descent (NumPy) | 2.005 | 3.112 |
| scikit-learn | 2.005 | 3.112 |

True values: slope = 2, intercept = 3, noise σ = 5.

| Noise (σ) | R² | MAE |
|---|---|---|
| 1 | 0.994 | 0.72 |
| 5 | 0.859 | 3.77 |
| 10 | 0.498 | 8.45 |

## How to run

Open `linear_regression.ipynb` in Google Colab or Jupyter and run all cells. All data is generated inside the notebook, so no downloads are needed.

Requirements: `numpy`, `pandas`, `matplotlib`, `scikit-learn`
