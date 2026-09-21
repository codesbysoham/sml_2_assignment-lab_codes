# SML 2 Assignment – Machine Learning Lab

A structured collection of Machine Learning Lab (SML 2) implementations using the BSDS500 (Berkeley Segmentation Data Set) image dataset.

This repository combines the original Module-II Metaheuristic Optimization work with a separate, self-contained set of BSDS500-based ML assignment notebooks (Q1–Q7).

## Overview

The BSDS500 dataset contains natural images together with human-annotated segmentation/boundary information. For the seven ML questions, the image data is converted into a pixel-level classification / feature-learning setup.

### Dataset setup
- Images: JPEG/PNG image files
- Ground truth: MATLAB `.mat` annotation files
- Ground-truth structure: `groundTruth`
- Boundary field: `Boundaries`
- Target: boundary vs. non-boundary pixel
- Pixel features: RGB, grayscale intensity and gradient magnitude
- Splits: original train / validation / test directory structure is preserved

> Ground-truth annotations are loaded directly from MATLAB `.mat` files rather than being treated as image files.

## Repository Structure

```text
sml_2_assignment-lab_codes/
│
├── README.md
├── requirements.txt
│
├── BSDS500_ML_Assignment/
│   ├── README.md
│   ├── Q1_kNN.ipynb
│   ├── Q2_Decision_Tree.ipynb
│   ├── Q3_Naive_Bayes.ipynb
│   ├── Q4_Logistic_Regression.ipynb
│   ├── Q5_PCA_tSNE.ipynb
│   ├── Q6_Outlier_Detection.ipynb
│   └── Q7_LR_vs_SVM.ipynb
│
├── Module-II/
│   ├── Simulated-Annealing/
│   │   └── README.md
│   └── Genetic-Algorithm/
│       ├── GA-Q1/
│       │   └── README.md
│       └── GA-Q2/
│           └── README.md
│
├── Simulated_Annealing_Unique.ipynb
├── Genetic_Algorithm_1_Unique.ipynb
└── Genetic_Algorithm_2_Unique.ipynb
```

## BSDS500 ML Assignment

The `BSDS500_ML_Assignment/` folder contains seven notebooks covering supervised learning, dimensionality reduction and outlier detection.

| Question | Method | Main focus |
|---|---|---|
| Q1 | k-Nearest Neighbours | Pixel-level boundary classification |
| Q2 | Decision Tree | Gini impurity, split selection and recursive tree construction |
| Q3 | Gaussian Naive Bayes | Class-conditional Gaussian modelling |
| Q4 | Logistic Regression | Binary classification using gradient descent |
| Q5 | PCA + t-SNE | Dimensionality reduction and 2D representation |
| Q6 | Outlier Detection | Z-score and IQR-based analysis |
| Q7 | Logistic Regression vs SVM | Comparative metrics and ROC/AUC |

### Q1 — k-Nearest Neighbours
Implements k-NN with vectorized Euclidean distance computation and evaluates multiple values of k for boundary/non-boundary pixel classification.

### Q2 — Decision Tree
Builds a decision tree from scratch using Gini impurity, threshold-based splitting, recursive partitioning and tree visualization.

### Q3 — Gaussian Naive Bayes
Implements Gaussian Naive Bayes from scratch using class-wise feature statistics and Gaussian likelihoods.

### Q4 — Logistic Regression
Implements binary logistic regression from scratch using the sigmoid function and gradient-descent optimization.

### Q5 — PCA and t-SNE
Performs PCA using covariance/eigen decomposition and a lightweight t-SNE workflow for two-dimensional visualization of pixel-feature structure.

### Q6 — Outlier Detection
Studies image-level summary statistics using Z-score and IQR methods, followed by winsorization/capping analysis.

### Q7 — Logistic Regression vs SVM
Trains both classifiers from scratch and compares them using:
- Accuracy
- Precision
- Recall
- F1-score
- ROC curves
- AUC

## Dataset

The notebooks expect the BSDS500 archive in the following local layout:

```text
bsds500archive/
├── images/
│   ├── train/
│   ├── val/
│   └── test/
└── ground_truth/
    ├── train/
    ├── val/
    └── test/
```

The current notebooks use:

```python
BASE = r"C:\Users\cqds\Downloads\bsds500archive"
```

Update `BASE` before running the notebooks if the dataset is stored elsewhere.

## Running the notebooks

### 1. Install dependencies

```bash
python -m pip install -r requirements.txt
```

Additional packages used by the BSDS500 notebooks:

```text
scipy
pillow
```

### 2. Open a notebook
Use Jupyter Notebook, JupyterLab, or VS Code with a Python kernel.

### 3. Execute cells top-to-bottom
Each notebook follows a consistent workflow: dataset setup → preprocessing → algorithm implementation → evaluation → visualization.

## Important Notes

- BSDS500 ground truth files are `.mat` MATLAB files, not `.jpg` files.
- Image and annotation files are paired using the image filename stem.
- Q1–Q4 and Q7 use the annotated boundary ground truth.
- Q5 and Q6 use image-derived features and do not require ground-truth `.mat` files.
- The notebooks implement the requested algorithms directly rather than replacing the core methods with black-box model calls.

## Module-II Metaheuristic Work

The repository also contains the earlier Module-II work:

- Simulated Annealing — numerical function minimization
- Genetic Algorithm Q1 — binary chromosome optimization
- Genetic Algorithm Q2 — real-valued decoding and minimization

These files remain available at the repository root and inside `Module-II/`.

## Author

**Soham**  
GitHub: [@codesbysoham](https://github.com/codesbysoham)

---

*Machine Learning Lab — SML 2*