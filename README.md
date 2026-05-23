# Kyle Salamone

Experimental Physics PhD student working on large-scale detector data analysis, machine learning systems, and computational physics. Focused on designing and deploying scientific and ML pipelines in high-performance research environments, with emphasis on quantum information and data-driven modeling of physical systems.

*Current PhD research is proprietary — projects here represent independent work.*

---

## What I Work On

- Quantum and computational physics (variational algorithms, Hamiltonian simulation)
- Machine learning systems engineering (PyTorch → ONNX → C++ inference pipelines)
- Scientific computing infrastructure (reproducible visualization and analysis tooling)

---

## Featured Projects

### C++ ML Inference Profiler Engine
[View Repository](https://github.com/ksalamone59/inference-profiler)

CLI for profiling, benchmarking, and comparing ML inference backends in C++; designed for performance-critical environments where Python is not a viable runtime. Supports four modes: inference, benchmark, compare, and batch sweep. Backends are abstracted behind a pure virtual interface, allowing new engines 
to drop in cleanly. Sweep mode outputs `.dat` files across batch sizes for direct plotting pipeline integration.

ORT 4-thread inference achieves **13.97M samples/s** at batch size 1024 — **~5.6× over single-threaded TorchScript** under identical conditions. Model-to-model R²=0.9999 confirms numerical equivalence between backends.

*Focus: ML inference systems, C++ performance engineering, statistical benchmarking, backend abstraction*

---

### PyTorch → ONNX → C++ Inference Pipeline
[View Repository](https://github.com/ksalamone59/pytorch-onnx-cpp-pipeline) 

[![C++ Unit Tests](https://github.com/ksalamone59/pytorch-onnx-cpp-pipeline/actions/workflows/cpp-tests.yml/badge.svg)](https://github.com/ksalamone59/pytorch-onnx-cpp-pipeline/actions/workflows/cpp-tests.yml)

C++ inference engine with pre-allocated tensor reuse and singleton session 
management for zero-overhead-per-call ORT deployment. Includes statistically 
rigorous benchmarking via Welford online variance estimation — batched inference 
achieves 9.4M samples/s, ~16× over sequential baseline. Engineering patterns 
drawn from production physics reconstruction constraints.

*Focus: ML deployment, C++ inference systems, performance benchmarking*

---

### Quantum Eigensolver – Hydrogen VQE Discretization Study
[View Repository](https://github.com/ksalamone59/variational-quantum-eigensolver-hydrogen-study)

Variational Quantum Eigensolver (VQE) study of the hydrogen atom ground state, directly benchmarked against a classical eigenvalue solver under identical finite-difference discretization.


This project isolates **variational error vs discretization error**, showing that in low-qubit regimes, VQE performance is primarily limited by the underlying numerical representation rather than ansatz or optimizer choice.

*Focus: quantum algorithms, Hamiltonian discretization, error decomposition, variational landscapes, scaling behavior*

---

### Scientific Plotting Infrastructure
[View Repository](https://github.com/ksalamone59/gnuplot_latex_utils)

Reproducible gnuplot + LaTeX system for consistent publication-quality scientific figures across projects.

*Focus: scientific visualization, automation, reproducibility*

---

## Main Results

<div align="center">
    <img src="results_plots/throughput_per_batch.png" width="750">
</div>
<p>
Output from C++ ML Inference Backend Profile project of throughput vs batch size for 4 different models: ORT and Torch C++ APIs, single vs quad threaded. ORT consistently outperforms Torch at the same thread count. Threaded variants have higher variance due to synchronization overhead. 
</p>

<div align="center">
 <img src="results_plots/heatmap.png" width="750">
</div>
<p>
Output from characterizing VQE as a solution to the Hydrogen atom's ground state. Quantifying the minimum achievable error as a function of the number of qubits and maximum radius r in the Hamiltonian approximation
</p>

<div align="center">
 <img src="results_plots/final_inference.png" width="750">
</div>
<p>
Output from the ONNX ML pipeline. Showcases:
- Noisy input data to the C++ inference  
- The output C++ inference  
- The true function
</p>

Both plots were created using my gnuplot latex utilities repository.
## System View

Physics Simulation → ML Modeling → Deployment Runtime → Scientific Visualization

---

## Tools & Stack
Python · PyTorch · Qiskit · ONNX · C++ · Eigen · CMake · Gnuplot · LaTeX · Linux

---

## Contact
GitHub: ksalamone59
 
[LinkedIn](https://www.linkedin.com/in/kyle-salamone-a834b6205/)
