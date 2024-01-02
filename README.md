# Quantum Maze Solver

## Overview

The Quantum Maze Solver is a Python project that demonstrates the principles of quantum computing applied to the problem of solving mazes. It uses Qiskit, a quantum computing framework, to create and simulate quantum circuits that represent and explore all possible paths through a simple maze.

## Documentation

For an in-depth explanation of the project, including the underlying quantum computing concepts and a detailed code walkthrough, please refer to the [DOCUMENTATION.md](DOCUMENTATION.md) file.

## Features

- Creation of quantum circuits to represent maze-solving paths.
- Simulation of quantum circuits using Qiskit's Aer simulator.
- Visualization of possible paths using histogram plots.

### Rough notes

- Define a simple 3x3 binary maze

Maze:
1 0 1
1 1 0
0 1 1

In this maze, the goal could be to move from the top-left corner to the bottom-right corner, moving only through cells marked '1'.

**What do we need to do?**

- [ ] Define the maze.
- [ ] Run the quantum circuit.
- [ ] Interpret the output as paths through the maze.
- [ ] (Optionally) Create visualizations for these paths.

**Conceptual Approach**

In a 3x3 binary maze, let's assume each row represents a decision point and each column represents a possible path. The goal is to find a path from the top to the bottom of the maze, moving only through cells marked '1'.

- Maze Representation: We represent the maze as a 3x3 grid of 0s and 1s. Each row in the maze corresponds to a qubit in the quantum circuit. A '1' in a row means a passable path, and a '0' means a blocked path.

- Quantum Circuit: We need an oracle to mark the valid paths according to the maze configuration.

_conceptual code:_

```python
from qiskit import QuantumCircuit, Aer, execute
from qiskit.visualization import plot_histogram

def create_maze_circuit(maze):
    qc = QuantumCircuit(3)

    # Apply Hadamard gates to create superposition
    qc.h([0, 1, 2])

    # Apply the oracle

    # Add measurement gates
    qc.measure_all()

    return qc

def solve_maze(maze):
    qc = create_maze_circuit(maze)
    simulator = Aer.get_backend('qasm_simulator')
    result = execute(qc, simulator).result()
    counts = result.get_counts(qc)
    return counts

def interpret_results(counts, maze):
    # Interpret the quantum results to find valid paths
    # This is a placeholder. The real implementation would require checking the maze configuration.
    valid_paths = []
    for path in counts:
        if is_path_valid(path, maze):
            valid_paths.append(path)
    return valid_paths

def is_path_valid(path, maze):
    # Placeholder for path validation logic
    # Implement the logic to check if the path is valid according to the maze configuration.
    return True

# Define the maze
maze = [[1, 0, 1], [1, 1, 0], [0, 1, 1]]

# Solve the maze and get the possible paths
possible_paths = solve_maze(maze)
valid_paths = interpret_results(possible_paths, maze)
print("Valid paths:", valid_paths)

# Visualize the possible paths (conceptual)
qc = create_maze_circuit(maze)
plot_histogram(possible_paths)

```

- Interpreting Results: After measuring the quantum state, we interpret the output to determine the valid paths through the maze.

**Conceptual Steps for a Quantum Maze Solver:**

1. Maze Representation:

   - The maze is represented in such a way that each position in the maze corresponds to a quantum state. For a simple 2x2 maze like:
     Maze:
     1 1
     0 1

     Each cell can be represented by a quantum state, and the walker's position corresponds to being in one of these cells.

   - **Steps of the Quantum Walk**: The quantum walker moves through the maze, exploring different paths via superposition. In each step, the walker's state evolves according to predefined rules (akin to the rules of moving through the maze).

   - **Constraints and Goals**: The rules for updating the walker's state can include constraints based on the maze's structure (e.g., cannot move into walls represented by '0') and the goal (e.g., reaching the bottom-right corner).

   - **Measuring the Walker's Position**: After a certain number of steps, measuring the walker's position collapses its superposition to a specific location, potentially indicating a path through the maze.

**Challenges:**

- Oracle Design: Creating an oracle that accurately reflects the maze's layout and identifies the correct path is complex. This involves translating the maze's structure into a quantum logic gate operation.
- Resource Requirements: A real quantum maze solver for even a small maze would require more qubits and quantum gates than are practically available on current quantum computers. _3x3 or 4x4 grid should be possible..._

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
