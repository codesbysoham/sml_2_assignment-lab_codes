# BSDS500 ML Assignment

## Purpose

This folder contains the seven Jupyter notebooks for the SML 2 machine-learning assignment, implemented using the BSDS500 image dataset.

The notebooks use a common data representation wherever the problem requires supervised learning: sampled image pixels are described by RGB, grayscale and gradient-based features, while BSDS500 `.mat` annotations provide the boundary labels.

## Dataset Layout

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

Images are loaded from the image directories and matched to the corresponding `.mat` annotation using the image filename stem. Ground truth is read with `scipy.io.loadmat` from the `groundTruth` / `Boundaries` structure.

## Assignment Map

| File | Method | What it demonstrates |
|---|---|---|
| `Q1_kNN.ipynb` | k-NN | Vectorized distance computation, neighbourhood voting, model selection over k, evaluation |
| `Q2_Decision_Tree.ipynb` | Decision Tree | Gini impurity, threshold search, recursive tree construction, prediction and visualization |
| `Q3_Naive_Bayes.ipynb` | Gaussian Naive Bayes | Class-wise Gaussian statistics, likelihood-based prediction and evaluation |
| `Q4_Logistic_Regression.ipynb` | Logistic Regression | Sigmoid model, gradient descent, binary classification metrics |
| `Q5_PCA_tSNE.ipynb` | PCA + t-SNE | Covariance/eigen decomposition, variance explained and 2D embedding |
| `Q6_Outlier_Detection.ipynb` | Outlier Detection | Z-score, IQR fences, outlier identification and capping |
| `Q7_LR_vs_SVM.ipynb` | Logistic Regression + SVM | Two classifiers, confusion metrics, ROC curves and AUC comparison |

## Running

1. Download/extract BSDS500 and reproduce the directory structure above.
2. Open the required notebook in Jupyter, JupyterLab or VS Code.
3. Update the `BASE` variable if the dataset is not stored at the path currently configured in the notebook.
4. Run cells from top to bottom.

### Packages

```bash
python -m pip install -r ../requirements.txt scipy pillow
```

## Reproducibility Notes

- Random sampling uses explicit seeds in the notebooks where sampling is involved.
- Train/test directory separation is retained.
- Ground-truth dimensions are checked against the corresponding image dimensions.
- Ground-truth files are never opened with PIL; PIL is used only for image files.

## Scope

Q1–Q4 and Q7 use supervised boundary labels from BSDS500 annotations. Q5 and Q6 work from image-derived features and therefore do not require the `.mat` annotations.

---

**SML 2 · BSDS500 Machine Learning Assignment**