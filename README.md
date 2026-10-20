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
