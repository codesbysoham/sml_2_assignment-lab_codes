# SML 2 Assignment – Machine Learning Lab

A structured collection of Machine Learning Lab (SML 2) implementations using the BSDS500 (Berkeley Segmentation Data Set) image dataset.

This repository combines the Module-II metaheuristic optimization notebooks with a separate set of BSDS500-based ML assignment notebooks (Q1–Q7).

## Repository Structure

```text
sml_2_assignment-lab_codes/
├── README.md
├── requirements.txt
├── BSDS500_ML_Assignment/
│   ├── README.md
│   ├── Q1_kNN.ipynb
│   ├── Q2_Decision_Tree.ipynb
│   ├── Q3_Naive_Bayes.ipynb
│   ├── Q4_Logistic_Regression.ipynb
│   ├── Q5_PCA_tSNE.ipynb
│   ├── Q6_Outlier_Detection.ipynb
│   └── Q7_LR_vs_SVM.ipynb
├── Module-II/
│   ├── README.md
│   ├── Simulated-Annealing/
│   └── Genetic-Algorithm/
├── Simulated_Annealing_Unique.ipynb
├── Genetic_Algorithm_1_Unique.ipynb
├── Genetic_Algorithm_2_Unique.ipynb
└── Q11_PSO_Unique.ipynb
```

## Module-II: Metaheuristic Optimization

| Notebook | Method | Main focus |
|---|---|---|
| [Simulated_Annealing_Unique.ipynb](Simulated_Annealing_Unique.ipynb) | Simulated Annealing | Numerical function minimization |
| [Genetic_Algorithm_1_Unique.ipynb](Genetic_Algorithm_1_Unique.ipynb) | Genetic Algorithm | Binary chromosome optimization |
| [Genetic_Algorithm_2_Unique.ipynb](Genetic_Algorithm_2_Unique.ipynb) | Genetic Algorithm | Real-valued decoding and minimization |
| [Q11_PSO_Unique.ipynb](Q11_PSO_Unique.ipynb) | Particle Swarm Optimization | One-dimensional quadratic maximization; per-iteration position, velocity and fitness output |

### PSO exercise

The PSO notebook maximizes (f(x)=-0.8(x-3.5)^2+18) on ([-8,9]). It starts from a specified swarm, uses zero initial velocities, and prints each iteration's particle state alongside the global best. The analytical maximum is at (x=3.5) with fitness 18.

## BSDS500 ML Assignment

The `BSDS500_ML_Assignment/` directory contains seven notebooks covering supervised learning, dimensionality reduction and outlier detection.

| Question | Method | Main focus |
|---|---|---|
| Q1 | k-Nearest Neighbours | Pixel-level boundary classification |
| Q2 | Decision Tree | Gini impurity and split selection |
| Q3 | Gaussian Naive Bayes | Class-conditional Gaussian modelling |
| Q4 | Logistic Regression | Binary classification with gradient descent |
| Q5 | PCA + t-SNE | Dimensionality reduction and 2D representation |
| Q6 | Outlier Detection | Z-score and IQR analysis |
| Q7 | Logistic Regression vs SVM | Comparative metrics and ROC/AUC |

## Running the notebooks

Open a notebook in Jupyter Notebook, JupyterLab or VS Code and execute its cells from top to bottom. Install the repository dependencies first:

```bash
python -m pip install -r requirements.txt
```

The BSDS500 notebooks also use `scipy` and `pillow`. Update the dataset path in those notebooks to match your local copy.

## Author

**Soham**  
GitHub: [@codesbysoham](https://github.com/codesbysoham)

---

*Machine Learning Lab — SML 2*