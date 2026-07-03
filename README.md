# ode-simulation-and-fitting-epidemiological-models
Python implementation of ordinary differential equation (ODE) models for simulation and parameter estimation. Includes SIR epidemiological and logistic growth models, numerical integration with SciPy, optimization-based model fitting, and visualization using Matplotlib.

## Project Workflow

This project demonstrates the complete workflow for modeling dynamic systems using ordinary differential equations (ODEs) in Python. Starting from mathematical model formulation, the project numerically solves the governing equations, simulates system behavior, estimates unknown model parameters from observed data, and evaluates model performance through visualization and quantitative error minimization.

The workflow is summarized below:

```text
Input Data
      │
      ▼
Define Mathematical Model
(SIR or Logistic Growth)
      │
      ▼
Implement Differential Equations
      │
      ▼
Numerically Solve ODEs
(solve_ivp)
      │
      ▼
Generate Simulations
      │
      ├──────────────► Visualization (figures/)
      │
      ▼
Load Experimental Data
      │
      ▼
Compute Sum of Squared Errors (SSE)
      │
      ▼
Parameter Optimization
(minimize)
      │
      ▼
Best-Fit Parameters
      │
      ▼
Compare Model Predictions with Data
      │
      ▼
Final Figures and Analysis
```

### Workflow Description

**1. Input Data**
- Define the initial conditions, model parameters, and time interval for simulation.
- Import experimental datasets when performing parameter estimation.

**2. Define Mathematical Model**
- Formulate the governing ordinary differential equations describing the system.
- This project includes:
  - The SIR epidemiological model.
  - The logistic population growth model.

**3. Implement Differential Equations**
- Translate the mathematical equations into Python functions that return the derivatives of the state variables.
- These functions are compatible with SciPy's numerical ODE solvers.

**4. Numerically Solve the ODEs**
- Use `scipy.integrate.solve_ivp()` to compute numerical solutions over the specified time interval.
- The solver approximates the evolution of the system when analytical solutions are unavailable.

**5. Generate Simulations**
- Simulate the dynamics of the system using the specified initial conditions and parameter values.
- The resulting trajectories describe how the state variables evolve over time.

**6. Visualization**
- Plot simulation results using Matplotlib to observe system behavior and validate model dynamics.
- Generated figures are stored in the `figures/` directory.

**7. Load Experimental Data**
- Import observed datasets using Pandas for comparison with the simulated model output.
- Experimental measurements provide the basis for parameter estimation.

**8. Compute the Sum of Squared Errors (SSE)**
- Calculate the discrepancy between observed data and model predictions.
- The SSE serves as the objective function that quantifies model fit.

**9. Parameter Optimization**
- Use `scipy.optimize.minimize()` with the Nelder–Mead algorithm to estimate the model parameters that minimize the SSE.

**10. Best-Fit Parameters**
- Obtain the optimized parameter estimates that provide the closest agreement between the model and the observed data.

**11. Compare Model Predictions with Data**
- Overlay the optimized model trajectory with the experimental observations to assess model performance visually.

**12. Final Figures and Analysis**
- Produce publication-quality figures and summarize the results, illustrating both the simulated dynamics and the fitted models.
