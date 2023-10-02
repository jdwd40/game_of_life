### Introduction
This repository contains a Python implementation of Conway's Game of Life using the `pygame` library. Conway's Game of Life is a cellular automaton that simulates a population of cells evolving over discrete time steps. Each cell is either alive or dead, and its state changes based on specific rules, determined by the number of live neighbors it has.

The game is a zero-player game, meaning that its evolution is determined by its initial state, requiring no further input. The "board" is a grid of cells, each of which can be alive or dead. The grid evolves in discrete time steps, and the state of each cell in any given step depends on its state and the states of its 8 neighbors (the cells orthogonally and diagonally adjacent) in the previous step. Here are the rules:

### Rules of Conway's Game of Life

1. **Overpopulation**: If a live cell has more than 3 live neighbors, it dies.
2. **Stasis**: If a live cell has 2 or 3 live neighbors, it survives.
3. **Underpopulation**: If a live cell has fewer than 2 live neighbors, it dies.
4. **Reproduction**: If a dead cell has exactly 3 live neighbors, it becomes a live cell.

#### Neighbor Cells

For any cell at position \( (x, y) \), its neighbors are the cells at the following positions:

- \( (x-1, y-1) \)
- \( (x-1, y) \)
- \( (x-1, y+1) \)
- \( (x, y-1) \)
- \( (x, y+1) \)
- \( (x+1, y-1) \)
- \( (x+1, y) \)
- \( (x+1, y+1) \)

#### How the Rules are Implemented in the Code

The function `adjust_grid(positions)` in the code takes care of applying these rules. It iterates through each cell that is alive, counts its live neighbors, and then determines whether the cell should remain alive or die in the next generation. Additionally, it looks at dead cells that are neighbors of live cells to see if they should be brought to life.

- A cell remains in the set of live cells (`new_positions`) if it has exactly 2 or 3 live neighbors. (Rules 1 and 2)
- A cell is added to the set of live cells if it is currently dead and has exactly 3 live neighbors. (Rule 4)

The game starts with an initial random set of live cells or a pattern defined by the user, and it evolves over time following these rules when the simulation is running.




### Dependencies
- Python 3.x
- pygame

You can install `pygame` using pip:

```
pip install pygame
```

---

### How to Run
1. Clone the repository
2. Navigate to the project folder
3. Run `python main.py` (or the name you saved the file as)

---

### Code Structure

The code is organized as follows:

1. **Initialization**: Initializes pygame and sets up constant variables.
2. **Utility Functions**:
    - `gen(num)`: Generates a set of random cell positions.
    - `draw_grid(positions)`: Draws the grid and the alive cells on the pygame window.
    - `adjust_grid(positions)`: Adjusts the grid based on the Game of Life rules.
    - `get_neighbours(pos)`: Returns the neighboring cells for a given cell.
3. **Main Loop**: Handles the game state and user interactions.

---

#### Key Functions

- **gen(num)**
  - Input: `num` (Number of random cells to generate)
  - Output: A set containing random cell positions.

- **draw_grid(positions)**
  - Input: `positions` (Set of alive cells)
  - Output: None, draws the grid and cells on the screen.

- **adjust_grid(positions)**
  - Input: `positions` (Set of alive cells)
  - Output: A new set of alive cells for the next generation.

- **get_neighbours(pos)**
  - Input: `pos` (Tuple representing cell position)
  - Output: List of neighboring cells.

---

### User Interactions

- Left-click to add or remove a cell at the mouse position.
- Press SPACE to start or pause the simulation.
- Press 'C' to clear the grid.
- Press 'G' to generate a random set of cells.

---
