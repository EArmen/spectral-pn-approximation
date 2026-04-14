# Spectral Approximation of the Internal Debye Layer in the Equilibrium p--n Junction Model

This repository provides reproducibility code for numerical experiments studying approximation complexity in the one-dimensional equilibrium Poisson--Boltzmann model of an abrupt p--n junction.

The code reproduces numerical results related to the formation of the internal Debye layer and its impact on effective approximation dimension in spectral and polynomial representations.

---

## Mathematical Formulation

We consider the finite-interval boundary-value problem:

$$
-\delta^2 u''(s) = e^{-u(s)} - e^{u(s)} + C(s), \quad s \in (-1,1)
$$

with Dirichlet boundary conditions:

$$
u(-1)=u_p, \quad u(1)=u_n
$$

where $C(s)$ is a step-function doping profile corresponding to an abrupt p--n junction.

The system is studied in the singular perturbation regime:

$$
\delta = \frac{L_D}{L} \ll 1
$$

in which the solution develops a thin internal Debye layer near the junction interface.

---

## Computational Pipeline

For each prescribed value of $\delta$, the code performs:

1. Solves the equilibrium Poisson--Boltzmann boundary-value problem;

2. Constructs the residual profile:

   $$
   w_\delta(s) = u(s) - u_{\mathrm{lin}}(s)
   $$

3. Computes the derivative of the residual;

4. Evaluates sine spectral coefficients;

5. Computes Chebyshev coefficients;

---

## Scientific Objective

The numerical experiments illustrate the scaling behavior associated with internal layer formation.

In particular, they demonstrate that:

$$
K_\varepsilon \sim \frac{1}{\delta}
$$

as the Debye length decreases.

These results provide numerical evidence consistent with the theoretical framework developed in the associated paper.

**Note:**  
These computations are illustrative and do not constitute proofs of the analytical results.

---

## Repository Structure

```
run_experiment.py
requirements.txt
notebooks/
outputs/
paper/
```

---

## Input Parameters

The default configuration uses:

$$
\delta \in \{0.20,\;0.10,\;0.05,\;0.025\}
$$

with a symmetric doping profile unless modified in the script.

---

## Installation

```bash
pip install -r requirements.txt
```

---

## Running the Experiment

```bash
python run_experiment.py
```

---

## Generated Outputs

```
outputs/scaling_results.csv
outputs/scaling_results.json
outputs/table_scaling_results.tex
outputs/profiles_delta.png
outputs/residual_derivative_delta.png
outputs/scaling_plot.png
```

---

## Reproducibility

The code has been tested with Python 3.10--3.12.

For full reproducibility:
- use the specified dependency versions;
- rerun the experiment from scratch to regenerate all outputs.

---

## Interpretation of Results

The primary diagnostic is:

$$
K_\varepsilon^{H^1,\sin}
$$

with additional comparison metrics:
- $K_\varepsilon^{L^2,\sin}$  
- $K_\varepsilon^{\mathrm{cheb}}$

**Conclusion:**  
Thinner internal layers require higher effective approximation dimension.

---

## Citation

If you use this repository, please cite the associated paper.
