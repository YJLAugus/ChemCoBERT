# Drug-Drug Interaction Prediction Project (Script 1)

## Project Introduction

This project is designed for predicting drug-drug interactions based on SMILES molecular representations and various machine learning models. It includes traditional machine learning models and a deep learning model based on ChemBERTa (ChemCoBERT).

## Directory Structure

```
1/
├── data/              # Data directory
├── models/            # Model saving directory
├── results/           # Results output directory
├── data1_process.ipynb # Main script file
├── requirements.txt   # Dependency package file
└── README.md          # Project description file
```

## Features

- **Multiple Model Support**: Includes Decision Tree, AdaBoost, GBDT, K-NN, Naive Bayes, and ChemCoBERT deep learning model
- **Feature Extraction**: Extracts molecular descriptors and Morgan fingerprints from SMILES representations
- **Cross-Validation**: Supports 3-fold and 5-fold cross-validation
- **Model Evaluation**: Calculates evaluation metrics such as AUC, Sensitivity, Specificity, Kappa, MCC, and F1
- **Visualization**: Generates ROC curves and PR curves
- **Memory Management**: Includes memory-safe decorator to optimize memory usage

## Dependency Installation

```bash
pip install -r requirements.txt
```

## Usage

1. Place your data files in the `data/` directory
2. Modify the data file paths in the script
3. Run the `data1_process.ipynb` script
4. Model results will be saved in the `results/` directory
5. Best models will be saved in the `models/` directory

## Data Format

Input data should be tab-separated text files with the following format:

```
drug1_smiles    drug2_smiles    label
```

Where `drug1_smiles` and `drug2_smiles` are SMILES representations of drugs, and `label` is a binary classification label (0 or 1).

## Model Outputs

- Model evaluation metrics (AUC, Sensitivity, Specificity, etc.)
- ROC curve and PR curve visualizations
- Best model weight files
- Prediction result CSV files

## Notes

- Running the deep learning model requires GPU support
- Large datasets may require longer running times
- First-time run will automatically download the ChemBERTa model, which requires network connection
