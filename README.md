# Statistical Machine Learning II — Lab Repository

A structured collection of practical implementations, experiments and reports for Statistical Machine Learning II.

## Repository layout

```text
.
├── BSDS500_ML_Assignment/        Seven image-boundary ML assignment notebooks
├── Module-I/                     Expanded lab sequence and study documentation
│   ├── Lab01_kNN.ipynb
│   ├── Lab02_Decision_Tree.ipynb
│   ├── Lab03_Naive_Bayes.ipynb
│   ├── Lab04_Logistic_Regression.ipynb
│   ├── Lab05_PCA_tSNE.ipynb
│   ├── Lab06_Outlier_Detection.ipynb
│   ├── Lab07_LR_vs_SVM.ipynb
│   ├── Module_I_Combined.ipynb
│   └── README.md
├── Module-II/                     Metaheuristic optimisation and kernel methods
│   ├── Simulated Annealing
│   ├── Genetic Algorithms
│   ├── Particle Swarm Optimisation
│   ├── Ant Colony Optimisation
│   ├── L1-L2-ElasticNet_Regularization.ipynb
│   ├── Kernel_PCA.ipynb
│   └── README.md
├── reports/                       Experiment write-ups
├── data/                          Dataset preparation scripts and local data
└── requirements.txt
```

## Module I — Core machine learning

The Module I experiments use the BSDS500 image segmentation dataset for boundary versus non-boundary pixel classification and related image-level analysis.

| Lab | Topic | Key implementation |
|---|---|---|
| 1 | k-Nearest Neighbours | Distance computation, scaling, k selection and classification |
| 2 | Decision Trees | Gini impurity, split search, recursive tree construction and pruning concepts |
| 3 | Naive Bayes | Class priors, Gaussian likelihoods and posterior classification |
| 4 | Logistic Regression | Sigmoid model, binary cross-entropy and gradient descent |
| 5 | PCA and t-SNE | Covariance eigendecomposition, explained variance and 2-D embeddings |
| 6 | Outlier Detection | Z-score, IQR, robust scores and winsorisation |
| 7 | Logistic Regression vs SVM | Hinge loss, confusion matrix, precision, recall, F1 and ROC-AUC |

The expanded notebooks are available in `Module-I/`. The `BSDS500_ML_Assignment/` directory retains the original assignment-specific notebooks.

### Dataset setup

The existing assignment notebooks expect the BSDS500 dataset to be available locally. Arrange the data as:

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

Update the `BASE` variable in a notebook's first setup cell to the local `bsds500` directory. The notebooks load images and corresponding MATLAB ground-truth annotations; raw BSDS500 data is not redistributed here.

## Module II — Optimisation and kernel methods

| Lab | Topic | Key implementation |
|---|---|---|
| 8 | Simulated Annealing | Temperature schedule, probabilistic acceptance and local-minimum escape |
| 9 | Genetic Algorithm | Binary and real-valued representations; TSP optimisation |
| 10 | Particle Swarm Optimisation | Particle position/velocity updates and Rosenbrock minimisation |
| 11 | L1, L2 and Elastic Net | Ridge/Lasso/Elastic Net, coefficient shrinkage, sparsity and regularisation paths |
| 12 | Kernel PCA | RBF kernel, kernel centering, eigendecomposition and nonlinear embeddings |
| 13 | Ant Colony Optimisation | Transition probabilities, pheromone evaporation/deposition and shortest paths |

The additional regularisation and Kernel PCA labs complement the existing SA, GA, PSO and ACO implementations.

## Setup

Install the Python dependencies:

```bash
python -m pip install -r requirements.txt
```

Launch Jupyter:

```bash
jupyter lab
```

Open notebooks from the repository root unless a notebook's instructions specify otherwise. Run cells sequentially. Some experiments use BSDS500 image data and therefore require the local dataset setup described above.

## Reproducibility

- Random seeds are set in experiments wherever sampling or stochastic optimisation is used.
- Evaluation metrics and plots are generated in the notebooks.
- Dataset paths should be configured locally; absolute machine-specific paths should not be committed.

## Author

**Soham**  
GitHub: [@codesbysoham](https://github.com/codesbysoham)
