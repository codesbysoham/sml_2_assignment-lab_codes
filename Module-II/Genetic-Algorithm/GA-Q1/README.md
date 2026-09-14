# Genetic Algorithm – Question 1

## Objective

Implement a Genetic Algorithm using binary chromosomes to demonstrate population evaluation and evolutionary operators.

## Workflow

The notebook performs the following steps:

1. Define the initial binary population.
2. Decode each chromosome into its decimal value.
3. Calculate the fitness of every individual.
4. Compute total and average fitness.
5. Calculate selection probabilities.
6. Determine expected selection counts.
7. Construct the mating pool using the supplied random-selection procedure.
8. Apply single-point crossover.
9. Apply mutation.
10. Decode and evaluate the resulting population.
11. Compare the generations and identify the best individual.

## Main Genetic Operators

### Selection
Individuals with higher fitness receive a greater probability of being selected for reproduction.

### Crossover
Two parent chromosomes exchange genetic material at the specified crossover point to produce offspring.

### Mutation
A selected chromosome undergoes a bit flip to introduce genetic diversity and reduce the possibility of premature convergence.

## Notebook

Use `Genetic_Algorithm_1_Unique.ipynb` in the repository root for the complete calculations and executed results.
