# BBOB Optimization Benchmarking Suite

This repository provides a MATLAB-based benchmarking environment for evaluating black-box optimization algorithms. It is built upon the **Black-Box Optimization Benchmarking (BBOB)** framework, allowing for rigorous comparison of optimizers across various function landscapes, including noisy and noise-free environments.

## 📋 Features

* **Comprehensive Testbed:** Access to a wide range of standard benchmark functions via `benchmarks.m` (noise-free) and `benchmarksnoisy.m` (noisy).
* **Standardized Evaluation:** Uses `fgeneric.m` for automated housekeeping, data logging, and performance tracking.
* **Sample Optimizer:** Includes `MY_OPTIMIZER.m`, a template showing how to implement a custom optimizer (currently uses a uniform random sampling strategy).
* **Automated Experiments:** * `exampleexperiment.m`: Runs a full performance evaluation across multiple dimensions and function instances.
    * `exampletiming.m`: Measures the computational overhead of the optimizer.

## 🛠️ Components

| File | Description |
| :--- | :--- |
| `MY_OPTIMIZER.m` | The optimization algorithm to be tested. |
| `fgeneric.m` | Wrapper for benchmark functions; handles logging and target values. |
| `benchmarks.m` | Collection of noise-free benchmark functions (f1–f24). |
| `benchmarksnoisy.m` | Collection of noisy benchmark functions (f101–f130). |
| `exampleexperiment.m` | Main script to run benchmarking trials. |
| `exampletiming.m` | Script to measure the runtime complexity of the optimizer. |

## 🚀 Getting Started

### 1. Prerequisites
* MATLAB or GNU Octave.
* Basic understanding of black-box optimization.

### 2. Running an Experiment
1.  Open `exampleexperiment.m`.
2.  Update the `datapath` variable to specify where you want the results saved.
3.  Set your algorithm name in `opt.algName`.
4.  Run the script:
    ```matlab
    exampleexperiment
    ```

### 3. Benchmarking Your Own Optimizer
To test your own algorithm, modify `MY_OPTIMIZER.m` or create a new function following the same signature:
```matlab
function xbest = MY_OPTIMIZER(FUN, DIM, ftarget, maxfunevals)
    % Your optimization logic here
end
