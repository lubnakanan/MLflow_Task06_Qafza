# Titanic Survival Prediction with MLflow

This repository contains a notebook and insights related to the **Titanic Survival Prediction** task. The project uses MLflow for experiment tracking and evaluates various metrics to understand model performance across different scenarios.

---

## Main Data Information

The dataset is based on the historical Titanic passenger data, which includes features such as:

- **Pclass**: Passenger class (1st, 2nd, 3rd)
- **Sex**: Gender of the passenger
- **Age**: Passenger's age
- **Fare**: Ticket fare
- **Embarked**: Port of embarkation (C, Q, S)
- **Survived**: Target variable indicating survival status (1 = Survived, 0 = Did not survive)

### Data Preprocessing Steps
1. Imputation of missing values:
   - Median age for missing `Age`.
   - Most frequent value ('S') for missing `Embarked`.
2. One-hot encoding for categorical variables (`Sex` and `Embarked`).
3. Selection of key features:
   - `Pclass`, `Age`, `Fare`, `Sex_male`, `Embarked_Q`, `Embarked_S`.

---

## Insights from Offline Evaluation Metrics

### Perturbation Tests
- **Accuracy on noisy data**: 0.7877
  - Insight: The model maintains stability under noise, showing moderate robustness.

### Invariance Tests
- **Accuracy without 'Sex_male' feature**: 0.7151
  - Insight: Removing the `Sex_male` feature significantly reduces performance, indicating high dependence on gender for predictions.

### Directional Expectation Tests
- **Accuracy after increasing 'Fare' by 50%**: 0.7654
  - Insight: The model's performance shows minor sensitivity to fare increases, reflecting a reasonable understanding of its importance.

### Slice-Based Evaluation
- **Accuracy for male passengers**: 0.8
- **Accuracy for female passengers**: 0.7971
  - Insight: The model performs consistently across gender groups, showing minimal bias.

#### Performance Based on Age:
- **Passengers under 30**: 0.8455
- **Passengers 30 or older**: 0.7246
  - Insight: Higher accuracy for younger passengers suggests age-related trends in survival predictions.

---

## Experiment Logs

View the MLflow experiment logs on Google Drive: [MLflow Logs Folder](https://drive.google.com/drive/folders/1hi9qaD4YOoOPVgOoApOmUmFKCt3ma49C?usp=sharing)

---

## How to Use This Repository
1. **Notebook**: Open the `MLflow_Task06_Qafza.ipynb` file to explore the code and MLflow experiment tracking setup.
2. **Insights**: Read the Insights from `MLflow_Task06_LubnaKanan.docx` file or from this `README File`.
