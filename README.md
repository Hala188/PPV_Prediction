# README: Machine Learning Regression Workflow

## Overview

This project demonstrates a machine learning workflow for regression tasks using PyCaret. The dataset contains four columns: `Gender`, `Age`, `Dur` (duration), and `PPV` (pay-per-view). The goal is to predict the `PPV` values based on the other features.

The best-performing model in this process was identified as the **Extra Trees Regressor**. Below is a step-by-step explanation of the process, how to run the code, and justifications for the chosen methods.

---

## Prerequisites

Before running the code, ensure you have the following installed:

- Python 3.8 or higher
- Required Python libraries:
  - pandas
  - pycaret
  - matplotlib
  - seaborn
  - openpyxl (to read Excel files)

Install the required libraries using pip:

```bash
pip install pandas pycaret matplotlib seaborn openpyxl
```

---

## Step-by-Step Process

### 1. Dataset Loading

The dataset is loaded using `pandas.read_excel`. Ensure the file `TG_T_CashValues_Rel.xlsx` is present in the working directory.

```python
import pandas as pd

df = pd.read_excel('TG_T_CashValues_Rel.xlsx')
```

### 2. Data Preprocessing

- **Checking for Missing Values:**

  - No missing values were detected in the dataset.

- **Checking for Duplicates:**

  - No duplicate records were found.

- **Ensuring Data Consistency:**

  - Verified that `Age`, `Dur`, and `PPV` are non-negative.
  - Converted `Gender` from object to categorical type for memory optimization.

- **Feature Engineering:**

  - Encoded `Gender` into numerical values: `Male` = 0 and `Female` = 1.
  - Adjusted data types for better memory usage.

### 3. Exploratory Data Analysis (EDA)

- **Correlation Heatmap:**

  - Visualized feature relationships using a heatmap.

- **Distribution Plot:**

  - Checked the distribution of the target variable `PPV`.

### 4. Model Training and Selection

- **PyCaret Setup:**

  - Initialized PyCaret’s regression module, specifying `PPV` as the target variable and `Gender` as a categorical feature.

- **Model Comparison:**

  - Compared multiple regression models using key metrics like MAE, RMSE, and R².
  - The **Extra Trees Regressor** was selected as the best-performing model with the lowest MAE (0.0096) and RMSE (0.0263).

### 5. Model Evaluation

- **Feature Importance:**

  - Assessed feature contributions to the model’s predictions. Although `Gender` had lower importance, retaining it improved performance.

- **Residual Analysis:**

  - Examined residuals to verify that errors are randomly distributed.

---

## How to Run the Code

1. Clone or download the project files.
2. Ensure the dataset (`TG_T_CashValues_Rel.xlsx`) is in the same directory as the script.
3. Run the script in a Python environment or IDE (e.g., Jupyter Notebook).
4. Follow the output logs to verify each step.

---

## Model Justification

The **Extra Trees Regressor** was chosen due to its:

- High accuracy (R² = 1.0000).
- Robust performance across validation folds.
- Superior performance in handling numerical and categorical features.

This model’s low MAE and RMSE indicate it generalizes well to unseen data while minimizing prediction errors.

---

## Additional Resources

- **PyCaret Documentation:** [https://pycaret.org/](https://pycaret.org/)
- **Seaborn Documentation:** [https://seaborn.pydata.org/](https://seaborn.pydata.org/)
- **Matplotlib Documentation:** [https://matplotlib.org/](https://matplotlib.org/)

Feel free to modify the code to test other datasets or additional features.

---

## Contact

For any issues or questions, please contact [halrantisi2@smail.ucas.edu.ps/https://www.linkedin.com/in/hala-alrantisi-890101253].

