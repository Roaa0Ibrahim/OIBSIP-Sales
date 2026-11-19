# Sales Prediction from Advertising

Task from the **Oasis Infobyte Data Science Internship** (OIBSIP), June 2024.

## Question
Sales depend on how much a business spends on advertising and where. Can we predict sales from advertising spend, and which channel actually matters?

## Data
`Advertising.csv`: **200 markets × 3 advertising budgets** (TV, radio, newspaper) and the resulting sales.

## What I did
1. **Data inspection:** structure, unique values, nulls and duplicates (none); dropped the index column.
2. **Visual analysis:** scatter plots of sales against each channel, histograms, distributions, pair plot and box plots.
3. **Outliers:** removed markets with newspaper spend above 80 (196 markets kept).
4. **Prediction model:** linear regression on a 70/30 train–test split.
5. **Statistical model:** ordinary least squares (statsmodels) of `Sales ~ TV + Radio + Newspaper`, to test each channel's effect.

## Result
| Channel | Coefficient | p-value |
|---|---|---|
| TV | 0.046 | < 0.001 |
| Radio | 0.187 | < 0.001 |
| Newspaper | 0.004 | 0.59 |

**TV and radio spending had a significant effect on sales; newspaper spending did not.** The statistical model was fitted on all 196 markets (R² = 0.90), so it describes the data rather than measuring prediction on unseen data.

## Tools
Python · Pandas · NumPy · scikit-learn · statsmodels · Matplotlib · Seaborn · Jupyter

## Files
- `Sales Predictions.ipynb`: analysis and models
- `Advertising.csv`: dataset

## Data source
The Advertising dataset from *An Introduction to Statistical Learning* (James, Witten, Hastie and Tibshirani), provided with the internship task.

## Running it
Place `Advertising.csv` next to the notebook and change the `read_csv` path to `"Advertising.csv"`.
