# Statistical Machine Learning II Lab — Expanded Module I Suite

This report documents seven core machine-learning experiments using BSDS500 image data. Each lab uses image-derived features to study a distinct statistical-learning method.

## Experiments

1. **k-Nearest Neighbours:** Standardise feature columns, compute distances, compare values of k, and report classification performance.
2. **Decision Trees:** Compute Gini impurity, search candidate thresholds, recursively split nodes, and visualise the resulting tree.
3. **Naive Bayes:** Estimate class priors and Gaussian feature likelihoods, combine log-likelihoods, and predict the most likely class.
4. **Logistic Regression:** Implement the sigmoid model, binary cross-entropy and gradient descent; inspect the cost curve and coefficients.
5. **PCA and t-SNE:** Centre and scale features, inspect covariance eigendecomposition and explained variance, and visualise low-dimensional structure.
6. **Outlier Detection:** Compare Z-score and IQR fences, inspect robust alternatives, and quantify the effect of winsorisation.
7. **Logistic Regression vs SVM:** Compare linear classifiers using confusion counts, accuracy, precision, recall, F1 and ROC-AUC.

## Dataset and execution

Place BSDS500 images and their corresponding MATLAB ground-truth annotations in a local directory with images/train, images/val, images/test and ground_truth/train, ground_truth/val, ground_truth/test subdirectories. Configure BSDS500_BASE or the BASE variable in the notebooks. The raw dataset is not included in this repository.

Install packages with `python -m pip install -r requirements.txt`, open JupyterLab, then run the notebook cells sequentially.

## Evaluation considerations

Boundary detection is an imbalanced classification problem. Accuracy alone can be misleading, so precision, recall and F1 should also be reported. Human annotations can differ, and high gradient energy may indicate texture rather than a semantic object boundary.

## Reproducibility

Use image-wise train/test separation and training-set statistics for feature scaling. Record random seeds and model settings whenever an experiment samples pixels or uses stochastic optimisation.
