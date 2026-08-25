# FALQON Algorithm Simulation for Quantum Optimization

This repository contains a Python simulation of the **FALQON (Feedback-Based Algorithm for Quantum OptimizatioN)** algorithm, accelerated by a GPU using the CuPy library. The objective of this project is to computationally validate the behavior of FALQON for solving optimization problems formulated as **QUBO (Quadratic Unconstrained Binary Optimization)**.

## About the FALQON Algorithm

FALQON is a feedback-based quantum control algorithm introduced in *Physical Review Letters 129, 250502 (2022)*. Unlike other variational algorithms, FALQON does not require an expensive classical optimization loop. Instead, it uses measurements from the quantum system itself as "feedback" to constructively build the circuit parameters, mathematically guaranteeing a monotonic decrease in the system's energy towards the optimal solution.

## Repository Contents

- **`FALQON-optimizationQUBO.ipynb`**: A Jupyter Notebook containing the full implementation of the simulation. The notebook includes:
  - Detailed theoretical explanations of key concepts (QUBO, mapping to Hamiltonians, FALQON theory).
  - Two functional versions of the simulation script:
    1.  For solving the **Number Partitioning Problem**.
    2.  For solving the **Max-Cut Problem** (used as a benchmark in the original paper).
  - The necessary code to visualize the results, including the energy evolution, feedback signal, and the final probability distribution.

## Requirements

To run the GPU-accelerated simulation, you will need the following environment:

- **Hardware:** An NVIDIA GPU with CUDA support.
- **Software:**
  - Python 3.x
  - The **CUDA Toolkit** installed.
  - The following Python libraries:
    - `cupy` (for the GPU backend; install the version corresponding to your CUDA Toolkit).
    - `numpy`
    - `scipy`
    - `matplotlib`

You can install the required libraries using pip:
```bash
pip install numpy scipy matplotlib cupy-cudaXXx # Replace XXx with your CUDA version (e.g., cupy-cuda12x)
