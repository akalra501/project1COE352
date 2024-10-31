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

As visible here, the results from out Custom SVD function, and NumPy's built in function are the same, proving that the custom SVD system works.

# 2. Spring-Mass System SVD Solver

This project implements a numerical solution for a spring-mass system using Singular Value Decomposition (SVD). The code calculates equilibrium displacements, internal stresses, and elongations of a spring-mass system based on user-defined parameters.

## Description
The code calculates the displacements, internal forces, and elongations of a spring-mass system using the following steps:
1. Create matrices representing the system.
2. Calculate the stiffness matrix and force vector.
3. Solve for displacements using SVD.
4. Calculate elongations and internal forces.

The system supports different boundary conditions: `Fixed-Free` and `Fixed-Fixed`. Discussion of the Free-Free boundary condition is at the end of readme file.

## Features
- User-friendly interface for inputting parameters.
- SVD implementation for matrix decomposition.
- Calculation of condition numbers to assess matrix stability.
- Support for various spring-mass configurations.

#### Note: All masses are in kilograms.

### Test
For the purpose of testing our system, 3 springs and 3 masses were entered with one fixed boundary condition. Here is the output.

![image](https://github.com/user-attachments/assets/b20c1c90-854d-453d-9532-0304a46bba8c)

I also tested what happens when an out of bounds boundary condition is added. Here is the output.

![image](https://github.com/user-attachments/assets/edd95f00-cbeb-4c25-ba53-e350f725e34f)

The system also doesn't work when equal number of springs and masses are added in a fixed-free system. This makes sense as an extra spring is needed to fix the system to a rigid body. Here is the output:
![image](https://github.com/user-attachments/assets/ca4482d3-bc39-4c4a-9f29-da9aa674e9f1)

Note: 2 Free boundary conditions does not make sense practically. A two-free-end boundary condition in a spring-mass system implies that both ends can move freely without restrictions, which doesn’t make sense because the ends need fixed points to establish a force balance. If both ends are free, there’s no anchor for the springs to push against, allowing them to stretch or compress without actually doing any work or creating tension. This leads to unstable equilibrium; if you pull on the masses, they’ll simply float away without any restoring force to bring them back to an equilibrium position. Additionally, springs rely on interacting with fixed structures to exert forces, and without t

