# Simulation and Visualization of Stochastic Processes

Computational materials for the degree project:
**Simulation and Visualization of Stochastic Mechanisms: Applications to
Engineering Course Development**.

This repository contains the Jupyter notebooks and selected figures developed
for the thesis. The materials are designed to make stochastic mechanisms
visible, reproducible and suitable for classroom exploration. They supplement
the mathematical discussion in the thesis rather than replace it.

## Project aims

Each teaching module follows a common computational workflow:

1. define a stochastic model and its assumptions;
2. state the simulation algorithm;
3. generate sample paths or realisations;
4. repeat the experiment to estimate a distribution or expectation;
5. compare the empirical result with a theoretical benchmark;
6. interpret the result through visualisation.

The mathematical scope includes Monte Carlo methods, counting processes,
random walks, Brownian motion, discrete- and continuous-time Markov chains,
reliability models and queueing systems.

## Notebook modules

| Module | Notebook | Main topic |
| --- | --- | --- |
| 0 | `00_Monte_Carlo.ipynb` | Monte Carlo simulation and convergence |
| 1 | `01_Bernoulli&Poisson.ipynb` | Bernoulli and Poisson processes |
| 2 | `02_Random_Walk_Part1.ipynb` | Discrete-time random walks and gambler's ruin |
| 3 | `03_Random_Walk_Part2.ipynb` | Continuous-time random walks |
| 4 | `04_Random_Walk_Part3.ipynb` | Brownian motion and random-walk approximation |
| 5 | `05_Markov_Chain_Part1.ipynb` | Discrete-time Markov chains and PageRank |
| 6 | `06_Markov_Chain_Part2.ipynb` | Continuous-time chains and birth-death processes |
| 7 | `07_Markov_Chain_Part3.ipynb` | Reliability, buffers and the M/M/1 queue |
| 8 | `08_Exploratory_Module_1.ipynb` | Non-homogeneous Poisson processes |
| 9 | `09_Exploratory_Module_2.ipynb` | Growing self-avoiding walks |
| 10 | `010_Exploratory_Module_3..ipynb` | Coalescing particles on a circle |

The three exploratory modules vary one modelling assumption at a time:
time-homogeneous intensity, path independence and the use of a single-particle
state.

## Repository structure

```text
.
├── figures/               # Selected figures used by the project
├── notebooks/             # Teaching modules 0–10
├── src/                   # Reserved for reusable simulation code
├── README.md
├── REPRODUCIBILITY.md
└── requirements.txt
```

Exercise drafts and third-party reference PDFs are intentionally excluded from
this branch and from version control.

## Installation

Python 3.10 or newer is recommended.

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
pip install -r requirements.txt
jupyter lab
```

Open `notebooks/` and run the files in numerical order. For assessed or archived
results, restart the kernel and run all cells from top to bottom. See
[REPRODUCIBILITY.md](REPRODUCIBILITY.md) for the random-seed policy, numerical
checks and submission checklist.

## Reproducibility

Figures and numerical summaries cited in the thesis should use fixed random
seeds. Exploratory classroom cells may deliberately generate different
realisations, provided that they are clearly labelled. Empirical outputs should
always be interpreted together with their theoretical reference values.

## Scope

This repository is the computational companion to the thesis. The final thesis
PDF, editable manuscript and any institution-specific submission forms should
be packaged and submitted separately through the required university system.
