# Experiment 13: Ant Colony Optimisation for Shortest-Path Finding

**Student:** Soham Kamble  
**Roll No.:** IED/10014/23  
**Course:** SML-II Laboratory Record  
**Related notebook:** [Q13_ACO_Shortest_Path.ipynb](../Q13_ACO_Shortest_Path.ipynb)

## 1. Aim

To implement Ant Colony Optimisation (ACO) for finding a low-cost path from start node S to destination G in a weighted undirected graph, and validate the path cost against Dijkstra's exact shortest-path algorithm.

## 2. Problem statement

The graph contains seven nodes—S, A, B, C, D, E, and G—and eleven undirected weighted edges. The task is to find a path from S to G that minimises the sum of its edge costs. ACO builds paths probabilistically using pheromone levels and edge costs. Because ACO is heuristic, Dijkstra's algorithm is also applied to the same graph as an exact reference for this graph with nonnegative edge weights.

## 3. Theory

### 3.1 Transition probability

For a possible move from node u to neighbour v, the unnormalised weight is `pheromone(u,v)^alpha * (1 / edge_cost(u,v))^beta`. Here, alpha controls the influence of pheromone and beta controls preference for lower-cost edges. Weights of available neighbours are normalised to obtain transition probabilities. The implementation avoids revisiting a node within the same path.

### 3.2 Pheromone update

After ants construct paths, pheromone evaporates by multiplying existing values by `(1 - rho)`, where rho is the evaporation rate. Each successful ant deposits `Q / L` on every edge in its path, where Q is a deposit constant and L is that path's total cost. Shorter successful paths therefore deposit more pheromone per edge under this rule.

### 3.3 Dijkstra validation

Dijkstra's algorithm is deterministic for graphs with nonnegative edge weights and provides an exact reference cost for this graph. Matching Dijkstra's cost validates the ACO result for this instance, but does not make ACO a guaranteed exact method on arbitrary graphs.

## 4. Algorithm

1. Define the seven nodes and eleven undirected weighted edges, then construct an adjacency list.
2. Initialise pheromone to 1.0 on both directions of every edge.
3. Set alpha = 1, beta = 2, rho = 0.25, Q = 10, 25 ants per iteration, and 80 iterations.
4. For each ant, start at S and choose an unvisited neighbour according to the normalised pheromone/cost weights.
5. Stop an ant when it reaches G or cannot continue without revisiting a node.
6. Record successful paths and update the best path found so far.
7. Evaporate pheromone and add Q/L deposits for each successful path edge.
8. Repeat for 80 iterations, recording best-so-far cost and the number of ants reaching G.
9. Run Dijkstra on the same adjacency list and compare its path and cost with ACO.
10. Plot the weighted graph with the best path highlighted and plot best path cost against iteration.

## 5. Program

The full executable implementation is maintained in the linked notebook, including graph construction, probabilistic ant transitions, path construction, pheromone evaporation and deposits, Dijkstra validation, and plots. The core transition weighting is:

```python
weight = pheromone[(u, v)] ** alpha * (1.0 / edge_cost) ** beta
probability = weight / sum(weights_for_available_neighbours)
```

## 6. Output and analysis

**Best ACO path:** S → A → C → G  
**ACO path cost:** 7  
**Dijkstra shortest path cost:** 7  
**Validation:** The costs match for this graph.

The matching cost indicates that ACO found a shortest path for this graph and run. Dijkstra supplies the exact reference. ACO remains stochastic, so results on other graphs can depend on graph structure, random choices, and parameter settings.

## 7. Convergence and graph visualisations

Run the notebook to view the weighted graph with the best path highlighted and the best-so-far path cost across 80 iterations. A downward step indicates a cheaper path was found; a flat section indicates that no lower-cost best path was found during that interval.

## 8. Parameter modification table

These are proposed tests, not additional measured outcomes from the baseline run.

| Parameter | Baseline | Suggested variation | What to observe |
|---|---:|---|---|
| Number of ants | 25 | 10, 50 | Search coverage and runtime |
| Iterations | 80 | 40, 120 | Whether the best path is found earlier or more consistently |
| Alpha | 1 | 0.5, 2 | Sensitivity to pheromone |
| Beta | 2 | 1, 3 | Preference for low-cost edges |
| Evaporation rho | 0.25 | 0.10, 0.50 | Persistence of old pheromone versus exploration |
| Deposit constant Q | 10 | 5, 20 | Scale of pheromone updates |

Change one parameter at a time, keep the graph unchanged, and record the best path, path cost, and convergence curve. Repeat stochastic settings with multiple seeds if comparing reliability.

## 9. Conclusion

The ACO implementation found S → A → C → G with total cost 7. Dijkstra's algorithm returned the same shortest-path cost, validating the result for this graph. The experiment demonstrates how probabilistic path construction and pheromone reinforcement can identify a low-cost route, while the deterministic comparison provides a useful correctness check.