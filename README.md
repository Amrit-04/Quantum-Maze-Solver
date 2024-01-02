# Quantum Maze Solver

## Overview

The Quantum Maze Solver is a Python project that demonstrates the principles of quantum computing applied to the problem of solving mazes. It uses Qiskit, a quantum computing framework, to create and simulate quantum circuits that represent and explore all possible paths through a simple maze.

## Documentation

For an in-depth explanation of the project, including the underlying quantum computing concepts and a detailed code walkthrough, please refer to the [DOCUMENTATION.md](DOCUMENTATION.md) file.

## Features

- Creation of quantum circuits to represent maze-solving paths.
- Simulation of quantum circuits using Qiskit's Aer simulator.
- Visualization of possible paths using histogram plots.

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
