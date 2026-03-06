# Spectral Approximation of the Internal Layer in the Equilibrium p–n Junction Model

This repository contains the reproducibility code for numerical experiments related to the spectral approximation
of the internal layer in the stationary 1D Poisson–Boltzmann model of an abrupt p–n junction.

## Repository Structure

- run_experiment.py — main experiment script
- requirements.txt — Python dependencies
- notebooks/ — optional Jupyter notebook versions of experiments
- examples/ — example outputs (results, plots)
- paper/ — related paper PDF

## What the Code Does

The script:

1. Solves the Poisson–Boltzmann boundary value problem.
2. Computes sine spectral coefficients.
3. Computes Chebyshev coefficients.
4. Estimates tail energy and effective resolution index.
5. Exports experiment outputs such as:
   - results.csv
   - results_table.tex
   - scaling plots

## Installation

Install dependencies:

pip install -r requirements.txt

## Run the Experiment

python run_experiment.py

## Output

Running the script generates numerical artifacts including:

- results.csv
- results_table.tex
- scaling_plot.png or scaling_plot.pdf

These files summarize the spectral convergence diagnostics for different
internal layer widths in the p–n junction model.

## Notes

The experiments demonstrate the scaling behavior showing that resolving
the internal layer requires spectral dimension proportional to δ^{-1}.
