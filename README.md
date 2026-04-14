# Spectral Approximation of the Internal Debye Layer in the Equilibrium p–n Junction Model

This repository provides reproducibility code for the numerical experiments accompanying the study of approximation complexity in the one-dimensional equilibrium Poisson–Boltzmann model of an abrupt p–n junction.

The code is designed to reproduce numerical results related to the formation of the internal Debye layer and its impact on effective approximation dimension in spectral and polynomial representations.

---

## Mathematical Formulation

We consider the finite-interval boundary-value problem:

-δ² u''(s) = e^{-u(s)} - e^{u(s)} + C(s),   s ∈ (-1,1)

with Dirichlet boundary conditions:

u(-1)=u_p,   u(1)=u_n

where C(s) is a step-function doping profile corresponding to an abrupt p–n junction.

The system is studied in the singular perturbation regime:

δ = L_D / L << 1

in which the solution develops a thin internal Debye layer near the junction interface.

---

## Computational Pipeline

For each prescribed value of δ, the code performs the following steps:

1. Solves the equilibrium Poisson–Boltzmann boundary-value problem;
2. Constructs the residual profile:
   w_δ(s) = u(s) - u_lin(s);
3. Computes the derivative of the residual;
4. Evaluates sine spectral coefficients;
5. Computes Chebyshev coefficients;
6. Extracts resolution diagnostics:
   - energy-based sine index K_ε^{H¹,sin},
   - unweighted sine index K_ε^{L²,sin},
   - Chebyshev index K_ε^{cheb};
7. Exports reproducible artifacts, including figures, data tables, and LaTeX-ready outputs.

---

## Scientific Objective

The numerical experiments illustrate the scaling behavior associated with internal layer formation.

In particular, they demonstrate that as the Debye length decreases, the effective approximation dimension grows approximately as:

K_ε ~ 1/δ

These results provide numerical evidence consistent with the theoretical framework developed in the associated paper.

Important:
The computations presented here are illustrative and do not constitute proofs of the analytical results.

---

## Repository Structure

run_experiment.py        # Main experiment script
requirements.txt        # Python dependencies
notebooks/              # Optional exploratory notebooks
outputs/                # Generated numerical results
paper/                  # Manuscript and related materials

---

## Input Parameters

The default configuration uses:

δ ∈ {0.20, 0.10, 0.05, 0.025}

with a symmetric doping profile unless modified in the script.

---

## Installation

pip install -r requirements.txt

---

## Running the Experiment

python run_experiment.py

---

## Generated Outputs

outputs/scaling_results.csv  
outputs/scaling_results.json  
outputs/table_scaling_results.tex  
outputs/profiles_delta.png  
outputs/residual_derivative_delta.png  
outputs/scaling_plot.png  

---

## Reproducibility

Tested with Python 3.10–3.12.

For full reproducibility:
- use the specified dependency versions,
- rerun the experiment from scratch.

---

## Interpretation of Results

Primary diagnostic:

K_ε^{H¹,sin}

Additional metrics:
- K_ε^{L²,sin}
- K_ε^{cheb}

Conclusion:

Thinner internal layers require higher effective approximation dimension.

---

## Citation

If you use this repository, please cite the associated paper.
