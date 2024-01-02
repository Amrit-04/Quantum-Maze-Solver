# Quantum Maze Solver

## Overview

The Quantum Maze Solver is a Python project that demonstrates the principles of quantum computing applied to the problem of solving mazes. It uses Qiskit, a quantum computing framework, to create and simulate quantum circuits that represent and explore all possible paths through a simple maze.

## Documentation

For an in-depth explanation of the project, including the underlying quantum computing concepts and a detailed code walkthrough, please refer to the [DOCUMENTATION.md](DOCUMENTATION.md) file.

## Features

- Creation of quantum circuits to represent maze-solving paths.
- Simulation of quantum circuits using Qiskit's Aer simulator.
- Visualization of possible paths using histogram plots.

## Rough notes

## Task Overview

- [x] **Define the Maze**: Establish a clear representation of the maze structure.

  - For now using a simple binary string with a n x n maze setup
  - ```
    Maze:
    1 1
    0 1
    ```

- [ ] **Run the Quantum Circuit**: Execute a quantum circuit that simulates a quantum walk.
- [ ] **Interpret Output**: Decode the quantum state measurements to identify viable paths through the maze.
- [ ] **Visualization** (Optional): Create graphical representations of the potential paths.

## Conceptual Framework: Quantum Walk

### Quantum Walk Overview

A quantum walk exploits quantum mechanics principles to explore multiple paths simultaneously in a maze-like structure.

### Steps for Implementing a Quantum Walk:

1. **Maze Representation**:

   - Each position in a simple 2x2 maze is associated with a distinct quantum state. The maze layout:

     ```
     Maze:
     1 1
     0 1
     ```

   - Cells in the maze are marked '1' for passable and '0' for blocked paths.

2. **Quantum Walker Dynamics**:

   - The quantum walker traverses the maze, exploring routes based on quantum superposition.
   - Predefined rules guide the walker's state evolution, similar to conventional maze navigation.

3. **Constraints and Objectives**:

   - The walker's movements are constrained by the maze's structure, avoiding '0' cells.
   - The primary goal is typically reaching a specific endpoint, such as the maze's bottom-right corner.

4. **Measurement and Path Determination**:
   - Measuring the walker’s quantum state after several steps collapses the superposition to a definite position, indicating a potential path through the maze.

### Quantum Walk vs. Classical Random Walk

**Key Distinctions**:

- **Superposition**: Quantum walkers can occupy multiple positions concurrently, as opposed to a single position in classical walks.
- **Entanglement**: Complex systems introduce entanglement, enabling intricate movement patterns.
- **Interference**: Path interference in quantum walks can constructively or destructively influence the walker's location probability.

### Quantum Algorithm for the 2x2 Maze (Conceptual Model)

1. **Initialization**:

   - The quantum walker is prepared in a state of superposition, representing potential simultaneous positions.

2. **Direction Determination (Coin Toss)**:

   - A Hadamard gate emulates a coin toss, influencing the walker's direction in each step.

3. **Conditional Position Update**:

   - The walker's position shifts based on the coin toss outcome, adhering to the maze’s layout.

4. **State Measurement**:
   - After several steps, the walker's position is measured, collapsing its state to a specific location within the maze.

## Requirements

- Python 3.x
- Qiskit
- Matplotlib (for visualization)

## Installation

To set up the Quantum Maze Solver, follow these steps:

1. **Clone the Repository**

```
git clone https://github.com/viraatdas/Quantum-Maze-Solver.git
cd Quantum-Maze-Solver
```

2. **Set Up a Python Virtual Environment (Optional)**

```
python -m venv venv
source venv/bin/activate # For Unix or MacOS
venv\Scripts\activate # For Windows
```

I personally prefer [pipenv](https://pipenv.pypa.io/en/latest/) btw

For _Pipenv_

```
pipenv install --ignore-pipfile
pipenv shell
```

3. **Install Dependencies**

```
pip install qiskit
pip install matplotlib
```

## Usage

To run the Quantum Maze Solver, execute the main script:

```
python solver.py
```

This will run the quantum circuit for the maze and display the possible paths in a histogram.

## How It Works

- The script initializes a quantum circuit with three qubits, each representing a decision point in a simple maze.
- Hadamard gates are applied to each qubit to create a superposition of all possible paths.
- The script then measures the state of each qubit, simulating the exploration of all possible paths through the maze.
- Finally, the results are visualized in a histogram showing the distribution of these paths.

## Contributing

Contributions to the Quantum Maze Solver are welcome. Please ensure to follow best practices for code style and commit messages. For major changes, please open an issue first to discuss what you would like to change.

## License

[MIT License](LICENSE)

## Acknowledgments

- Thanks to the Qiskit community for providing an accessible quantum computing framework.
- This project is inspired by the principles of quantum computing and its application in solving complex problems.
