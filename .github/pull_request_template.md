## What changes are you trying to make? (e.g. Adding or removing code, refactoring existing code, adding reports)
 🔄 Changes Implemented
- Refactored feature selection to remove low-impact categorical variables.
- Improved SHAP analysis by refining visualizations and extracting clearer insights.
- Focused on numerical transformations for better predictive performance.

## What did you learn from the changes you have made?
📚 Key Learnings
- Geographic location (`num__coord_x`) plays a more significant role in fire spread predictions than initially thought.
- Several categorical features (`cat__month_*`) showed near-zero SHAP values, reinforcing the need for feature reduction.
- Numerical features related to moisture, temperature, and wind remain dominant predictors.

## Was there another approach you were thinking about making? If so, what approach(es) were you thinking of?
🔍 Alternative Approaches Considered
- Removing additional categorical variables, but we opted for a stepwise removal approach to avoid drastic performance drops.
- Applying PCA for dimensionality reduction instead of direct feature selection.
- Experimenting with different regression models, such as SVR or LightGBM.

## Were there any challenges? If so, what issue(s) did you face? How did you overcome it?
🚧 Challenges & Solutions
- **Issue:** Some features were mistakenly removed before encoding, causing key errors.
  - **Solution:** Adjusted feature selection to occur post-encoding.
- **Issue:** SHAP waterfall plots were initially empty.
  - **Solution:** Verified SHAP computation and ensured proper data transformations.
- **Issue:** Model retraining after feature removal affected stability.
  - **Solution:** Incremental removal and continuous validation using RMSE, MAE, and R².

## How were these changes tested?
🧪 Testing Methodology
- Conducted cross-validation on different feature sets.
- Monitored SHAP plots to ensure interpretability remained intact.
- Compared model performance before and after feature selection using RMSE, MAE, and R².

## A reference to a related issue in your repository (if applicable)
N/A

## Checklist
- [X] I can confirm that my changes are working as intended
- [x] SHAP visualizations are now interpretable.
- [x] Feature selection improves efficiency without sacrificing performance.
