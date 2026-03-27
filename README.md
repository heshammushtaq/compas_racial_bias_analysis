# README

## Purpose of the analysis

This notebook reproduces the Lecture 01 R workflow in Python using the COMPAS data.

The goal is to follow the same analysis flow from the R version:
- load the dataset
- clean and filter the data using the same rules
- do the same exploratory summaries and plots
- fit the same logistic regression model
- evaluate the model using the same confusion-matrix style checks and race-level diagnostics

After the filtering steps, the working sample has 6172 rows.

A few of the main results from the notebook are:
- correlation between COMPAS score and length of stay: about 0.207
- two-year recidivism count: 2809
- two-year recidivism rate: about 45.51%
- African-American defendants are estimated to be about 1.45 times more likely than white defendants to receive a higher score, holding the other variables in the model fixed
- women are about 1.19 times more likely than men to receive a higher score
- defendants under 25 are about 2.50 times more likely than the 25-45 group to receive a higher score

The notebook also reproduces the model evaluation section. The overall confusion matrix in the final version is:

- Predicted No Recid / Actual No Recid: 2653
- Predicted No Recid / Actual Recid: 945
- Predicted Recid / Actual No Recid: 710
- Predicted Recid / Actual Recid: 1864

Then the notebook breaks those results out by race and compares false positive rate and false negative rate across groups, which is the same general point of the R script's diagnostic section.

## Python libraries used

The notebook uses these libraries:

- pandas
- numpy
- statsmodels
- matplotlib
- IPython.display
- warnings

What they are used for in this notebook:
- pandas: loading the CSV file, filtering rows, creating summary tables, crosstabs, and grouped metrics
- numpy: numeric work and conditional logic
- statsmodels: fitting the logistic regression model with the same structure as the R script
- matplotlib: plotting the COMPAS decile score distributions
- IPython.display: printing the model summary in notebook form
- warnings: hiding warning messages so the notebook output stays cleaner

## Instructions for reproducing the results

1. Put the notebook and the data file in the same working folder.
   The notebook expects the file named `compas-scores-two-years.csv`.

2. Open the notebook:
   `Lecture_01_Alignment_Python_G23607459.ipynb`

3. Run the notebook from top to bottom.

4. The workflow in the notebook is:
   - import libraries
   - read the COMPAS dataset
   - filter and clean the rows the same way as in the R script
   - create the transformed variables used in the analysis
   - generate descriptive summaries
   - plot the decile score distributions
   - fit the logistic regression model
   - compute the predicted classes
   - print the confusion matrix and race-level diagnostics

5. If everything is set up correctly, you should see the main checkpoint outputs:
   - filtered sample size: 6172
   - correlation between score and length of stay: about 0.2073
   - two-year recidivism count: 2809
   - two-year recidivism rate: about 45.51
   - logistic regression coefficients with the same direction as the R script
   - interpretation values near 1.4528, 1.1948, and 2.4961
   - overall confusion matrix with counts 2653, 945, 710, and 1864

This README is only for the Python notebook part of the assignment.
