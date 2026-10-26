# Experiment 10: Particle Swarm Optimisation for the Rosenbrock Function

**Student:** Soham Kamble  
**Roll No.:** IED/10014/23  
**Course:** SML-II Laboratory Record  
**Related notebook:** [Q10_PSO_Rosenbrock.ipynb](../Q10_PSO_Rosenbrock.ipynb)

## 1. Aim

To implement Particle Swarm Optimisation (PSO) for minimising the two-dimensional Rosenbrock function, inspect the best solution across iterations, and compare the numerical result with the known global minimum.

## 2. Problem statement

Minimise

[
f(x,y) = (1-x)^2 + 100(y-x^2)^2
]

over the bounded search region (-3 le x le 3) and (-3 le y le 3). The known global minimum is ((x,y)=(1,1)), where the function value is zero. The Rosenbrock function has a narrow, curved valley; the challenge is to reach the valley and then follow it toward the minimum.

## 3. Theory

### 3.1 Particle representation

Each particle represents a candidate point ((x,y)) and has a velocity vector. The objective function measures the quality of that point, with lower values preferred. Each particle remembers its personal-best position, while the swarm shares the global-best position found by any particle.

### 3.2 Velocity and position update

The velocity update combines three components:

- **Inertia:** continuation of the particle's current motion.
- **Cognitive component:** attraction toward the particle's own best-known point.
- **Social component:** attraction toward the best point found by the swarm.

Random multipliers make the search stochastic. The new position is the old position plus the updated velocity.

This implementation uses linearly decreasing inertia from 0.9 to 0.4, cognitive and social coefficients of 1.7, velocity clipping to ([-1,1]) per component, and position clipping to ([-3,3]). These bounds keep the search inside the intended domain.

### 3.3 Sanity checks

The function is evaluated at several points before optimisation:

| Point | Expected function value |
|---|---:|
| ((1,1)) | 0 |
| ((0,0)) | 1 |
| ((-1,1)) | 4 |
| ((2,2)) | 401 |

These checks verify the expression and illustrate that points away from the curved valley can have large objective values.

## 4. Algorithm

1. Define the vectorised Rosenbrock objective and set NumPy's random seed to 7.
2. Evaluate the test points and verify that (f(1,1)=0).
3. Initialise 40 particle positions uniformly in ([-3,3]^2) and velocities in ([-0.5,0.5]^2).
4. Set each particle's personal best to its initial position and identify the lowest objective value as the global best.
5. For each of 200 iterations, calculate the linearly decreasing inertia weight.
6. Update velocities using inertia, cognitive, and social components, then clip each velocity component to ([-1,1]).
7. Update positions and clip them to ([-3,3]).
8. Evaluate the particles and update personal-best and global-best records whenever an improvement occurs.
9. Save the global-best value at selected iterations and plot the objective contours and convergence curve.

## 5. Program

The complete executable implementation, including both plots, is maintained in the linked Jupyter notebook. The objective function used is:

```python
import numpy as np

def rosenbrock(position):
    """Vectorised Rosenbrock objective for one point or an array."""
    x, y = position[..., 0], position[..., 1]
    return (1 - x)**2 + 100 * (y - x**2)**2
```

The notebook contains the particle initialisation, velocity and position updates, clipping, personal/global best updates, iteration checkpoints, contour plot, and convergence plot.

## 6. Output and analysis

**Final global-best position:** approximately ((1.000002, 1.000004))  
**Final objective value:** (6.120717 	imes 10^{-12})  
**Distance from the known minimum ((1,1)):** (4.933387 	imes 10^{-6})

The final position is extremely close to the known global minimum, and the objective value is effectively zero at the displayed precision. The small nonzero value is expected in a numerical stochastic optimisation run. It is a strong agreement with the reference solution for this run, rather than a symbolic proof of exact equality.

## 7. Convergence and contour graphs

Run the notebook to view:
1. **Objective contour plot:** displays the Rosenbrock landscape and the optimiser's best point.
2. **Convergence plot:** displays the global-best objective value across iterations.

The contour plot helps show the narrow, curved valley. The convergence plot shows whether the best objective value decreases and then stabilises. For a minimisation task, lower values indicate better solutions.

## 8. Parameter modification table

The following are suggested follow-up tests, not additional results from the reported run.

| Parameter | Baseline | Suggested variation | What to observe |
|---|---:|---|---|
| Number of particles | 40 | 20, 80 | Exploration coverage and runtime |
| Iterations | 200 | 100, 400 | Convergence speed and final objective |
| Inertia weight | 0.9 to 0.4 | Fixed 0.7; 0.8 to 0.3 | Exploration versus exploitation |
| Cognitive coefficient | 1.7 | 1.2, 2.0 | Influence of personal experience |
| Social coefficient | 1.7 | 1.2, 2.0 | Influence of swarm best |
| Velocity limit | 1.0 | 0.5, 1.5 | Stability and movement size |

For a fair comparison, vary one parameter at a time and keep the random seed fixed. Record the final objective, distance to ((1,1)), and convergence behaviour.

## 9. Conclusion

The PSO implementation converged to a solution extremely close to the known Rosenbrock minimum. The final position was approximately ((1.000002,1.000004)), with an objective value of (6.120717	imes10^{-12}). This demonstrates that the configured swarm was able to locate the narrow valley and approach its minimum in the recorded run.
