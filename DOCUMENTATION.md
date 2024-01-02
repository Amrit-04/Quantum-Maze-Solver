# Quantum Maze Solver Documentation

## Introduction

This document provides an explanation of some of the ideas explored. In the future, a full code write-up will be provided

One idea explored is using a Quantum Walk

### Conceptual Explanation of Quantum Walk

A quantum walk is the quantum analog of the classical random walk. In a classical random walk, such as a random walk on a line, the position of the walker changes in a stochastic manner at each step. For instance, in a one-dimensional walk, the walker moves either left or right with certain probabilities. Quantum walks, however, leverage quantum properties like superposition and entanglement, leading to a fundamentally different behavior.

**Key Differences from Classical Walks:**

- Superposition: In a quantum walk, the walker can be in a superposition of multiple positions at once. This means that instead of being at a single point at any given time, as in a classical walk, the quantum walker can simultaneously explore multiple paths.

- Entanglement: When more complex systems are involved, entanglement between different parts of the system can occur, allowing for even more complex behaviors.

- Interference: Quantum walks exhibit interference effects. This means that different paths can interfere with each other constructively or destructively, affecting the probability of finding the walker at certain positions.

**The Quantum Algorithm for the 2x2 Maze**
A toy example conceptualized:

- Initial State and Superposition: The quantum walker (represented by qubits in the circuit) is initialized in a superposition of states, allowing it to be in multiple positions simultaneously.
- Hadamard Gate for Coin Toss: The Hadamard gate is used to simulate the coin toss, determining the direction of the walker's next step.
- Conditional Shifts: Based on the coin's outcome, the walker's position is updated (shifted right or left).
- Measuring the Final State: After a predefined number of steps, the position is measured, collapsing the superposition to a specific state.

For the given 2x2 maze, a more elaborate setup would be required to map the maze's structure onto the quantum circuit, and specific rules would need to be implemented to account for the maze's walls and pathways.
