# Quantum-Protein-Structure-Predictor
This repository contains a quantum-inspired approach to protein structure prediction using the classical Hydrophobic-Polar (HP) model encoded on a 3D Body Centered Cubic (BCC) lattice.
Authors: Bhuvan V. and G.P. Pranav Vittal
---

# Quantum Protein Folding on a 3D BCC Lattice

A Qiskit-based approach to protein structure prediction

## Overview

This repository presents a quantum-inspired workflow for protein structure prediction using the Hydrophobic–Polar (HP) model embedded in a 3D Body-Centered Cubic (BCC) lattice.
The project formulates protein folding as a Hamiltonian minimization problem suitable for QAOA and other variational quantum algorithms, using Qiskit for Hamiltonian construction and evaluation.

This work was developed for:

Prompt 1 - Quantum Protein Structure Prediction (Cleveland Clinic)
Design a coordinate-based 3D lattice model and use a quantum algorithm to predict the folded structure of a short protein (5–10 residues). Construct Hamiltonians that account for interaction energies and structural constraints and explore lattice models such as BCC.

## Motivation

Protein folding is difficult due to an exponentially large conformational space. Quantum optimization methods offer a promising approach by encoding the problem directly as a Hamiltonian.
This project investigates the suitability of the BCC lattice for quantum protein folding, as it provides a favorable balance between biological realism and qubit efficiency.

## Core Idea

1. Encode each residue position using log2(number_of_lattice_nodes) qubits.
2. Construct a 3D BCC lattice to represent allowed residue coordinates.
3. Build a Hamiltonian consisting of:

   * Hydrophobic contact rewards (H–H adjacency)
   * Uniqueness penalties (one residue per node)
   * Adjacency penalties (the chain must remain connected)
4. Evaluate the Hamiltonian using Qiskit’s SparsePauliOp representation.
5. Use classical heuristics such as multi-start hill climbing and random sampling to approximate the optimal bitstring.
6. Decode the best bitstring into lattice coordinates and visualize the resulting fold.

## Key Features

* 3D BCC lattice generator with corner and body-center nodes
* Compact binary encoding of residue positions
* Qiskit-based Hamiltonian construction using Pauli operators
* High-speed classical energy evaluation for benchmarking
* Random search and local improvement heuristics
* Full 3D visualization of predicted fold structure


## Notebook Summary

The included notebook, `Qiskit Fall Fest.ipynb`, contains:

* Full problem statement
* Proposed solution aligned with the hackathon prompt
* Step-by-step mapping from the HP model to Hamiltonian terms
* The original code
* Explanations of lattice construction, Hamiltonian structure, and constraint enforcement

## How to Run

1. Visit the original source file on google colab- https://colab.research.google.com/drive/1Sd6SDW3XK4tm9BGqvDBo3SJZNoST-398?usp=sharing
   
2. Or run the code on device after installimg libraries- qiskit numpy networkx matplotlib tqdm

3. Run all cells to generate:

* Lattice construction
* Hamiltonian term counts
* Optimization results
* Final 3D structure visualization

## Results Summary

* The HP model is successfully embedded in a 3D BCC lattice.
* The Hamiltonian includes interaction terms and structural penalties.
* Efficient classical heuristics approximate optimal bitstrings.
* The final configuration is decoded and visualized.
* The workflow is prepared for integration with QAOA circuits and IBM quantum backends.

## Acknowledgements

* Cleveland Clinic and IBM Quantum for providing the challenge prompt
* The Qiskit open-source community
