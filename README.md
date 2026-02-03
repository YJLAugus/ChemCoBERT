# Drug-Drug Interaction Prediction Project Suite

## Project Overview

This repository contains a suite of three independent scripts for predicting drug-drug interactions based on SMILES molecular representations. Each script implements different approaches and features for drug interaction prediction, leveraging both traditional machine learning models and deep learning techniques.

## Directory Structure

```
 ChemCoBERT/
├── 1/                # Script 1 directory
│   ├── data/         # Data directory
│   ├── models/       # Model saving directory
│   ├── results/      # Results output directory
│   ├── data1_process.ipynb # Main script file
│   ├── requirements.txt # Dependency package file
│   └── README.md     # Project description file
├── 2/                # Script 2 directory
│   ├── data/         # Data directory
│   ├── models/       # Model saving directory
│   ├── results/      # Results output directory
│   ├── data2_process.ipynb # Main script file
│   ├── requirements.txt # Dependency package file
│   └── README.md     # Project description file
├── 3/                # Script 3 directory
│   ├── data/         # Data directory
│   ├── models/       # Model saving directory
│   ├── results/      # Results output directory
│   ├── data3_process.ipynb # Main script file
│   ├── requirements.txt # Dependency package file
│   └── README.md     # Project description file
└── README.md         # This overview document
```

## Script Descriptions

### Script 1

- **Main Feature**: Implements basic drug-drug interaction prediction with multiple machine learning models
- **Models**: Decision Tree, AdaBoost, GBDT, K-NN, Naive Bayes, and ChemCoBERT (deep learning)
- **Key Features**: Cross-validation (3-fold and 5-fold), ROC/PR curve visualization, memory optimization
- **Use Case**: Suitable for general drug interaction prediction tasks with standard evaluation

### Script 2

- **Main Feature**: Enhanced drug-drug interaction prediction with optimal threshold calculation
- **Models**: Same as Script 1
- **Key Features**: Optimal threshold calculation using Youden's J statistic, prediction result saving, model persistence
- **Use Case**: Suitable for tasks requiring precise threshold determination and result analysis

### Script 3

- **Main Feature**: Advanced drug-drug interaction prediction with improved evaluation functions
- **Models**: Same as Script 1
- **Key Features**: Improved evaluation for extreme cases, data balance checking, comprehensive model performance comparison
- **Use Case**: Suitable for complex datasets with potential class imbalance issues

## Common Dependencies

All scripts share the following core dependencies:

- pandas, numpy - Data processing
- scikit-learn - Machine learning models
- matplotlib, seaborn - Data visualization
- torch - Deep learning framework
- rdkit - Molecular feature extraction
- transformers - ChemBERTa model
- tqdm - Progress bars
- psutil - Memory management
- joblib - Model persistence (Scripts 2 and 3)

## Installation

To install dependencies for each script:

```bash
# For Script 1
cd 1
pip install -r requirements.txt

# For Script 2
cd ../2
pip install -r requirements.txt

# For Script 3
cd ../3
pip install -r requirements.txt
```

## Usage

1. **Prepare Data**: Place your drug interaction data in the `data/` directory of the respective script
2. **Configure Paths**: Modify the data file paths in the script if necessary
3. **Run Script**: Execute the Jupyter Notebook file (`dataX_process.ipynb`)
4. **View Results**: Check the `results/` directory for output files and visualizations
5. **Access Models**: Trained models are saved in the `models/` directory

## Data Format

All scripts expect tab-separated text files with the following format:

```
drug1_smiles    drug2_smiles    label
```

Where:
- `drug1_smiles` and `drug2_smiles` are SMILES string representations of drugs
- `label` is a binary classification label (0 = no interaction, 1 = interaction)

## Key Features Across All Scripts

- **Multiple Model Support**: Comprehensive set of machine learning models
- **Molecular Feature Extraction**: Uses RDKit to extract descriptors and fingerprints
- **Deep Learning Integration**: Incorporates ChemBERTa for enhanced prediction
- **Performance Evaluation**: Calculates multiple metrics (AUC, Sensitivity, Specificity, etc.)
- **Visualization**: Generates ROC and PR curves for model comparison
- **Memory Optimization**: Includes memory-safe decorators for efficient processing

## Choosing the Right Script

- **Script 1**: Basic implementation for standard use cases
- **Script 2**: Enhanced with optimal threshold calculation for better classification
- **Script 3**: Advanced with improved evaluation for complex datasets

## Hardware Requirements

- **CPU**: All scripts can run on CPU
- **GPU**: Recommended for running the ChemCoBERT deep learning model (significantly faster)
- **Memory**: At least 8GB RAM for medium-sized datasets

## Notes

- First-time execution will download the ChemBERTa model (requires internet connection)
- Large datasets may require longer processing times
- Each script is independent and can be used separately
- Model performance may vary based on dataset characteristics

## Troubleshooting

- **Memory Errors**: Reduce batch size or fingerprint size
- **GPU Issues**: Try running on CPU if GPU memory is insufficient
- **Model Download Failures**: Ensure stable internet connection
- **Data Format Errors**: Verify input files follow the required tab-separated format

## License

This project is open source and available for research purposes.

## Contact

For questions or issues, please contact the project maintainers.
