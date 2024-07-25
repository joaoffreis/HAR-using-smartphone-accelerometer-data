# Activity Classification Using Smartphone Accelerometer Data

This repository contains the code and documentation for the final project from the HarvardX course: "Using Python for Research". The project involves classifying physical activities based on tri-axial accelerometer data collected from smartphones. 

## Project Overview

The aim of this project is to develop a robust machine learning model to classify accelerometer data into four distinct activity categories:
- **1**: Standing
- **2**: Walking
- **3**: Stairs Down
- **4**: Stairs Up

## Dataset

The project uses the following datasets:
- **`train_time_series.csv`**: Contains raw accelerometer data with columns `timestamp`, `UTC time`, `accuracy`, `x`, `y`, and `z`.
- **`train_labels.csv`**: Contains activity labels corresponding to the accelerometer data in `train_time_series.csv`.
- **`test_time_series.csv`**: Contains accelerometer data for which predictions are to be made.
- **`test_labels.csv`**: Contains timestamps for the test set; predictions are to be added to this file.

## Methods

### Data Preprocessing
- Checked for missing or corrupted values.
- Verified class balance and completeness of measurements.
- Added acceleration magnitude as a feature.
- Addressed inconsistencies in timestamp records.

### Feature Extraction
- Applied PCA to reduce dimensionality and extract relevant features from the accelerometer data.

### Model Training
- **Model Selection**: Chose Support Vector Machine (SVM) for its superior F1 score and stability.
- **Hyperparameter Tuning**: Optimized using Grid Search with parameters including `C`, `kernel`, `gamma`, and `pca__n_components`.
- **Cross-Validation**: Used 3-fold cross-validation with stratified splits to handle class imbalance.

### Model Evaluation
- **Metrics**: Evaluated using F1 score and accuracy.
- **Test Set Results**: Achieved F1 Score: 0.6959 and Accuracy: 0.7299.

## Results

- The SVM model demonstrated reliable performance but showed limited improvement from hyperparameter tuning.
- Feature extraction and model tuning were crucial but improvements were modest.
- **Future Work**: Enhancements could include advanced feature engineering and exploring class imbalance techniques like SMOTE.

## Running the Code

To run the code:
1. Ensure you have the necessary Python libraries installed (e.g., `numpy`, `pandas`, `scikit-learn`).
2. Load the datasets and preprocess the data as described.
3. Run the model training and evaluation scripts.
4. Generate predictions for the test set and save them in `test_labels.csv`.

## Code Execution Time

Timing the execution of the code, from loading the test data to completing the predictions, was requested to compare the computational efficiency of different students. It does not affect grading.