# COMPAS Analysis in Python

## Purpose of the Analysis

This notebook reproduces the **Lecture 01** R workflow in Python using the **COMPAS** dataset.

The goal is to follow the same analysis pipeline as the original R version:

- Load the dataset
- Clean and filter the data using the same rules
- Produce the same exploratory summaries and plots
- Fit the same logistic regression model
- Evaluate the model using confusion-matrix style checks and race-level diagnostics

After applying the filtering steps, the final working sample contains **6,172 rows**.

## Main Results

A few of the key results reproduced in the notebook are:

- **Correlation between COMPAS score and length of stay:** approximately **0.207**
- **Two-year recidivism count:** **2,809**
- **Two-year recidivism rate:** approximately **45.51%**
- **African-American defendants** are estimated to be about **1.45 times more likely** than white defendants to receive a higher score, holding other model variables constant
- **Women** are estimated to be about **1.19 times more likely** than men to receive a higher score
- **Defendants under 25** are estimated to be about **2.50 times more likely** than defendants aged 25–45 to receive a higher score

## Model Evaluation

The notebook also reproduces the model evaluation section from the R workflow.

### Overall Confusion Matrix

The final confusion matrix is:

- **Predicted No Recid / Actual No Recid:** 2653
- **Predicted No Recid / Actual Recid:** 945
- **Predicted Recid / Actual No Recid:** 710
- **Predicted Recid / Actual Recid:** 1864

The notebook then breaks these results down by race and compares:

- False positive rate
- False negative rate

This matches the same general diagnostic goal as the original R script.

## Python Libraries Used

The notebook uses the following libraries:

- `pandas`
- `numpy`
- `statsmodels`
- `matplotlib`
- `IPython.display`
- `warnings`

### What Each Library Is Used For

- **pandas**: loading the CSV file, filtering rows, creating summary tables, crosstabs, and grouped metrics
- **numpy**: numerical operations and conditional logic
- **statsmodels**: fitting the logistic regression model with the same structure as the R script
- **matplotlib**: plotting COMPAS decile score distributions
- **IPython.display**: displaying the model summary in notebook format
- **warnings**: suppressing warning messages to keep notebook output cleaner

## Instructions for Reproducing the Results

Place the notebook and the data file in the same working directory. The notebook expects the dataset file to be named:

`compas-scores-two-years.csv`

Open the notebook:

`Lecture_01_Alignment_Python_G23607459.ipynb`

Run the notebook from top to bottom.

### Notebook Workflow

The workflow in the notebook is:

1. Import libraries
2. Read the COMPAS dataset
3. Filter and clean the rows using the same rules as the R script
4. Create the transformed variables used in the analysis
5. Generate descriptive summaries
6. Plot the decile score distributions
7. Fit the logistic regression model
8. Compute the predicted classes
9. Print the confusion matrix and race-level diagnostics

## Expected Checkpoint Outputs

If everything is set up correctly, you should see results close to the following:

- **Filtered sample size:** `6172`
- **Correlation between score and length of stay:** approximately `0.2073`
- **Two-year recidivism count:** `2809`
- **Two-year recidivism rate:** approximately `45.51`
- **Logistic regression coefficients** with the same directions as in the R script
- **Interpretation values** near:
  - `1.4528`
  - `1.1948`
  - `2.4961`
- **Overall confusion matrix counts:**
  - `2653`
  - `945`
  - `710`
  - `1864`
