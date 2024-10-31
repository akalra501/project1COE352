## 1. General Singular Value Decomposition (SVD) Routine

### Description
The `custom_svd` function performs the Singular Value Decomposition of an \( N \times M \) matrix and calculates the following:

- **Left singular vectors** \( U \)
- **Diagonal matrix of singular values** \( S \)
- **Transpose of the right singular vectors** \( V^T \)
- **Condition number**, calculated using the ratio of the maximum and minimum singular values
- **Matrix inverse**, computed only if the matrix is invertible (i.e., no zero singular values)

If any singular values are zero, the function raises an error to indicate that the inverse does not exist.

### Files
- `custom_svd.py`: Contains the `custom_svd` function implementation.

### Tests
To test out SVD function, the matrix was defined in the file itself: [[1,7,6], [4, 19,22], [13,12,201]] 

### Output
![image](https://github.com/user-attachments/assets/1e9f6e04-655d-4188-9e82-b7cd3e3d4ff0)

#2. Spring-Mass System SVD Solver

This project implements a numerical solution for a spring-mass system using Singular Value Decomposition (SVD). The code calculates equilibrium displacements, internal stresses, and elongations of a spring-mass system based on user-defined parameters.

## Table of Contents
- [Description](#description)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Code Structure](#code-structure)
- [Contributions](#contributions)
- [License](#license)

## Description
The code calculates the displacements, internal forces, and elongations of a spring-mass system using the following steps:
1. Create matrices representing the system.
2. Calculate the stiffness matrix and force vector.
3. Solve for displacements using SVD.
4. Calculate elongations and internal forces.

The system supports different boundary conditions: `Fixed-Free` and `Fixed-Fixed`.

## Features
- User-friendly interface for inputting parameters.
- Robust SVD implementation for matrix decomposition.
- Calculation of condition numbers to assess matrix stability.
- Support for various spring-mass configurations.
