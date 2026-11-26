# Module I — Core Statistical Machine Learning Labs

Seven notebook experiments apply core statistical-learning methods to BSDS500 image analysis.

| Lab | Topic | Main concepts |
|---|---|---|
| 1 | k-Nearest Neighbours | Distance metrics, scaling, neighbourhood voting, choosing k |
| 2 | Decision Trees | Gini impurity, split search, recursive trees, pruning |
| 3 | Naive Bayes | Bayes' theorem, priors, Gaussian likelihood, independence |
| 4 | Logistic Regression | Sigmoid, log-loss, gradient descent, classification metrics |
| 5 | PCA and t-SNE | Covariance, eigendecomposition, explained variance, embeddings |
| 6 | Outlier Detection | Z-score, IQR, robust scores, winsorisation |
| 7 | Logistic Regression vs SVM | Linear separators, hinge loss, confusion matrix, ROC-AUC |

## Dataset setup

Download BSDS500 independently and arrange it as:

```text
bsds500/
├── images/
│   ├── train/
│   ├── val/
│   └── test/
└── ground_truth/
    ├── train/
    ├── val/
    └── test/
```

Set the `BSDS500_BASE` environment variable to this directory, or edit `BASE` in each notebook. The notebooks need image files and matching MATLAB `.mat` annotations. Raw dataset files are not included.

Install the repository requirements and open notebooks from the repository root. Run cells in order. Each standalone notebook contains its own setup and model implementation.

## Evaluation note

Boundary pixels are less frequent than non-boundary pixels and may be labelled differently by human annotators. Interpret accuracy alongside precision, recall and F1. Strong gradients can also arise from texture and do not always correspond to object boundaries.
