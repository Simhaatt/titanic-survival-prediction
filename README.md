# Titanic Survival Prediction

Logistic regression baseline with feature engineering for the Kaggle Titanic dataset.

## Project Structure
- `notebook35b55729b3.ipynb` – end-to-end workflow: load data, clean features, train logistic regression, tune decision threshold, generate submission.

## Data
- Expects Kaggle Titanic files at `/kaggle/input/titanic/train.csv` and `/kaggle/input/titanic/test.csv` (Kaggle notebook paths). Update paths if running locally.

## Feature Engineering (inside the notebook)
- Titles extracted from `Name` with one-hot encoding.
- Deck letters derived from `Cabin` plus unknown bucket.
- Encodings for `Embarked` and `Sex`.
- Family-based features: `FamilySize`, `IsAlone`, `FarePerPerson`.
- Log transform of `Fare`, age bins, and `Sex_Pclass` interaction.
- Median/mode imputation for numerical/categorical gaps.

## Modeling
- Train/validation split with stratification.
- Logistic regression (`max_iter=1000`).
- Threshold sweep to maximize F1; best threshold reused for test predictions.
- Plots precision/recall/F1 vs. threshold.

## How to Run
1) Open the notebook in Kaggle (or locally with matching file paths).
2) Run all cells to train, evaluate, and write `submission.csv`.
3) Adjust `best_t` in the final cell if you change the threshold search logic.

## Notes
- The repo is minimal on purpose; add requirements or scripts if you turn this into a full project.
