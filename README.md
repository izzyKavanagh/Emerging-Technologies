# Emerging Technologies
## Deutsch & Deutsch–Jozsa Algorithm — Quantum Computing Notebook

This notebook provides a complete, ground-up implementation of **Deutsch's algorithm** and the **Deutsch–Jozsa algorithm** using Python and Qiskit. It is structured as a guided walkthrough that builds from classical foundations to a fully verified quantum solution, with explanations, commented code, and tests at each stage.

---

## Overview

The Deutsch–Jozsa algorithm is one of the earliest examples of a quantum algorithm that provably outperforms any classical deterministic algorithm on a well-defined problem. This notebook demonstrates that advantage concretely across five problems:

| Problem | Description |
|:---|:---|
| 1 | Generate random constant and balanced Boolean functions: The Deutsch–Jozsa algorithm is designed to work with functions that accept a fixed number of Boolean inputs and return a single Boolean output. Each function is guaranteed to be either constant (always returns False or always returns True) or balanced (returns True for exactly half of the possible input combinations). Write a Python function random_constant_balanced that returns a randomly chosen function from the set of constant or balanced functions taking four Boolean arguments as inputs. |
| 2 | Solve the problem classically and establish the query cost: Deutsch's algorithm is designed to demonstrate a potential advantage of quantum computing over classical computation. To understand this advantage, we must first understand the classical cost of solving the underlying problem. Write a Python function determine_constant_balanced that takes as input a function f, as defined in Problem 1. The function should analyze f and return the string "constant" or "balanced" depending on whether the function is constant or balanced. Write a brief note on the efficiency of your solution. What is the maximum number of times you need to call f to be 100% certain whether it is constant or balanced? |
| 3 | Build quantum oracles for each single-input Boolean function: Deutsch's algorithm is the simplest example of a quantum algorithm using superposition to determine a global property of a function with a single evaluation. In the single-input case, there are four possible Boolean functions. Using Qiskit, create the appropriate quantum oracles for each of the possible single-Boolean-input functions used in Deutsch's algorithm. Demonstrate their use and explain how each oracle implements its corresponding function. |
| 4 | Implement Deutsch's algorithm for single-input functions: Use Qiskit to design a quantum circuit that solves Deutsch's problem for a function with a single Boolean input. Implement the necessary circuit and demonstrate its use with each of the quantum oracles from Problem 3. Describe how the interference pattern produced by the circuit allows you to determine whether the function is constant or balanced using only one query to the oracle. |
| 5 | Scale to the full Deutsch–Jozsa algorithm for four-input functions: The Deutsch–Jozsa algorithm generalizes Deutsch's approach to functions with several input bits. Use Qiskit to create a quantum circuit that can handle the four-bit functions generated in Problem 1. Explain how the classical function is encoded as a quantum oracle, and demonstrate the use of your circuit on both of the constant functions and any two balanced functions of your choosing. Show that the circuit correctly identifies the type of each function. |

---

## Repository Structure

```
├── .gitignore 
├── problems.ipynb  # Main notebook — all problems, explanations, and tests
├── README.md   # This file
└── requirements.txt    # Python dependencies
```

---

## Requirements

- Python 3.10 or higher
- Jupyter Notebook or JupyterLab

All Python package dependencies are listed in `requirements.txt`. To install them,
run:

```bash
pip install -r requirements.txt
```

---

## Getting Started

1. **Clone the repository:**

```bash
git clone https://github.com/izzyKavanagh/Emerging-Technologies.git
```

2. **Install dependencies:**

```bash
pip install -r requirements.txt
```

3. **Launch the notebook:**

```bash
jupyter notebook problems.ipynb
```

or, if using JupyterLab:

```bash
jupyter lab problems.ipynb
```

4. **Run all cells in order.** Each problem builds on the previous one, so cells should be executed sequentially from top to bottom.

---

## Key Concepts Covered

- **Boolean functions** — constant vs. balanced, and the Deutsch–Jozsa promise
- **Classical query complexity** — why up to 2ⁿ⁻¹ + 1 queries are needed classically
- **Quantum superposition** — evaluating all inputs simultaneously with Hadamard gates
- **Phase kickback** — encoding classical function outputs as quantum phases
- **Quantum interference** — converting phase information into a measurable outcome
- **Quantum oracles** — translating classical Boolean functions into unitary circuits
- **Deutsch's algorithm** — single-input case, 1 qubit, 1 query
- **Deutsch–Jozsa algorithm** — four-input case, 4 qubits, 1 query
