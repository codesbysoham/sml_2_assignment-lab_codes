# SML 2 Assignment – Lab Codes

This repository contains the Python/Jupyter Notebook implementations for **Module II – Metaheuristic Optimization ML Algorithms**.

## Repository Contents

The work covers two major metaheuristic optimization techniques:

- **Simulated Annealing** for numerical function minimization
- **Genetic Algorithm – Question 1** for population-based function optimization
- **Genetic Algorithm – Question 2** for real-valued function minimization

The notebooks are executed and include the calculations, intermediate results, tables, and final verification required for the assignment.

## Folder Structure

```text
sml_2_assignment-lab_codes/
│
├── README.md
├── requirements.txt
├── Simulated_Annealing_Unique.ipynb
├── Genetic_Algorithm_1_Unique.ipynb
├── Genetic_Algorithm_2_Unique.ipynb
│
└── Module-II/
    ├── Simulated-Annealing/
    │   └── README.md
    │
    └── Genetic-Algorithm/
        ├── GA-Q1/
        │   └── README.md
        └── GA-Q2/
            └── README.md
```

> The executable notebooks are kept at the repository root so they remain easy to locate and run directly. The `Module-II` documentation provides the corresponding academic organization without changing the working notebook files.

## Topics

### Simulated Annealing

Simulated Annealing is a probabilistic optimization technique inspired by the cooling process used in metallurgy. It can accept worse candidate solutions with a temperature-dependent probability, helping the search escape local minima.

The implementation demonstrates:

1. Initial solution and temperature setup
2. Neighbour generation
3. Objective-function evaluation
4. Difference in objective values
5. Acceptance probability
6. Random-number based acceptance of worse solutions
7. Temperature cooling
8. Tracking of the best solution
9. Analytical verification of the final optimum

### Genetic Algorithm – Q1

The first Genetic Algorithm implementation demonstrates binary chromosome representation and population-based optimization using:

1. Binary encoding
2. Decimal conversion
3. Fitness calculation
4. Total and average fitness
5. Selection probability
6. Expected and actual selection counts
7. Mating-pool formation
8. Single-point crossover
9. Mutation
10. Evaluation of the new population

### Genetic Algorithm – Q2

The second Genetic Algorithm implementation demonstrates minimization using real-valued decoding from 5-bit chromosomes. The workflow includes:

1. Binary chromosome representation
2. Decimal-to-real-value mapping
3. Objective-function evaluation
4. Fitness transformation for minimization
5. Roulette-wheel selection
6. Crossover at the specified chromosome position
7. New-generation evaluation
8. Analytical verification of the mathematical minimum

## How to Run

Open the required `.ipynb` file in Jupyter Notebook, JupyterLab, or VS Code with a Python kernel and execute the cells from top to bottom.

Install the required packages with:

```bash
python -m pip install -r requirements.txt
```

## Files

| Notebook | Topic |
|---|---|
| `Simulated_Annealing_Unique.ipynb` | Simulated Annealing numerical minimization |
| `Genetic_Algorithm_1_Unique.ipynb` | Genetic Algorithm – binary encoding and optimization |
| `Genetic_Algorithm_2_Unique.ipynb` | Genetic Algorithm – real encoding and minimization |

## Academic Note

The parameter values and problem settings in these notebooks were intentionally customized for this submission while retaining the required metaheuristic algorithms and solution methodology.
