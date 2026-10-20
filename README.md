# Student Performance Prediction System

## Project Overview

This project uses machine learning to predict students' final Portuguese course grades using the UCI Student Performance dataset.

## Dataset

- Source: UCI Machine Learning Repository
- Dataset ID: 320
- Records: 649
- Original features: 30
- Target variable: G3
- Grade scale: 0–20

Dataset: https://archive.ics.uci.edu/dataset/320/student+performance

Note: This dataset represents Portuguese secondary-school students, not Indian college students.

## Tools and Technologies

- Python
- Pandas
- Matplotlib
- scikit-learn
- ucimlrepo
- Google Colab

## Model Evaluation

### Scenario A: With Previous Grades (G1 and G2)

| Model | MAE | R² |
|---|---:|---:|
| Mean Baseline | 2.395 | -0.032 |
| Linear Regression | 0.765 | 0.849 |

### Scenario B: Without Previous Grades

| Model | MAE | R² |
|---|---:|---:|
| Mean Baseline | 2.395 | -0.032 |
| Linear Regression | 2.156 | 0.160 |
| Random Forest | 2.040 | 0.188 |

MAE measures average absolute prediction error in grade points. R² is not percentage accuracy.

## Limitations

- Results are based on one train-test split.
- The dataset is not representative of Indian college students.
- Further validation is needed before real-world use.
- The model should not be used alone for high-stakes academic decisions.

## Project Status

Initial model training and evaluation completed. Further validation and deployment are pending.

### Cross-Validation Results

Both Random Forest Regressor and Linear Regression were evaluated using 5-fold cross-validation on the training data. The experiment excluded the previous-period grades (`G1` and `G2`) to assess prediction using the remaining features.

| Model | Mean CV MAE | Standard Deviation |
|---|---:|---:|
| Random Forest Regressor | 2.023 | 0.093 |
| Linear Regression | 2.046 | 0.181 |

**Interpretation:** Random Forest achieved a slightly lower mean cross-validation MAE, while also showing lower fold-to-fold variation in this experiment. However, the difference in mean MAE was small, so these results do not establish a decisive performance advantage for either model.

**Limitations:** Results are based on the UCI Student Performance dataset and should not be generalized to Indian college students without further validation. Cross-validation scores represent training-data evaluation, not final test-set performance.

**Evaluation metric:** Mean Absolute Error (MAE), measured in grade points. Lower values indicate predictions closer to the actual grades on average.

### Final Test-Set Evaluation

The models were evaluated on a held-out test set containing 130 records. Previous-period grades (`G1` and `G2`) were excluded from the input features.

| Model | MAE | R² |
|---|---:|---:|
| Linear Regression | 2.156 | 0.160 |
| Random Forest Regressor | 2.040 | 0.188 |

**Result:** Random Forest achieved a slightly lower MAE and a slightly higher R² than Linear Regression on the held-out test set.

**Interpretation:** The Random Forest model's predictions differed from actual grades by approximately 2.04 grade points on average. Its R² of 0.188 indicates limited explanatory performance on this test set; it does not represent prediction accuracy.

**Limitations:** This experiment uses the UCI Student Performance dataset, which describes Portuguese secondary-school students. The results should not be generalized to Indian college students without external validation.
