# Experiment 09: Genetic Algorithm for the Travelling Salesperson Problem

**Student:** Soham Kamble  
**Roll No.:** IED/10014/23  
**Course:** SML-II Laboratory Record  
**Related notebook:** [Q9_GA_TSP.ipynb](../Module-II/Q9_GA_TSP.ipynb)

## 1. Aim

To implement a Genetic Algorithm (GA) that searches for a short closed tour through eight cities, visits every city exactly once, and returns to the starting city. The experiment demonstrates how selection, crossover, mutation, and elitism affect a population of candidate routes.

## 2. Problem statement

The eight city coordinates are:

| City index | x | y |
|---:|---:|---:|
| 1 | 0 | 0 |
| 2 | 2 | 6 |
| 3 | 5 | 3 |
| 4 | 6 | 8 |
| 5 | 8 | 2 |
| 6 | 9 | 6 |
| 7 | 3 | 9 |
| 8 | 1 | 4 |

The distance between two cities is Euclidean distance. A route is a permutation of the city indices. Its closed-tour length is the sum of the distances between consecutive cities, including the edge from the last city back to the first. The objective is to minimise this total distance.

The TSP is a combinatorial optimisation problem. A GA searches a population of candidate routes and improves them across generations. It is a heuristic method: the reported result is the best route found in this run, not a proof that no shorter tour exists.

## 3. Theory

### 3.1 Route encoding and objective

Each individual is encoded as a permutation of the eight city indices. This representation ensures that each city occurs exactly once. Since the task minimises distance, smaller tour lengths are better; the implementation uses route length directly as the score.

### 3.2 Genetic operators

- **Initial population:** 60 random permutations provide candidate routes.
- **Tournament selection:** Four population members are sampled, and the route with the shortest distance wins.
- **Order crossover:** A segment from Parent 1 is copied into the child; missing cities are filled in the order in which they appear in Parent 2. This preserves a valid permutation.
- **Swap mutation:** Two randomly selected positions are exchanged to introduce variation.
- **Elitism:** The best route of each generation is copied unchanged into the next generation so the best-so-far candidate is not lost.

### 3.3 Reproducibility

The random seeds are set to 42 for Python's `random` module and NumPy. This makes the stochastic initialisation and GA choices repeatable under the same code and library environment.

## 4. Algorithm

1. Set the random seeds and define the city coordinates.
2. Compute the pairwise Euclidean distance matrix.
3. Define a tour-length function that sums consecutive distances and the return-to-start edge.
4. Create a population of 60 random city permutations.
5. For each generation, calculate every route's length and identify the current best route.
6. Record the best distance for the convergence history and selected checkpoints.
7. Copy the best individual into the next population using elitism.
8. Select parent pairs by tournament selection, apply order crossover with probability 0.90, and apply swap mutation with probability 0.15.
9. Continue for 100 generations, then report the best route and plot convergence.

## 5. Program

The complete executable Python implementation is maintained in the linked Jupyter notebook so the report and runnable code remain associated. The core tour-length calculation is:

```python
import numpy as np

def tour_length(route, distance_matrix):
    total = 0.0
    for i in range(len(route)):
        current_city = route[i]
        next_city = route[(i + 1) % len(route)]
        total += distance_matrix[current_city, next_city]
    return total
```

The notebook includes the distance matrix, permutation initialisation, tournament selection, order crossover, swap mutation, elitism, printed checkpoints, and convergence plot.

## 6. Output and analysis

**Best route found:** 3 → 1 → 8 → 2 → 7 → 4 → 6 → 5 → 3  
**Closed-tour distance:** 29.4056

| Generation checkpoint | Best distance |
|---:|---:|
| 0 | 36.2584 |
| 1 | 36.2584 |
| 2 | 36.2584 |
| 5 onward | 29.4056 |

The best distance improved from 36.2584 to 29.4056 by generation 5 and remained at that value in later checkpoints. Elitism helps preserve this incumbent solution. A flat convergence curve after an improvement means the algorithm did not find a better route during the remaining generations; it does not prove global optimality.

## 7. Convergence graph

Run the notebook to display the recorded best-distance-versus-generation plot. The curve shows the best-so-far tour length; for a minimisation problem, a downward step indicates an improvement and a flat segment indicates no new best was found.

## 8. Parameter modification table

The following are suggested experiments to perform; they are not additional measured results from the reported run.

| Parameter | Baseline | Suggested variation | What to observe |
|---|---:|---|---|
| Population size | 60 | 30, 100 | Diversity and runtime |
| Generations | 100 | 50, 200 | Whether additional search improves the best route |
| Crossover probability | 0.90 | 0.70, 1.00 | How strongly routes are recombined |
| Mutation probability | 0.15 | 0.05, 0.25 | Exploration versus disruption |
| Tournament size | 4 | 2, 6 | Selection pressure and diversity |

Change one parameter at a time, rerun with the same seed for controlled comparisons, and record the final best distance and convergence behaviour.

## 9. Conclusion

The GA successfully produced a valid closed tour that visits all eight cities exactly once and returns to the starting city. The best route found in the recorded run had length 29.4056. The convergence checkpoints show an improvement by generation 5, followed by no further improvement in the observed run. Since GA is heuristic, the result should be interpreted as the best route found by this configuration rather than a proof of the global optimum.
