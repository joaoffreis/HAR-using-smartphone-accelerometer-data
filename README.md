# Activity Classification Using Smartphone Accelerometer Data

This repository contains code and documentation for the final project from the HarvardX course: "Using Python for Research." The project involves classifying physical activities based on tri-axial accelerometer data collected from smartphones. Evaluation by the faculty was based primarily on the **accuracy** of the model's predictions on the test set, serving as the principal criterion for grading.

## Project Overview

The goal is to develop a machine learning model to classify accelerometer data into four activity categories:
- **1**: Standing
- **2**: Walking
- **3**: Stairs Down
- **4**: Stairs Up

## Dataset

The project uses the following datasets:
- **`train_time_series.csv`**: Contains raw accelerometer data with columns `timestamp`, `UTC time`, `accuracy`, `x`, `y`, and `z`.
- **`train_labels.csv`**: Contains activity labels for `train_time_series.csv`.
- **`test_time_series.csv`**: Contains accelerometer data for predictions.
- **`test_labels.csv`**: Contains timestamps for the test set; predictions will be saved here.

## Methods

### Data Preprocessing
- Checked for missing or corrupted values, and addressed class balance.
- Added acceleration magnitude as a feature and resolved timestamp inconsistencies.

### Feature Extraction
- Applied **Fourier Transform** and **Power Spectral Density** to generate frequency-domain features.
- Calculated statistical features, such as mean, max, skewness, and acceleration magnitudes.
  
### Model Training
- **Model Selection**: Chose **Random Forest** based on balanced performance across classes.
- **Class Imbalance Handling**: Applied **SMOTE** and calculated class weights to address imbalances.
- **Hyperparameter Tuning**: Used **Grid Search** to optimize parameters.
- **Cross-Validation**: Used 5-fold stratified cross-validation for robust evaluation.

### Model Evaluation
- **Metrics**: Evaluated primarily using F1 score, alongside precision, recall, and accuracy.
- **Test Set Results**: Achieved F1 Score: 0.7535, Precision: 0.7565, Recall: 0.7594, Accuracy: 0.7594.
- **Confusion Matrix** and **ROC Curve**: Analyzed model performance across classes.

## Results

- The Random Forest model demonstrated reliable performance across all activity classes.
- Minor improvements were noted from hyperparameter tuning.
- **Future Work**: Additional feature engineering and advanced imbalance handling could further enhance model performance.

## Code Execution Time

Execution timing, from loading test data to predictions, is measured to compare efficiency across students. This does not affect grading.