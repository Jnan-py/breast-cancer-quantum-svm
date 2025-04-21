# Quantum and Classical SVM for Breast Cancer Classification

A comparative implementation of Support Vector Classifiers (SVC) on the UCI Breast Cancer Wisconsin dataset using both classical and quantum kernels in Python.

## Description

This repository demonstrates how to preprocess data, apply PCA for dimensionality reduction, and train both classical and quantum SVMs with custom feature maps (ZZ, Z, and Pauli) on the breast cancer dataset. Results include training and test accuracies, along with classification reports.

## Features

- Data loading and standard scaling
- PCA for reducing to 2 dimensions
- Custom quantum feature maps (ZZ, Z, Pauli)
- RealAmplitudes ansatz composition
- Fidelity-based quantum kernels with Qiskit Machine Learning
- Classical SVM comparison
- Model persistence with pickle

## Requirements

See [requirements.txt](requirements.txt) for the full list of Python dependencies.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Jnan-py/breast-cancer-quantum-svm.git
   cd breast-cancer-quantum-svm
   ```
2. Create and activate a virtual environment (optional but recommended):
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows: venv\\Scripts\\activate
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

1. Run the main script (e.g., `breast_cancer_qsvc.ipynb`):

2. The script will:

   - Load and preprocess the data
   - Reduce dimensions via PCA
   - Build and compose the quantum circuits
   - Train or load pre-trained classical and quantum SVC models
   - Output training and test accuracies
   - Display classification report for the best-performing model

3. Trained model files will be saved under the `models/` directory.

(Train your own models with different PCA reduction as the trained and stored PCA file might be different)

## Project Structure

```
├── models/                    # Saved model binaries ('*.pkl')
├── breast_cancer_qsvc.ipynb   # Main Python script
├── requirements.txt           # Python package dependencies
└── README.md                  # Project documentation
```

## Feature Maps

- **ZZ Feature Map**: Custom implementation of ZZ interactions with RY and RZ rotations.
- **Z Feature Map**: Z-rotations interleaved with CX and RX.
- **Pauli Feature Map**: Z, X, and Y rotations per qubit with entanglement.

## Model Training & Inference

- **QSVC (Quantum SVC)**

  - FidelityQuantumKernel built with `ComputeUncompute` and `Sampler` primitives.
  - Uses custom feature maps composed with a `RealAmplitudes` ansatz.
  - Models saved as `models/qsvc_{map}.pkl`.

- **SVC (Classical SVM)**
  - RBF kernel SVM from scikit-learn.
  - Saved as `models/svc_model.pkl`.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request.
