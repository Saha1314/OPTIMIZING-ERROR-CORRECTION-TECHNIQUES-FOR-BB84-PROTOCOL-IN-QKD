# Enhancing Security in Quantum Key Distribution: Optimizing Error Correction in BB84 Protocol

This repository contains code for enhancing the security of Quantum Key Distribution (QKD) by optimizing error correction techniques in the BB84 protocol, reducing noise in simulated environments, and improving the reliability of key generation for real-world secure communication networks.

## Problem Statement

Quantum Key Distribution (QKD) using protocols like BB84 offers a highly secure method for sharing cryptographic keys over quantum channels. However, the efficiency and effectiveness of these protocols are significantly impacted by noise and defective channels. This project aims to enhance the security of QKD by optimizing error correction techniques in the BB84 protocol.

## Objectives

- Develop and optimize error correction techniques specifically tailored for the BB84 protocol in QKD.
- Enhance the reliability of key generation in quantum channels by applying advanced error reduction methods such as Entanglement Purification to minimize noise in simulated environments.

## Keywords

- Quantum Key Distribution
- BB84 Protocol
- Noise Mitigation
- Error Correction
- Secure Communication

## Proposed Work

### System Model

The project involves the following key modules:

1. **Entanglement Module**
2. **Quantum Key Generation and Transmission Module**
3. **Reconciliation Module**

### Modules in Proposed Work

#### Entanglement Module

**Entanglement Generation:**

- Responsible for producing entangled pairs of qubits necessary for QKD.
- Utilizes quantum gates like Hadamard and CNOT gates to create entanglement.

**Entanglement Purification:**

- Ensures the produced entangled pairs are maximally entangled.
- Uses strategies like entanglement swapping to improve the quality of entangled pairs.

#### Quantum Key Generation and Transmission Module

**Quantum Key Generation and Transmission:**

- Initiates secure key generation once maximally entangled pairs are obtained.
- Shares entangled pairs between sender and receiver, then aligns measurement bases to generate the quantum key.
- Transmits the quantum key through a Quantum Depolarization Noise Channel.

#### Reconciliation Module

**Encoding:**

- Encodes quantum information to maximally entangled pairs on the sender’s side using operations like S gate, unitary operations, and CNOT gates.

**Error Detection:**

- Utilizes ancilla qubits and methods like measurement operations and CNOT gates to detect errors introduced during transmission.

**Error Correction:**

- Corrects detected errors by applying appropriate quantum gates (X, Z, or their combination) to ensure the integrity of the transmitted quantum information.

**Decoding:**

- Reverses the encoding process on the receiver’s side to retrieve the original quantum information after error correction.

## Mathematical Background

- **Qubit**: A qubit is the quantum mechanical analogue of a classical bit, capable of representing both 0 and 1 simultaneously (superposition).
- **Hadamard Gate**: Transforms a qubit state into a superposition of |0⟩ and |1⟩.
  
  **Matrix Form:**
  \[
  H = \frac{1}{\sqrt{2}}
  \begin{bmatrix}
  1 & 1 \\
  1 & -1
  \end{bmatrix}
  \]
  
- **CNOT (Controlled NOT) Gate**: A two-qubit operation that performs a NOT operation on the target qubit only if the control qubit is in state |1⟩.
- **Bell State**: A specific type of entangled quantum state involving two qubits, produced using Hadamard and CNOT gates.
- **S Gate**: Applies a phase shift of π/2 radians to a qubit’s quantum state.
- **U Gate**: Introduces a phase shift to a qubit’s quantum state by a specified angle.
- **Phase Measurement**: Calculates the phase of quantum states with a given probability.
- **Error Rate**: Measures the difference between the maximum probability and the probability of the expected output state.
- **Encoded Information**: Converts a single logical qubit into multiple physical qubits using CNOT gates.

## Algorithm

### 1. Entanglement Module

1. Initialize quantum and classical registers.
2. Perform Hadamard and CNOT operations.
3. Perform Bell State Measurement and further CNOT operations to obtain maximally entangled pairs.

### 2. Quantum Key Generation and Transmission Module

1. Initialize quantum and classical registers.
2. Apply random basis for entanglement, followed by purification protocol.
3. Perform NOT, S, U operations, and CNOT gates.
4. Transmit encoded information through a depolarization quantum channel with noise model simulation.

### 3. Reconciliation Module

1. Initialize quantum, classical, and ancilla registers.
2. Perform CNOT operations and measure ancilla qubits.
3. Correct errors using Z gates if necessary.
4. Apply unitary operations, S gates, and measure final quantum states.

## Implementation

### Module 1 – Entanglement

1. Initialize the size of Quantum register q[] and Classical register c[] as 4.
2. Perform Hadamard operation on q[0] and q[3].
3. Perform CNOT operations on q[0] & q[1], q[0] & q[2], q[0] & q[3].
4. Observe the correlation between entangled pairs by performing Bell State Measurement.
5. Perform CNOT operations on q[0], q[3].
6. Perform Hadamard operation on q[0] and q[3].
7. Perform additional CNOT operations and store results in Classical registers.
8. Measure the information stored in Classical register.

### Module 2 – Quantum Key Generation and Transmission

1. Encode Quantum Information by applying NOT operation.
2. Apply S and U gates for encoding.
3. Apply CNOT gates to encode information in all the qubits.
4. Measure the qubits.
5. Simulate the circuit using ‘qasm – simulator’.
6. Transmit the qubits via Depolarization Noise Channel.

### Inference

- **Module 1 – Entanglement Generation and Purification**: Produces maximally entangled pairs of qubits with strong correlations. These pairs are used to generate and transmit the Quantum Key securely.
- **Module 2 – Quantum Key Generation and Transmission**: Generates a secure quantum key based on entangled pairs. Transmits the key through a Depolarization Noise Channel, ensuring security through encryption and decryption of messages.

## Evaluation Metrics

- **Channel Noise Rate**: Probability of errors due to environmental factors.
- **Third Party Detection Rate**: Probability of detecting unauthorized attempts to intercept quantum signals.
- **Total Error Rate**: Percentage of errors caused by noise or third-party interruptions.
- **QKD Communication Efficiency**: Ratio of successfully exchanged secret key bits to the total transmitted bits, indicating the protocol's effectiveness.

## Project Setup

To run the project, follow these steps:

1. Install required quantum computing libraries such as Qiskit.
2. Initialize quantum and classical registers as per the algorithm specifications.
3. Implement the entanglement, quantum key generation, and reconciliation modules.
4. Simulate the circuits using a quantum simulator.
5. Analyze the output and evaluate using defined metrics.

This README provides an overview and implementation guide for the project "Enhancing Security in Quantum Key Distribution: Optimizing Error Correction in BB84 Protocol." For further details, refer to the project documentation and code files.
