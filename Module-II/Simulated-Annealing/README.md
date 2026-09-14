# Simulated Annealing

## Objective

Minimize the assigned numerical objective function using the **Simulated Annealing (SA)** metaheuristic.

## Method

The implementation follows the standard SA workflow:

1. Start from the specified initial solution.
2. Set the initial temperature.
3. Generate a neighbouring solution.
4. Calculate the change in objective value, `Δf`.
5. Accept an improved solution directly.
6. For a worse solution, calculate the temperature-dependent acceptance probability.
7. Compare the probability with the supplied random number.
8. Reduce the temperature using the cooling factor.
9. Continue until the stopping temperature/iteration condition is reached.
10. Report the best solution found.

## Notebook

Use `Simulated_Annealing_Unique.ipynb` in the repository root. The notebook contains the complete numerical trace, acceptance decisions, best-solution tracking, and analytical verification.

## Key Concepts

- Temperature and cooling schedule
- Neighbourhood search
- Acceptance probability
- Escaping local minima
- Exploration versus exploitation
- Analytical verification of the optimum
