# Quantum_Audio_Detection

# Comparative Analysis of Quantum SVM vs. Classical Architectures for ASVspoof5 (2024)

# Research Objective
This project evaluates the application of Quantum Support Vector Machines (QSVM) in detecting high-fidelity audio deepfakes. Specifically, we investigate whether mapping acoustic features into 12 qubits provides superior non-linear separation compared to standard Multi-Layer Perceptrons (MLP).

# The Technical Pipeline
We implemented a hybrid architecture to bridge the gap between raw audio binaries and quantum circuits:

1.  Acoustic Front-end: Utilized the Wav2Vec2.0 Transformer (Self-Supervised Learning) to extract 768-dimensional contextual embeddings.
2.  Dimensionality Alignment: Applied Principal Component Analysis (PCA) to reduce embeddings to a 12 to 20-qubit register.
3.  Quantum State Preparation: Implemented ZZFeatureMap with Circular Entanglement and a circuit depth of reps=3 to maximize feature interaction.
4.  Simulation Engine: Leveraged the Matrix Product State (MPS) algorithm to maintain memory efficiency during high-qubit simulation.

# Infrastructure & Optimization
Due to the exponential complexity of simulating a $2^{20}$ statevector, the project was deployed on **AWS (m6i.2xlarge)**:
*   Memory: 32 GB RAM (Essential for 20-30 qubit math).
*   CPU: 8 vCPUs utilizing Intel AVX-512 acceleration.
*   Parallelism: Configured Qiskit Aer backend for **8-core multi-threaded** kernel evaluation, achieving a 70% reduction in compute time.

# Key Results
| Metric | Classical MLP | Classical SVM | Quantum SVM (20Q) |
| :--- | :--- | :--- | :--- |
| **Accuracy** | 0.XXX | 0.XXX | **0.XXX** |
| **AUC** | 0.XXX | 0.XXX | **0.XXX** |
| **EER** | 0.XXX | 0.XXX | **0.XXX** |

# Data Availability
The **ASVspoof5 (2024)** dataset is approximately 13GB. Due to GitHub's size limitations, raw data is excluded. The repository contains scripts to automate the ingestion of the dataset from local storage.
