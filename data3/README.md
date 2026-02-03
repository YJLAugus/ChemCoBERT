# Drug-Drug Interaction Prediction Project (Script 3)

## Project Introduction

This project is designed for predicting drug-drug interactions based on SMILES molecular representations and various machine learning models. It includes traditional machine learning models and a deep learning model based on ChemBERTa (ChemCoBERT), with special emphasis on improved evaluation functions and data balance checking features.

## Directory Structure

```
3/
├── data/              # Data directory
├── models/            # Model saving directory
├── results/           # Results output directory
├── data3_process.ipynb # Main script file
├── requirements.txt   # Dependency package file
└── README.md          # Project description file
```

## Features

- **Multiple Model Support**: Includes Decision Tree, AdaBoost, GBDT, K-NN, Naive Bayes, and ChemCoBERT deep learning model
- **Feature Extraction**: Extracts molecular descriptors and Morgan fingerprints from SMILES representations
- **Improved Evaluation Functions**: Supports handling extreme cases (such as test sets with all 0 or 1 labels)
- **Optimal Threshold Calculation**: Uses Youden's J statistic to find the optimal classification threshold
- **Model Evaluation**: Calculates evaluation metrics such as AUC, Sensitivity, Specificity, Kappa, MCC, and F1
- **Data Balance Checking**: Automatically checks class distribution in training and test sets
- **Memory Management**: Includes memory-safe decorator to optimize memory usage
- **Prediction Result Saving**: Saves prediction scores and original labels as CSV files
- **Model Persistence**: Supports saving and loading models
- **Model Performance Comparison**: Generates performance comparison tables for all models

## Dependency Installation

```bash
pip install -r requirements.txt
```

## Usage

1. Place your training data file in the `data/` directory, named `train.txt`
2. Place your test data file in the `data/` directory, named `test.txt`
3. Modify the data file paths in the script
4. Run the `data3_process.ipynb` script
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
- Model performance comparison tables
- Best model weight files (.pth or .joblib format)
- Prediction result CSV files, including original labels and prediction scores
- Data balance analysis

## Unique Features

1. **Improved Evaluation Functions**: Supports handling extreme cases where test set labels are all 0 or 1, providing reasonable fallback metric calculations
2. **Data Balance Checking**: Automatically checks class distribution in training and test sets to help understand data characteristics
3. **Model Performance Comparison**: Generates performance comparison tables for all models, facilitating intuitive comparison of different models' performance
4. **Training Set Fallback Threshold**: Uses training set to determine optimal threshold when ROC curve cannot be calculated from test set

## Notes

- Running the deep learning model requires GPU support
- Large datasets may require longer running times
- First-time run will automatically download the ChemBERTa model, which requires network connection
- Traditional machine learning models are saved using joblib, while deep learning models are saved using torch

## Performance Comparison

After running the script, a `model_performance_comparison.csv` file will be generated, containing performance metric comparisons for all models, making it easy for users to select the best model.

## Troubleshooting

- **Memory Errors**: If you encounter memory errors, try reducing the batch size or using a smaller fingerprint size
- **GPU Memory Insufficient**: If GPU memory is insufficient, try reducing the batch size or running on CPU
- **Model Download Failure**: Ensure network connection is normal, as the ChemBERTa model needs to be downloaded from Hugging Face
