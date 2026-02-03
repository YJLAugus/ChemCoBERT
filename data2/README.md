# Drug-Drug Interaction Prediction Project (Script 2)

## Project Introduction

This project is designed for predicting drug-drug interactions based on SMILES molecular representations and various machine learning models. It includes traditional machine learning models and a deep learning model based on ChemBERTa (ChemCoBERT), with special emphasis on optimal threshold calculation and prediction result saving functions.

## Directory Structure

```
2/
├── data/              # Data directory
├── models/            # Model saving directory
├── results/           # Results output directory
├── data2_process.ipynb # Main script file
├── requirements.txt   # Dependency package file
└── README.md          # Project description file
```

## Features

- **Multiple Model Support**: Includes Decision Tree, AdaBoost, GBDT, K-NN, Naive Bayes, and ChemCoBERT deep learning model
- **Feature Extraction**: Extracts molecular descriptors and Morgan fingerprints from SMILES representations
- **Optimal Threshold Calculation**: Uses Youden's J statistic to find the optimal classification threshold
- **Model Evaluation**: Calculates evaluation metrics such as AUC, Sensitivity, Specificity, Kappa, MCC, and F1
- **Visualization**: Generates ROC curves and PR curves
- **Memory Management**: Includes memory-safe decorator to optimize memory usage
- **Prediction Result Saving**: Saves prediction scores and original labels as CSV files
- **Model Persistence**: Supports saving and loading models

## Dependency Installation

```bash
pip install -r requirements.txt
```

## Usage

1. Place your training data file in the `data/` directory, named `train.txt`
2. Place your test data file in the `data/` directory, named `test.txt`
3. Modify the data file paths in the script
4. Run the `data2_process.ipynb` script
5. Model results will be saved in the `results/` directory
6. Best models will be saved in the `models/` directory

## Data Format

Input data should be tab-separated text files with the following format:

```
drug1_smiles    drug2_smiles    label
```

Where `drug1_smiles` and `drug2_smiles` are SMILES representations of drugs, and `label` is a binary classification label (0 or 1).

## Model Outputs

- Model evaluation metrics (AUC, Sensitivity, Specificity, etc.)
- ROC curve and PR curve visualizations
- Best model weight files (.pth or .joblib format)
- Prediction result CSV files, including original labels and prediction scores
- Test set prediction results (with optimal threshold)

## Unique Features

1. **Optimal Threshold Calculation**: Automatically finds the optimal classification threshold using Youden's J statistic to improve model performance
2. **Prediction Result Saving**: Saves each model's prediction scores and original labels as CSV files for subsequent analysis
3. **Model Persistence**: Supports saving and loading models for later use
4. **Test Set Prediction**: Can generate prediction results even when test set has no labels

## Notes

- Running the deep learning model requires GPU support
- Large datasets may require longer running times
- First-time run will automatically download the ChemBERTa model, which requires network connection
- Traditional machine learning models are saved using joblib, while deep learning models are saved using torch
