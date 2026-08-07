# Reproducibility guide

This document describes how to reproduce the computational material associated
with the degree project.

## 1. Environment

Recommended:

- Python 3.10–3.12;
- a new virtual environment;
- the dependencies listed in `requirements.txt`.

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
pip install -r requirements.txt
```

When preparing an assessed archive, record the exact environment:

```bash
python --version
pip freeze > environment-freeze.txt
```

`environment-freeze.txt` is a local submission artefact and is ignored by Git.
Include it in an assessed archive only when requested.

## 2. Notebook execution order

Run each notebook from top to bottom in this order:

1. `00_Monte_Carlo.ipynb`
2. `01_Bernoulli&Poisson.ipynb`
3. `02_Random_Walk_Part1.ipynb`
4. `03_Random_Walk_Part2.ipynb`
5. `04_Random_Walk_Part3.ipynb`
6. `05_Markov_Chain_Part1.ipynb`
7. `06_Markov_Chain_Part2.ipynb`
8. `07_Markov_Chain_Part3.ipynb`
9. `08_Exploratory_Module_1.ipynb`
10. `09_Exploratory_Module_2.ipynb`
11. `10_Exploratory_Module_3.ipynb`

Use **Kernel → Restart Kernel and Run All Cells** for every notebook. A clean
run must not depend on variables created by another notebook or by an earlier
interactive session.

## 3. Random-seed policy

- Normal notebook execution uses a fresh NumPy random generator without a
  fixed seed, so rerunning a notebook produces another valid realisation.
- Record important parameter values and sample sizes next to the result or in
  its caption.
- Reproducibility means that the same model, procedure and statistical
  behaviour can be obtained in a compatible environment; it does not require
  identical random values.
- A fixed seed may be supplied temporarily when debugging a specific result,
  but it is not required for the teaching experiments.

## 4. Numerical checks

For each main module, compare empirical output with an appropriate reference:

- Monte Carlo: convergence of the estimator and its sampling error;
- Poisson process: mean count `lambda * t` and exponential waiting times;
- random walk: endpoint mean, variance and hitting behaviour;
- Brownian motion: terminal mean zero and variance `T`;
- Markov chain: row-stochastic transition matrices, empirical frequencies and
  stationary distributions;
- queueing and reliability: parameter constraints and theoretical benchmark
  quantities where available.

Stochastic simulations are not exact equality tests. Small discrepancies are
expected and should generally decrease as the sample size grows.

## 5. Repository and submission checklist

- [ ] All 11 final notebooks are present under `notebooks/`.
- [ ] Every notebook runs from a clean kernel without manual intervention.
- [ ] Each selected figure can be traced to its generating notebook and
      parameter values.
- [ ] Figures, tables and equations use the same notation as the thesis text.
- [ ] `requirements.txt` covers the imports used by the notebooks.
- [ ] README, notebook names and thesis chapter references agree.
- [ ] No local paths, API keys, virtual environments, caches or `.DS_Store`
      files are tracked.
- [ ] Exercise drafts under `exercises/` are not published on this branch.
- [ ] Third-party PDFs under `reference/` are not published.
- [ ] The final thesis PDF and editable source are packaged separately when
      required by the examiner or university submission system.
