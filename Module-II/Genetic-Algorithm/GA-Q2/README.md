# Genetic Algorithm – Question 2

## Objective

Solve the assigned **minimization problem** using a Genetic Algorithm with real-valued decoding from binary chromosomes.

## Representation

Each individual is represented using a 5-bit binary chromosome. The decimal chromosome value is mapped to the specified numerical search interval using the standard linear decoding formula.

## Workflow

1. Initialize the four given chromosomes.
2. Convert each binary chromosome to decimal form.
3. Decode the decimal value into the corresponding real decision variable.
4. Evaluate the objective function.
5. Convert objective values into selection fitness suitable for a minimization problem.
6. Calculate selection probabilities and cumulative probabilities.
7. Use the supplied random numbers to construct the mating pool.
8. Perform single-point crossover at the specified crossover position.
9. Decode and evaluate the new generation.
10. Identify the best candidate found.
11. Verify the mathematical optimum analytically.

## Important Point

For a minimization problem, smaller objective values should be favoured during selection. The notebook therefore uses a transformed selection fitness rather than directly treating the objective value as a maximization fitness.

## Notebook

Use `Genetic_Algorithm_2_Unique.ipynb` in the repository root for the complete numerical calculations, selection table, crossover results, and analytical verification.
