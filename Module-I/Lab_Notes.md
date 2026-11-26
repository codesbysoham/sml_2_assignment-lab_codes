# Module I — Experiment Notes

## Common problem setting

BSDS500 provides images and human-drawn segmentation boundaries. The classification experiments formulate pixel-level boundary detection as a binary prediction task. Image-derived features are used to classify a pixel as boundary (1) or non-boundary (0).

## Important implementation choices

- Split by image before sampling pixels, so pixels from a given image do not leak across train and test sets.
- Standardise feature columns using training statistics only for distance-based and gradient-based models.
- Tune hyperparameters on a validation set where possible; do not select them from the final test set.
- Report precision, recall and F1 along with accuracy because the positive boundary class is comparatively sparse.
- PCA is linear and maximises variance; t-SNE is a nonlinear visualisation technique and should not be interpreted as a predictive classifier.
- Outlier treatment is domain-dependent: unusually strong gradients may be genuine boundary evidence, not data errors.

## Lab-by-lab viva prompts

1. Why does kNN require scaling? What is the bias-variance effect of increasing k?
2. How does Gini impurity measure node heterogeneity? Why does pruning help?
3. What is the naive conditional-independence assumption? Why are log-likelihoods used?
4. Derive the logistic sigmoid and binary cross-entropy gradient.
5. Explain covariance eigendecomposition and explained variance. How does t-SNE differ from PCA?
6. Compare z-score and IQR. What is the masking effect?
7. Explain the hinge loss, margin and the effect of the SVM kernel.

## Dataset integrity

Use BSDS500 images and corresponding ground-truth annotations. Configure paths locally via `BSDS500_BASE`; do not commit raw dataset archives or machine-specific absolute paths.
